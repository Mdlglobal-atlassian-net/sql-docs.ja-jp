---
title: トレース データの再生
titleSuffix: SQL Server Distributed Replay
description: SQL Server 分散再生機能では、管理ツールの replay オプションを使用して、分散再生のイベント再生段階を開始します。
ms.custom: seo-lt-2019
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: 19ff5285-fb9d-4fd1-97c4-ec72c311c384
author: markingmyname
ms.author: maghan
ms.openlocfilehash: d03afc892fcdadbdaa346366096bec184707e70b
ms.sourcegitcommit: b8933ce09d0e631d1183a84d2c2ad3dfd0602180
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83152183"
---
# <a name="replay-trace-data"></a>トレース データの再生
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  入力トレース データが準備できたら、[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 分散再生機能を使用して、分散再生を開始できます。 詳細については、「 [入力トレース データの準備](../../tools/distributed-replay/prepare-the-input-trace-data.md)」を参照してください。  
  
 分散再生のイベント再生段階を開始するには、管理ツールの **replay** オプションを使用します。 この段階は、トレース データのディスパッチと、分散再生の開始および同期の 2 つの部分で構成されています。  
  
 ![イベントの分散再生](../../tools/distributed-replay/media/eventreplay.gif "イベントの分散再生")  
  
 トレース データは、2 つのシーケンス モード (ストレス モードまたは同期モード) のいずれかで再生できます。 既定の動作では、ストレス モードでトレース データを再生します。 イベント再生段階とシーケンス モードの詳細については、「 [SQL Server Distributed Replay](../../tools/distributed-replay/sql-server-distributed-replay.md)」を参照してください。  
  
> [!NOTE]  
>  入力トレース データは、Distributed Replay と互換性があるバージョンの [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] でキャプチャする必要があります。 また、入力トレース データは、トレース データを再生するターゲット サーバーと互換性がある必要があります。 バージョンの要件の詳細については、「 [Distributed Replay Requirements](../../tools/distributed-replay/distributed-replay-requirements.md)」を参照してください。  
  
### <a name="to-replay-the-trace"></a>トレースを再生するには  
  
1.  **(省略可能) 再生の構成設定を変更する**:シーケンス モード、各種のスケーリング値など、再生の構成設定を変更する場合は、XML ベースの再生構成ファイル `DReplay.exe.replay.config` の `<ReplayOptions>` 要素を変更する必要があります。 また、 `<OutputOptions>` 要素を変更すると、行数を記録するかどうかなどの出力設定を指定することもできます。 再生構成ファイルを変更する場合は、元のファイルではなく、コピーを変更することをお勧めします。 設定を変更するには、次の手順に従います。  
  
    1.  既定の再生構成ファイル `DReplay.exe.replay.config`のコピーを作成し、新しいファイルの名前を変更します。 既定の再生構成ファイルは管理ツールのインストール フォルダーにあります。  
  
    2.  新しい構成ファイル内の再生の構成設定を変更します。  
  
    3.  イベント再生段階 (次の手順) を開始するときに、 *replay* オプションの **config_file** パラメーターを使用して、変更した構成ファイルの場所を指定します。  
  
     再生構成ファイルの詳細については、「 [Distributed Replay の構成](../../tools/distributed-replay/configure-distributed-replay.md)」を参照してください。  
  
2.  **イベント再生段階を開始する**:分散再生を開始するには、**replay** オプションを使用して、管理ツールを実行する必要があります。 詳細については、「[replay オプション &#40;Distributed Replay 管理ツール&#41;](../../tools/distributed-replay/replay-option-distributed-replay-administration-tool.md)」を参照してください。  
  
    1.  Windows のコマンド プロンプト ユーティリティ (**CMD.exe**) を開き、Distributed Replay 管理ツール (**DReplay.exe**) のインストール場所に移動します。  
  
    2.  (省略可能) 管理ツールを実行するコンピューターとは別のコンピューター上でコントローラー サービスが実行されている場合、 *controller* パラメーター **-m**を使用して、コントローラーを指定します。  
  
    3.  *controller_working_directory* パラメーター **-d**を使用して、前処理段階でコントローラーに保存した中間ファイルの場所を指定します。  
  
    4.  (省略可能) **-o** パラメーターを使用して、各クライアントで再生アクティビティを結果のトレース ファイルにキャプチャします。  
  
    5.  (省略可能) *target_server* パラメーター **-s**を使用して、分散再生クライアントでトレース ワークロードを再生する [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] インスタンスを指定します。 `<Server>` 要素を使用して、再生構成ファイルの `<ReplayOptions>` 要素でターゲット サーバーを指定している場合、このパラメーターは必要ありません。  
  
    6.  *clients* パラメーター **-w**を使用して、再生に参加する分散再生クライアントを指定します。 クライアント コンピューター名はコンマで区切って指定します。 注:IP アドレスは指定できません。  
  
    7.  (省略可能) *config_file* パラメーター **-c**を使用して、再生構成ファイルの場所を指定します。 既定の再生構成ファイルのコピーを変更した場合は、このパラメーターを使用して、新しい構成ファイルを指定します。  
  
    8.  (省略可能) *status_interval* パラメーター **-f**を使用して、30 秒以外の周期で状態メッセージを表示するかどうかを指定します。  
  
     たとえば、次の構文では、コントローラー サービスと同じコンピューターで再生段階を開始し、 `c:\WorkingDir`にあるコントローラー作業ディレクトリを使用し、参加している各クライアントで再生アクティビティをキャプチャして、クライアント `client1` と `client2` を使用して再生を実行し、残りの再生の構成設定を `c:\modifiedreplay.config`にある変更済みの再生構成ファイルから取得します。  
  
     `dreplay replay -d c:\WorkingDir -o -w client1,client2 -c c:\modifiedreplay.config`  
  
3.  分散再生が終了すると、管理ツールから概要情報が返されます。 **-o** オプションを指定した場合、各クライアントで再生アクティビティが結果のトレース ファイルに保存されます。 結果のトレース ファイルの詳細については、「 [再生結果の確認](../../tools/distributed-replay/review-the-replay-results.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [Distributed Replay Requirements](../../tools/distributed-replay/distributed-replay-requirements.md)   
 [管理ツール コマンド ライン オプション &#40;Distributed Replay Utility&#41;](../../tools/distributed-replay/administration-tool-command-line-options-distributed-replay-utility.md)   
 [分散再生の構成](../../tools/distributed-replay/configure-distributed-replay.md)  
  
  
