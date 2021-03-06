---
title: ドライバー マネージャーは |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- driver manager [ODBC], backward compatibility
- compatibility [ODBC], driver manager
- ODBC driver manager [ODBC]
- backward compatibility [ODBC], driver manager
ms.assetid: 57f65c38-d9ee-46c8-9051-128224a582c6
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 4fa53595d304dc8200805a98491a824cf52a1bbb
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47639130"
---
# <a name="what-the-driver-manager-does"></a>ドライバー マネージャーの機能
次の表にまとめたものですか ODBC 3 *.x*ドライバー マネージャーは、ODBC 2 への呼び出しをマップします *。x*および ODBC 3 *.x*ドライバー。  
  
|関数または<br /><br /> ステートメント属性|コメント|  
|-----------------------------------------|--------------|  
|SQL_ATTR_FETCH_BOOKMARK_PTR|使用したブックマークを指す**SQLFetchScroll**します。 次に、実装の詳細を示します。<br /><br /> -設定した場合、アプリケーションこれで、ODBC 2。*x*ドライバー、ODBC 3 *.x*ドライバー マネージャーは、それをキャッシュします。 ポインターを逆参照し、値を ODBC 2 に渡します。*x*ドライバー、 *FetchOffset*の引数**SQLExtendedFetch**とき**SQLFetchScroll**は、後で、アプリケーションによって呼び出されます。<br />場合、ODBC 3 でのアプリケーション設定この *.x*ドライバー、ODBC 3 *.x*ドライバー マネージャーがドライバーに呼び出しを渡します。|  
|SQL_ATTR_ROW_STATUS_PTR|埋められた行の状態配列を指す**SQLFetch**、 **SQLFetchScroll**、 **SQLBulkOperations**、および**SQLSetPos**します。 次に、実装の詳細を示します。<br /><br /> -設定した場合、アプリケーションこれで、ODBC 2。*x*ドライバー、ODBC 3 *.x*ドライバー マネージャーは、その値をキャッシュします。 ODBC 2 に、この値を渡します。*x*ドライバー、 *RowStatusArray*の引数**SQLExtendedFetch**とき**SQLFetchScroll**または**SQLFetch**が呼び出されます。<br />場合、ODBC 3 でのアプリケーション設定この *.x*ドライバー、ODBC 3 *.x*ドライバー マネージャーがドライバーに呼び出しを渡します。<br />状態の場合は、アプリケーション設定し、SQL_ATTR_ROW_STATUS_PTR とを呼び出して、S6 で**SQLBulkOperations** (で、*操作*SQL_ADD の) または**SQLSetPos**最初に呼び出さず**SQLFetch**または**SQLFetchScroll**、SQLSTATE HY011 (属性はここで設定することはできません) が返されます。|  
|SQL_ATTR_ROWS_FETCHED_PTR|バッファーを指す**SQLFetch**と**SQLFetchScroll**フェッチされた行の数を返します。 次に、実装の詳細を示します。<br /><br /> -設定した場合、アプリケーションこれで、ODBC 2。*x*ドライバー、ODBC 3 *.x*ドライバー マネージャーは、その値をキャッシュします。 ODBC 2 に、この値を渡します。*x*ドライバー、 *RowCountPtr*の引数**SQLExtendedFetch**とき**SQLFetch**または**SQLFetchScroll**はアプリケーションによって呼び出されます。<br />場合、ODBC 3 でのアプリケーション設定この *.x*ドライバー、ODBC 3 *.x*ドライバー マネージャーがドライバーに呼び出しを渡します。|  
|SQL_ATTR_ROW_ARRAY_SIZE|行セットのサイズを設定します。 次に、実装の詳細を示します。<br /><br /> -設定した場合、アプリケーションこれで、ODBC 2。*x*ドライバー、ODBC 3 *.x*ドライバー マネージャーが、SQL_ROWSET_SIZE ステートメント属性にマップします。<br />場合、ODBC 3 でのアプリケーション設定この *.x*ドライバー、ODBC 3 *.x*ドライバー マネージャーがドライバーに呼び出しを渡します。<br />場合、ODBC 3 の操作をアプリケーション *.x*ドライバー呼び出し**SQLSetScrollOptions**の値に設定されている SQL_ROWSET_SIZE、*複合カーソル*引数場合、基になります。ドライバーがサポートしていない**SQLSetScrollOptions**します。|  
|SQL_ROWSET_SIZE|使用される行セットのサイズを設定**SQLExtendedFetch**とき**SQLExtendedFetch** ODBC 2 によって呼び出される *.x*アプリケーション。 次に、実装の詳細を示します。<br /><br /> -アプリケーションが、これを設定する ODBC 3 *.x*ドライバー マネージャーがドライバーのバージョンに関係なく、ドライバーに呼び出しを渡します。<br />場合、ODBC 2 アプリケーション。*x*ドライバー呼び出し**SQLSetScrollOptions**の値に設定されている SQL_ROWSET_SIZE、**複合カーソル**引数。|  
|**SQLBulkOperations**|Insert 操作、または update、delete、またはブックマーク操作によってフェッチを実行します。 次に、実装の詳細を示します。<br /><br /> のアプリケーションを呼び出すと**SQLBulkOperations**で、*操作*SQL_ADD ODBC 2 での *。x*ドライバー、ODBC 3 *.x*ドライバー マネージャーにマップ**SQLSetPos**で、*操作*SQL_ADD の。<br />-場合は、ODBC 2 を使用します。*x*がサポートされていないドライバー **SQLSetPos**で、*操作*SQL_ADD、ODBC 3 の *.x*ドライバー マネージャーががマップされていない**SQLSetPos**で、*操作*に SQL_ADD の**SQLBulkOperations**で、*操作*SQL_ADD の。 これは、ため**SQLBulkOperations**状態 S7、どので ODBC 2 で呼び出すことはできません *。x*を唯一の状態が**SQLSetPos**呼び出すことができます。<br />場合は、アプリケーションを呼び出す**SQLBulkOperations**で、*操作*SQL_ADD ODBC 2 での *。x*呼び出す前にドライバー **SQLFetchScroll**、ODBC 3 *.x*ドライバー マネージャーでエラーが返されます。|  
|**SQLExtendedFetch**|指定した行セットを返します。 ODBC 3 だけに注意して、制限を除く *.x*ドライバー マネージャーへの呼び出しに渡します**SQLExtendedFetch**ドライバーのバージョンに関係なく、ドライバーにします。|  
|**SQLFetch**|次の行セットを返します。 次に、実装の詳細を示します。<br /><br /> のアプリケーションを呼び出すと**SQLFetch** 、ODBC 2 *。x*ドライバー、ODBC 3 *.x*ドライバー マネージャーにマップ**SQLExtendedFetch**します。 *FetchOrientation*の引数**SQLExtendedFetch** SQL_FETCH_NEXT に設定されます。 ドライバー マネージャーは、キャッシュされた値に対応し、SQL_ATTR_ROW_STATUS_PTR ステートメント属性の*RowStatusArray*引数と SQL_ATTR_ROWS_FETCHED_PTR ステートメント属性のキャッシュされた値、 *RowCountPtr*引数。<br />-ODBC 3 *.x*への呼び出しを混在させることがアプリケーション**SQLFetch**と**SQLFetchScroll** 、ODBC 2 *。x*ドライバーのため ODBC 3 *.x*ドライバー マネージャー マップ**SQLFetch**に**SQLExtendedFetch**呼び出すときに、アプリケーションが、ODBC 2 *。x*ドライバー。<br />場合は ODBC 2。*x*ドライバーがサポートしていない**SQLExtendedFetch**、ODBC 3 *.x*ドライバー マネージャーがマップされていない**SQLFetch**または**SQLFetchScroll**に**SQLExtendedFetch**アプリケーションを呼び出すと、そのドライバー。 アプリケーションが、SQL_ATTR_ROW_ARRAY_SIZE を 1、SQLSTATE HYC00 より大きい値に設定しようとしています。 場合 (省略可能な機能が実装されていません) が返されます。<br />-以外の制限だけに注意して、ODBC 3 *.x*ドライバー マネージャーへの呼び出しに渡します**SQLFetch**ドライバーのバージョンに関係なく、ドライバーにします。|  
|**SQLFetchScroll**|指定した行セットを返します。 次に、実装の詳細を示します。<br /><br /> のアプリケーションを呼び出すと**SQLFetchScroll** 、ODBC 2 *。x*ドライバー、ODBC 3 *.x*ドライバー マネージャーにマップ**SQLExtendedFetch**します。 キャッシュされた値に対応し、SQL_ATTR_ROW_STATUS_PTR ステートメント属性の使用、 *RowStatusArray*引数と SQL_ATTR_ROWS_FETCHED_PTR ステートメント属性のキャッシュされた値、 *RowCountPtr*引数。 場合、 *FetchOrientation*引数**SQLFetchScroll** SQL_FETCH_BOOKMARK は、SQL_ATTR_FETCH_BOOKMARK_PTR ステートメント属性のキャッシュされた値を使用して、 *FetchOffset*引数と、エラーが返されます、 *FetchOffset*の引数**SQLFetchScroll**が 0 ではありません。<br />-アプリケーションを呼び出すとこれで、ODBC 3 *.x*ドライバー、ODBC 3 *.x*ドライバー マネージャーがドライバーに呼び出しを渡します。|  
|**SQLSetPos**|さまざまな位置指定操作を実行します。 ODBC 3 *.x*ドライバー マネージャーへの呼び出しに渡します**SQLSetPos**ドライバーのバージョンに関係なく、ドライバーにします。|  
|**SQLSetScrollOptions**|ドライバー マネージャーがマップされます**SQLSetScrollOptions** 、ODBC 3 の操作、アプリケーションの *.x*がサポートされていないドライバー **SQLSetScrollOptions**、ドライバーマネージャーに SQL_ROWSET_SIZE ステートメントのオプション、not、SQL_ATTR_ROW_ARRAY_SIZE ステートメント属性を設定、*複合カーソル*引数**SQLSetScrollOption**します。 その結果、 **SQLSetScrollOptions**への呼び出しで複数の行をフェッチするときに、アプリケーションでは使用できません**SQLFetch**または**SQLFetchScroll**します。 フェッチの複数の行への呼び出しで場合にのみ使用できます**SQLExtendedFetch**します。|
