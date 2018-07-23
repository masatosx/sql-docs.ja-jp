---
title: シーケンス クラスター モデル (中級者向けデータ マイニング チュートリアル) の検証 |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: f8a485d5-47ed-4dd5-bb66-ef4d6d463845
caps.latest.revision: 45
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 1a17523ea68b8f04de5240011ad426dbe19779e3
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37226622"
---
# <a name="exploring-the-sequence-clustering-model-intermediate-data-mining-tutorial"></a>シーケンス クラスター モデルの検証 (中級者向けデータ マイニング チュートリアル)
  これでビルドした、 **Sequence Clustering with Region**モデルでは、利用できることを使用して、[!INCLUDE[msCoName](../includes/msconame-md.md)]でシーケンス クラスター ビューアー、**マイニング モデル ビューアー**データ マイニング デザイナーのタブ。 [!INCLUDE[msCoName](../includes/msconame-md.md)]シーケンス クラスター ビューアーには、5 つのタブが含まれています:**クラスター ダイアグラム**、**クラスターのプロファイル**、**クラスターの特性**、 **ClusterDiscrimination**、および**状態遷移**します。 このビューアーを使用する方法の詳細については、次を参照してください。 [Microsoft シーケンス クラスター ビューアーを使用してモデルの参照](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)します。  
  
