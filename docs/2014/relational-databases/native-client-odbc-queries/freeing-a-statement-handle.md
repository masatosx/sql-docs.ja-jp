---
title: ステートメント ハンドルの解放 |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- reusing statement handles
- freeing statement handles
- statements [ODBC], statement handles
- SQLFreeStmt function
- ODBC applications, statements
- statement handles [ODBC]
ms.assetid: 96fdff84-0ca7-460a-a240-94ee826ea41c
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 9b1a155f7d2ee6cc5f92d46c2bb744168dc5ebc0
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48073822"
---
# <a name="freeing-a-statement-handle"></a>ステートメント ハンドルの解放
  ステートメント ハンドルは、削除して新しいハンドルを割り当てるよりも、再利用する方が効率的です。 アプリケーションでは、任意のステートメント ハンドルで新しい SQL ステートメントを実行する前に、現在のステートメント設定が適切であることを確認する必要があります。 確認する設定には、ステートメント属性、パラメーター バインド、結果セットのバインドがあります。 一般に、パラメーターと結果を設定します、古い SQL ステートメントを呼び出すことによってバインド解除する必要があります[SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) SQL_RESET_PARAMS と SQL_UNBIND オプションし、新しい SQL ステートメントの再バインドします。  
  
 呼び出しステートメントを使用するが、アプリケーションが完了したら、 [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md)ステートメントを解放します。 なお**SQLDisconnect**接続ですべてのステートメントを自動的に解放します。  
  
## <a name="see-also"></a>参照  
 [クエリの実行&#40;ODBC&#41;](executing-queries-odbc.md)  
  
  
