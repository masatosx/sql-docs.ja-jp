---
title: "C から SQL へ: ビット |Microsoft ドキュメント"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- converting data from c to SQL types [ODBC], bit
- bit data type [ODBC]
- data conversions from C to SQL types [ODBC], bit
ms.assetid: 267c9fa9-599e-4ee6-b51b-0cae43f09183
caps.latest.revision: 7
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 8e7232773b97a66fc0b1b047e3fb8cc4212754f0
ms.contentlocale: ja-jp
ms.lasthandoff: 09/09/2017

---
# <a name="c-to-sql-bit"></a>C から SQL へ: ビット
ODBC C データ型の識別子です。  
  
 SQL_C_BIT  
  
 次の表は、ODBC SQL データ型のビット C のデータを変換することがありますを示します。 列とテーブルの用語の詳細については、次を参照してください。[に変換するデータを C から SQL データ型を](../../../odbc/reference/appendixes/converting-data-from-c-to-sql-data-types.md)です。  
  
|SQL 型の識別子|テスト|SQLSTATE|  
|-------------------------|----------|--------------|  
|SQL_CHAR SQL_VARCHAR<br /><br /> SQL_LONGVARCHAR<br /><br /> SQL_WCHAR SQL_WVARCHAR<br /><br /> SQL_WLONGVARCHAR|なし|n/a|  
|SQL_DECIMAL SQL_NUMERIC<br /><br /> SQL_TINYINT SQL_SMALLINT<br /><br /> SQL_INTEGER SQL_BIGINT<br /><br /> SQL_REAL 使用できます。<br /><br /> SQL_DOUBLE|なし|n/a|  
|SQL_BIT|なし|n/a|  
  
 ドライバーは、C データ型からデータを変換するときに長さ/インジケーター値を無視し、データ バッファーのサイズがビット C データ型のサイズであると見なされます。 長さ/インジケーター値に渡されます、 *StrLen_or_Ind*引数**SQLPutData**とで指定したバッファー内の*StrLen_or_IndPtr* で引数**SQLBindParameter**です。 データ バッファーを指定した、 *DataPtr*引数**SQLPutData**と*ParameterValuePtr*引数**SQLBindParameter**.