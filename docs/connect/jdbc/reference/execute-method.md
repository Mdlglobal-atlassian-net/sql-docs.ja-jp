---
title: execute メソッド () | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerPreparedStatement.execute ()
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: fa96d0f8-101b-422f-a767-405be9a5f74f
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: e4acb89b86540c6142961a2c3cad6f8ea28e5813
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "80922120"
---
# <a name="execute-method-"></a>execute () メソッド
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  [SQLServerPreparedStatement](../../../connect/jdbc/reference/sqlserverpreparedstatement-class.md) オブジェクトの SQL ステートメントを実行します。すべての種類の SQL ステートメントを実行することができます。  
  
## <a name="syntax"></a>構文  
  
```  
  
public boolean execute()  
```  
  
## <a name="return-value"></a>戻り値  
 このステートメントで結果セットを返す場合は **true** です。 これが更新数を返す場合、または結果を返さない場合は **false** です。  
  
## <a name="exceptions"></a>例外  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>解説  
 この execute メソッドは、java.sql.PreparedStatement インターフェイスの execute メソッドで規定されています。  
  
## <a name="see-also"></a>参照  
 [execute メソッド &#40;SQLServerPreparedStatement&#41;](../../../connect/jdbc/reference/execute-method-sqlserverpreparedstatement.md)   
 [SQLServerPreparedStatement のメンバー](../../../connect/jdbc/reference/sqlserverpreparedstatement-members.md)   
 [SQLServerPreparedStatement クラス](../../../connect/jdbc/reference/sqlserverpreparedstatement-class.md)  
  
  
