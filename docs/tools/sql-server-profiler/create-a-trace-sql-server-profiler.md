---
title: トレースを作成する
titleSuffix: SQL Server Profiler
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
ms.assetid: 0302fa6d-d2b5-43fe-ad70-7a337575b112
author: markingmyname
ms.author: maghan
ms.custom: seo-lt-2019
ms.date: 08/01/2016
ms.openlocfilehash: 5a5c004bbc7e93720f18df998b989c46ced0188e
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2020
ms.locfileid: "75307331"
---
# <a name="create-a-trace-sql-server-profiler"></a>トレースの作成 (SQL Server Profiler)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

このトピックでは、 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] を使用してトレースを作成する方法について説明します。  
  
### <a name="to-create-a-trace"></a>トレースを作成するには  
  
1.  **[ファイル]** メニューの **[新しいトレース]** をクリックし、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]のインスタンスに接続します。  
  
     **[トレースのプロパティ]** ダイアログ ボックスが表示されます。  
  
    > **注:** **[接続の確立直後にトレースを開始する]** を選択している場合は、 **[トレースのプロパティ]** ダイアログ ボックスは表示されずに、トレースが開始されます。 この設定を無効にするには、* *[ツール]* * メニューの **[オプション]** をクリックし、[接続の確立直後にトレースを開始する] チェック ボックスをオフにします。  
  
2.  **[トレース名]** ボックスに、トレースの名前を入力します。  
  
3.  **[使用するテンプレート]** ボックスの一覧で、トレースの基本として使用するトレース テンプレートを選択します。テンプレートを使用しない場合は、 **[空白]** を選択します。  
  
4.  トレース結果を保存するには、次のいずれかの操作を実行します。  
  
    -   **[ファイルに保存する]** をクリックし、トレースをファイルにキャプチャします。 **[最大ファイル サイズの設定]** ボックスに値を指定します。 既定値は 5 MB です。  
  
         ファイル サイズが最大に達したとき新しいファイルを自動的に作成する場合は、 **[ファイル ロールオーバーを有効にする]** チェック ボックスをオンにします。 または、 **[サーバーがトレース データを処理する]** を選択することもできます。これを選択すると、トレースを実行しているサービスが、クライアント アプリケーションに代わってトレース データを処理します。 サーバーがトレース データを処理する場合、ストレス条件下でもイベントはスキップされません。ただし、サーバー パフォーマンスは低下する場合があります。  
  
    -   トレースをデータベース テーブルに記録する場合は、 **[テーブルに保存]** をクリックします。  
  
         必要に応じて、 **[最大行数の設定 (1000 行単位)]** チェック ボックスをオンにし、値を指定します。  
  
    > **注意!!** トレース結果をファイルにもテーブルにも保存しない場合は、 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] を開いているときにトレースを表示できます。 ただし、トレースを停止して [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]を終了した場合、トレース結果は失われます。 このようにトレース結果が失われないようにするには、 **[ファイル]** メニューの **[保存]** をクリックして、 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]を終了する前にトレース結果を保存します。  
  
5.  必要に応じて、 **[トレース停止時刻を有効にする]** チェック ボックスをオンにして、停止日時を指定します。  
  
6.  イベント、データ列、フィルターを追加または削除するには、 **[イベントの選択]**  タブをクリックします。詳細については、次を参照してください。[トレース ファイルに含めるイベントとデータ列の指定 &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
  
7.  **[実行]** をクリックしてトレースを開始します。  
  
## <a name="see-also"></a>関連項目  
 [SQL Server Profiler の実行に必要な権限](../../tools/sql-server-profiler/permissions-required-to-run-sql-server-profiler.md)   
 [SQL Server プロファイラーのテンプレートと権限](../../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md)   
 [[SQL Server Profiler]](../../tools/sql-server-profiler/sql-server-profiler.md)   
 [トレースと Windows パフォーマンス ログ データの関連付け &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/correlate-a-trace-with-windows-performance-log-data-sql-server-profiler.md)  
  
  
