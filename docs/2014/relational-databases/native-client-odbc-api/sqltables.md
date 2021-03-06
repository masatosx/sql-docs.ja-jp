---
title: SQLTables |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLTables function
ms.assetid: 77b6c15c-9cf7-4019-b3f0-3d27d23ef656
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 90ae76e10c4f9ceab4f7185de6448f6add944b5f
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48111493"
---
# <a name="sqltables"></a>SQLTables
  SQLTables は静的サーバー カーソルで実行できます。 SQLTables を更新可能な (動的またはキーセット) カーソルで実行するとは、カーソルの種類が変更されたことを示す SQL_SUCCESS_WITH_INFO を返します。  
  
 SQLTables からすべてのテーブルをレポートするデータベース、 *CatalogName*パラメーターが SQL_ALL_CATALOGS およびその他のすべてのパラメーターは、既定値 (NULL ポインター) を含めることができます。  
  
 SQLTables には、使用可能なカタログ、スキーマ、およびテーブル型を報告するため、空の文字列 (長さが 0 バイトのポインター) の特別な用途が。 空文字列は、既定値 (NULL ポインター) ではありません。  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC ドライバーでは、リンク サーバー上のテーブルに関する情報のレポートをサポートの 2 つの部分名をそのまま使用して、 *CatalogName*パラメーター: *Linked_Server_Name.Catalog_Name*.  
  
 SQLTables がテーブルの名前が一致をに関する情報を返します*TableName*現在のユーザーによって所有されているとします。  
  
## <a name="sqltables-and-table-valued-parameters"></a>SQLTables とテーブル値パラメーター  
 ステートメント属性 SQL_SOPT_SS_NAME_SCOPE が、既定値の SQL_SS_NAME_SCOPE_TABLE ではなく sql_ss_name_scope_table_type である場合、値、SQLTables はテーブル型に関する情報を返します。 SQLTables によって返される結果セットの列 4 でテーブル型に対して返される TABLE_TYPE 値は、テーブル型です。 SQL_SOPT_SS_NAME_SCOPE の詳細については、次を参照してください。 [SQLSetStmtAttr](sqlsetstmtattr.md)します。  
  
 テーブル、ビュー、およびシノニムは、テーブル型によって使用される名前空間とは異なる、共通の名前空間を共有します。 テーブルとビューを同じ名前にすることはできませんが、同じ名前のテーブルとテーブル型を同じカタログおよびスキーマ内に配置することはできます。  
  
 テーブル値パラメーターの詳細については、次を参照してください。[テーブル値パラメーター &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md)します。  
  
## <a name="example"></a>例  
  
```  
// Get a list of all tables in the current database.  
SQLTables(hstmt, NULL, 0, NULL, 0, NULL, 0, NULL,0);  
  
// Get a list of all tables in all databases.  
SQLTables(hstmt, (SQLCHAR*) "%", SQL_NTS, NULL, 0, NULL, 0, NULL,0);  
  
// Get a list of databases on the current connection's server.  
SQLTables(hstmt, (SQLCHAR*) "%", SQL_NTS, (SQLCHAR*)"", 0, (SQLCHAR*)"",  
    0, NULL, 0);  
```  
  
## <a name="see-also"></a>参照  
 [SQLTables 関数](http://go.microsoft.com/fwlink/?LinkId=59374)   
 [ODBC API 実装の詳細](odbc-api-implementation-details.md)  
  
  
