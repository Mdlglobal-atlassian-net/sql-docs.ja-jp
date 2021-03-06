---
title: Prompt プロパティ-動的 (ADO) |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
helpviewer_keywords:
- Prompt property [ADO]
ms.assetid: c4f001b5-8d16-4d39-a42e-c0e2faaaceaf
author: rothja
ms.author: jroth
ms.openlocfilehash: e99273a94fc38779b50203d3dd5b78106f6a90c6
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2020
ms.locfileid: "82761920"
---
# <a name="prompt-property-dynamic-ado"></a>Prompt プロパティ - 動的 (ADO)
OLE DB プロバイダーがユーザーに初期化情報の入力を求めるかどうかを指定します。  
  
## <a name="settings-and-return-values"></a>設定と戻り値  
 [ConnectPromptEnum](../../../ado/reference/ado-api/connectpromptenum.md)値を設定して返します。  
  
## <a name="remarks"></a>解説  
 **Prompt**は動的プロパティであり、OLE DB プロバイダーによって[接続](../../../ado/reference/ado-api/connection-object-ado.md)オブジェクトの[プロパティ](../../../ado/reference/ado-api/properties-collection-ado.md)コレクションに追加される場合があります。 初期化情報を要求するために、OLE DB プロバイダーは通常、ユーザーにダイアログボックスを表示します。  
  
 **接続が閉じ**られると、[接続](../../../ado/reference/ado-api/connection-object-ado.md)オブジェクトの動的プロパティは失われます。 既定以外の値を使用するには、**接続**を再度開く前に、 **Prompt**プロパティをリセットする必要があります。  
  
> [!NOTE]
>  ユーザーがダイアログボックスに応答できないシナリオで、プロバイダーがユーザーにメッセージを表示するように指定しないでください。 たとえば、アプリケーションがユーザーのクライアントではなくサーバーシステム上で実行されている場合や、ユーザーがログオンしていないシステムでアプリケーションが実行されている場合は、ユーザーは応答できません。 このような場合、アプリケーションは応答を無期限に待機し、ロックアップしているように見えます。  
  
## <a name="usage"></a>使用  
  
```  
Set cn = New Connection  
cn.Provider = "SQLOLEDB"  
cn.Properties("Prompt") = adPromptNever    ' do not prompt the user  
```  
  
## <a name="applies-to"></a>適用対象  
 [Connection オブジェクト (ADO)](../../../ado/reference/ado-api/connection-object-ado.md)
