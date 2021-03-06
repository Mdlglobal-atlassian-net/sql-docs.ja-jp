---
title: 型マッピングの編集 (DB2ToSQL) |Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: f93c4b7d-74fc-4856-bf42-035289918e83
author: Shamikg
ms.author: Shamikg
ms.openlocfilehash: 29669535f3544dafea58e7064e6d2c5281f6102f
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "67989700"
---
# <a name="edit-type-mapping-db2tosql"></a>型マッピングの編集 (DB2ToSQL)
[**型マッピングの編集**] ダイアログボックスでは、転送元データベースオブジェクトと転送先データベースオブジェクトの間で型がどのようにマップされるかを指定できます。  
  
このダイアログボックスには、いくつかの場所でアクセスできます。  
  
-   ソースデータベースまたはデータベースオブジェクトを選択すると、[**型マッピング**] タブがメタデータエクスプローラーの右側に表示されます。 [**追加**] をクリックして新しい型マッピングを追加するか、[**編集**] をクリックして既存の型マッピングを変更します。  
  
-   [**ツール**] メニューの [**プロジェクトの設定**] または [既定の**プロジェクトの設定**] をクリックします。 表示されるダイアログボックスで、[**型マッピング**] を選択します。 [**追加**] をクリックして新しい型マッピングを追加するか、[**編集**] をクリックして既存の型マッピングを変更します。  
  
テーブル固有の型マッピングは、データベースおよびプロジェクトの種類のマッピングをオーバーライドします。 データベース固有のマッピングは、プロジェクトのマッピングをオーバーライドします。  
  
## <a name="options"></a>オプション  
**ソースの種類**  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]データ型にマップするソースデータ型を選択します。  
  
データ型が可変長の場合、[**ソースの種類**] の下に次のフィールドが表示されます。  
  
**From**  
このマッピングの最小の長さを指定します。 たとえば、 **nchar**データ型の場合は、「10」と入力して、このマッピングが**nchar (10)** から始まる範囲になるように指定できます。  
  
**To**  
このマッピングの最大長を指定します。 たとえば、 **nchar**データ型の場合は、「20」と入力すると、このマッピングが**nchar (20)** で終わる範囲に対して指定されます。  
  
**変換後の型**  
変換元[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]のデータ型がマップされるデータ型を選択します。 SSMA に[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]よってテーブルまたはストアドプロシージャが作成されると、変換元のデータ型はこのデータ型に変更されます。  
  
データ型が可変長の場合、[**対象の型**] の下に次のフィールドが表示されます。  
  
**置換後の文字列**  
このマッピングの対象の長さを指定します。 たとえば、 **nvarchar**データ型の場合、「20」と入力すると、指定した変換元データ型を**nvarchar (20)** にマップするように指定できます。  
  
