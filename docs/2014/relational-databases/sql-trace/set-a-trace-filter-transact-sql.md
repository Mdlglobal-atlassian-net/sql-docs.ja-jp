---
title: Setブール値メソッド (Sqlserviceadvanced Property クラス) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- SetBoolValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetBoolValue method
ms.assetid: 5252b439-fce5-446a-8e57-99e3054bee69
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 302ac36150d21dfecca1e6c6edfbcf6fd86c42f0
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "63226142"
---
# <a name="setboolvalue-method-sqlserviceadvancedproperty-class"></a>SetBoolValue メソッド (SqlServiceAdvancedProperty クラス)
  プロパティのブール値を設定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
object  
.SetBoolValue [= value]  
```  
  
## <a name="parts"></a>要素  
 *object*  
 詳細プロパティを表す [SqlServiceAdvancedProperty クラス](../wmi-provider-configuration-classes/sqlserviceadvancedproperty-class/sqlserviceadvancedproperty-class.md) オブジェクト。  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|*ブール値*|詳細プロパティの値を指定するブール値|  
  
## <a name="property-valuereturn-value"></a>プロパティ値/戻り値  
 `uint32` 値。サービスが正常に変更された場合は 0、要求がサポートされていない場合は 1 になります。それ以外の数値はエラーを示します。  
  
## <a name="remarks"></a>Remarks  
 プロパティをブール値に設定するには、プロパティ値の型がブール型である必要があります。  
  
## <a name="see-also"></a>参照  
 [サービスの開始および停止](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  
