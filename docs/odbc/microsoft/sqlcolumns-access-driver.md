---
title: "SQLColumns (Access ドライバー) |Microsoft ドキュメント"
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
- SQLColumns function [ODBC], Access Driver
- Access driver [ODBC], SQLColumns
ms.assetid: 1eac255c-6110-4805-a1bc-feee1eec35d0
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 6359fe8948e670a05a076537e2acf3e28b3cba1d
ms.contentlocale: ja-jp
ms.lasthandoff: 09/09/2017

---
# <a name="sqlcolumns-access-driver"></a>SQLColumns (Access ドライバー)
> [!NOTE]  
>  このトピックでは、アクセス ドライバー固有の情報を提供します。 この関数の概要については、下の該当するトピックを参照してください。 [ODBC API リファレンス](../../odbc/reference/syntax/odbc-api-reference.md)です。  
  
|列|コメント|  
|------------|--------------|  
|TABLE_QUALIFIER|データベース ファイルへのパスが返されます。|  
|TABLE_OWNER|所有者名がサポートされていないために、この列に NULL が返されます。|  
|NULLABLE|主キーまたは一意のインデックスに含まれる列の SQL_NO_NULLS が返されます。|