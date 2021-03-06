---
title: sp_delete_backuphistory (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_delete_backuphistory
- sp_delete_backuphistory_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_delete_backuphistory
ms.assetid: bdb56834-616e-47e4-b942-e895d2325e97
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: afaf4166facc16e7582f3978f3806d8d5a68fb0e
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82831276"
---
# <a name="sp_delete_backuphistory-transact-sql"></a>sp_delete_backuphistory (Transact-sql)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  指定した日付より古いバックアップセットのエントリを削除することにより、バックアップと復元の履歴テーブルのサイズを小さくします。 バックアップまたは復元の各操作が実行された後、バックアップと復元の履歴テーブルに追加の行が追加されます。そのため、 **sp_delete_backuphistory**を定期的に実行することをお勧めします。  
  
> [!NOTE]  
>  バックアップと復元の履歴テーブルは、 **msdb**データベースに格納されています。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sp_delete_backuphistory [ @oldest_date = ] 'oldest_date'   
```  
  
## <a name="arguments"></a>引数  
`[ @oldest_date = ] 'oldest\_date'`バックアップと復元の履歴テーブルに保持されている最も古い日付です。 *oldest_date*は**datetime**,、既定値はありません。  
  
## <a name="return-code-values"></a>リターン コードの値  
 0 (成功) または 1 (失敗)  
  
## <a name="result-sets"></a>結果セット  
 なし  
  
## <a name="remarks"></a>解説  
 **sp_delete_backuphistory**は**msdb**データベースから実行する必要があり、次のテーブルに影響します。  
  
-   [backupfile](../../relational-databases/system-tables/backupfile-transact-sql.md)  
  
-   [backupfilegroup](../../relational-databases/system-tables/backupfilegroup-transact-sql.md)  
  
-   [backupmediafamily](../../relational-databases/system-tables/backupmediafamily-transact-sql.md)  
  
-   [backupmediaset](../../relational-databases/system-tables/backupmediaset-transact-sql.md)  
  
-   [backupset](../../relational-databases/system-tables/backupset-transact-sql.md)  
  
-   [restorefile](../../relational-databases/system-tables/restorefile-transact-sql.md)  
  
-   [restorefilegroup](../../relational-databases/system-tables/restorefilegroup-transact-sql.md)  
  
-   [restorehistory](../../relational-databases/system-tables/restorehistory-transact-sql.md)  
  
 すべての履歴を削除しても、物理的なバックアップ ファイルは維持されます。  
  
## <a name="permissions"></a>アクセス許可  
 **Sysadmin**固定サーバーロールのメンバーシップが必要ですが、他のユーザーに権限を与えることができます。  
  
## <a name="examples"></a>使用例  
 次の例では、バックアップと復元の履歴テーブルから 2010 年 1 月 14 日の午前 12 時 より前のすべてのエントリを削除します。  
  
```  
USE msdb;  
GO  
EXEC sp_delete_backuphistory @oldest_date = '01/14/2010';  
```  
  
## <a name="see-also"></a>参照  
 [sp_delete_database_backuphistory &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sp-delete-database-backuphistory-transact-sql.md)   
 [バックアップの履歴とヘッダーの情報 &#40;SQL Server&#41;](../../relational-databases/backup-restore/backup-history-and-header-information-sql-server.md)  
  
  
