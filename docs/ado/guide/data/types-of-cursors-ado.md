---
title: 種類のカーソル (ADO) |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- cursors [ADO], types
ms.assetid: 7cc01544-e814-403b-bbfe-a2750bf921bd
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: ecf079c86362aeae78b7c9ceaad640b0ad1519c4
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47786960"
---
# <a name="types-of-cursors-ado"></a>カーソルの種類 (ADO)
一般的な規則として、アプリケーションに必要なデータ アクセスを提供する最も簡単なカーソルを使用する必要があります。 各追加のカーソルの特性 (順方向専用、読み取り専用、静的、スクロール、バッファーなし) の基本機能を越えてが価格 — クライアントのメモリ、ネットワーク負荷やパフォーマンスにします。 多くの場合は、既定のカーソル オプションは、アプリケーションが実際に必要以上より複雑なカーソルを生成します。  
  
 カーソルの種類の選択とによって異なります、アプリケーションが結果セットを使用する方法も、結果セットでは、使用される可能性のデータの割合、データの変更、およびアプリケーションのパフォーマンスに対する感度のサイズなど、いくつかの設計考慮事項要件。  
  
 基本的では、カーソル選択で変更または単にデータを表示する必要があるかどうかによって異なります。  
  
-   結果がない変更データのセットをスクロールする場合を使用して、[順方向専用](../../../ado/guide/data/forward-only-cursors.md)または[静的](../../../ado/guide/data/static-cursors.md)カーソル。  
  
-   場合は、大きな結果セットと、いくつかの行を選択する必要がある場合を使用して、[キーセット](../../../ado/guide/data/keyset-cursors.md)カーソル。  
  
-   使用してでの設定を最近使用した結果に追加し、変更されると、し、同時実行のすべてのユーザーによって削除を同期する場合、[動的](../../../ado/guide/data/dynamic-cursors.md)カーソル。  
  
 各カーソルの種類別にする見えますは、これらのカーソルの種類がないことほどの多様な単に重複する特性とオプションの結果として留意してください。  
  
 このセクションでは、次のトピックを扱います。  
  
-   [順方向専用カーソル](../../../ado/guide/data/forward-only-cursors.md)  
  
-   [静的カーソル](../../../ado/guide/data/static-cursors.md)  
  
-   [Keyset カーソル](../../../ado/guide/data/keyset-cursors.md)  
  
-   [動的カーソル](../../../ado/guide/data/dynamic-cursors.md)  
  
## <a name="see-also"></a>参照  
 [順方向専用カーソル](../../../ado/guide/data/forward-only-cursors.md)   
 [静的カーソル](../../../ado/guide/data/static-cursors.md)   
 [Keyset カーソル](../../../ado/guide/data/keyset-cursors.md)   
 [動的カーソル](../../../ado/guide/data/dynamic-cursors.md)
