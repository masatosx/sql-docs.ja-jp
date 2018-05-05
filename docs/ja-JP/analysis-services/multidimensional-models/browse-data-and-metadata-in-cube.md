---
title: データとキューブ内のメタデータを参照 |Microsoft ドキュメント
ms.date: 05/02/2018
ms.prod: sql
ms.technology: analysis-services
ms.component: multidimensional-models
ms.topic: article
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 433cd1af6480cc01df2da2e0a0e80f514c714adf
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="browse-data-and-metadata-in-cube"></a>キューブ内のデータおよびメタデータの参照
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  キューブ デザイナーの **[ブラウザー]** タブを使用すると、キューブ データを参照できます。 このビューでは、キューブ構造を検証し、データベース オブジェクトのデータ、計算、書式設定、およびセキュリティを確認できます。 レポート ツールや他のクライアント アプリケーションで、キューブがユーザーにどのように表示されるかを迅速に検証できます。 キューブのデータを参照すると、異なるディメンションを表示し、メンバーをドリル ダウンし、ディメンションをスライスできます。  
  
 キューブを参照するには、その前にキューブを処理し、再接続する必要があります。 キューブの処理後、キューブ デザイナーの **[ブラウザー]** タブが開きます。 ツール バーの [再接続] ボタンをクリックし、接続を更新します。  
  
 **[ブラウザー]** タブには、メタデータ ペイン、フィルター ペイン、およびデータ ペインの 3 つのペインが表示されます。 メタデータ ペインは、ツリー形式でキューブの構造を検証するために使用します。 **[ブラウザー]** タブの一番上にあるフィルター ペインは、参照するサブキューブの定義に使用します。 データ ペインは、結果セットを参照し、ディメンション階層をドリル ダウンするために使用します。  
  
## <a name="setting-up-the-browser"></a>ブラウザーの設定  
 キューブを参照する準備として、使用するパースペクティブまたは翻訳を指定できます。 データ ペインにメジャーとディメンションを追加し、フィルター ペインでフィルターを指定します。  
  
##### <a name="specifying-a-perspective"></a>パースペクティブの指定  
 **[パースペクティブ]** 一覧では、キューブに対して定義するパースペクティブを選択します。 パースペクティブはキューブ デザイナーの **[パースペクティブ]** タブで定義されています。 別のパースペクティブに切り替えるには、一覧でパースペクティブを選択します。  
  
##### <a name="specifying-a-translation"></a>翻訳の指定  
 **[言語]** 一覧を使用して、キューブに対して定義する翻訳を選択します。 翻訳はキューブ デザイナーの **[翻訳]** タブで定義されています。 **[ブラウザー]** タブには、最初、キューブの **"言語"** プロパティで設定した既定の言語のキャプションが表示されます。 別の言語に切り替えるには、一覧から言語を選択します。  
  
##### <a name="formatting-the-data-pane"></a>データ ペインの書式設定  
 データ ペインのキャプションとセルを書式設定することができます。 書式設定の対象として選択したセルまたはキャプションを右クリックし、 **[コマンドおよびオプション]** をクリックします。 **[コマンドおよびオプション]** ダイアログ ボックスには、選択した項目に応じて、 **[書式]**、 **[フィルターおよびグループ]**、 **[レポート]**、および **[動作]** の各設定が表示されます。  
  
## <a name="setting-up-the-data"></a>データの設定  
  
##### <a name="adding-or-removing-measures"></a>メジャーの追加と削除  
 参照するメジャーをメタデータ ペインからデータ ペインの詳細領域にドラッグします。詳細領域は、ワークスペースの右下側にある、大きな空のペインです。 追加のメジャーをドラッグすると、それらのメジャーは列として追加されます。 垂直線は、追加した各メジャーをドロップする場所を示します。 **[メジャー]** フォルダーをドラッグすると、すべてのメジャーが詳細領域にドロップされます。  
  
 詳細領域からメジャーを削除するには、削除するメジャーをデータ ペインの外にドラッグするか、右クリックしてショートカット メニューの **[削除]** をクリックします。  
  
