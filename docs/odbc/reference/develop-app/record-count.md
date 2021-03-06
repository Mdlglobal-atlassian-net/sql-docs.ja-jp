---
title: レコード数 |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- record count [ODBC]
- descriptors [ODBC], record count
ms.assetid: 46eec3cc-0ecc-4980-9020-fb74a9af5730
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 28e503ae4602d87fc9138ed018ee1e95f135ec57
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "81281818"
---
# <a name="record-count"></a>レコード カウント
記述子の SQL_DESC_COUNT header フィールドは、データを格納する最大番号のレコードの1から始まるインデックスです。 このフィールドは、バインドされているすべての列またはパラメーターの数ではありません。 記述子が割り当てられると、SQL_DESC_COUNT の初期値は0になります。  
  
 ドライバーは、記述子情報を保持するために必要なすべてのストレージを割り当て、維持するために必要なアクションを実行します。 アプリケーションでは、記述子のサイズを明示的に指定したり、新しいレコードを割り当てたりすることはありません。 数値が SQL_DESC_COUNT の値よりも大きい記述子レコードの情報がアプリケーションによって提供されると、ドライバーは自動的に SQL_DESC_COUNT を増やします。 アプリケーションが一番大きい番号の記述子レコードをバインド解除すると、ドライバーは、残りの最大のレコード数を含むように、SQL_DESC_COUNT を自動的に減らします。
