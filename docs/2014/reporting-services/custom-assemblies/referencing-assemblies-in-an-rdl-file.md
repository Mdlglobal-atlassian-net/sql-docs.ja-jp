---
title: RDL ファイルのアセンブリの参照 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- RDL [Reporting Services], referencing assemblies
- referencing custom assemblies
- custom assemblies [Reporting Services], referencing
- Report Definition Language, referencing assemblies
- report definition files [Reporting Services]
ms.assetid: 9a48e552-7d47-4243-9be1-894990c506d9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bc52419f382ea44fc718a47e99bbd0981275d240
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "63264794"
---
# <a name="referencing-assemblies-in-an-rdl-file"></a>RDL ファイルのアセンブリの参照
  レポート定義ファイルでのカスタム コード アセンブリの使用をサポートするため、2 つのレポート定義言語 (RDL) 要素 **CodeModules** と **Classes** が RDL 仕様に含まれています。  
  
 **CodeModules** 要素を使用すると、レポート式でマネージド コード アセンブリを参照できます。 **CodeModules** は、レポート定義ファイルで特殊な関数の呼び出しに使用するアセンブリへの参照を含むトップレベルの要素です。 カスタム アセンブリの使用をサポートするレポート定義のエントリは次のようになります。  
  
```  
<CodeModules>  
   <CodeModule>CurrencyConversion, Version=1.0.1363.31103, Culture=neutral, PublicKeyToken=null</CodeModule>  
</CodeModules>  
```  
  
 カスタム コードから <xref:System.Reflection.Assembly.Load%2A> を呼び出すのではなく、**CodeModule** 要素を RDL ファイルに手動で追加するか、**[レポートのプロパティ]** ダイアログの **[参照]** タブを使用してカスタム アセンブリを登録します。 詳細については、「 [レポート デザイナーでカスタム コードやアセンブリを式から参照する (SSRS)](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md)を表しています。  
  
 **Classes** 要素では、レポート定義でのインスタンス メンバーの使用がサポートされます。 **Classes** は、クラス名とインスタンス名への参照を含むトップレベルの要素です。 インスタンス メンバーの使用をサポートするレポート定義のエントリは次のようになります。  
  
```  
<Classes>  
   <Class>  
      <ClassName>CurrencyConversion.DollarCurrencyConversion</ClassName>  
      <InstanceName>m_myDollarConversion</InstanceName>  
   </Class>  
</Classes>  
```  
  
 詳細については、「[式を使用したカスタム アセンブリへのアクセス](accessing-custom-assemblies-through-expressions.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [レポートでのカスタム アセンブリの使用](using-custom-assemblies-with-reports.md)  
  
  
