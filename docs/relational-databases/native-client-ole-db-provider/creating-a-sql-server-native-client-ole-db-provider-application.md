---
title: OLE DB アプリを作成する
ms.custom: ''
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, application creation
- applications [SQL Server Native Client]
- OLE DB, creating applications
ms.assetid: f3ae6815-f32d-4913-a1a2-2ba2f20cfd88
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: cf15d32e162dfd7881e6d0418a28e1f10212a44d
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "81388568"
---
# <a name="creating-a-sql-server-native-client-ole-db-provider-application"></a>SQL Server Native Client OLE DB プロバイダー アプリケーションの作成
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  Native Client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] OLE DB プロバイダーアプリケーションを作成するには、次の手順を実行します。  
  
1.  データ ソースへの接続の確立。  
  
2.  コマンドの実行。  
  
3.  結果の処理。  

> [!NOTE]  
>  可能な場合は、Windows 認証を使用します。 Windows 認証が使用できない場合は、実行時に資格情報を入力するようユーザーに求めます。 資格情報をファイルに保存するのは避けてください。 資格情報を保存する必要がある場合は、[Win32 CryptoAPI](https://go.microsoft.com/fwlink/?LinkId=9504) を使用して暗号化してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [データ ソースへの接続の確立](../../relational-databases/native-client-ole-db-provider/establishing-a-connection-to-a-data-source.md)  
  
-   [コマンドの実行](../../relational-databases/native-client-ole-db-provider/executing-a-command.md)  
  
-   [結果の処理](../../relational-databases/native-client-ole-db-provider/processing-results.md)  
  
-   [OLE DB プロパティについて](../../relational-databases/native-client-ole-db-provider/about-ole-db-properties.md)  
  
-   [SQL Server Native Client の OLE DB での OUTPUT 句の使用](../../relational-databases/native-client-ole-db-provider/using-the-output-clause-with-ole-db-in-sql-server-native-client.md)  
  
## <a name="see-also"></a>参照  
 [SQL Server Native Client &#40;OLE DB&#41;](../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