-   [クラスター ダイアグラム タブ](#bkmk_CDiagram)  
  
-   [クラスターのプロファイル タブ](#bkmk_CProfiles)  
  
-   [クラスターの特性 タブ](#bkmk_CChars)  
  
-   [クラスターの識別 タブ](#bkmk_CDiscrim2)  
  
-   [状態遷移 タブ](#bkmk_StateTran)  
  
-   [汎用コンテンツ ツリー ビューアー](#bkmk_Generic)  
  
##  <a name="bkmk_CDiagram"></a> クラスター ダイアグラム タブ  
 **クラスター ダイアグラム** タブは、データベース内のアルゴリズムで発見されたクラスターをグラフィカルに表示されます。 ダイアグラムのレイアウトは、類似するクラスターを緊密にグループ化したクラスターのリレーションシップを表します。 既定では、各ノードの色の濃さはクラスターに存在するケースの密度を表し、ノード色が濃くなるほど多数のケースが存在することになります。 ノードの色の濃さが各クラスター内の属性や状態のサポートを表すように、設定を変更することもできます。  
  
 目的のクラスターを簡単に識別したり操作したりできるようにクラスターの名前を変更することもできます。 このチュートリアルでは、太平洋地域の顧客の割合が最も高いクラスターと全体のケースの数が最も多いクラスターの名前を変更します。  
  
> [!NOTE]  
>  データとモデル パラメーターによっては、モデルを再処理したときに、特定のクラスターに割り当てられたケースが変更されることがあります。 また、クラスターの名前を変更した場合、それらの名前は、マイニング モデルを再処理すると失われます。  
  
#### <a name="to-change-the-attribute-used-for-highlighting-clusters"></a>クラスターを強調表示するために使用される属性を変更するには  
  
1.  **網掛け変数**一覧で、**モデル**します。  
  
2.  選択**Cycling Cap**で、**状態**一覧。  
  
     ダイアグラムが更新されて、選択した製品の各クラスターにおける集中度が表示されます。 最も色の濃いクラスターに、サイクリング キャップが最も高い密度で含まれます。 シェーディング変数は、任意の入力列の任意の状態を使用するように変更できます。  
  
3.  **網掛け変数**一覧で、**母集団**します。  
  
     シェーディング変数を母集団に変更すると、ダイアグラムが更新されて、クラスターがサイズで比較されるようになります。 最も色の濃いクラスターに最も多くのケースが含まれています。  
  
#### <a name="to-rename-nodes-in-the-model"></a>モデルのノードの名前を変更するには  
  
1.  変更**網掛け変数**に`Region`、設定と**状態**に**太平洋**します。  
  
2.  グラフで最も色の濃いノードを強調表示させます。  
  
3.  このクラスターを右クリックして**クラスターの名前を変更します。**  
  
4.  名前を入力します**Pacific Cluster します。**  
  
5.  値を変更**網掛け変数**に**母集団**します。  
  
6.  更新されたグラフで、最も色の濃いクラスター (最も大きなクラスター) を見つけます。 色の濃さからはどのクラスターが最も大きいか判断できない場合は、各クラスターの上にマウス ポインターを置いてツールヒントを確認し、最も多くのケースが含まれているクラスターを選択します。  
  
7.  このクラスターを右クリックして**クラスター名の変更**します。 新しい名前を入力`Largest Cluster`します。  
  
 クラスターを表すノードからドリルスルーして、各クラスター内のケースの詳細を表示することができます。 たとえば、顧客に電子メールを送信するなど、分析の結果に対して操作を実行する場合に便利です。 構造には含まれているがモデルでは使用されていない、ケースのその他の属性を参照することもできます (Region や IncomeGroup など)。 マイニング モデルからドリルスルーする基になるケースの詳細については、次を参照してください。[ドリルスルー クエリ&#40;データ マイニング&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)します。  
  
#### <a name="to-drill-through-to-details-from-the-cluster-diagram"></a>クラスター ダイアグラムから詳細情報にドリルスルーするには  
  
1.  右クリック`Pacific Cluster`を選択します**ドリル スルー**、し、**モデルおよび構造列**します。  
  
     **ドリル スルー**  ダイアログ ボックスが表示されます。 モデルで使用されていないが、クエリで使用できる列が付いて**構造**します。  
  
     このクラスターに含まれている顧客はほとんどが太平洋地域の顧客で、その他の地域の顧客はごくわずかであることがわかります。  
  
2.  入れ子になった列 v Assoc Seq Line Items のプラス記号をクリックして、特定の顧客注文のアイテムのシーケンスを表示します。  
  
3.  閉じる、**ドリル スルー**  ダイアログ ボックス。  
  
    > [!NOTE]  
    >  **再生**ボタンでは、データを再クエリすることができます。 ただし、クエリを再実行は変更されません、表示されているデータ モデルが更新されていない限り動的にバック グラウンドで他のプロセスでします。  
  
 [ページのトップへ](#bkmk_CDiagram)  
  
##  <a name="bkmk_CProfiles"></a> クラスターのプロファイル タブ  
 **クラスターのプロファイル**タブには、各クラスターに含まれるシーケンスが表示されます。 クラスターは、個々 の列の右側に記載されて、**状態**列。  
  
 ビューアーで、**モデル**行が、クラスター内の項目の全体的な分布について説明しますと、 **Model.samples**行には、アイテムのシーケンスが含まれています。 各行の各セルの色のシーケンス、 **Model.samples**行は、クラスター内のランダムに選択したユーザーの動作を表します。  
  
 シーケンス ヒストグラムでは、各製品モデルがそれぞれ異なる色で示されます。 マイニング凡例は、色分けと製品モデル名の両方を使用して製品のシーケンスを表します。 クラスターのモデルにその他の列 (Region や Income Group など) を追加した場合は、各列に対応する追加の行がビューアーに含まれます。それらの行には、各クラスター内のそれらの値の分布が表示されます。  
  
#### <a name="to-view-the-sequences-that-are-most-common-in-a-cluster"></a>クラスターで最も一般的なシーケンスを表示するには  
  
1.  右クリックし、**モデル**、クラスターの列の行`Largest Cluster`、選択と**凡例を表示する**します。  
  
     **色**列には、シーケンス内のアイテムの頻度を示す色つきのバーが含まれています。 各アイテムがそれぞれ異なる色で表されます。 **意味**列色ごとに製品モデル名が表示されます。 **配布**列は、この項目のシーケンスに含まれているケースの割合を示します。  
  
2.  閉じる、**マイニング凡例**します。  
  
3.  右クリックし、 **Model.samples** 、見出しと列の行**人口、** 選択**凡例を表示する**。  
  
4.  全体的なモデル内のシーケンスの一覧をスキャンします。`.`  
  
     マイニング凡例では最も一般的なシーケンスが最初に表示されるため、多くのシーケンスで Mountain Tire Tube が最初のアイテムになっていることがわかります。 これは、Mountain Tire Tube を最初に買い物かごに入れる顧客が多いことを示しています。  
  
#### <a name="to-drill-through-to-cases-from-the-cluster-viewer"></a>クラスター ビューアーからケースにドリルスルーするには  
  
1.  行が見つかるまで、属性 ペインで下へスクロール、`Region`属性。  
  
     モデルでは、各クラスターのヒストグラムと 1 つの追加のヒストグラムを行に含まれる**母集団**モデルで使用されるケースのセット全体を意味します。 ヒストグラムとは、さまざまな色を含むバーで、それぞれの色が属性を表し、色の付いた部分のサイズがその色の属性を持つケースの割合を表します。  
  
2.  名前を変更したクラスターのヒストグラムを比較`Pacific Cluster`と`Largest Cluster`します。 各クラスターはそれぞれ異なる列に表示されます。  
  
     どちらも単色に見えますが、同じ色ではありません。  
  
3.  `Region`行で、カラー ヒストグラムの上にマウス ポインターを置く`Largest Cluster`します。  
  
     各地域のケースの実際の割合を示す値がツールヒントに表示されます。  
  
4.  カラー ヒストグラムを右クリックし、`Region`行の`Pacific Cluster`を選択します**ドリル スルー**、し、**モデル列のみ**します。  
  
5.  スクロール バーを動かして、このクラスターのすべての顧客を調べます。  
  
     詳細情報にドリルスルーした結果からは、クラスターに含まれている注文のほとんどが太平洋地域からの注文であっても、北米地域やヨーロッパ地域からの注文もわずかに含まれていることがわかります。  
  
6.  閉じる、**ドリル スルー**  ダイアログ ボックス。  
  
 [ページのトップへ](#bkmk_CDiagram)  
  
##  <a name="bkmk_CChars"></a> クラスターの特性 タブ  
 **クラスターの特性** タブは、選択したクラスターの属性の値の重要度を視覚的に表すバーを表示することで、クラスターにおける状態間の遷移をまとめたものです。 **変数**列は、モデルが選択されているクラスターや母集団重要見つかったを示して: 特定の値またはと呼ばれる値の間のリレーションシップのいずれか*遷移*します。 **値**列値または遷移の詳細については、および**確率**列が視覚的にこの属性または遷移の重みを表します。  
  
#### <a name="to-view-the-important-attributes-for-a-cluster"></a>クラスターの重要な属性を表示するには  
  
1.  **クラスター**ドロップダウン リストで、`Pacific Cluster`します。  
  
     名前を変更したクラスターの特性を表示の一覧は更新`Pacific Cluster`します。 最も重要な特性は、このクラスターで`Region`します。  
  
2.  行の色付きのバーの上にマウス ポインターを置く`Region`します。  
  
     値が Pacific である確率が非常に高いことがわかります。 これらの値を解釈する方法の詳細については、次を参照してください。 [Microsoft シーケンス クラスタ リング アルゴリズム テクニカル リファレンス](../../2014/analysis-services/data-mining/microsoft-sequence-clustering-algorithm-technical-reference.md)します。  
  
3.  最初の遷移行が見つかるまでクラスターの特性の一覧を調べていきます。  
  
4.  遷移行には、遷移のテキストが含まれています。 で、**変数**列、および連続属性の値の組み合わせ、**値**列。 [Start] や missing がシーケンスに含まれる場合もあります。  
  
     たとえば、遷移の値が "[Start] -> Road Tire Tube" だった場合は、 そのクラスターの顧客がよく Road Tire Tube を最初に買い物かごに入れているということになります。 これは、その製品が顧客によって最初に探される人気のアイテムであることを示している場合もあれば、その製品がその購入サイトで見つけやすいということを示しているだけの場合もあります。  
  
5.  ない最初の遷移が見つかるまで一覧をスクロール **[Start]** または**不足している**にします。  
  
     たとえば、移行を検索する**Touring Tire, Touring Tire Tube**します。 そのクラスターの顧客がこれらのアイテムをよくこの順序で一緒に購入していることになります。  
  
6.  この遷移の色付きのバーの上にマウス ポインターを置きます。  
  
     この遷移の確率がパーセントで表示されます。  
  
7.  **クラスター**ドロップダウン リストで、**母集団 (すべて)** します。  
  
     属性の一覧が更新されて、モデルの作成に使用されたすべての注文の特性が表示されます。 クラスター間で区別するための最も重要な特性は、このマイニング モデルで`Region`の値を持つ**北米**します。  
  
 以上の作業から、2 つのことがわかりました。 1 つは、意味のある数の組み合わせを得るためには大量のデータが必要であるということです。 たとえば、最も高い確率でシーケンスが含まれる可能性が、 **[Start]** または**Missing**状態。  
  
 属性に対する強力なクラスター化の効果があること、2 つ目は、`Region`がより困難に、シーケンスのグループを参照してください。 したがって、地域や収入の列を含まない、シーケンスのみを使用する別のモデルを作成することにします。  
  
 [ページのトップへ](#bkmk_CDiagram)  
  
##  <a name="bkmk_CDiscrim2"></a> クラスターの識別 タブ  
 **クラスターの識別** タブを使用して、どの属性が別のクラスターから特定のクラスターを区別する、2 つのクラスターを比較できます。 タブには、4 つの列が含まれる:**変数**、**値**、**クラスター 1**、および**クラスター 2**します。  任意のクラスターとして使用することができます**クラスター 1**と**クラスター 2**します。  
  
 **変数**列は、列名または列名と、単語の組み合わせを指定できますいずれかの属性の名前を通知**遷移**します。 **値**列には、属性または遷移の正確な値が表示されます。 列の色付きのバー**クラスター 1**と**クラスター 2**を比較するクラスター内の属性の強さを示します。 バーが長いほど、その属性を持つケースがクラスターに含まれる可能性が高くなります。  
  
#### <a name="to-compare-two-clusters-by-using-the-cluster-discrimination-tab"></a>[クラスターの識別] タブを使用して 2 つのクラスターを比較するには  
  
1.  **クラスターの識別** タブの**クラスター 1**、`Pacific Cluster`します。  
  
     既定で選択されたを**クラスター 2**への変更**補数の太平洋 * * * クラスター**。  
  
     最も重要な属性を区別する`Pacific Cluster`それ以外の場合からは、リージョン。 地域がクラスター化のための属性として強力すぎるために、他の属性がわかりにくくなっています。 この影響を回避するために、いくつかの小さなクラスターを互いに比較してみます。 そうすれば、属性の一覧が変更されて、モデル間の遷移がより多く含まれるようになる可能性があります。  
  
2.  遷移行を見つけて、色付きのバーの上にマウス ポインターを置きます。  
  
     内の項目、**値**列は、状態と遷移の両方を含めることができます。 各アイテムの色は識別スコアを表します。 さまざまなスコアの意味の詳細については、次を参照してください。[シーケンス クラスター モデルのマイニング モデル コンテンツ&#40;Analysis Services - データ マイニング&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-sequence-clustering-models.md)します。  
  
 [ページのトップへ](#bkmk_CDiagram)  
  
##  <a name="bkmk_StateTran"></a> 状態遷移 タブ  
 **状態遷移** タブで、クラスターを選択し、参照状態が遷移することができます。 選択した場合**母集団 (すべて)** クラスター ドロップダウン リストから、図は、マイニング モデル全体の状態の分布を示しています。  
  
 グラフの各ノードは、分析しようとしているシーケンスの状態または使用可能な値を表します。 ノードの背景色は、その状態の頻度を表します。 一部の状態を結ぶ線は、状態間の遷移を表します。 スライダーを上下に動かして、遷移の確率のしきい値を変更することもできます。 一部のノードに関連付けられている数値は、その状態の確率を表します。  
  
#### <a name="to-explore-the-relationships-in-the-state-transition-tab"></a>[状態遷移] タブで関係を調査するには  
  
1.  **状態遷移**選択は、マイニング モデル ビューアーのタブ`Pacific Cluster`クラスターの一覧から。 いることを確認、**線のラベルを表示する**オプションを選択します。  
  
     グラフが更新されて、このクラスターで最も一般的な遷移が表示されます。  
  
2.  別のノードと線で結ばれている任意のノードをクリックします。  
  
     グラフが更新されて、関連するノードが強調表示されます。 線の横の数値はその遷移の確率を表します。  
  
3.  スライダーを最大発生**すべてのリンク**をグラフに含まれる遷移の数を増やします。  
  
4.  選択**母集団 (すべて)** から**クラスター**します。  
  
     別のクラスターを読み込むとグラフが既定の表示設定にリセットされるため、スライダー コントロールが中央の位置に戻ります。  
  
5.  最も色の濃いノードとして使用すると、グラフをクリックします**sport-100**します。  
  
     この製品を他の製品と結ぶ線はありません。  
  
6.  スライダーを 1 段階上に動かして、グラフに含まれる遷移の数を増やします。 至るください**すべてリンク**まだします。  
  
     グラフが更新されていくつかの遷移が追加されますが、Sport-100 モデルを含む遷移はありません。  
  
7.  スライダーの制御に至る移動**すべてリンク**します。 まだ選択されていない場合は、Sport-100 ノードをクリックします。  
  
     グラフが更新されて、Sport-100 という製品を含む多数の遷移が表示されます。 ノードを結ぶ線の矢印の向きは、Sport-100 がペアの 1 つ目のアイテムとして選択されたか 2 つ目のアイテムとして選択されたかを表します。  
  
8.  Touring Tire のノードをクリックし、スライダー コントロールを中央の位置まで戻します。  
  
     最初は、Touring Tire を他の製品と結ぶ遷移の線が多数ありましたが、確率のしきい値を上げると、確率の低い遷移がグラフから取り除かれて、"Touring Tire > Touring Tire Tube" という遷移のみになります。 この遷移は、顧客が Touring Tire を買い物かごに入れた場合、その次に Touring Tire Tube をかごに入れる確率が高いことを示しています。  
  
 [ページのトップへ](#bkmk_CDiagram)  
  
##  <a name="bkmk_Generic"></a> 汎用コンテンツ ツリー ビューアー  
 このビューアーは、アルゴリズムやモデルの種類に関係なく、すべてのモデルで使用できます。 **MicrosoftGeneric コンテンツ ツリー ビューアー**から利用できますが、**ビューアー**ドロップダウン リスト。  
  
 コンテンツ ツリーは、マイニング モデルを一連のノードで表したものです。各ノードは、トレーニング データに関する学習済みの知識を表します。 ノードには、いくつかの属性が共通するパターン、一連のルール、クラスター、または日付範囲の定義を含めることができます。 ノードの正確な内容はアルゴリズムや予測可能な属性に応じて変わりますが、内容の全体的な表示は同じです。  
  
 各ノードを展開して、より詳細なレベルで表示したり、任意のノードの内容をクリップボードにコピーしたりできます。 詳細については、「 [Microsoft 汎用コンテンツ ツリー ビューアーを使用したモデルの参照](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-generic-content-tree-viewer.md)」をご覧ください。  
  
#### <a name="to-view-details-for-a-sequence-clustering-model-by-using-the-generic-content-tree-viewer"></a>汎用コンテンツ ツリー ビューアーを使用してシーケンス クラスター モデルの詳細を表示するには  
  
1.  **マイニング モデル ビューアー**タブをクリックし、**ビューアー**一覧**Microsoft 汎用コンテンツ ツリー ビューアー**します。  
  
2.  **ノードのキャプション**ウィンドウで、をクリック`Pacific Cluster (1)`します。  
  
     このノードの名前には、クラスターに割り当てた表示名と、基になるノード ID の両方が含まれています。 ノード ID を使用してモデルの詳細にドリル ダウンできます。  
  
3.  という名前の最初の子ノードを展開**クラスター 1 のシーケンス レベル**します。  
  
     クラスターのシーケンス レベル ノードには、そのクラスターに含まれる状態と遷移の詳細が含まれています。 これらの詳細 (NODE_DISTRIBUTION 列に表示されます) を使用して、各クラスターまたはモデル全体のシーケンスと状態を調査することができます。  
  
4.  ノードをさらに展開して、HTML ビューアー ペインに詳細を表示します。  
  
 マイニング モデルの内容と、ビューアーで詳細を使用する方法の詳細については、次を参照してください。[シーケンス クラスター モデルのマイニング モデル コンテンツ&#40;Analysis Services - データ マイニング&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-sequence-clustering-models.md)します。  
  
 [ページのトップへ](#bkmk_CDiagram)  
  
## <a name="next-task-in-lesson"></a>このレッスンの次の作業  
 [関連するシーケンス クラスター モデルを作成する&#40;中級者向けデータ マイニング チュートリアル&#41;](../../2014/tutorials/creating-a-related-sequence-clustering-model-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a>参照  
 [Microsoft シーケンス クラスタ リング アルゴリズム](../../2014/analysis-services/data-mining/microsoft-sequence-clustering-algorithm.md)   
 [シーケンス クラスター モデルのクエリの例](../../2014/analysis-services/data-mining/sequence-clustering-model-query-examples.md)  
  
  