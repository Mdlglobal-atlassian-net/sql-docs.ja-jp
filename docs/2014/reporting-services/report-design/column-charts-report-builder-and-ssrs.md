---
title: 縦棒グラフ (レポート ビルダーおよび SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ae8c138b-e356-4ad8-862c-a4a8d0c04149
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e8477b4e8e0e6c0fc6e4801a975b11d79dadf83f
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "66106229"
---
# <a name="column-charts-report-builder-and-ssrs"></a>Column Charts (Report Builder and SSRS)
  縦棒グラフでは、カテゴリ別にグループ化された縦棒のセットとして系列が表示されます。 縦棒グラフは、時間の経過に伴うデータの変化を示す場合やアイテム間の比較を示す場合に便利です。 一般的な縦棒グラフは、横棒グラフおよび範囲縦棒グラフと密接な関係にあります。横棒グラフでは、横棒のセットとして系列が表示され、範囲縦棒グラフでは、始点と終点が異なる縦棒のセットとして系列が表示されます。 詳細については、「 [横棒グラフ &#40;レポート ビルダーおよび SSRS&#41;](charts-report-builder-and-ssrs.md) 」と「 [範囲グラフ &#40;レポート ビルダーおよび SSRS&#41;](range-charts-report-builder-and-ssrs.md)」を参照してください。  
  
 3 つの系列では共通の期間が共有され、有効な比較が可能になるため、このデータには縦棒グラフが適しています。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations-of-a-column-chart"></a>縦棒グラフの種類  
  
-   **積み上げ**: 複数の系列が垂直方向に積み上げられた縦棒グラフ。 グラフに系列が 1 つしかない場合、積み上げ縦棒グラフでも、縦棒グラフと同じように表示されます。  
  
-   **100% 積み上げ**: 複数の系列がグラフ領域で 100% になるように垂直方向に積み上げられた縦棒グラフ。 グラフに系列が 1 つしかない場合、すべての縦棒はグラフ領域で 100% になります。  
  
-   **3-D 集合**: 各系列を 3-D グラフの個別の行で表す縦棒グラフ。  
  
-   **3-D 円柱**: 3-D グラフで棒が円柱のような形をしている縦棒グラフ。  
  
-   `Histogram`. グラフの棒が正規分布で配置されるように計算されている縦棒グラフ。  
  
-   `Pareto`. 棒が最も高い方から順に配置されている縦棒グラフ。  
  
## <a name="data-considerations-for-a-column-chart"></a>縦棒グラフのデータに関する注意点  
  
-   横棒グラフおよび縦棒グラフは、主に、グループ間の比較を示すために使用されます。 グラフに 4 つ以上の系列が存在する場合は、積み上げ横棒グラフまたは積み上げ縦棒グラフの使用を検討してください。 また、グラフに複数の系列がある場合は、積み上げ横棒グラフまたは積み上げ縦棒グラフを複数のグループにまとめることもできます。 詳細については、「[棒グラフ &#40;レポートビルダーと SSRS&#41;](charts-report-builder-and-ssrs.md)および*縦棒グラフ*」を参照してください。  
  
-   縦棒グラフでは、カテゴリ軸のラベルを横方向に表示するための十分な領域がありません。 カテゴリのラベルが長い場合は、横棒グラフを使用するか、ラベルの回転角度を変更することを検討してください。  
  
-   縦棒グラフの各棒に特殊な描画スタイルを追加して、視覚的な効果を高めることができます。 描画スタイルには、くさび形、エンボス、円柱、およびグラデーションがあります。 これらの効果は、2D グラフを見やすくするためにデザインされています。 3D グラフを使用している場合でも描画スタイルを適用できますが、同じ効果を得られないことがあります。 横棒グラフに描画スタイルを追加する方法の詳細については、「 [グラフへの傾斜、エンボス、およびテクスチャのスタイルの追加 &#40;レポート ビルダーおよび SSRS&#41;](chart-effects-add-bevel-emboss-or-texture-report-builder.md)」をご覧ください。  
  
-   グラフをヒストグラムまたはパレート グラフとして表示する機能は、縦棒グラフ固有の機能です。 これを行うに`Histogram`は、Showの nas プロパティをに`Pareto`設定するか、 `true`プロパティウィンドウでをに設定します。  
  
## <a name="see-also"></a>参照  
 [グラフ &#40;レポート ビルダーおよび SSRS&#41;](charts-report-builder-and-ssrs.md)   
 [グラフの種類 &#40;レポート ビルダーおよび SSRS&#41;](chart-types-report-builder-and-ssrs.md)   
 [横棒グラフ (レポート ビルダーおよび SSRS)](charts-report-builder-and-ssrs.md)   
 [範囲グラフ &#40;レポート ビルダーおよび SSRS&#41;](range-charts-report-builder-and-ssrs.md)   
 [チュートリアル: レポートへの横棒グラフの追加 &#40;レポート ビルダー&#41;](../tutorial-add-a-bar-chart-to-your-report-report-builder.md)   
 [グラフ内の空のデータ ポイントおよび NULL データ ポイント (レポート ビルダーおよび SSRS)](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md)  
  
  
