---
title: キューブの定義 |Microsoft Docs
ms.date: 05/06/2019
ms.prod: sql
ms.technology: analysis-services
ms.custom: multidimensional-models
ms.topic: tutorial
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: cfa0e6297958aaee90dac7888349595c21e2fbc4
ms.sourcegitcommit: 54c8420b62269f6a9e648378b15127b5b5f979c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65403944"
---
# <a name="lesson-2-2---defining-a-cube"></a>レッスン 2-2-キューブの定義
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]

キューブ ウィザードを使用すると、キューブのメジャー グループとディメンションを定義できます。 この実習では、キューブ ウィザードを使用してキューブを作成します。  
  
### <a name="to-define-a-cube-and-its-properties"></a>キューブとそのプロパティを定義するには  
  
1.  ソリューション エクスプローラーで **[キューブ]** を右クリックし、 **[新しいキューブ]** をクリックします。 キューブ ウィザードが表示されます。  
  
2.  **[キューブ ウィザードへようこそ]** ページで **[次へ]** をクリックします。  
  
3.  **[作成方法の選択]** ページで **[既存のテーブルを使用する]** オプションが選択されていることを確認し、 **[次へ]** をクリックします。  
  
4.  **[メジャー グループ テーブルの選択]** ページで、 **Adventure Works DW 2012** データ ソース ビューが選択されていることを確認します。  
  
5.  **[候補検索]** をクリックすると、メジャー グループの作成に使用するテーブルがキューブ ウィザードによって提示されます。  
  
    ウィザードでそれらのテーブルが調べられ、 **InternetSales** がメジャー グループ テーブルとして提示されます。 メジャー グループ テーブル (ファクト テーブルとも呼ばれます) には、販売数など必要なメジャーが含まれています。  
  
6.  **[次へ]** をクリックします。  
  
7.  **[メジャーの選択]** ページで、 **Internet Sales** メジャー グループ内の選択されているメジャーを確認し、以下のメジャーのチェック ボックスをオフにします。  
  
    -   **Promotion Key**  
  
    -   **Currency Key**  
  
    -   **Sales Territory Key**  
  
    -   **Revision Number**  
  
    既定では、ファクト テーブル内で、ディメンションにリンクしていないすべての数値列がメジャーとして選択されます。 ただし、上の 4 つの列は実際にはメジャーではありません。 最初の 3 つは、ファクト テーブルとディメンション テーブルをリンクするキー値で、この初期段階のキューブでは使用しません。  
  
8.  **[次へ]** をクリックします。  
  
9. **[既存のディメンションの選択]** ページで、既に作成した **Date** ディメンションが選択されていることを確認し、 **[次へ]** をクリックします。  
  
10. **[新しいディメンションの選択]** ページで、作成する新しいディメンションを選択します。 そのためには、 **[Customer]**、 **[Geography]**、 **[Product]** の各チェック ボックスがオンになっていることを確認し、 **[InternetSales]** チェック ボックスをオフにします。  
  
11. **[次へ]** をクリックします。  
  
12. **[ウィザードの完了]** ページで、[キューブ名] ボックスに「 **Analysis Services Tutorial**」と入力します。 [プレビュー] ペインで、 **InternetSales** メジャー グループとそのメジャーを表示できます。 **Date**、 **Customer** 、 **Product** の各ディメンションも表示できます。  
  
13. **[完了]** をクリックしてウィザードを終了します。  
  
    ソリューション エクスプローラーで、 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Tutorial プロジェクトの [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] [キューブ] **フォルダー内に** Tutorial キューブが表示されます。また、 **[ディメンション]** フォルダーの下には、Customer、Product というデータベース ディメンションが表示されます。 さらに、開発環境の中央の [キューブ構造] タブには [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Tutorial キューブが表示されます。  
  
14. キューブ内のディメンション テーブルとファクト テーブルをすべて表示できるよう、[キューブ構造] タブのツール バーで、 **ズーム** レベルを 50% に変更します。 ファクト テーブルは黄色、ディメンション テーブルは青で表示されています。  
  
15. **[ファイル]** メニューの **[すべてを保存]** をクリックします。  
  
## <a name="next-task-in-lesson"></a>このレッスンの次の作業  
[ディメンションへの属性の追加](lesson-2-3-adding-attributes-to-dimensions.md)  
  
## <a name="see-also"></a>参照  
[多次元モデルのキューブ](../multidimensional-models/cubes-in-multidimensional-models.md)  
[多次元モデル内のディメンション](../multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
  