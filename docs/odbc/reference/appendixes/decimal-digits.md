---
title: 10進数 |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- size of data types [ODBC]
- decimal digits of data types [ODBC]
- data types [ODBC], decimal digits
- SQL data types [ODBC], column characteristics
ms.assetid: 07f3d1fc-b4ee-4693-b342-330b2231b6d0
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 4921a6162b6d711e657f223b5be5783dfa37bca8
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "81285162"
---
# <a name="decimal-digits"></a>10 進数字
Decimal および numeric データ型の*小数点*以下桁数は、小数点の右側の最大桁数、またはデータの小数点以下桁数として定義されます。 浮動小数点数の概数列またはパラメーターの場合、小数点の右側の桁数が固定されていないため、小数点以下桁数が定義されていません。 秒の部分を含む datetime または interval データの場合、小数点以下の桁数は、データの秒部分の小数点の右側の桁数として定義されます。  
  
 データ型の SQL_DECIMAL と SQL_NUMERIC では、通常、最大小数点以下桁数は最大有効桁数と同じです。 ただし、データソースによっては、最大スケールに対して個別の制限が課される場合があります。 データ型に対して許可されるスケールの最小値と最大値を決定するために、アプリケーションは**SQLGetTypeInfo**を呼び出します。  
  
 次の表に、各簡潔な SQL データ型に対して定義されている10進数字を示します。  
  
|SQL 型|数字|  
|--------------|--------------------|  
|すべての文字型とバイナリ型 [a]|該当なし|  
|SQL_DECIMAL<br />SQL_NUMERIC|小数点の右側に定義されている桁数。 たとえば、NUMERIC (10, 3) として定義された列の小数点以下桁数は3です。 指数表記を使用せずに非常に大きな数値の格納をサポートするには、負の数値を指定できます。たとえば、"12000" は、小数点以下桁数が3の "12" として格納できます。|  
|SQL_DECIMAL と SQL_NUMERIC 以外のすべての数値型 [a]|0|  
|すべての概数データ型 [a]|該当なし|  
|SQL_TYPE_DATE、および秒の部分を持たないすべての期間の種類 [a]|該当なし|  
|SQL_TYPE_DATE を除くすべての datetime 型と、秒コンポーネントを含むすべての期間型|値の秒部分の小数点の右側の桁数 (秒の小数部)。 この数値を負の値にすることはできません。|  
|SQL_GUID|該当なし|  
  
 [a] このデータ型では、 **SQLBindParameter**の*DecimalDigits*引数は無視されます。  
  
 10進数に対して返される値は、1つの記述子フィールドの値に対応していません。 値は、次の表に示すように、データ型に応じて、SQL_DESC_SCALE または SQL_DESC_PRECISION のいずれかのフィールドから取得できます。  
  
|SQL 型|に対応する記述子フィールド<br /><br /> 10進数|  
|--------------|----------------------------------------------------------|  
|すべての文字型とバイナリ型|該当なし|  
|すべての真数型|SCALE|  
|SQL_BIT|該当なし|  
|すべての概数型|該当なし|  
|すべての datetime 型|PRECISION|  
|秒のコンポーネントを含むすべての期間の種類|PRECISION|  
|秒の部分を持たないすべての期間の種類|該当なし|
