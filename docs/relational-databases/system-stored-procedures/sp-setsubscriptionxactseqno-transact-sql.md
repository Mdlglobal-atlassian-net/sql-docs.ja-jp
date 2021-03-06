---
title: sp_setsubscriptionxactseqno (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_setsubscriptionxactseqno
- sp_setsubscriptionxactseqno_TSQL
helpviewer_keywords:
- sp_setsubscriptionxactseqno
ms.assetid: cdb4e0ba-5370-4905-b03f-0b0c6f080ca6
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 60d27260378a8f0d6706b85ea02232ffca6a05c8
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82827498"
---
# <a name="sp_setsubscriptionxactseqno-transact-sql"></a>sp_setsubscriptionxactseqno (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  トラブルシューティング中に、ログシーケンス番号 (LSN) を使用して最後に配信されたトランザクションを指定し、ディストリビューションエージェントが次のトランザクションで配信を開始できるようにするために使用します。 再起動すると、ディストリビューションエージェントによって、ディストリビューションデータベースキャッシュ (msrepl_commands) からこのウォーターマーク (LSN) を超えるトランザクションが返されます。 このストアドプロシージャは、サブスクライバー側のサブスクリプションデータベースで実行されます。 SQL Server 以外のサブスクライバーではサポートされていません。  
  
> [!CAUTION]  
>  このストアドプロシージャを誤って使用するか、正しくない LSN 値を指定すると、ディストリビューションエージェントがサブスクライバーで既に適用されている変更を元に戻したり、残りの変更をすべてスキップしたりする可能性があります。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sp_setsubscriptionxactseqno [ @publisher = ] 'publisher'  
        , [ @publisher_db = ] 'publisher_db'  
        , [ @publication = ] 'publication'  
        , [ @xact_seqno = ] xact_seqno   
```  
  
## <a name="arguments"></a>引数  
`[ @publisher = ] 'publisher'`パブリッシャーの名前を指定します。 *publisher*は**sysname**で、既定値はありません。  
  
`[ @publisher_db = ] 'publisher_db'`パブリケーションデータベースの名前を指定します。 *publisher_db*は**sysname**であり、既定値はありません。 SQL Server 以外のパブリッシャーの場合、 *publisher_db*はディストリビューションデータベースの名前です。  
  
`[ @publication = ] 'publication'`パブリケーションの名前を指定します。 *publication*は**sysname**,、既定値はありません。 ディストリビューションエージェントが複数のパブリケーションによって共有されている場合は、 *publication*に ALL を指定する必要があります。  
  
`[ @xact_seqno = ] xact_seqno`サブスクライバーで適用される、ディストリビューターの次のトランザクションの LSN を指定します。 *xact_seqno*は**varbinary (16)**,、既定値はありません。  
  
## <a name="result-set"></a>結果セット  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**ORIGINAL XACT_SEQNO**|**varbinary(16)**|サブスクライバーで適用される次のトランザクションの元の LSN。|  
|**UPDATED XACT_SEQNO**|**varbinary(16)**|サブスクライバー側で適用される次のトランザクションの、更新された LSN。|  
|**SUBSCRIPTION STREAM COUNT**|**int**|最後の同期中に使用されたサブスクリプション ストリームの数。|  
  
## <a name="return-code-values"></a>リターン コードの値  
 **0** (成功) または**1** (失敗)  
  
## <a name="remarks"></a>Remarks  
 **sp_setsubscriptionxactseqno**は、トランザクションレプリケーションで使用します。  
  
 **sp_setsubscriptionxactseqno**は、ピアツーピアトランザクションレプリケーショントポロジでは使用できません。  
  
 **sp_setsubscriptionxactseqno**を使用すると、サブスクライバーで適用されるときにエラーの原因となっている特定のトランザクションをスキップできます。 エラーが発生し、ディストリビューションエージェントが停止した後、ディストリビューターで[transact-sql&#41;を &#40;sp_helpsubscriptionerrors](../../relational-databases/system-stored-procedures/sp-helpsubscriptionerrors-transact-sql.md)を呼び出して、失敗したトランザクションの xact_seqno 値を取得し、 **sp_setsubscriptionxactseqno を呼び出して**、この値を*xact_seqno*に渡します。 こうすると、この LSN より後のコマンドだけが処理されます。  
  
 ディストリビューションデータベース内の保留中のすべてのコマンドをサブスクライバーに配信するには、 *xact_seqno*に値**0**を指定します。  
  
 ディストリビューションエージェントがマルチサブスクリプションストリームを使用していると**sp_setsubscriptionxactseqno**が失敗することがあります。  
  
 このエラーが発生した場合は、1つのサブスクリプションストリームでディストリビューションエージェントを実行する必要があります。 詳細については、「 [Replication Distribution Agent](../../relational-databases/replication/agents/replication-distribution-agent.md)」を参照してください。  
  
## <a name="permissions"></a>アクセス許可  
 **Sp_setsubscriptionxactseqno**を実行できるのは、固定サーバーロール**sysadmin**または固定データベースロール**db_owner**のメンバーだけです。  
  
## <a name="see-more"></a>詳細情報

[ブログ: トランザクションをスキップする方法](https://repltalk.com/2019/05/28/how-to-skip-a-transaction/)  
