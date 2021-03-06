---
title: StartService メソッド (SqlService クラス) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- StartService Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- StartService method
ms.assetid: 83dfb6bd-dbd5-45d8-aad2-a11926317f91
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: d0a425bda3d32f19aca5be09dbb8ba4b7b6ac899
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "62911719"
---
# <a name="startservice-method-sqlservice-class"></a>StartService メソッド (SqlService クラス)
  サービスを開始状態にする動作を試行します。  
  
## <a name="syntax"></a>構文  
  
```  
  
object  
.StartService()  
  
```  
  
## <a name="parts"></a>要素  
 *object*  
 サービスを表す [SqlService クラス](sqlservice-class.md) オブジェクト。  
  
## <a name="property-valuereturn-value"></a>プロパティ値/戻り値  
 次のスタートアップ状態のうちの 1 つを指定する uint32 値。  
  
 0  
 正常終了しました。 要求が受け入れられました。  
  
 1  
 サポートされていません。 要求はサポートされていません。  
  
 2  
 アクセスが拒否されました。 ユーザーには適切なアクセス権がありませんでした。  
  
 3  
 依存サービス実行中。 そのサービスは、実行中の他のサービスが依存しているので停止できません。  
  
 4  
 無効なサービス コントロール。 要求された制御コードは有効でないか、またはサービスを受け入れ可能ではありません。  
  
 5  
 サービスは制御を受け付けられません。 サービスの状態 (Win32_BaseService:State) が 0、1、または 2 と等しいので、要求された制御コードはサービスに送信されませんでした。  
  
 6  
 サービスはアクティブではありません。 サービスは開始されていません。  
  
 7  
 サービス要求タイムアウト。 サービスは適切な時間内に開始要求に応答しませんでした。  
  
 8  
 不明なエラーです。 サービスの開始時に不明なエラーが発生しました。  
  
 9  
 パスが見つかりません。 サービス実行可能ファイルへのディレクトリ パスが見つかりませんでした。  
  
 10  
 サービスは既に実行中です。 サービスは既に実行されています。  
  
 11  
 サービス データベースはロックされています。 新しいサービスを追加するデータベースはロックされています。  
  
 12  
 サービス依存は削除されました。 このサービスが依存する依存関係はシステムから削除されました。  
  
 13  
 サービス依存エラー。 サービスは依存関係のあるサービスから必要なサービスを見つけられませんでした。  
  
 14  
 無効なサービス。 サービスはシステムから無効になっています。  
  
 15  
 サービス ログオンに失敗しました。 サービスにはシステムで実行するための正しい認証がありません。  
  
 16  
 サービスは削除をマークしました。 サービスはシステムから削除されています。  
  
 17  
 サービス スレッドなし。 サービスに実行スレッドがありません。  
  
 18  
 状態循環依存。 サービスの開始時に循環依存があります。  
  
 19  
 状態重複名。 同じ名前で実行中のサービスがあります。  
  
 20  
 状態無効名。 サービスの名前に有効ではない文字があります。  
  
 21  
 状態無効パラメーター。 有効ではないパラメーターがサービスに渡されました。  
  
 22  
 状態無効サービス アカウント。 このサービスを実行しようとしているアカウントは無効か、またはサービスを実行する権限がありません。  
  
 23  
 状態サービスが存在します。 サービスは、システムから利用できるサービスのデータベースにあります。  
  
 24  
 サービスは既に一時停止しています。 サービスは現在システムで一時停止されています。  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>参照  
 [サービスの開始および停止](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  
