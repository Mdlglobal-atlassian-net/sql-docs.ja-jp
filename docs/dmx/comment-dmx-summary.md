---
title: --(コメント) (DMX) Summary |Microsoft Docs
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 241ab17847a040e33c1fdb5e116e39fbc535d16d
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "68073090"
---
# <a name="---comment-dmx-summary"></a>--(コメント) (DMX) の概要
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  実行しないテキスト文字列[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]を示します。 コメントは、データマイニング拡張機能 (DMX) ステートメント内で入れ子にしたり、コード行の末尾に含めたり、別の行に挿入したりすることができます。  
  
## <a name="syntax"></a>構文  
  
```  
  
-- Comment_Text      
```  
  
#### <a name="parameters"></a>パラメーター  
 *Comment_Text*  
 コメントのテキストを含む文字列です。  
  
## <a name="remarks"></a>Remarks  
 この演算子は、単一行または入れ子になったコメントに使用します。 --を使用して挿入されたコメントは、改行文字で区切られます。  
  
 コメントの長さには制限がありません。  
  
 DMX でさまざまな種類のコメントを使用する方法の詳細については、「 [&#40;dmx&#41;](../dmx/comments-dmx.md)に関するコメント」を参照してください。  
  
## <a name="see-also"></a>参照  
 [DMX&#41;&#41; &#40;スラッシュの星 &#40;コメント](../dmx/slash-star-comment-dmx.md)   
 [DMX&#41;&#41; &#40;スラッシュ &#40;コメント](../dmx/double-slash-comment-dmx.md)   
 [DMX&#41; オペレーターリファレンス &#40;データマイニング拡張機能](../dmx/data-mining-extensions-dmx-operator-reference.md)   
 [DMX&#41;&#40;オペレーター](../dmx/operators-dmx.md)  
  
  
