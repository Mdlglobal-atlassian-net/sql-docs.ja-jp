---
title: sp_helptracertokens (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_helptracertokens
- sp_helptracertokens_TSQL
helpviewer_keywords:
- sp_helptracertokens
ms.assetid: 61f27234-531d-4b37-8fa3-fe4c32e6f521
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b04bf618bccb5d4d49724e0b62f03ba193dc0f2a
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82826043"
---
# <a name="sp_helptracertokens-transact-sql"></a>sp_helptracertokens (Transact-SQL)
[!INCLUDE[appliesto-ss-asdbmi-xxxx-xxx-md](../../includes/appliesto-ss-asdbmi-xxxx-xxx-md.md)]

  待機時間を決定するためにパブリケーションに挿入されたトレーサートークンごとに1行の値を返します。 このストアドプロシージャは、パブリッシャー側でパブリケーションデータベースに対して、またはディストリビューター側でディストリビューションデータベースに対して実行されます。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sp_helptracertokens [ @publication = ] 'publication'   
    [ , [ @publisher = ] 'publisher' ]   
    [ , [ @publisher_db = ] 'publisher_db' ]  
```  
  
## <a name="arguments"></a>引数  
`[ @publication = ] 'publication'`トレーサートークンが挿入されたパブリケーションの名前を指定します。 *publication*は**sysname**,、既定値はありません。  
  
`[ @publisher = ] 'publisher'`パブリッシャーの名前です。 *publisher*は**sysname**で、既定値は NULL です。  
  
> [!NOTE]
>  このパラメーターは、以外のパブリッシャーに対してのみ指定する必要があり [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ます。  
  
`[ @publisher_db = ] 'publisher_db'`パブリケーションデータベースの名前です。 *publisher_db*は**sysname**で、既定値は NULL です。 ストアドプロシージャがパブリッシャーで実行される場合、このパラメーターは無視されます。  
  
## <a name="result-set"></a>結果セット  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**tracer_id**|**int**|トレーサートークンレコードを識別します。|  
|**publisher_commit**|**datetime**|パブリッシャーでパブリケーション データベースにトークン レコードがコミットされた日付と時刻です。|  
  
## <a name="return-code-values"></a>リターン コードの値  
 **0** (成功) または**1** (失敗)  
  
## <a name="remarks"></a>Remarks  
 **sp_helptracertokens**は、トランザクションレプリケーションで使用します。  
  
 **sp_helptracertokens**は[、transact-sql&#41;&#40;sp_helptracertokenhistory](../../relational-databases/system-stored-procedures/sp-helptracertokenhistory-transact-sql.md)実行するときにトレーサートークン id を取得するために使用されます。  
  
## <a name="example"></a>例  
 [!code-sql[HowTo#sp_tracertokens](../../relational-databases/replication/codesnippet/tsql/sp-helptracertokens-tran_1.sql)]  
  
## <a name="permissions"></a>アクセス許可  
 **Sp_helptracertokenhistory**を実行できるのは、 **sysadmin**固定サーバーロールのメンバー、パブリケーションデータベースの固定データベースロール**db_owner** 、またはディストリビューションデータベースの**db_owner**固定データベースロールまたは**replmonitor**ロールのメンバーだけです。  
  
## <a name="see-also"></a>参照  
 [トランザクションレプリケーションの待機時間を計測して接続を検証する](../../relational-databases/replication/monitor/measure-latency-and-validate-connections-for-transactional-replication.md)   
 [sp_deletetracertokenhistory &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sp-deletetracertokenhistory-transact-sql.md)  
  
  
