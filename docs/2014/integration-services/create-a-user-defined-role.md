---
title: ユーザー定義ロールの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
ms.assetid: c4128993-2333-48c7-84b1-e51cdcea393d
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: ac839255a5c065d312852de582607de4ae0c2949
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48199189"
---
# <a name="create-a-user-defined-role"></a>ユーザー定義ロールを作成する
    
### <a name="to-create-a-user-defined-role"></a>ユーザー定義ロールを作成するには  
  
1.  [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]を開きます。  
  
2.  **[表示]** メニューの **[オブジェクト エクスプローラー]** をクリックします。  
  
3.  オブジェクト エクスプローラー ツール バーで **[接続]** をクリックし、 **[データベース エンジン]** をクリックします。  
  
4.  **[サーバーへの接続]** ダイアログ ボックスで、サーバー名を指定し、認証モードを選択します。 (Local)、ピリオド (.) を使用するまたは`localhost`をローカル サーバーを指定します。  
  
5.  **[接続]** をクリックします。  
  
6.  [データベース]、[システム データベース]、[msdb]、[セキュリティ]、[ロール] を順に展開します。  
  
7.  [ロール] ノードの [データベース ロール] を右クリックし、 **[新しいデータベース ロール]** をクリックします。  
  
8.  [全般] ページでロール名を指定します。必要に応じて、所有者および所有されているスキーマを指定し、ロール メンバーを追加します。  
  
9. 必要に応じて、 **[権限]** をクリックし、オブジェクトの権限を構成します。  
  
10. 必要に応じて、 **[拡張プロパティ]** をクリックし、任意の拡張プロパティを構成します。  
  
11. **[OK]** をクリックします。  
  
  
