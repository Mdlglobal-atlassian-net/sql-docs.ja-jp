---
title: dm_pdw_dms_workers (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 0a284d18-3c46-4ffa-bcc9-689e660ee8b4
author: ronortloff
ms.author: rortloff
monikerRange: '>= aps-pdw-2016 || = azure-sqldw-latest || = sqlallproducts-allversions'
ms.openlocfilehash: 6e5f295637db0e138caf324e3126707b9e0ea774
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "67899506"
---
# <a name="sysdm_pdw_dms_workers-transact-sql"></a>dm_pdw_dms_workers (Transact-sql)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md.md)]

  DMS ステップを完了するすべてのワーカーに関する情報を保持します。  
  
|列名|データ型|説明|範囲|  
|-----------------|---------------|-----------------|-----------|  
|request_id|**nvarchar(32)**|この DMS ワーカーが含まれているクエリ。<br /><br /> request_id、step_index、および dms_step_index は、このビューのキーを形成します。|『 [Transact-sql&#41;&#40;dm_pdw_exec_requests](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-requests-transact-sql.md)の request_id を参照してください。|  
|step_index|**int**|この DMS ワーカーが含まれているクエリステップ。<br /><br /> request_id、step_index、および dms_step_index は、このビューのキーを形成します。|『 [Transact-sql&#41;&#40;dm_pdw_request_steps](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-request-steps-transact-sql.md)の step_index を参照してください。|  
|dms_step_index|**int**|このワーカーが実行されている DMS プランのステップ。<br /><br /> request_id、step_index、および dms_step_index は、このビューのキーを形成します。||  
|pdw_node_id|**int**|ワーカーが実行されているノード。|『 [Transact-sql&#41;&#40;dm_pdw_nodes](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-nodes-transact-sql.md)の node_id を参照してください。|  
|distribution_id|**Int**|ワーカーが実行されているディストリビューション (存在する場合)。|『 [Transact-sql&#41;&#40;pdw_distributions](../../relational-databases/system-catalog-views/sys-pdw-distributions-transact-sql.md)の distribution_id を参照してください。|  
|型|**nvarchar(32)**|このエントリが表す DMS ワーカースレッドの種類。|' DIRECT_CONVERTER '、' DIRECT_READER '、' FILE_READER '、' HASH_CONVERTER '、' HASH_READER '、' ROUNDROBIN_CONVERTER '、' EXPORT_READER '、' EXTERNAL_READER '、' EXTERNAL_WRITER '、' PARALLEL_COPY_READER '、' REJECT_WRITER '、' WRITER '|  
|status|**nvarchar(32)**|DMS ワーカーの状態。|[!INCLUDE[ssInfoNA](../../includes/ssinfona-md.md)]|  
|bytes_per_sec|**bigint**|最後の1秒間に読み取りまたは書き込みのスループット。|0以上。 ワーカーが実行される前にクエリが取り消されたか失敗した場合は NULL です。|  
|bytes_processed|**bigint**|このワーカーによって処理された合計バイト数。|0以上。 ワーカーが実行される前にクエリが取り消されたか失敗した場合は NULL です。|  
|rows_processed|**bigint**|このワーカーに対して読み取りまたは書き込みが行った行の数。|0以上。 ワーカーが実行される前にクエリが取り消されたか失敗した場合は NULL です。|  
|start_time|**datetime**|このワーカーの実行が開始された時刻。|このワーカーが所属するクエリステップの開始時刻以上。 「 [Sys. dm_pdw_request_steps &#40;transact-sql&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-request-steps-transact-sql.md)」を参照してください。|  
|end_time|**datetime**|実行が終了した、失敗した、または取り消された時刻。|実行中またはキューに置かれたワーカーの場合は NULL です。 それ以外の場合は start_time より大きい。|  
|total_elapsed_time|**int**|実行に費やされた合計時間 (ミリ秒単位)。|0以上。<br /><br /> システムの開始または再起動からの経過時間の合計。 Total_elapsed_time が整数の最大値 (ミリ秒単位で24.8 日) を超えた場合、オーバーフローによる具体化エラーが発生します。<br /><br /> ミリ秒単位の最大値は24.8 日に相当します。|  
|cpu_time|**bigint**|このワーカーによって消費された CPU 時間 (ミリ秒単位)。|0以上。|  
|query_time|**int**|SQL がスレッドに行を返すまでの時間 (ミリ秒単位)。|0以上。|  
|buffers_available|**int**|未使用のバッファーの数。| ワーカーが実行される前にクエリが取り消されたか失敗した場合は NULL です。|  
|sql_spid|**int**|この DMS ワーカーの処理を実行している SQL Server インスタンスのセッション id。||  
|dms_cpid|**int**|実行中の実際のスレッドのプロセス ID。||  
|error_id|**nvarchar (36)**|このワーカーの実行中に発生したエラーの一意の識別子 (存在する場合)。|『 [Transact-sql&#41;&#40;dm_pdw_request_steps](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-request-steps-transact-sql.md)の error_id を参照してください。|  
|source_info|**nvarchar (4000)**|リーダーの場合は、ソーステーブルと列を指定します。||  
|destination_info|**nvarchar (4000)**|ライターの場合は、変換先テーブルを指定します。||  
  
 このビューで保持される最大行数の詳細については、「[容量制限](/azure/sql-data-warehouse/sql-data-warehouse-service-capacity-limits#metadata)」トピックの「メタデータ」セクションを参照してください。  
  
## <a name="see-also"></a>参照  
 [SQL Data Warehouse および並列データウェアハウスの動的管理ビュー &#40;Transact-sql&#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  
