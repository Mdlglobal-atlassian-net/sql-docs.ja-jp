---
title: '手順 1: 作業フォルダーと環境変数の作成 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 45091ba2-ea3d-4399-9814-489d812b42cc
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: b58da11d973d169a0372e59c7e8d7e174e3cf789
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2020
ms.locfileid: "62767654"
---
# <a name="step-1-creating-working-folders-and-environment-variables"></a>手順 1:作業フォルダーと環境変数の作成
  このタスクでは、この後のチュートリアル タスクで使用する作業フォルダー (C:\DeploymentTutorial) と新しいシステム環境変数 (`DataTransfer` および `LoadXMLData`) を作成します。  
  
 作業フォルダーは、C ドライブのルートにあります。 別のドライブまたは場所を使用する必要がある場合は、変更してかまいません。 ただし、この場所を書き留めておいて、チュートリアルで DeploymentTutorial 作業フォルダーの場所が参照されたときに、該当する場所を使用する必要があります。  
  
 この後のレッスンでは、ファイル システムに保存されているパッケージを msdb[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] データベースの sysssispackages テーブルに配置します。 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] パッケージは別のコンピューターに配置するのが理想的です。 これが不可能な場合でも、パッケージをローカル コンピューターの [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] のインスタンスに配置してこのチュートリアルを実行すれば、多くのことを学習できます。 ローカル コンピューターと配置先コンピューターで使用する環境変数には同じ変数名が付いていますが、変数に格納される値は異なります。 たとえば、ローカル コンピューターでは、環境変数 `DataTransfer` の値は C:\DeploymentTutorial フォルダーを参照しています。一方、ターゲット コンピューターでは、環境変数 `DataTransfer` は C:\DeploymentTutorialInstall フォルダーを参照しています。  
  
 ローカル コンピューターに配置する場合は、1 つのセットの環境変数を作成するだけで済みます。ただし、ローカルの配置を行う前に、環境変数を適切な値に更新する必要があります。  
  
 パッケージを別のコンピューターに配置する場合は、2 つのセットの環境変数を作成する必要があります。1 つはローカル コンピューター用で、もう 1 つは配置先コンピューター用です。 現時点では、ソース コンピューター用の変数のみを作成できます。配置先コンピューター用の変数は後で作成しますが、配置先コンピューターにパッケージをインストールする前に、このコンピューターでフォルダーと環境変数が使用可能になっている必要があります。  
  
### <a name="to-create-the-local-working-folder"></a>ローカルの作業フォルダーを作成するには  
  
1.  [スタート] メニューを右クリックし、[エクスプローラー] をクリックします。  
  
2.  **[ローカル ディスク (C:)]** をクリックします。  
  
3.  **[ファイル]** メニューの **[新規作成]** をポイントし、 **[フォルダー]** をクリックします。  
  
4.  新しいフォルダーの名前`DeploymentTutorial`をに変更します。  
  
### <a name="to-create-local-environment-variables"></a>ローカルの環境変数を作成するには  
  
1.  **[スタート]** ボタンをクリックし、 **[コントロール パネル]** をクリックします。  
  
2.  コントロール パネルで、 **[システム]** をダブルクリックします。  
  
3.  **[システムのプロパティ]** ダイアログ ボックスで、 **[詳細設定]** タブをクリックし、 **[環境変数]** をクリックします。  
  
4.  **[環境変数]** ダイアログ ボックスの **[システム環境変数]** フレームで、 **[新規]** をクリックします。  
  
5.  [**新しいシステム変数**] ダイアログボックスで、 `DataTransfer` [**変数名**] ボックスに「 `C:\DeploymentTutorial\datatransferconfig.dtsconfig` 」と入力し、[**変数の値**] ボックスに「」と入力します。  
  
6.  **[OK]** をクリックします。  
  
7.  もう一度 [**新規**] を`LoadXMLData`クリックし、[**変数名**] `C:\DeploymentTutorial\loadxmldataconfig.dtsconfig`ボックスに「」と入力し、[**変数の値**] ボックスに「」と入力します。  
  
8.  **[OK]** をクリックして **[環境変数]** ダイアログ ボックスを閉じます。  
  
9. **[OK]** をクリックして **[システムのプロパティ]** ダイアログ ボックスを閉じます。  
  
10. 必要に応じて、コンピューターを再起動します。 コンピューターを再起動しない場合、新しい変数の名前はパッケージ構成ウィザードには表示されませんが、この変数を使用することはできます。  
  
### <a name="to-create-destination-environment-variables"></a>配置先の環境変数を作成するには  
  
1.  **[スタート]** ボタンをクリックし、 **[コントロール パネル]** をクリックします。  
  
2.  コントロール パネルで、 **[システム]** をダブルクリックします。  
  
3.  **[システムのプロパティ]** ダイアログ ボックスで、 **[詳細設定]** タブをクリックし、 **[環境変数]** をクリックします。  
  
4.  **[環境変数]** ダイアログ ボックスの **[システム環境変数]** フレームで、 **[新規]** をクリックします。  
  
5.  [**新しいシステム変数**] ダイアログボックスで、 `DataTransfer` [**変数名**] ボックスに「 `C:\DeploymentTutorialInstall\datatransferconfig.dtsconfig` 」と入力し、[**変数の値**] ボックスに「」と入力します。  
  
6.  **[OK]** をクリックします。  
  
7.  もう一度 [**新規**] を`LoadXMLData`クリックし、[**変数名**] `C:\DeploymentTutorialInstall\loadxmldataconfig.dtsconfig`ボックスに「」と入力し、[**変数の値**] ボックスに「」と入力します。  
  
8.  **[OK]** をクリックして **[環境変数]** ダイアログ ボックスを閉じます。  
  
9. **[OK]** をクリックして **[システムのプロパティ]** ダイアログ ボックスを閉じます。  
  
10. 必要に応じて、コンピューターを再起動します。  
  
## <a name="next-task-in-lesson"></a>このレッスンの次の作業  
 [手順 2: 配置プロジェクトの作成](../integration-services/lesson-1-2-creating-the-deployment-project.md)  
  
![Integration Services アイコン (小)](media/dts-16.gif "Integration Services のアイコン (小)")**は Integration Services で最新の**状態を維持  <br /> マイクロソフトが提供する最新のダウンロード、アーティクル、サンプル、ビデオ、およびコミュニティで選択されたソリューションについては、MSDN の [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] のページを参照してください。<br /><br /> [MSDN の Integration Services のページを参照する](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> これらの更新が自動で通知されるようにするには、ページの RSS フィードを定期受信します。  
  
  
