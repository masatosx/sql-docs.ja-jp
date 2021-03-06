---
title: 複雑なステートメントの処理 |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 6b807a45-a8b5-4b1c-8b7b-d8175c710ce0
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: d44f2c229755c742d5481f3ca427f11fb5586c2c
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47623930"
---
# <a name="handling-complex-statements"></a>複雑なステートメントの処理
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] を使用するときは、実行時に動的に生成されるステートメントなど、複雑なステートメントに対処しなければならないことがあります。 複雑なステートメントは、更新、挿入、および削除などのさまざまなタスクを頻繁に実行します。 これらの種類のステートメントは、複数の結果セットや出力パラメーターを返すこともあります。 こうした状況では、ステートメントを実行する Java コードが、返されるデータやオブジェクトの型および数について事前に知らない場合があります。  
  
 複雑なステートメントを効率的に処理するため、JDBC ドライバーでは、返されるオブジェクトやデータをクエリし、アプリケーションがそれらを正しく処理するための多くのメソッドが用意されています。 複雑なステートメントを処理するために重要となるのは、[SQLServerStatement](../../connect/jdbc/reference/sqlserverstatement-class.md) クラスの [execute](../../connect/jdbc/reference/execute-method-sqlserverstatement.md) メソッドです。 このメソッドが戻る、**ブール**値。 値が true の場合、ステートメントから返される最初の結果は結果セットです。 値が false の場合、返される最初の結果は更新数です。  
  
 返されたオブジェクトまたはデータの型がわかっている場合、[getResultSet](../../connect/jdbc/reference/getresultset-method-sqlserverstatement.md) メソッドまたは [getUpdateCount](../../connect/jdbc/reference/getupdatecount-method-sqlserverstatement.md) メソッドのいずれかを使用してそのデータを処理することができます。 複雑なステートメントから返された次のオブジェクトまたはデータへ進むため、[getMoreResults](../../connect/jdbc/reference/getmoreresults-method.md) メソッドを呼び出すことができます。  
  
 次の例は、[!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal_md.md)] サンプル データベースに対して開いている接続を関数に渡し、ストアド プロシージャ呼び出しと SQL ステートメントを結合する複雑なステートメントを作成して実行します。次に `do` ループを使用して、返されたすべての結果セットおよび更新数を処理します。  
  
 [!code[JDBC#HandlingComplexStatements1](../../connect/jdbc/codesnippet/Java/handling-complex-statements_1.java)]  
  
## <a name="see-also"></a>参照  
 [JDBC ドライバーでのステートメントの使用](../../connect/jdbc/using-statements-with-the-jdbc-driver.md)  
  
  
