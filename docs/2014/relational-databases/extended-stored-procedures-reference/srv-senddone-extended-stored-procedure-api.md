---
title: srv_senddone (拡張ストアド プロシージャ API) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_senddone
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_senddone
ms.assetid: 1fc4f1d5-56d4-43f6-b5e4-0c0cc295cba3
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 2bce064ee38082861e9b6c5d4f2c6e28bf41dded
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "62745523"
---
# <a name="srv_senddone-extended-stored-procedure-api"></a>srv_senddone (拡張ストアド プロシージャ API)
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]代わりに CLR Integration をご使用ください。  
  
 結果完了メッセージをクライアントに送信します。  
  
## <a name="syntax"></a>構文  
  
```  
  
int srv_senddone (  
SRV_PROC *  
srvproc  
,  
DBUSMALLINT   
status  
,  
DBUSMALLINT  
info  
,  
DBINT  
count   
);  
  
```  
  
## <a name="arguments"></a>引数  
 *srvproc*  
 特定のクライアント接続のためのハンドル (この場合は、言語要求を受け取るハンドル) である SRV_PROC 構造体を指すポインターです。 この構造体には、アプリケーションとクライアントの間の通信やデータを管理するために、拡張ストアド プロシージャ API ライブラリで使用する情報が格納されます。  
  
 *status*  
 各種の *status* フラグに使用する 2 バイトのフィールドです。 *status* フラグの値に AND 論理演算子や OR 論理演算子を使用することにより、複数のフラグを設定できます。 次の表は、使用可能な *status* フラグを示しています。  
  
|status フラグ|説明|  
|-----------------|-----------------|  
|SRV_DONE_COUNT|*count* パラメーターに有効なカウントを格納します。|  
|SRV_DONE_ERROR|現在のクライアント コマンドがエラーを受け取ったことを示します。|  
  
 *インフォメーション*  
 2 バイトの予約フィールドです。 この値は 0 に設定します。  
  
 *count*  
 現在の結果セットに対するカウントを示す 4 バイト フィールドです。 *status* フィールドに SRV_DONE_COUNT フラグを設定した場合、*count* には有効なカウントが格納されます。  
  
## <a name="returns"></a>戻り値  
 SUCCEED または FAIL を返します。  
  
## <a name="remarks"></a>Remarks  
 サーバーは 1 つのクライアント要求から、複数のコマンドを実行して複数の結果セットを返すことができます。 **srv_senddone** は、各結果セットに対して結果完了メッセージをクライアントに返す必要があります。  
  
 *count* フィールドは、コマンドの影響を受ける行数を示します。 *count* フィールドにカウントが格納されている場合は、*status* フィールドに SRV_DONE_COUNT フラグを設定する必要があります。 この設定により、*count* の値が 0 かどうか、*count* フィールドが使用されていないのかをクライアントが区別できるようになります。  
  
 **srv_senddone** を SRV_CONNECT ハンドラーから呼び出さないでください。  
  
> [!IMPORTANT]  
>  拡張ストアド プロシージャのソース コードを十分に確認し、コンパイル済み DLL を、運用サーバーにインストールする前にテストする必要があります。 セキュリティの確認およびテストについて詳しくは、[Microsoft の Web サイト](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/)をご覧ください。  
  
  
