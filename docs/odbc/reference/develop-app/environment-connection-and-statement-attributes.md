---
title: 環境、接続、およびステートメント属性 |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- environment attributes [ODBC]
- connection attributes [ODBC]
- statement attributes [ODBC]
ms.assetid: 9e15b276-3b7a-428a-b72f-a3ddfe1ba1ce
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: e77be71458eb10e97a82c925d34141a7bcaf1dc4
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47685936"
---
# <a name="environment-connection-and-statement-attributes"></a>環境、接続、およびステートメント属性
ODBC では、さまざまな環境、接続、またはステートメントに関連付けられている属性を定義します。  
  
 環境属性では、接続プールが有効にするかどうかなど、環境全体に影響します。 環境属性が設定されて**SQLSetEnvAttr**で取得および**SQLGetEnvAttr**します。  
  
 接続属性に影響を与える接続ごとに個別に、方法など、ドライバーが待機するタイムアウトになるまでのデータ ソースに接続しようとしています。接続属性が設定されて**SQLSetConnectAttr**で取得および**SQLGetConnectAttr**します。 接続属性の詳細については、次を参照してください。[接続属性](../../../odbc/reference/develop-app/connection-attributes.md)します。  
  
 ステートメント属性ステートメントを非同期的に実行する必要があるかどうかなど、個別に各ステートメントに影響します。 ステートメント属性が設定されて**SQLSetStmtAttr**で取得および**SQLGetStmtAttr**します。 いくつかのステートメント属性は読み取り専用の属性であり、設定することはできません。 たとえば、カーソルの現在の行の数を取得するために使用されて、SQL_ATTR_ROW_NUMBER ステートメント属性は読み取り専用です。 ステートメント属性の詳細については、次を参照してください。[ステートメント属性](../../../odbc/reference/develop-app/statement-attributes.md)します。  
  
 ODBC で定義された属性だけでなく、ドライバーは、独自の接続とステートメント属性を定義できます。 ドライバー定義の属性は、オープンのグループに、2 つのドライバーのベンダーに割り当てないでください同じ整数値、別の専用の属性を登録する必要があります。 詳細については、次を参照してください。[ドライバー固有のデータ型、記述子の種類、情報の種類、診断型、および属性](../../../odbc/reference/develop-app/driver-specific-data-types-descriptor-information-diagnostic.md)します。  
  
 属性の完全な一覧を参照してください。 [SQLSetEnvAttr](../../../odbc/reference/syntax/sqlsetenvattr-function.md)、 [SQLSetConnectAttr](../../../odbc/reference/syntax/sqlsetconnectattr-function.md)、および[SQLSetStmtAttr](../../../odbc/reference/syntax/sqlsetstmtattr-function.md)します。 ほとんどの属性は、それらに影響する ODBC 関数の説明にも説明されています。
