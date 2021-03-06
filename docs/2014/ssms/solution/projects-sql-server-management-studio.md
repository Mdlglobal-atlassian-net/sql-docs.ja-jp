---
title: プロジェクト (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: c13af859-ca66-4e43-b76a-0650ac6566c0
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 85bc34af971db386862528ac36ea04fef33f2daa
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "63035688"
---
# <a name="projects-sql-server-management-studio"></a>プロジェクト (SQL Server Management Studio)
  [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] のプロジェクトは、論理的に関連したスクリプトやファイルの集合体であり、データベースの管理と開発のためにスクリプトやファイルをまとめて保存できるようになっています。  
  
## <a name="script-project-overview"></a>スクリプト プロジェクトの概要  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] スクリプト プロジェクトは、 [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]のコンポーネントであるソリューション エクスプローラーに表示されます。 1 つのスクリプト プロジェクトにはゼロ個以上のプロジェクト ファイルを組み込めます。 1 つのソリューションに 1 つのプロジェクトを追加することも、複数のプロジェクトをまとめて組み込むことも可能です。  
  
 プロジェクトには、次のようなものがあります。  
  
-   **接続**。 プロジェクト内に保存される接続には、ログイン情報、サーバー名、既定のデータベース、優先プロトコル、認証の種類、接続プロパティが含まれています。 接続情報をスクリプトと一緒に格納することも可能です (以下の説明を参照)。  
  
-   **SQL スクリプト**。 ユーザーが頻繁に使用する SQL スクリプトです。 プロジェクト内の .sql ファイルをダブルクリックすると、そのスクリプトが SQL エディターに表示されます。  
  
-   **MDX、DMX、および XMLA スクリプト**。 ユーザーが頻繁に使用する MDX スクリプトです。 プロジェクト内の .mdx ファイルをダブルクリックすると、そのスクリプトが SQL エディターに表示されます。  
  
-   **その他**。このフォルダーには、他の既定の種類のノードのどれにも適さないファイル (プロジェクトの目的を記述したテキスト ファイルなど) を込むことができます。  
  
 プロジェクトをソース コード管理システムに統合することもできます。  
  
## <a name="connecting-to-an-instance-of-sql-server-from-a-script-project"></a>スクリプト プロジェクトから SQL Server インスタンスへの接続  
 スクリプト プロジェクトには、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]への接続を組み込めます。 その接続をクリックすることで、プロジェクト内の [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] インスタンスに接続できます。 接続できた時点で、その選択した接続に定義されている [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] インスタンスに接続している SQL スクリプト ウィンドウが開きます。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 認証を使用する接続で [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] または MDX のスクリプトを開いた場合、エディターが開き、スクリプトが読み込まれてから、 **[SQL Server への接続]** ダイアログ ボックスでパスワードを入力するよう求められます。  
  
 ウィンドウを閉じると、それに対応する接続も終了します。  
  
 接続情報の修正には、 [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]の [プロパティ] ウィンドウを使用します。  
  
## <a name="project-tasks"></a>プロジェクト タスク  
  
|タスクの説明|トピック|  
|----------------------|-----------|  
|ソリューションに新しいプロジェクトを作成する方法について説明します。|[プロジェクトを作成する](create-a-project.md)|  
|既存のプロジェクトをソリューションに追加する方法について説明します。|[ソリューションへの既存のプロジェクトの追加](add-an-existing-project-to-a-solution.md)|  
|プロジェクト ファイルが保存される既定の場所を変更する方法について説明します。|[プロジェクトの既定の場所の変更](change-the-default-location-for-projects.md)|  
|プロジェクトの現在のプロパティを表示する方法について説明します。|[プロジェクトのプロパティの表示](view-project-properties.md)|  
|接続やスクリプト ファイルなどの新しい項目をプロジェクトに追加する方法について説明します。|[プロジェクトへの新規項目の追加](add-new-items-to-a-project.md)|  
|クエリの接続情報を確立する方法について説明します。|[クエリとプロジェクト内の接続との関連付け](associate-a-query-with-a-connection-in-a-project.md)|  
|クエリの接続情報を変更する方法について説明します。|[クエリに関連付けられた接続の変更](change-the-connection-associated-with-a-query.md)|  
|接続プロパティを変更する方法について説明します。|[プロジェクト内の接続のプロパティを表示または変更する方法](view-or-change-the-properties-of-a-connection-in-a-project.md)|  
  
## <a name="see-also"></a>参照  
 [ソリューション エクスプローラー](solution-explorer.md)   
 [ソリューション &#40;SQL Server Management Studio&#41;](solutions-sql-server-management-studio.md)   
 [ソリューション エクスプローラーのソース管理](../../database-engine/solution-explorer-source-control.md)  
  
  
