---
title: カーソルを閉じる |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- cursors [ODBC], closing
- closing cursors [ODBC]
ms.assetid: 4f19bf5e-6d8c-40ae-a975-cfd62a0790ec
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 632a922abb544a379892dfa168f55efd605304c8
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47792960"
---
# <a name="closing-the-cursor"></a>カーソルを閉じる
アプリケーションは、カーソルの使用が完了したら、それを呼び出す**SQLCloseCursor**カーソルを閉じます。 以下に例を示します。  
  
```  
SQLCloseCursor(hstmt);  
```  
  
 アプリケーションが、カーソルを閉じるまで、別の SQL ステートメントの実行など、他のほとんどの操作、カーソルを開いた、ステートメントを使用できません。 カーソルが開いているときに呼び出すことができる関数の完全な一覧を参照してください。[付録 b: ODBC の状態遷移テーブル](../../../odbc/reference/appendixes/appendix-b-odbc-state-transition-tables.md)します。  
  
> [!NOTE]  
>  カーソルを閉じるには、アプリケーションを呼び出す必要があります**SQLCloseCursor**ではなく、 **SQLCancel**します。  
  
 カーソルを開いたままが明示的に閉じるまでトランザクションがコミットまたはロールバック時に一部のデータ ソース、カーソルを閉じる点が異なります。 具体的には、結果の最後に到達した場合に設定、 **SQLFetch** sql_no_data が返されます、カーソルを閉じられません。 空の結果セット (結果セットが正常に実行されたステートメントが行を返さなかった場合に作成された) であってもカーソルは、明示的に終了する必要があります。
