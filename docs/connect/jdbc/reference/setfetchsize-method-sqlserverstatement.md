---
title: setFetchSize メソッド (SQLServerStatement) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerStatement.setFetchSize
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 760e555e-9667-4b40-b0ba-778026ff2923
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 9fa7be5cc2f0e3f39e3d89881d38fb91a525b545
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "80922315"
---
# <a name="setfetchsize-method-sqlserverstatement"></a>setFetchSize メソッド (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  さらに行が必要な場合にデータベースからフェッチする必要がある行数について、[!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] にヒントを示します。  
  
## <a name="syntax"></a>構文  
  
```  
  
public final void setFetchSize(int rows)  
```  
  
#### <a name="parameters"></a>パラメーター  
 *rows*  
  
 フェッチする行数を示す **int** です。  
  
## <a name="exceptions"></a>例外  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>解説  
 この setFetchSize メソッドは、java.sql.Statement インターフェイスの setFetchSize メソッドによって指定されます。  
  
## <a name="see-also"></a>参照  
 [SQLServerStatement のメンバー](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement クラス](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
