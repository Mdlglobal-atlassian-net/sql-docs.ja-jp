---
title: 序数 (MDX) |Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: b22cc6d5a609f8e1f585ccc1229e0e1cd67e1796
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "68055640"
---
# <a name="ordinal-mdx"></a>Ordinal (MDX)


  レベルに関連付けられた、0から始まる序数値を返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
Level_Expression.Ordinal   
```  
  
## <a name="arguments"></a>引数  
 *Level_Expression*  
 レベルを返す有効な多次元式 (MDX) 式です。  
  
## <a name="remarks"></a>Remarks  
 **序数**関数は、クエリ結果内の各セルの序数位置に基づいて、さまざまな階層レベルのさまざまな値を条件付きで表示するために、 **IIF**および**currentmember**関数と組み合わせて使用されることがよくあります。 たとえば、 **Ordinal**関数を使用すると、特定のレベルで計算を実行し、他のレベルで "N/a" という既定値を表示できます。  
  
## <a name="example"></a>例  
 次の例では、Calendar 階層内の Calendar Quarter レベルの序数が返されます。  
  
```  
WITH MEMBER Measures.x AS [Date].[Calendar].[Calendar Quarter].Ordinal  
SELECT Measures.x on 0  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>参照  
 [MDX 関数リファレンス &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
