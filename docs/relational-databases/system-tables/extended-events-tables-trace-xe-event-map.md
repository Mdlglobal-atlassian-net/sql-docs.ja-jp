---
title: trace_xe_event_map (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- trace_xe_event_map_TSQL
- trace_xe_event_map
dev_langs:
- TSQL
helpviewer_keywords:
- trace_xe_event_map
- extended events [SQL Server], tables
ms.assetid: 537aa292-3540-47e8-be28-56dc01abc343
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8f3908fb257b761d5bee12aec07141b191e0328e
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82806329"
---
# <a name="extended-events-tables---trace_xe_event_map"></a>拡張イベント テーブル - trace_xe_event_map
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  SQL トレース イベント クラスに割り当てられている拡張イベントのイベントごとに 1 行のデータを格納します。 このテーブルは、sys スキーマの master データベースに格納されます。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|trace_event_id|**smallint**|マップされている SQL トレース イベント クラスの ID。|  
|package_name|**nvarchar(60)**|マップされたイベントが存在する拡張イベントパッケージの名前です。|  
|xe_event_name|**nvarchar(60)**|SQL トレースイベントクラスにマップされる拡張イベントイベントの名前です。|  
  
## <a name="remarks"></a>Remarks  
 次のクエリを使用すると、SQL トレース イベント クラスと同様の拡張イベントを特定できます。  
  
```  
SELECT te.name, xe.package_name, xe.xe_event_name  
FROM sys.trace_events AS te  
LEFT JOIN sys.trace_xe_event_map AS xe  
   ON te.trace_event_id = xe.trace_event_id  
WHERE xe.trace_event_id IS NOT NULL  
```  
  
 すべてのイベント クラスに同等の拡張イベントが存在するとは限りません。 次のクエリを使用すると、拡張イベントと同様ではないイベント クラスの一覧を表示できます。  
  
```  
SELECT te.trace_event_id, te.name  
FROM sys.trace_events AS te  
LEFT JOIN sys.trace_xe_event_map AS xe  
   ON te.trace_event_id = xe.trace_event_id  
WHERE xe.trace_event_id IS NULL  
```  
  
 前のクエリでは、返されるイベント クラスのほとんどは、監査に関係しています。 監査には [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 監査を使用することをお勧めします。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 監査では、拡張イベントを使用して監査を作成します。 詳しくは、「[SQL Server Audit &#40;データベース エンジン&#41;](../../relational-databases/security/auditing/sql-server-audit-database-engine.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [trace_xe_action_map &#40;Transact-SQL&#41;](../../relational-databases/system-tables/extended-events-tables-trace-xe-action-map.md)  
  
  
