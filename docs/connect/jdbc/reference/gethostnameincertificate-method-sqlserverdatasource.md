---
title: getHostNameInCertificate メソッド (SQLServerDataSource) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- getHostNameInCertificate Method (SQLServerDataSource)
apilocation:
- getHostNameInCertificate Method (SQLServerDataSource)
apitype: Assembly
ms.assetid: 45ea04e2-9ea5-4171-9136-d09f8a95e128
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 5f35af25109bc68a36560c6496cf5f5268bd9319
ms.sourcegitcommit: 54cfeb36c9caa51ec68fa8f4a1918e305db5e00a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2020
ms.locfileid: "81219261"
---
# <a name="gethostnameincertificate-method-sqlserverdatasource"></a>getHostNameInCertificate メソッド (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  SQL Server の TLS (トランスポート層セキュリティ) (以前の SSL (Secure Sockets Layer)) 証明書を検証するために使用するホスト名が返されます。  
  
## <a name="syntax"></a>構文  
  
```  
  
public java.lang.String getHostNameInCertificate()  
```  
  
## <a name="return-value"></a>戻り値  
 ホスト名を含む **String** です。値が設定されていない場合は null です。  
  
## <a name="remarks"></a>解説  
 ホスト名は、通信レイヤーが TLS/SSL で暗号化されているときに、SQL Server の TLS/SSL 証明書の値を検証するために使用されます。  
  
 ホスト名が設定されていない場合、[getHostNameInCertificate](../../../connect/jdbc/reference/gethostnameincertificate-method-sqlserverdatasource.md) メソッドは null を返します。  
  
## <a name="see-also"></a>参照  
 [SQLServerDataSource のメンバー](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource クラス](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
