---
title: CALL ステートメント (MDX) |Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: de74590ac4c43a9141c0ab2092babf41ffd23ba5
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "68106299"
---
# <a name="mdx-data-manipulation---call"></a>MDX データ操作 - CALL


  現在のスコープまたは必要に応じて指定したキューブで void を返すストアドプロシージャを実行します。  
  
## <a name="syntax"></a>構文  
  
```  
  
CALL SP_Name   
   [ (SP_Argument   
      [, SP_Argument ,...n]  
      ) ]   
[ONCube_Expression]  
```  
  
## <a name="arguments"></a>引数  
 *SP_Name*  
 ストアド プロシージャの名前を指定する有効な文字列式です。  
  
 *SP_Argument*  
 呼び出したストアド プロシージャに渡す引数を指定する有効な文字列式です。  
  
 *Cube_Expression*  
 キューブの名前を指定する有効な文字列キューブ式です。  
  
## <a name="remarks"></a>Remarks  
 **CALL**ステートメントは、指定された登録済みストアドプロシージャを実行します。オプションで、指定したストアドプロシージャの1つ以上の引数を含めることができます。 **CALL**ステートメントは、値を返さないストアドプロシージャでのみ使用されます。 MDX 式の中でこのステートメントと他の関数や演算子を併用することはできません。 値を返す登録済みのストアド プロシージャについては、MDX 式の中で直接呼び出すことも、MDX の他の関数や演算子と併用することも可能です。  
  
 キューブが指定されていない場合、ステートメントは、現在のキューブに対してストアドプロシージャを実行します。  
  
> [!NOTE]  
>  ストアドプロシージャがクライアントに登録されていない場合、 **call**ステートメントはの[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]インスタンスからストアドプロシージャを呼び出そうとします。  
  
## <a name="see-also"></a>参照  
 [Mdx&#41;&#40;MDX データ操作ステートメント](../mdx/mdx-data-manipulation-statements-mdx.md)   
 [ストアド プロシージャの使用 &#40;MDX&#41;](../mdx/using-stored-procedures-mdx.md)  
  
  
