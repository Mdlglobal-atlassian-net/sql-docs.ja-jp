---
title: setCatalog メソッド (SQLServerConnection) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerConnection.setCatalog
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 553c0603-c07d-436a-86eb-3ba6b51bd696
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 3a7da2d69f4865eda439b0fb1219be6357c1c40e
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "80929096"
---
# <a name="setcatalog-method-sqlserverconnection"></a>setCatalog メソッド (SQLServerConnection)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  渡されたカタログ名を設定し、[SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) オブジェクトのデータベースの作業用サブスペースを選択します。  
  
## <a name="syntax"></a>構文  
  
```  
  
public void setCatalog(java.lang.String catalog)  
```  
  
#### <a name="parameters"></a>パラメーター  
 *catalog*  
  
 カタログ名を含む**文字列**です。  
  
## <a name="exceptions"></a>例外  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>解説  
 この setCatalog メソッドは、java.sql.Connection インターフェイスの setCatalog メソッドで指定されています。  
  
 *catalog* 引数は、[!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] によって自動的にエスケープされます。 このメソッドを使用すると、Connection オブジェクトのカタログ プロパティが設定されます。 このプロパティは、他の方法で暗黙的に設定されることはありません。  
  
## <a name="see-also"></a>参照  
 [SQLServerConnection のメンバー](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection クラス](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
