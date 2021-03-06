---
title: 配置スクリプトを作成するために使用する入力ファイルについてMicrosoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input files [Analysis Services]
- Analysis Services Deployment Wizard, scripts
- deploying [Analysis Services], input files
- Analysis Services Deployment Wizard, input files
- scripts [Analysis Services], deployment
- Analysis Services deployments, input files
- modifying input files
ms.assetid: 20e080cd-6a0e-4591-b022-ea4cd3638e36
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: dec93494dd21412c067af293832066087ca3ed37
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "66075412"
---
# <a name="understanding-the-input-files-used-to-create-the-deployment-script"></a>配置スクリプトを作成するための入力ファイルについて
  プロジェクトを[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]ビルドすると、 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]によってプロジェクトの XML ファイルが生成されます。 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] では、これらの XML ファイルは [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] プロジェクトの出力フォルダーに保存されます。 既定では、出力は \Bin フォルダーに対して行われます。 次の表は、 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] で作成される XML ファイルを示しています。  
  
|XMLA ファイル|説明|  
|---------------|-----------------|  
|\<*プロジェクト名*> asdatabase|プロジェクト内のすべての [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] オブジェクトの宣言定義が含まれています。|  
|\<*プロジェクト名*> deploymenttargets|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] オブジェクトが作成される [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] インスタンスおよびデータベースの名前が含まれています。|  
|\<*プロジェクト名*>. configsettings|データ ソース接続情報やオブジェクト格納場所など、環境に固有の設定が含まれています。 このファイルの設定は、 \<*プロジェクト名*>. asdatabase ファイルの設定よりも優先されます。|  
|\<*プロジェクト名*> deploymentoptions|配置がトランザクションであるかどうかや、配置したオブジェクトを配置後に処理するかどうかなどの配置オプションが含まれています。|  
  
> [!NOTE]  
>  [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] では、プロジェクト ファイルにパスワードは保存されません。  
  
## <a name="modifying-the-input-files"></a>入力ファイルの変更  
 入力ファイル内の値または入力ファイルから取得された値を変更すると、 \<*プロジェクト名*> asdatabase ファイル (または、既存[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]のデータベースからスクリプトを生成する場合は XMLA スクリプトファイル全体) を編集しなくても、配置先、構成設定、および配置オプションを変更できるようになります。 個々のファイルを変更できると、さまざまな目的に合わせてさまざまな配置スクリプトを簡単に作成できます。  
  
 次のトピックでは、さまざまな入力ファイル内の値を変更する方法について説明します。  
  
-   [インストール先の指定](deployment-script-files-specifying-the-installation-target.md)  
  
-   [パーティションおよびロールの配置オプションの指定](deployment-script-files-partition-and-role-deployment-options.md)  
  
-   [ソリューションの配置に関する構成設定の指定](deployment-script-files-solution-deployment-config-settings.md)  
  
-   [処理オプションの指定](deployment-script-files-specifying-processing-options.md)  
  
## <a name="see-also"></a>参照  
 [Analysis Services 配置ウィザードの実行](running-the-analysis-services-deployment-wizard.md)   
 [Analysis Services 配置スクリプトについて](understanding-the-analysis-services-deployment-script.md)  
  
  
