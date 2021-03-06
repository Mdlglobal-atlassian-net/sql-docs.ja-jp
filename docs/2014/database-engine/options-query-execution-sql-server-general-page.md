---
title: '[オプション] ([クエリ実行]-SQL Server-[全般] ページ) |Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryExecution.SqlServer.SqlExecutionGeneral
ms.assetid: 3f8d59bc-3f97-4e5d-8b86-5ac670d20780
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 6d14371c1db5273d66fee327cc03d2b2e2de3edb
ms.sourcegitcommit: 4b5919e3ae5e252f8d6422e8e6fddac1319075a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2020
ms.locfileid: "83000799"
---
# <a name="options-query-execution-sql-server-general-page"></a>[オプション] ([クエリ実行]-SQL Server-[全般] ページ)
  このページを使用すると、 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] クエリを実行するためのオプションを指定できます。 これらのオプションに加えられた変更は、新しい [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] クエリだけに適用されます。 現在のクエリのオプションを変更するには、**[クエリ]** メニューの **[クエリ オプション]** をクリックするか、[[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] クエリ] ウィンドウで右クリックし、**[クエリ オプション]** を選択します。  
  
## <a name="options"></a>オプション  
 **SET ROWCOUNT**  
 既定値の 0 は、 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] がすべての結果を受け取るまで待機することを意味します。 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] が指定された行数を取得した後にクエリを停止するように設定するには、0 より大きい値を指定します。 このオプションをオフにして、すべての行が返されるようにするには、SET ROWCOUNT 0 を指定してください。  
  
 **SET TEXTSIZE**  
 既定値の 2,147,483,647 バイトは、[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] が `text` データ フィールドおよび `ntext` データ フィールドの上限まで、完全なデータ フィールドを提供することを示します。 大きな値の場合に結果を制限するには、これより小さなサイズを指定します。 指定されたサイズよりも大きい列は切り捨てられます。  
  
 **[実行タイムアウト]**  
 **[新しい接続]** ダイアログ ボックスに既定値を設定します。 このスピン ボックスは、クエリを取り消す前に待機する秒数を [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] に指示するために使用します。 値0は待機時間が無期限であるか、タイムアウトがないことを示します。新しいインストールでは、この値は0です。  
  
 **[バッチ区切り記号]**  
 [!INCLUDE[tsql](../includes/tsql-md.md)] ステートメントをバッチに分けるために使用する単語を入力します。 既定値は GO です。  
  
 **[既定で、新しいクエリを SQLCMD モードで開始する]**  
 新しいクエリを SQLCMD モードで開始するには、このチェック ボックスをオンにします。 SQLCMD モードに関する情報については、「[クエリ エディターによる SQLCMD スクリプトの編集](../relational-databases/scripting/edit-sqlcmd-scripts-with-query-editor.md)」を参照してください。  
  
 このオプションを選択する場合は、次の制限事項に注意してください。  
  
-   [!INCLUDE[ssDE](../includes/ssde-md.md)] クエリ エディターの IntelliSense が無効になります。  
  
-   クエリ エディターはコマンド ラインから実行できないため、変数などのコマンド ライン パラメーターを渡すことができません。  
  
-   クエリ エディターはオペレーティング システムのプロンプトに応答できないため、対話型のステートメントを実行しないように注意する必要があります。  
  
 **既定値にリセット**  
 クリックすると、このページ上のすべての値が元の既定値にリセットされます。  
  
## <a name="see-also"></a>参照  
 [sqlcmd Utility](../tools/sqlcmd-utility.md)  
  
  
