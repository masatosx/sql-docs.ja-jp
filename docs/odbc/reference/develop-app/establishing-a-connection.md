---
title: 接続を確立する |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- data sources [ODBC], connection functions
- SQLBrowseConnect function [ODBC], establising a connection
- functions [ODBC], data source or driver connections
- connecting to data source [ODBC], functions
- connecting to driver [ODBC], functions
- connection functions [ODBC]
- SQLConnect function [ODBC], establising a connection
- SQLDriverConnect function [ODBC], making a connection
- ODBC drivers [ODBC], connection functions
ms.assetid: 8e3c717e-35e3-47ef-b5d3-3a96eeb7b869
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 70f459f60616e7edd77078a7e9653ab9dff097e9
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47606382"
---
# <a name="establishing-a-connection"></a>接続の確立
環境と接続ハンドルの割り当てし、任意の接続属性を設定した後は、アプリケーションは、データ ソースまたはドライバーに接続する準備。 これを行うアプリケーションを使用できる 3 つの異なる関数がある: **SQLConnect** (Core インターフェイスへの準拠レベル)、 **SQLDriverConnect** (コア) と**SQLBrowseConnect**(レベル 1)。 さまざまなシナリオで使用するのには 3 つの各設計されています。 サポートがこれらの関数のうち、接続する前に、アプリケーションが判断できます、 **ConnectFunctions**キーワードによって返される**SQLDrivers**します。  
  
> [!NOTE]  
>  一部のドライバーでは、サポートされるアクティブな接続の数を制限します。 アプリケーションを呼び出す**SQLGetInfo**特定のドライバーがサポートしているアクティブな接続の数を決定する SQL_MAX_DRIVER_CONNECTIONS オプションを使用します。  
  
 このセクションでは、次のトピックを扱います。  
  
-   [既定のデータ ソース](../../../odbc/reference/develop-app/default-data-source.md)  
  
-   [SQLConnect による接続](../../../odbc/reference/develop-app/connecting-with-sqlconnect.md)  
  
-   [接続文字列](../../../odbc/reference/develop-app/connection-strings.md)  
  
-   [SQLDriverConnect による接続](../../../odbc/reference/develop-app/connecting-with-sqldriverconnect.md)  
  
-   [SQLBrowseConnect による接続](../../../odbc/reference/develop-app/connecting-with-sqlbrowseconnect.md)
