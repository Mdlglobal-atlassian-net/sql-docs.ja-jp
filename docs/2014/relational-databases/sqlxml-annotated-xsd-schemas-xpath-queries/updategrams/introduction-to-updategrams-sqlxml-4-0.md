---
title: アップデートグラムの概要 (SQLXML 4.0) |Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- explicit schema mapping [SQLXML]
- updategrams [SQLXML], mapping schema specifying
- namespaces [SQLXML]
- updategrams [SQLXML], about updategrams
- attribute-centric mapping
- invalid characters [SQLXML]
- element-centric mapping [SQLXML]
- mapping schema [SQLXML], updategrams
- namespaces [SQLXML], updategrams
- executing updategrams [SQLXML]
- implicit schema mapping
ms.assetid: cfe24e82-a645-4f93-ab16-39c21f90cce6
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 185b10d428217bad55d0b30720976562da84556e
ms.sourcegitcommit: b72c9fc9436c44c6a21fd96223c73bf94706c06b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "82703084"
---
# <a name="introduction-to-updategrams-sqlxml-40"></a>アップデートグラムの概要 (SQLXML 4.0)
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] アップデートグラムまたは OPENXML 関数を使用して、既存の XML ドキュメントからデータベースを変更 (挿入、更新、または削除) することができ [!INCLUDE[tsql](../../../includes/tsql-md.md)] ます。  
  
 OPENXML 関数は、既存の XML ドキュメントを断片化し、INSERT、UPDATE または DELETE ステートメントに渡すことができる行セットを提供することで、データベースを変更する関数です。 OPENXML を使用すると、データベース テーブルに対して操作を直接実行できます。 したがって、ソースにテーブルなどの行セット プロバイダーがある場合は常に、OPENXML を使用するのが最適です。  
  
 アップデートグラムを使用すると、OPENXML と同様にデータベースに対してデータを挿入、更新、または削除できます。ただし、アップデートグラムは注釈付き XSD (または XDR) スキーマにより提供される XML ビューに対して動作します。たとえば、更新はマッピング スキーマにより提供される XML ビューに適用されます。 マッピング スキーマには、XML 要素と属性を対応するデータベース テーブルと列にマップするための、必要な情報が含まれています。 アップデートグラムでは、このマッピング情報を使用してデータベース テーブルと列が更新されます。  
  