##### <a name="adding-or-removing-dimensions"></a>ディメンションの追加または削除  
 階層またはディメンションを行またはフィルター領域にドラッグします。  
  
 複数のディメンションを扱う場合は、"Excel で分析" を使用します。 "Excel で分析" は、 [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]と同じコンピューターに Excel がインストールされている場合に、それを起動するショートカットです。 Excel は、現在のデータベースへの既存の接続と、事前にメジャーとディメンションが読み込まれたピボットテーブル フィールド リストを含むブックを開きます。 詳細については、「[[Excel で分析] (キューブ デザイナーの [ブラウザー] タブ) (Analysis Services - 多次元データ)](http://msdn.microsoft.com/library/890ed457-137e-44ac-9b2c-83344a1b8fc9)」を参照してください。  
  
 ディメンションを削除するには、削除するディメンションをデータ ペインの外にドラッグするか、右クリックしてショートカット メニューの **[削除]** をクリックします。  
  
##### <a name="adding-or-removing-filters"></a>フィルターの追加と削除  
 フィルターを追加するには、次の 2 つの方法のいずれかを使用します。  
  
-   メタデータ ペインでディメンションを展開し、フィルター ペインに階層をドラッグします。  
  
     \- または -  
  
-   **ディメンション**の列、**フィルター**  ウィンドウで、をクリックして**\<次元の選択 >** リストから、ディメンションを選択し、をクリックして**\<階層を選択 >** で、**階層**列と、一覧から階層を選択します。  
  
 階層を指定した後、演算子とフィルター式を指定します。 次の表では、演算子とフィルター式について説明しています。  
  
|演算子|[フィルター式]|Description|  
|--------------|-----------------------|-----------------|  
|等号|1 つ以上のメンバー|値は、指定されたメンバーに等しい必要があります<br /><br /> (親子階層以外の属性階層の複数のメンバー選択、および他の階層の単一のメンバー選択が提供されます)。|  
|不等号|1 つ以上のメンバー|値は、指定されたメンバーと異なる必要があります<br /><br /> (親子階層以外の属性階層の複数のメンバー選択、および他の階層の単一のメンバー選択が提供されます)。|  
|In|1 つ以上の名前付きセット|値は指定された名前付きセットである必要があります<br /><br /> (属性の階層のみをサポート)。|  
|[次に含まれない]|1 つ以上の名前付きセット|値は指定された名前付きセット以外である必要があります。<br /><br /> (属性の階層のみをサポート)。|  
|[範囲 (包含)]|範囲の 1 つまたは 2 つの区切りメンバー|値は、区切りメンバーの間、または区切りメンバーに等しい必要があります。 2 つの区切りメンバーが等しい場合、または区切りメンバーが 1 つだけ指定されている場合、範囲は適用されず、すべての値が許容されます<br /><br /> (属性階層のみをサポート。 範囲は、階層の 1 つのレベル上にある必要があります。 無制限の範囲は、現在サポートされていません)。|  
|[範囲 (排他)]|範囲の 1 つまたは 2 つの区切りメンバー|値は、区切りメンバーの間にある必要があります。 2 つの区切りメンバーが等しい場合、または区切りメンバーが 1 つだけ指定されている場合、値は区切りメンバーより大または小である必要があります<br /><br /> (属性階層のみをサポート。 範囲は、階層の 1 つのレベル上にある必要があります。 無制限の範囲は、現在サポートされていません)。|  
|MDX (MDX)|メンバー セットを返す MDX 式|値は、計算されるメンバー セットにある必要があります。 このオプションを選択すると、 **[計算されるメンバー ビルダー]** ダイアログ ボックスが表示されて、MDX 式を作成できます。|  
  
 ユーザー定義の階層では、フィルター式の中に複数のメンバーを指定できますが、指定するすべてのメンバーが同じレベルで、同じ親を共有する必要があります。 この制限は親子階層には適用されません。  
  
## <a name="working-with-data"></a>データの処理  
  
##### <a name="drilling-down-into-a-member"></a>メンバーのドリル ダウン  
 特定のメンバーをドリルダウンするには、メンバーの横のプラス記号 (+) をクリックするか、メンバーをダブルクリックします。  
  
##### <a name="slicing-through-cube-dimensions"></a>キューブ ディメンションのスライス  
 キューブ データをフィルター処理するには、最上位列の列見出しにあるドロップダウン リスト ボックスをクリックします。 階層を展開し、任意のレベルのメンバーをオンまたはオフにして、そのすべての子孫を表示または非表示にすることができます。 階層のメンバーをすべてオフにするには、 **[(All)]** の横のチェック ボックスをオフにします。  
  
 ディメンションにこのフィルターを設定した後、データ ペインを右クリックし、 **[自動フィルター]** をクリックしてオンとオフを切り替えることができます。  
  
##### <a name="filtering-data"></a>データのフィルター処理  
 フィルター領域では、参照するサブキューブを定義できます。 フィルターを追加するには、フィルター ペインでディメンションをクリックするか、メタデータ ペインでディメンションを展開し、階層をフィルター ペインにドラッグします。 その後、 **[演算子]** と **[フィルター式]** を指定します。  
  
##### <a name="performing-actions"></a>アクションの実行  
 データ ペインの見出しまたはセルに表示されている三角形は、アクションが存在することを示します。 これは、ディメンション、レベル、メンバーまたはキューブ セルに適用できます。 使用可能なアクションの一覧を表示するには、見出しオブジェクトにポインターを合わせます。 セル内の三角形をクリックすると、メニューが表示され、関連付けられたプロセスが開始します。  
  
 セキュリティのため、 **[ブラウザー]** タブでは次の操作のみがサポートされます。  
  
-   [URL]  
  
-   [行セット]  
  
-   ドリルスルー  
  
 コマンド ライン、ステートメント、専用の各アクションはサポートされていません。 URL アクションの安全性は、それがリンクする先の Web ページの安全性を超えることはありません。  
  
##### <a name="viewing-member-properties-and-cube-cell-information"></a>メンバー プロパティとキューブ セル情報の表示  
 ディメンション オブジェクトまたはセル値に関する情報を表示するには、セルにポインターを合わせます。  
  
##### <a name="showing-or-hiding-empty-cells"></a>空のセルの表示と非表示  
 データ ペイン内を右クリックして **[空のセルを表示]** をクリックすると、データ グリッド内の空のセルを非表示にすることができます。  
  
  