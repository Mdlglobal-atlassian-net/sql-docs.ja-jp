---
title: 無名のパラメーターを使用したクエリの作成
ms.custom: seo-lt-2019
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- unnamed parameters
- parameters [SQL Server], unnamed
ms.assetid: 5f4b664b-3d3d-4d07-a0e7-791d78743504
author: markingmyname
ms.author: maghan
ms.manager: jroth
ms.reviewer: ''
ms.openlocfilehash: 4706388261588c58aac6a1366f0be40358ec2910
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2020
ms.locfileid: "75254282"
---
# <a name="create-queries-with-unnamed-parameters-visual-database-tools"></a>無名のパラメーターを使用したクエリの作成 (Visual Database Tools)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
リテラル値のプレースホルダーとして疑問符 (?) を指定すると、無名のパラメーターを持つクエリを作成できます。 クエリおよびビュー デザイナーにより、一時的な名前が指定されます。 クエリには、必要な数の無名のパラメーターを指定できます。  
  
クエリおよびビュー デザイナーでクエリを実行すると、一時的な名前と共に [クエリ パラメーター] ダイアログ ボックスが表示されます。  
  
### <a name="to-specify-an-unnamed-parameter"></a>無名のパラメーターを指定するには  
  
1.  検索する列または式を [抽出条件ペイン](../../ssms/visual-db-tools/criteria-pane-visual-database-tools.md)に追加します。 検索列または検索式をクエリ出力に表示しない場合は、出力列から削除します。  
  
2.  検索するデータ列または式を含む行を選択し、 **[フィルター]** グリッド列に疑問符 (?) を入力します。  
  
    既定では、"=" 演算子が追加されます。 ただし、セルを編集して、">"、"<"、または他の SQL 比較演算子にも変更できます。  
  
## <a name="see-also"></a>参照  
[パラメーターを使用したクエリ (Visual Database Tools)](../../ssms/visual-db-tools/query-with-parameters-visual-database-tools.md)  
  
