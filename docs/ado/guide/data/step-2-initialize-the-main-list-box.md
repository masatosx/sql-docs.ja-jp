---
title: "手順 2: メイン リスト ボックスの初期化 |Microsoft ドキュメント"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1454493-1c86-46c2-ada8-d3c6fcdaf3c1
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: c291da043764d9599311704af86952eec47578b6
ms.contentlocale: ja-jp
ms.lasthandoff: 09/09/2017

---
# <a name="step-2-initialize-the-main-list-box"></a>手順 2: メイン リスト ボックスを初期化します。
グローバルのレコードと、レコード セット オブジェクトを宣言するには、([全般]) (宣言) Form1 に次のコードを挿入します。  
  
```  
Option Explicit  
Dim grec As Record  
Dim grs As Recordset  
```  
  
 このコードでは、このシナリオでは後で使用されるレコードと、レコード セット オブジェクトのグローバル オブジェクト参照を宣言します。  
  
## <a name="to-connect-to-a-url-and-populate-lstmain"></a>URL に接続し、lstMain を設定するには  
 Form1 のフォームの読み込みイベント ハンドラーに次のコードを挿入します。  
  
```  
Private Sub Form_Load()  
    Set grec = New Record  
    Set grs = New Recordset  
    grec.Open "", "URL=http://servername/foldername/", , _  
        adOpenIfExists Or adCreateCollection  
    Set grs = grec.GetChildren  
    While Not grs.EOF  
        lstMain.AddItem grs(0)  
        grs.MoveNext  
    Wend  
End Sub  
```  
  
 このコードは、グローバルのレコードと、レコード セット オブジェクトをインスタンス化します。 Record オブジェクト`grec`、ActiveConnection として指定された URL でが開きます。 URL が存在する場合は、開かれています。これは既に存在しない場合は作成されます。 お客様の環境から"http://servername/foldername/"の有効な URL を置き換える必要がありますに注意してください。  
  
 レコード セット オブジェクト`grs`、レコードの子で開かれる`grec`です。 `lstMain` URL に公開されているリソースのファイル名が格納されます。  
  
## <a name="see-also"></a>参照  
 [インターネット発行シナリオ](../../../ado/guide/data/internet-publishing-scenario.md)   
 [手順 1: Visual Basic プロジェクトの設定します。](../../../ado/guide/data/step-1-set-up-the-visual-basic-project.md)   
 [手順 3: フィールドのリスト ボックスを表示します。](../../../ado/guide/data/step-3-populate-the-fields-list-box.md)