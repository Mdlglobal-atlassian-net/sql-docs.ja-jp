---
title: '[レベル名前付けテンプレート] ダイアログボックス (Analysis Services-多次元データ) |Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.levelnamingtemplatedialog.f1
helpviewer_keywords:
- Level Naming Template dialog box
ms.assetid: 96cad715-213e-4eac-9003-130a2f5fc985
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: febaae6051e8428d3fed2bb6533ce2c4d972950f
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "66078059"
---
# <a name="level-naming-template-dialog-box-analysis-services---multidimensional-data"></a>[レベル名前付けテンプレート] ダイアログ ボックス (Analysis Services - 多次元データ)
  **の** [レベル名前付けテンプレート] [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] ダイアログ ボックスを使用すると、ディメンション内の親属性のレベル名前付けテンプレートを作成できます。 レベル名前付けテンプレートの詳細については、「[NamingTemplate 要素 &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/namingtemplate-element-assl)」を参照してください。 [**レベル名前付けテンプレート**] ダイアログボックスを表示するには、**ディメンションデザイナー**の [**翻訳] タブ**の [**翻訳の詳細**] ペインで、属性の翻訳の`NamingTemplate`値の省略記号ボタン ([.**..**]) をクリックします。  
  
## <a name="options"></a>オプション  
  
|用語|定義|  
|----------|----------------|  
|**[レベル テンプレートの定義]**|親属性のレベルの階層を設計するためのグリッドを表示します。 このグリッドには次の列が含まれています。<br /><br /> **Level**: **name**に指定された名前が使用されるレベルの序数位置を表示します。 レベルに新しい名前付けテンプレートを追加するには、 **[レベル]** のアスタリスク (\*) を含む行で **[名前]** を選択します。<br /><br /> **名前**:**レベル**で示されるレベルに使用される名前付けテンプレートが含まれています。 名前付けテンプレートのレベルの順位に対してプレースホルダーを追加するには、1 つのアスタリスク (*) を追加します。 名前付けテンプレートによって作成された名前の一部としてアスタリスクを追加\*\*するには、2つのアスタリスク () を追加します。|  
|**すべてクリア**|クリックすると、 **[レベル テンプレートの定義]** の行がすべて削除されます。|  
|**結果**|ダイアログ ボックスによって構築されたレベルの名前付けテンプレートを表示します。|  
  
## <a name="see-also"></a>参照  
 [多次元データ &#40;Analysis Services のデザイナーとダイアログボックス&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)   
 [翻訳 &#40;ディメンションデザイナー&#41; &#40;Analysis Services-多次元データ&#41;](translations-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
