---
title: SQL Server (ODBC) との通信 |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, communicating with SQL Server
- ODBC applications, communicating with SQL Server
- ODBC, communicating with SQL Server
ms.assetid: cca3dcf0-2a7e-465a-84de-7ce055360eb6
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 915884866ce58346fa1257b6746c35b4f5cddc40
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48085322"
---
# <a name="communicating-with-sql-server-odbc"></a>SQL Server との通信 (ODBC)
  ODBC アプリケーションのインスタンスと通信する[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]環境を割り当てる必要があります、および接続を処理し、データ ソースに接続します。 接続が確立されると、アプリケーションからサーバーにクエリを送信し、任意の結果セットを処理できます。 データ ソースの使用が終了したら、アプリケーションでデータ ソースを切断して接続ハンドルを解放します。 すべての接続ハンドルを解放してから、環境ハンドルを解放します。  
  
 アプリケーションからは任意の数のデータ ソースに接続できます。 また、アプリケーションでは、複数のドライバーと複数のデータ ソースの組み合わせ、1 つのドライバーと複数データ ソースの組み合わせ、1 つのドライバーと 1 つのデータ ソースへの複数の接続を使用できます。  
  
 ダウンロードすることができます[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ネイティブ クライアント ODBC のサンプル コードから、 [SQL Server ダウンロード](http://go.microsoft.com/fwlink/?LinkId=62796)MSDN ページにアクセスします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [環境ハンドルの割り当て](allocating-an-environment-handle.md)  
  
-   [接続ハンドルの割り当て](allocating-a-connection-handle.md)  
  
-   [SQL Server Native Client ODBC データ ソース](../../integration-services/connection-manager/data-sources.md)  
  
-   [データ ソースに接続する&#40;ODBC&#41;](connecting-to-a-data-source-odbc.md)  
  
-   [データ ソースからの切断](disconnecting-from-a-data-source.md)  
  
## <a name="see-also"></a>参照  
 [SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md)   
 [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md)  
  
  