> [!NOTE]  
>  このドキュメントは、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] でサポートされるテンプレートとマッピング スキーマについて理解していることを前提としています。 詳細については、「[注釈付き XSD スキーマの概要 &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md)」を参照してください。 XDR を使用するレガシアプリケーションでは、 [SQLXML 4.0&#41;では、注釈付き Xdr スキーマ &#40;非推奨](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md)とされています。  
  
## <a name="required-namespaces-in-the-updategram"></a>アップデートグラムで必要な名前空間  
 ** \< 同期>**、 ** \<>前**、および** \<>後**のアップデートグラムのキーワードは、名前空間に存在し `urn:schemas-microsoft-com:xml-updategram` ます。 名前空間プレフィックスは、任意のものを使用できます。 このドキュメントでは、`updg` 名前空間を表すものとして `updategram` プレフィックスを使用します。  
  
## <a name="reviewing-syntax"></a>構文の確認  
 アップデートグラムは、 ** \< 同期>**、 ** \<>前**、およびアップデートグラムの構文を形成する>ブロックの** \< 後**にあるテンプレートです。 次のコードは、最も単純な構文です。  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync [mapping-schema= "AnnotatedSchemaFile.xml"] >  
    <updg:before>  
        ...  
    </updg:before>  
    <updg:after>  
        ...  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 次に、これらの各ブロックの役割について説明します。  
  
 **\<>前**  
 レコード インスタンスの既存の状態 ("before 状態") を指定します。  
  
 **\<>後**  
 データの変更後の新しい状態を指定します。  
  
 **\<同期>**  
 ** \< Before>** および** \< after>** ブロックを格納します。 ** \< 同期>** ブロックには、>** \<>** ブロックの後** \< に**複数のセットを含めることができます。 >ブロックの** \< 前>** と** \< 後**ののセットが複数ある場合は、これらのブロック (空の場合でも) をペアとして指定する必要があります。 さらに、アップデートグラムには複数の** \< 同期>** ブロックを含めることができます。 各** \< 同期>** ブロックは1つのトランザクション単位です (つまり、 ** \< sync>** ブロック内のすべての処理が完了しているか、何も実行されていないことを意味します)。 アップデートグラムに複数の** \< 同期>** ブロックを指定した場合、1つの** \< 同期>** ブロックの失敗は、他の** \< 同期>** ブロックには影響しません。  
  
 アップデートグラムによってレコードインスタンスが削除、挿入、または更新されるかどうかは、 ** \< 前の>** と>ブロックの** \< 後**の内容によって異なります。  
  
-   レコードインスタンスが** \< before>** ブロックにのみ存在し、対応するインスタンスが** \< after>** ブロックにない場合、アップデートグラムは削除操作を実行します。  
  
-   レコードインスタンスが** \< after>** ブロックにのみ出現し、対応するインスタンスが** \< before>** ブロックにない場合は、挿入操作になります。  
  
-   レコードインスタンスが** \< before>** ブロックに出現し、対応するインスタンスが** \< after>** ブロックに存在する場合、そのインスタンスは更新操作になります。 この場合、アップデートグラムは、レコードインスタンスを** \< after>** ブロックで指定された値に更新します。  
  
## <a name="specifying-a-mapping-schema-in-the-updategram"></a>アップデートグラムでマッピングスキーマを指定する  
 アップデートグラムでは、暗黙的または明示的に、マッピング スキーマによって XML データを操作できます。つまり、マッピング スキーマを指定しても指定しなくてもアップデートグラムは動作します。マッピング スキーマは XSD と XDR の両方がサポートされています。 マッピングスキーマを指定しない場合、アップデートグラムでは、暗黙的なマッピング (既定のマッピング) が想定されます。このマッピングでは、 ** \< before>** block または** \< after>** ブロックの各要素がテーブルにマップされ、各要素の子要素または属性がデータベース内の列にマップされます。 マッピング スキーマを明示的に指定する場合、アップデートグラムの要素と属性は、マッピング スキーマ内の要素と属性に一致する必要があります。  
  
### <a name="implicit-default-mapping"></a>暗黙的なマッピング (既定)  
 単純な更新を実行するアップデートグラムではほとんどの場合、マッピング スキーマは必要ありません。 この場合、アップデートグラムは既定のマッピング スキーマに従います。  
  
 次のアップデート グラムは、暗黙的なマッピングを示しています。 この例では、アップデートグラムによって新しい顧客が Sales.Customer テーブルに挿入されます。 このアップデートグラムでは、暗黙的なマッピングが使用されるため、sales. customer \<> 要素が sales. customer テーブルにマップされ、CustomerID 属性と SalesPersonID 属性が sales. customer テーブル内の対応する列にマップされます。  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
</updg:before>  
<updg:after>  
    <Sales.Customer CustomerID="1" SalesPersonID="277" />  
    </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="explicit-mapping"></a>明示的なマッピング  
 XSD または XDR のいずれかのマッピング スキーマを指定した場合、アップデートグラムではそのスキーマによって、更新するデータベース テーブルと列が決定されます。  
  
 アップデートグラムにおいて、マッピング スキーマで指定される親子リレーションシップに基づいて複数のテーブルにレコードを挿入するなど、複雑な更新を実行する場合は、`mapping-schema` 属性でマッピング スキーマを明示的に指定する必要があります。アップデートグラムはこの属性で指定されたマッピング スキーマに対して実行されます。  
  
 アップデートグラムはテンプレートであり、アップデートグラム内でマッピング スキーマに指定するパスは、テンプレート ファイルの場所 (アップデートグラムが保存されている場所) に対する相対パスです。 詳細については、「[アップデートグラムでの注釈付きマッピングスキーマの指定 &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md)」を参照してください。  
  
## <a name="element-centric-and-attribute-centric-mapping-in-updategrams"></a>アップデートグラムでの要素中心および属性中心のマッピング  
 アップデートグラムでマッピング スキーマが指定されていないときに使用される既定のマッピングでは、アップデートグラムの要素がテーブルにマップされ、要素中心マッピングの場合は子要素、属性中心マッピングの場合は属性が、それぞれ列にマップされます。  
  
### <a name="element-centric-mapping"></a>要素中心のマッピング  
 要素中心のアップデートグラムでは、要素に、要素のプロパティを表す子要素を含めます。 たとえば、次のアップデートグラムを参照してください。 ** \< Person. Contact>** 要素には、 ** \< FirstName>** と** \< LastName>** 子要素が含まれています。 これらの子要素は、 ** \< Person. Contact>** 要素のプロパティです。  
  
 このアップデートグラムではマッピングスキーマが指定されていないため、このアップデートグラムでは暗黙的なマッピングを使用します。このマッピングでは、 ** \< person. contact>** 要素が person テーブルとその子要素にマップされ、FirstName 列と LastName 列にマップされます。  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:after>  
    <Person.Contact>  
       <FirstName>Catherine</FirstName>  
       <LastName>Abel</LastName>  
    </Person.Contact>  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="attribute-centric-mapping"></a>属性中心のマッピング  
 属性中心のマッピングでは、要素に属性を指定します。 たとえば、次のアップデートグラムでは属性中心のマッピングが使用されています。 この例では、 ** \< Person>** 要素は**FirstName**属性と**LastName**属性で構成されています。 これらの属性は、 ** \< Person. Contact>** 要素のプロパティです。 前の例と同様に、このアップデートグラムではマッピングスキーマが指定されていないので、暗黙的なマッピングに依存して、 ** \<>person** . contact テーブルと要素の属性をテーブル内のそれぞれの列にマップします。  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:before>  
  </updg:before>  
  <updg:after>  
    <Person.Contact FirstName="Catherine" LastName="Abel" />  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="using-both-element-centric-and-attribute-centric-mapping"></a>要素中心と属性中心の両方のマッピングの使用  
 次のアップデートグラムに示すように、要素中心と属性中心のマッピングは併用できます。 ** \< Person>** 要素には、属性と子要素の両方が含まれていることに注意してください。 また、このアップデートグラムは暗黙的なマッピングに従います。 このため、 **FirstName**属性と** \< LastName>** 子要素は、Person. Contact テーブルの対応する列にマップされます。  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:before>  
  </updg:before>  
  <updg:after>  
    <Person.Contact FirstName="Catherine" >  
       <LastName>Abel</LastName>  
    </Person.Contact>  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
## <a name="working-with-characters-valid-in-sql-server-but-not-valid-in-xml"></a>SQL Server で有効であり、XML で有効でない文字の取り扱い  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] では、テーブル名に空白を含めることができます。 ただし、このようなテーブル名は XML では有効でありません。  
  
 有効な識別子であるが有効な XML 識別子ではない文字をエンコードするには、 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] \_ \_ エンコード値として ' __xHHHH ' を使用します。ここで、HHHH は、最上位ビットから順に、文字の4桁の16進数の UCS 2 コードを表します。 このエンコード方式を使用すると、スペース文字は x0020 (スペース文字の4桁の16進コード) に置き換えられます。このため、のテーブル名 [Order Details] は [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] XML で _x005B_Order_x0020_Details_x005D になり \_ ます。  
  
 同様に、 \< [database]. [データベース] など、3つの要素で構成される要素名を指定する必要がある場合もあります。 [所有者]。[テーブル] >。 角かっこ文字 ([および]) は XML では無効であるため、これを _x005B_database_x005D として指定する必要があり \< \_ ます。 _x005B_owner_x005D \_ _x005B_table_x005D \_>。ここで _x005B \_ は左角かっこ ([) のエンコーディングで、_x005D \_ は右角かっこ (]) のエンコーディングです。  
  
## <a name="executing-updategrams"></a>アップデートグラムの実行  
 アップデートグラムはテンプレートであり、テンプレートのすべての処理メカニズムが適用されます。 SQLXML 4.0 では、アップデートグラムを次のいずれかの方法で実行できます。  
  
-   ADO コマンドに含めて送信する。  
  
-   OLE DB コマンドとして送信する。  
  
## <a name="see-also"></a>参照  
 [SQLXML 4.0&#41;&#40;アップデートグラムのセキュリティに関する考慮事項](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
