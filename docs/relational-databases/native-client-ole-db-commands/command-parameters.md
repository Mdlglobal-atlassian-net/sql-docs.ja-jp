---
title: コマンド パラメーター | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- parameters [SQL Server Native Client]
- SQL Server Native Client OLE DB provider, parameters
- SQL Server Native Client OLE DB provider, commands
- parameters [SQL Server Native Client], OLE DB
- commands [OLE DB]
ms.assetid: 072ead49-ebaf-41eb-9a0f-613e9d990f26
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 5db24ee3b68d1a8989200479a3ce4018e63a5177
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "81304517"
---
# <a name="command-parameters"></a>コマンド パラメーター
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  コマンド テキスト内のパラメーターは、疑問符文字でマークされます。 たとえば、次の SQL ステートメントでは 1 つの入力パラメーターがマークされています。  
  
```  
{call SalesByCategory('Produce', ?)}  
```  
  
 ネットワークトラフィックを減らすことによってパフォーマンス[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]を向上させるために、Native Client OLE DB プロバイダーは、コマンドの実行前に**ICommandWithParameters:: Getparameterinfo**または**ICommandPrepare::P repare**が呼び出されない限り、パラメーター情報を自動的には派生しません。 これは、Native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client OLE DB プロバイダーが自動的に実行しないことを意味します。  
  
-   **ICommandWithParameters::SetParameterInfo** で指定されたデータ型の正当性を確認すること。  
  
-   アクセサー バインド情報で指定された DBTYPE から、そのパラメーターに対する適切な [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] データ型にマップすること。  
  
 アプリケーションで [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] データ型のパラメーターと互換性のないデータ型を指定すると、上記のいずれかが原因で、エラーが発生したり、有効桁数が失われる可能性があります。  
  
 このようなことが起きないようにするには、アプリケーションで次の条件を満たす必要があります。  
  
-   **ICommandWithParameters::SetParameterInfo** をハードコーディングしている場合、*pwszDataSourceType* をパラメーターの [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] データ型と一致させます。  
  
-   アクセサーをハードコーディングしている場合、パラメーターにバインドされている DBTYPE 値の型を、パラメーターの [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] データ型と同じにします。  
  
-   **ICommandWithParameters::GetParameterInfo** を呼び出すようにアプリケーションをコーディングし、プロバイダーでパラメーターの [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] データ型を動的に取得できるようにします。 これにより、ネットワーク上でサーバーとの余分なやり取りが増えることに注意してください。  
  
> [!NOTE]  
>  SQL Native Client OLE DB プロバイダーでは、FROM 句が含まれている [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] UPDATE ステートメントや DELETE ステートメント、パラメーターを含むサブクエリに依存する SQL ステートメント、比較の両方の式、LIKE 述部、および定量化された述語内にパラメーター マーカーを含む SQL ステートメント、またはパラメーターのいずれかが、関数に対するパラメーターになっているクエリの場合は、**ICommandWithParameters::GetParameterInfo** を呼び出すことはできません。 また、SQL ステートメントをバッチ処理する場合、バッチ内の最初のステートメントの後にあるステートメント内のパラメーター マーカーに対して、**ICommandWithParameters::GetParameterInfo** を呼び出すことはできません。 [!INCLUDE[tsql](../../includes/tsql-md.md)] コマンド内ではコメント (/* \*/) を使用できません。  
  
 Native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client OLE DB プロバイダーは、SQL ステートメントコマンドで入力パラメーターをサポートしています。 プロシージャ呼び出しコマンドでは、Native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client OLE DB プロバイダーは、入力、出力、入出力のパラメーターをサポートしています。 出力パラメーターの値は、実行時 (行セットが返されない場合のみ)、または返されたすべての行セットがアプリケーションによって使用されたときにアプリケーションに返されます。 返される値が有効であることを保証するには、**IMultipleResults** を使用して行セットを強制的に使用します。  
  
 ストアド プロシージャ パラメーターの名前を DBPARAMBINDINFO 構造体で指定する必要はありません。 *PwszName*メンバーの値には NULL を使用して、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB プロバイダーがパラメーター名を無視し、 **ICommandWithParameters:: setparameterinfo**の*rgParamOrdinals*メンバーに指定されている序数のみを使用するように指定します。 コマンド テキストに名前付きのパラメーターと名前のないパラメーターの両方が含まれている場合、どの名前付きパラメーターよりも前に、名前のないパラメーターをすべて指定する必要があります。  
  
 ストアドプロシージャパラメーターの名前が指定されている場合[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 、Native Client OLE DB プロバイダーは、その名前が有効であることを確認します。 Native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client OLE DB プロバイダーは、コンシューマーから間違ったパラメーター名を受け取ったときにエラーを返します。  
  
> [!NOTE]  
>  XML およびユーザー定義[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]型 (UDT) のサポートを公開するために[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 、Native Client OLE DB プロバイダーは新しい[isscommandwithparameters](../../relational-databases/native-client-ole-db-interfaces/isscommandwithparameters-ole-db.md)インターフェイスを実装しています。  
  
## <a name="see-also"></a>参照  
 [コマンド](../../relational-databases/native-client-ole-db-commands/commands.md)  
  
  
