---
title: C から SQL データ型にデータを変換する |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- converting data from c to SQL types [ODBC], about converting
- converting data from c to SQL types [ODBC]
- data conversions from C to SQL types [ODBC], about converting
- data types [ODBC], C data types
- data types [ODBC], converting data
- SQL data types [ODBC], converting from C types
- data types [ODBC], SQL data types
- data conversions from C to SQL types [ODBC]
- C data types [ODBC], converting to SQL types
ms.assetid: ee0afe78-b58f-4d34-ad9b-616bb23653bd
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 0f68b53dd77305163aa2595c60a1994a13bb9964
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47793810"
---
# <a name="converting-data-from-c-to-sql-data-types"></a>C から SQL データ型へのデータ変換
アプリケーションを呼び出すと**SQLExecute**または**SQLExecDirect**にバインドされているすべてのパラメーターのデータを取り出します**SQLBindParameter**記憶域の場所からアプリケーションです。 アプリケーションを呼び出すと**SQLSetPos**、ドライバーのデータの更新プログラムを取得または追加操作を使用してバインドされた列から**SQLBindCol**します。 アプリケーションを実行時データ パラメーターの場合にでパラメーター データを送信します**SQLPutData**します。 かどうか、必要に応じて、ドライバーのデータを変換で指定されたデータ型、 *ValueType*引数**SQLBindParameter**データ型を指定する、 *ParameterType*引数**SQLBindParameter**、し、データ ソースにデータを送信します。  
  
 次の表は、ODBC C からサポートされている変換にデータ型を ODBC SQL データ型を示します。 塗りつぶされた円は、SQL データ型の既定の変換を示します (元のデータは変換するときに、C データ型の値*ValueType* SQL_DESC_CONCISE_TYPE の記述子フィールドは SQL_C_DEFAULT または)。 白抜きの円では、サポートされている変換を示します。  
  
 変換後のデータの形式は、Windows® 国設定の影響を受けません。  
  
 ![変換がサポートされています SQL データ型を ODBC C](../../../odbc/reference/appendixes/media/apd1b.gif "apd1b。")  
  
 次のセクションでの表では、ドライバーまたはデータ ソースがデータ ソースに送信されるデータに変換する方法について説明しますすべての ODBC C データ型からそれらをサポートする ODBC SQL データ型への変換をサポートするためには、ドライバーが必要です。 テーブルの最初の列の特定の ODBC C データ型の有効な入力値を一覧表示、 *ParameterType*引数**SQLBindParameter**します。 2 番目の列には、データを変換できるかどうかを判断するドライバーを実行するテストの結果が表示されます。 3 番目の列の一覧の各結果によって返される SQLSTATE **SQLExecDirect**、 **SQLExecute**、 **SQLBulkOperations**、 **SQLSetPos**、または**SQLPutData**します。 データは、SQL_SUCCESS が返された場合にのみ、データ ソースに送信されます。  
  
 場合、 *ParameterType*引数**SQLBindParameter**特定の C データ型のテーブルに表示されていない ODBC SQL データ型の識別子を含む**SQLBindParameter**SQLSTATE 07006 が返されます (制限付きのデータ型は属性の違反)。 場合、 *ParameterType*引数には、ドライバー固有の識別子が含まれ、ドライバーでは、特定の ODBC C データ型からそのドライバー固有の SQL データ型への変換をサポートしていない**SQLBindParameter** SQLSTATE HYC00 を返します (省略可能な機能が実装されていません)。  
  
 場合、 *ParameterValuePtr*と*StrLen_or_IndPtr*で指定された引数**SQLBindParameter**はどちらも null ポインター、関数は、SQLSTATE HY009 を返します (が無効ですnull ポインターの) 使用します。 アプリケーションが指す長さ/インジケーター バッファーの値を設定してテーブルには表示されません、 *StrLen_or_IndPtr*の引数**SQLBindParameter**の値は、 *StrLen_or_IndPtr*の引数**SQLPutData** SQL_NULL_DATA NULL SQL データ値を指定します。 (、 *StrLen_or_IndPtr*引数 APD の SQL_DESC_OCTET_LENGTH_PTR フィールドに対応します)。アプリケーションこれらの値に設定 SQL_NTS ことを指定する値\* *ParameterValuePtr*で**SQLBindParameter**または\* *DataPtr*で**SQLPutData** (APD の SQL_DESC_DATA_PTR フィールドによって示される) は、null で終わる文字列。  
  
 次の用語は、テーブルで使用されます。  
  
-   **データのバイト長**— データ ソースに送信される前に、データは切り捨てられますかどうか、データ ソースに送信する使用可能な SQL データのバイト数。 文字列データは、これに null 終端文字のための領域は含まれません。  
  
-   **列のバイト長**— データ ソースでデータを格納するために必要なバイト数。  
  
-   **バイトの長さを文字**— 文字形式でデータを表示するために必要なバイトの最大数。 これでの SQL データ型ごとに定義されている[表示サイズ](../../../odbc/reference/appendixes/display-size.md)バイト長の文字が文字では、表示サイズ、(バイト単位) はを除き、します。  
  
-   **桁数**— (必要な場合)、マイナス記号、小数点、指数部を含む、数値を表すために使用する文字数。  
  
-   **内の単語**   
     ***斜体***— SQL 文法の要素。 文法要素の構文を参照してください。[付録 c: SQL の文法](../../../odbc/reference/appendixes/appendix-c-sql-grammar.md)します。  
  
 このセクションでは、次のトピックを扱います。  
  
-   [C から SQL へ: 文字](../../../odbc/reference/appendixes/c-to-sql-character.md)  
  
-   [C から SQL へ: 数値](../../../odbc/reference/appendixes/c-to-sql-numeric.md)  
  
-   [C から SQL へ: ビット](../../../odbc/reference/appendixes/c-to-sql-bit.md)  
  
-   [C から SQL へ: バイナリ](../../../odbc/reference/appendixes/c-to-sql-binary.md)  
  
-   [C から SQL へ: 日付](../../../odbc/reference/appendixes/c-to-sql-date.md)  
  
-   [C から SQL へ: GUID](../../../odbc/reference/appendixes/c-to-sql-guid.md)  
  
-   [C から SQL へ: 時刻](../../../odbc/reference/appendixes/c-to-sql-time.md)  
  
-   [C から SQL へ: タイムスタンプ](../../../odbc/reference/appendixes/c-to-sql-timestamp.md)  
  
-   [C から SQL へ: 年月の間隔](../../../odbc/reference/appendixes/c-to-sql-year-month-intervals.md)  
  
-   [C から SQL へ: 日付と時刻の間隔](../../../odbc/reference/appendixes/c-to-sql-day-time-intervals.md)  
  
-   [C から SQL へのデータ変換の例](../../../odbc/reference/appendixes/c-to-sql-data-conversion-examples.md)
