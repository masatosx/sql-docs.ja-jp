---
title: ナレッジ検出の実行 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- data-quality-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.kbanalyze.f1
- sql12.dqs.kb.viewselectcd.f1
- sql12.dqs.kb.kbmap.f1
- sql12.dqs.kb.kbterms.f1
ms.assetid: 34a0ea16-02e6-46ed-90bc-dede68687f63
caps.latest.revision: 37
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 172dfee131d4452e2d3adae7a3e8854591a8c0a1
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37206182"
---
# <a name="perform-knowledge-discovery"></a>ナレッジ検出の実行
  このトピックでは、ナレッジ検出を使用してナレッジ ベースを構築する方法について説明します。 検出プロセスでは、 [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) によって、コンピューター支援型のプロセスを使用してサンプル データ ソースのデータが分析され、取得されたナレッジがナレッジ ベースに追加されます。 そのナレッジは、ナレッジ検出アクティビティの **[ドメイン値の管理]** 手順か、ドメイン管理アクティビティで変更および強化できます。  
  
 ナレッジ検出は、3 つの手順を含むウィザード ベースのプロセスです。それぞれの手順を完了する必要があります。  
  
##  <a name="BeforeYouBegin"></a> 作業を開始する準備  
  
###  <a name="Prerequisites"></a> 前提条件  
 検出を実行する対象のソース データが Excel ファイルに含まれている場合は、 [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] コンピューターに Microsoft Excel がインストールされている必要があります。 Excel がインストールされていないと、マップ ステージで Excel ファイルを選択できません。 Microsoft Excel で作成されるファイルの拡張子は、.xlsx、.xls、または .csv です。 64 ビット バージョンの Excel を使用する場合は、Excel 2003 ファイル (.xls) のみがサポートされます。Excel 2007 または 2010 ファイル (.xlsx) はサポートされません。 64 ビット バージョンの Excel 2007 または 2010 を使用している場合は、ファイルを .xls ファイルまたは .csv ファイルとして保存するか、32 ビット バージョンの Excel をインストールしてください。  
  
###  <a name="Security"></a> セキュリティ  
  
####  <a name="Permissions"></a> Permissions  
 ナレッジ ベースを作成するには、DQS_MAIN データベースの dqs_kb_editor ロールまたは dqs_administrator ロールが必要です。  
  
##  <a name="FirstStep"></a> 最初の手順: ナレッジ検出の開始  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]「[Data Quality Client アプリケーションの実行](../../2014/data-quality-services/run-the-data-quality-client-application.md)」をご覧ください。  
  
2.  新しいナレッジ ベースでナレッジ検出を実行する場合は、 **[新しいナレッジ ベース]** をクリックし、名前と説明を入力して、必要に応じてナレッジ ベースの作成元を指定します。 既存のナレッジ ベースでナレッジ検出を実行する場合は、 **[ナレッジ ベースを開く]** をクリックし、ナレッジ ベースを選択します。  
  
3.  アクティビティとして **[ナレッジ検出]** を選択した後に、 **[作成]** をクリックして新しいナレッジ ベースを作成するか、 **[開く]** をクリックして既存のナレッジ ベースを開きます。  
  
##  <a name="Mapping"></a> マップ ステージ  
  
1.  **[データ ソース]** フィールドで、 **[SQL Server]** (既定値) または **[Excel ファイル]** を選択します。  
  
    > [!NOTE]  
    >  このページで、SQL Server データ ソースまたは Excel データ ソースへの接続を確立し、データ ソースの列とナレッジ ベースのドメインをマップします。 "マッピング" テーブルには、ナレッジを対応するドメインに追加するために分析するソース データベース内のすべての列が表示されます。 マッピングは、データ ソースの列とナレッジ ベースのドメインとの間で設定されます。  
  
2.  データ ソースが **SQL Server**の場合は、次の手順に従います。  
  
    1.  **[データベース]** フィールドで、ナレッジ ベースを作成するために分析するソース データベースを選択します。 ドロップダウン ボックスに、使用可能なデータベースの一覧が表示されます。 ソース データベースは、 [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)]と同じ SQL Server インスタンス上に存在する必要があります。 それ以外の場合、データベースはドロップダウン リストに表示されません。  
  
    2.  **[テーブル/ビュー]** フィールドで、ナレッジ ベースを作成するために分析するテーブルまたはビューを選択します。 データ クレンジングやデータ照合を実行するソース データベース全体ではなく、サンプル データとして使用するテーブルまたはビューを選択してください。 ドロップダウン ボックスに、選択したデータベースで使用可能なテーブルおよびビューの一覧が表示されます。  
  
3.  データ ソースが **Excel**の場合は、次の手順に従います。  
  
    1.  **[参照]** をクリックし、ナレッジ ベースを作成するために分析する Excel ファイルを選択します。 Excel ファイルを選択するには、 [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] コンピューターに Excel がインストールされている必要があります。 [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] コンピューターに Excel がインストールされていない場合は、[参照] ボタンを使用できません。Excel がインストールされていないことを通知するメッセージが、このテキスト ボックスの下に表示されます。  
  
    2.  Excel ファイルの最初の行に見出しのデータが含まれている場合は、 **[先頭の行を見出しとして使用]** チェック ボックスをオンにします。  
  
4.  **"マッピング"** テーブルで、次の手順に従って、ナレッジ検出を実行する各ソース列をナレッジ ベースのドメインにマップします。  
  
    1.  マッピングを作成するには、空の行の **[ソース列]** ボックスの一覧からソース列を選択し、同じ行の **[ドメイン]** ボックスの一覧からドメインを選択します。 ドメインが存在しない場合は、 **[ドメインの作成]** または **[複合ドメインの作成]** をクリックしてドメインを作成します。 詳細については、「 [ドメイン ルールを作成](../../2014/data-quality-services/create-a-domain-rule.md) 」または「 [複合ドメインの作成](../../2014/data-quality-services/create-a-composite-domain.md)」を参照してください。  
  
    2.  作成するマッピングごとに前の手順を繰り返します。 テーブルの行の数を変更するには、 **[列マッピングの追加]** をクリックするか、行を選択して **[選択した列マッピングを削除します]** をクリックします。 値が設定された行を選択した状態で **[選択した列マッピングを削除します]** をクリックすると、値が設定されていない行がある場合でも、選択した行が削除されます。  
  
        > [!NOTE]  
        >  ソース データを DQS ドメインにマッピングし、ナレッジ検出を実行できるのは、ソースのデータ型が DQS でサポートされていて、なおかつ DQS ドメインのデータ型と一致する場合だけです。 サポートされているデータ型の詳細については、「 [DQS ドメインに対してサポートされる SQL Server のデータ型と SSIS のデータ型](../../2014/data-quality-services/supported-sql-server-and-ssis-data-types-for-dqs-domains.md)」を参照してください。  
  
    3.  **[複合ドメインの表示と選択]** をクリックすると、定義されている複合ドメインが表示されます。 複合ドメインが定義されていない場合、このコントロールは使用できません。  
  
    4.  **[データ ソースのプレビュー]** をクリックすると、 **[テーブル/ビュー]** ボックスまたは **[Excel ファイル]** ボックスで選択したデータ ソースのすべてのデータがポップアップに表示されます。  
  
5.  **[次へ]** をクリックして、ナレッジ検出ウィザードの **[検出]** ページに進みます。 代わりに次の操作を行うこともできます。  
  
    -   **[キャンセル]** をクリックします。ナレッジ検出アクティビティが終了して作業内容が破棄され、DQS ホーム ページに戻ります。  
  
    -   **[閉じる]** をクリックします。作業内容が保存され、DQS ホーム ページに戻ります。 ナレッジ ベースがロックされ、 **[ナレッジ ベースを開く]** 画面のナレッジ ベース テーブルのナレッジ ベースの状態が **[検出 - マッピング]** になります。 **[閉じる]** をクリックした後でドメイン管理アクティビティを実行するには、 **[ナレッジ ベースを開く]** 画面で **[ナレッジ検出]** をクリックします。さらに、 **[ナレッジ ベース管理: ドメイン用語の管理]** 画面で、 **[完了]** をクリックし、ナレッジ ベースを発行する場合は **[はい]** を、作業内容をナレッジ ベースに保存して終了する場合は **[いいえ]** をクリックします。  
  
##  <a name="Discover"></a> 検出ステージ  
  
1.  **[開始]** をクリックして、データ ソースを分析します。  
  
    > [!NOTE]  
    >  検出は、 **[マップ]** ページの **"マッピング"** テーブルに入力した列に対して実行されます。 それぞれの列にマップされているドメインに、検出によって取得されたナレッジが設定されます。 ドメインが複合ドメインである場合は、その複合ドメインを構成する個々のドメインにナレッジが追加されます。  
  
2.  検出プロセスが実行されている間、検出の各手順 (" **レコードの前処理中**"、" **ドメイン ルールを実行中**"、および " **検出を実行中**") について表示される完了状態を確認します。 各手順の完了率と完了状態が表示されます。  
  
3.  分析が完了したら、完了統計の下のステータス行で、正常に完了したかどうかを確認します。  
  
    > [!NOTE]  
    >  ファイルのアップロードが完了する前に画面を移動すると、ファイルのアップロード プロセスが終了します。  
  
4.  分析の完了後、 **[プロファイラー]** タブの統計情報でデータの状態を確認します。 詳細については、「 **DQS でのデータ プロファイルと通知**」を参照してください。  
  
5.  分析が完了すると、 **[開始]** ボタンが **[再起動]** ボタンに変わります。 **[再起動]** をクリックすると、分析プロセスが再び実行されます。 ただし、前回の分析の結果はまだ保存されていないため、 **[再起動]** をクリックすると前のデータが失われます。 続行するには、ポップアップ画面で **[はい]** をクリックします。 分析の実行中にページを移動しないでください。ページを移動すると、分析プロセスが終了します。  
  
6.  **[次へ]** をクリックして、ナレッジ検出ウィザードの **[ドメイン値の管理]** ページに進みます。 このページでは、ナレッジ ベースのドメインに追加されたナレッジを変更できます。 代わりに次の操作を行うこともできます。  
  
    -   **[キャンセル]** をクリックします。ナレッジ検出アクティビティが終了して作業内容が破棄され、DQS ホーム ページに戻ります。  
  
    -   **[閉じる]** をクリックします。作業内容が保存され、DQS ホーム ページに戻ります。 ナレッジ ベースがロックされ、 **[ナレッジ ベースを開く]** 画面のナレッジ ベース テーブルのナレッジ ベースの状態が **[検出 - 検出]** になります。 **[閉じる]** をクリックした後でドメイン管理アクティビティを実行するには、 **[ナレッジ ベースを開く]** 画面で **[ナレッジ検出]** をクリックします。さらに、 **[ナレッジ ベース管理: ドメイン用語の管理]** 画面で、 **[完了]** をクリックし、ナレッジ ベースを発行する場合は **[はい]** を、作業内容をナレッジ ベースに保存して終了する場合は **[いいえ]** をクリックします。  
  
    -   [戻る] をクリックして **[検出]** ページに戻ります。  
  
##  <a name="Manage"></a> データの検出結果の管理ステージ  
 ナレッジ検出アクティビティの実行後、値を次のように変更できます。  
  
-   値の一覧にドメイン値を追加するか、値を選択して一覧から削除します。  
  
-   DQS 検出プロセスによって判定されたドメイン値の状態を、"適切"、"エラー"、または "無効" に変更します。  
  
-   "エラー" または "無効" の値の置換値を入力します。  
  
-   2 つ以上の値をシノニムとして設定し、検出プロセスによって設定された先頭の値を変更します。その結果、先頭の値によってシノニム値が置き換えられます (ドメインを作成したときに **[先頭の値を使用]** プロパティを設定した場合)。  
  
-   Excel ファイルからドメイン値をインポートします。  
  
 **"値"** テーブルには、ナレッジ ベースの 1 つのドメインに追加されたナレッジが表示されます。 ナレッジを表示するドメインは、左側のペインにあるドメイン リストで選択します。 フィールドの列を以下に示します。  
  
-   **[値]** 列: 選択したドメインに検出プロセスによってデータ サンプルのフィールドから追加されたすべての値が表示されます。 "エラー" と見なされた値は、"適切" と見なされた値のシノニムとして表示されます。  
  
-   **[頻度]** 列: ドメインがマップされているサンプル データベース フィールドの値のインスタンスの数が表示されます。 複合ドメインの場合は、頻度が 20 以上の値だけが表示されます。 頻度データを使用できるのは、ナレッジ検出プロセスがサンプル データベースへの接続を保持しているためです。 ドメイン管理プロセスはサンプル データベースへの接続を持たないため、[ドメイン管理] 画面の [ドメイン値] タブのドメイン テーブルでは頻度データを使用できません。  
  
-   **[種類]** 列: 検出プロセスによって判別された値の状態が表示されます。 緑のチェック マークは、値の状態が "適切" または "修正済み" であることを示します。赤い十字型は、値の状態が "エラー" であることを示します。感嘆符付きのオレンジ色の三角形は、値が "無効" であることを示します。 "無効" の値は、ドメインのデータ要件に準拠していません。 "エラー" の値は、有効である可能性がありますが、データ上の理由から適切な値ではありません。  
  
-   **[次に修正]** 列: "エラー" または "無効" としてマークされた元の値から変更される適切な値が表示されます。 DQS では、検出プロセスの結果として適切な値を提案することができます。  
  
 検出結果を管理するには、次の手順に従います。  
  
1.  左側の **[ドメイン リスト]** ペインで、ドメイン値を設定するドメインを選択します。 次のようにして、表示される値を変更することができます。  
  
    -   **[フィルター]** ボックスの一覧で状態を選択して、テーブルに表示する結果を状態に基づいて選択します。  
  
    -   検索する 1 つ以上の文字を [検索] ボックスに入力して、確認または変更するデータを検索します。 それらの文字が、含まれている場所に関係なく、表示されている値で強調表示されます。  
  
    -   **[新規のみ表示]** をクリックします。テーブルに表示される値が、以前のセッションではなく現在のセッションで検出された値のみに制限されます。  
  
    -   **[すべて展開]** をクリックして、シノニムのグループのすべての値を表示するか (現在折りたたまれている場合)、 **[すべて折りたたみ]** をクリックして、シノニムのグループの値を先頭の値以外すべて非表示にします (現在展開されている場合)。  
  
    -   **[ドメイン値の変更履歴パネルの表示/非表示]** をクリックして、"値" テーブルの下部に表示されるプレビュー ポップアップで、ドメイン値のコレクションに加えられた最近の変更を確認します。  
  
2.  **[フィルター]** を **[エラー]** に設定して、Data Quality Services の修正案を検索します。 値が実際にエラーであることと、 **[次に修正]** 列の値が適切であることを確認します。  
  
3.  **[フィルター]** を **[すべての値]** に設定して、値の状態が適切であることを確認します。 値の状態を変更するには、値を選択し、 **[選択したドメインの値を修正済みとして設定します]** (チェック マーク)、 **[選択したドメインの値をエラーとして設定します]** (十字型)、または **[選択したドメインの値を無効として設定します]** (三角形) をクリックします。  
  
4.  値の状態を変更するには、次の手順に従います。  
  
    1.  **[選択したドメインの値を修正済みとして設定します]**: 値の状態を "エラー" または "無効" から "適切" に変更するには、値を選択し、アイコン バーの下矢印または [種類] ボックスをクリックして、一覧で **[選択したドメインの値を修正済みとして設定します]** (チェック マーク) をクリックします。 その "エラー" または "無効" の値が "適切" の値とグループ化される場合は、この操作の後でその値を削除します。  
  
    2.  **[選択したドメインの値をエラーとして設定します]**: 値の状態を "適切" または "無効" から "エラー" に変更するには、値を選択し、アイコン バーの下矢印または [種類] ボックスをクリックして、一覧で **[選択したドメインの値をエラーとして設定します]** (十字型) アイコンをクリックします。 **[次に修正]** 列に修正を入力することも、空のままにしておくこともできます。  
  
    3.  **[選択したドメインの値を無効として設定します]**: 値の状態を "適切" または "エラー" から "無効" に変更するには、値を選択し、アイコン バーの下矢印または [種類] ボックスをクリックして、一覧で **[選択したドメインの値を無効として設定します]** (三角形) アイコンをクリックします。 **[次に修正]** 列に修正を入力することも、空のままにしておくこともできます。  
  
    4.  **[次に修正]**: 値を "エラー" または "無効" として設定した後、 **[次に修正]** 列に新しい値を入力すると、 その置換値のための新しい行が追加され、"適切" として指定されて、2 つの値がグループ化されます。 新しい値は先頭の値として太字で表示され、"エラー" または "無効" の値はインデントされます。  
  
5.  値をシノニムのグループとして指定するには、"適切" の値を複数選択し、次の手順に従います。  
  
    -   **[選択したドメイン値をシノニムとして設定]**: クリックすると、選択した値がシノニムとして設定されます。 値の 1 つが先頭の値として指定され、その他の値がその値に置き換えられます。  
  
        > [!NOTE]  
        >  グループ内の複数の値とグループ外の値を選択してシノニムとして設定すると、正しくないエラー メッセージが表示されますが、 そのエラー メッセージのポップアップを閉じると、それらの値がシノニムとして正しく設定されます。  
  
    -   **[選択したシノニム間の関係を解除]**: クリックすると、シノニムの指定が取り消されます。  
  
    -   **[選択したドメイン値をグループの先頭の値として設定]**: グループの先頭の値を変更するには、先頭の値として指定されていないグループ内の値を選択し、 **[選択したドメイン値をグループの先頭の値として設定]** をクリックします。  
  
6.  **[スペル チェック]**: [ドメインのプロパティ] ページで [スペル チェック] を有効にした場合は、修正案がある値の下に赤い波線が表示されます。 その値を右クリックし、必要に応じて修正を選択します。 修正を選択すると、値の種類が "エラー" になり (最初から "エラー" の場合はそのまま)、その修正が **[次に修正]** 列に追加されます。 下矢印をクリックすると、その他の修正案が表示されます。 手動で修正を入力してスペル チェックの辞書に追加すると、修正として選択できるようになります。 詳細については、「 [DQS のスペル チェックの使用](../../2014/data-quality-services/use-the-dqs-speller.md) 」および「 [ドメインのプロパティを設定する](../../2014/data-quality-services/set-domain-properties.md)」を参照してください。  
  
    > [!NOTE]  
    >  スペル チェックを使用するには、 **[ドメインのプロパティ]** ページで有効にする必要があります。 **[ドメインのプロパティ]** ページで無効になっている場合は、 **[データの検出結果を管理します]** ページで **[スペル チェックを有効/無効にします]** アイコンをクリックして有効にすることもできます。  
  
7.  **[新しいドメインの値を追加します]**: ドメインに新しい値を追加するには、 **[新しいドメインの値を追加します]** をクリックします。テーブルの末尾に行が追加されます。 その行に値を入力すると、行がアルファベット順に並べ替えられます。  
  
8.  **[ドメインの値を Excel からインポートします]**: Excel スプレッドシートから新しい値を追加するには、 **[値をインポートします]** アイコンの下矢印をクリックし、 **[ドメインの値を Excel からインポートします]** を選択します。 ファイル名を入力し、必要に応じて **[先頭の行を見出しとして使用]** を選択し、 **[OK]** をクリックします。 詳細については、「 [値を Excel ファイルからドメインへインポートする](../../2014/data-quality-services/import-values-from-an-excel-file-into-a-domain.md)」をご参照ください。  
  
9. **[プロジェクトの値のインポート]**: データ品質プロジェクトから新しい値を追加するには、 **[値をインポートします]** アイコンの下矢印をクリックし、 **[プロジェクトの値のインポート]** を選択します。 ファイル名を入力し、必要に応じて **[先頭の行を見出しとして使用]** を選択し、 **[OK]** をクリックします。 値をインポートするプロジェクトを選択し、 **[OK]** をクリックします。 インポートされた値が表示されます。 **[完了]** をクリックします。 詳細については、「プロジェクトの値をドメインにインポートする」を参照してください。  
  
10. **[選択したドメインの値を削除します]**: ドメインの既存の値を削除するには、削除する値を選択し、 **[選択したドメインの値を削除します]** をクリックします。 DQS_NULL というエントリは削除できません。したがって、削除する値を複数選択した場合に、選択した値の中に DQS_NULL が含まれていると、操作が失敗します。  
  
11. ナレッジ検出アクティビティを完了するには、 **[完了]** をクリックします。 まだ確認されていないドメインがある場合は、ポップアップ画面が表示されます。 確認を続ける場合は **[はい]** を、先に進む場合は **[いいえ]** をクリックします。 [いいえ] をクリックすると、また別のポップアップ画面が表示されます。そこで次のいずれかを選択します。  
  
    1.  **[発行]**: 現在のユーザーまたは他のユーザーに対してナレッジ ベースが発行されます。 ナレッジ ベースはロックされず、(ナレッジ ベース テーブルの) ナレッジ ベースの状態が空白に設定されます。ドメイン管理アクティビティとナレッジ検出アクティビティの両方を使用できるようになります。 ホーム ページに戻ります。 プロセスを完了するには、ポップアップ画面で **[はい]** をクリックします。  
  
    2.  **[いいえ]**: 作業内容が保存され、ナレッジ ベースはロックされたままになります。ナレッジ ベースの状態は [作業中] に設定されます。 ドメイン管理アクティビティとナレッジ検出アクティビティの両方を使用できるようになります。 ホーム ページに戻ります。  
  
    3.  **[キャンセル]**: ポップアップ画面が閉じて、 **[ドメイン値の管理]** ページに戻ります。  
  
12. 代わりに次の操作を行うこともできます。  
  
    -   **[キャンセル]** をクリックします。ナレッジ検出アクティビティが終了して作業内容が破棄され、DQS ホーム ページに戻ります。  
  
    -   **[閉じる]** をクリックします。作業内容が保存され、DQS ホーム ページに戻ります。 ナレッジ ベースがロックされ、 **[ナレッジ ベースを開く]** 画面のナレッジ ベース テーブルのナレッジ ベースの状態が **[検出 - 値管理]** になります。  
  
    -   **[戻る]** をクリックして **[検出]** ページに戻ります。 **[閉じる]** をクリックした後でドメイン管理アクティビティを実行するには、 **[ナレッジ ベースを開く]** 画面で **[ナレッジ検出]** をクリックします。さらに、 **[ナレッジ ベース管理: ドメイン用語の管理]** 画面で、 **[完了]** をクリックし、ナレッジ ベースを発行する場合は **[はい]** を、作業内容をナレッジ ベースに保存して終了する場合は **[いいえ]** をクリックします。  
  
##  <a name="FollowUp"></a> 補足情報: ナレッジ検出の実行後  
 コンピューター支援型のナレッジ検出プロセスでナレッジ ベースにナレッジを追加したら、そのナレッジ ベースをすぐにクレンジング プロジェクトに使用することも、クレンジングを実行する前にドメイン管理を実行することもできます。 データ クレンジングまたはドメイン管理について詳しくは、「[データ クレンジング](../../2014/data-quality-services/data-cleansing.md)」または「[ドメインの管理](../../2014/data-quality-services/managing-a-domain.md)」をご覧ください。  
  
##  <a name="Meaning"></a> "適切"、"エラー"、"無効" の各値の意味  
 **[ドメイン値]** ページの **"値"** テーブルの値には、" **適切** "、" **エラー**"、" **無効**" のいずれかの **種類**がそれぞれ割り当てられています。 値の種類は、最初はナレッジ検出アクティビティによって生成されますが、必要に応じて変更できます。 最終的な種類は、検出とインタラクティブな変更の両方に基づいて、クレンジング アクティビティによって生成されます。 これらの設定の意味を以下に示します。  
  
-   **適切:** ドメインに属している、構文エラーのない値です。 たとえば、City ドメインの "Chicago" は "適切" です。  
  
-   **エラー:** ドメインに属している、正しくない値です。 たとえば、City ドメインの "Chicago" が "Shicago" になっている場合は "エラー" になります。 DQS では、検出プロセスで構文エラーおよび関連付けられた修正が検出された場合に、値が "エラー" として指定されます。 構文エラーには、スペルミスなどがあります。  
  
-   **無効:** ドメインに属していない、修正が関連付けられていない値です。 たとえば、City ドメインの値 "12345" は "無効" です。 DQS では、ドメイン ルールが失敗した場合に値が "無効" として指定されます。  
  
 値の種類は、他の 2 つのいずれかに手動で変更できます。 手動操作には、妥当性とエラーのセマンティクスは適用されません。 したがって、状態を変更せずに "無効" の値の修正を入力したり、 ドメイン ルールが失敗していない値を "無効" として指定したり、 検出プロセスで構文エラーが見つかっていない値を "エラー" として指定したりすることができます。 "適切" としてマークされている "エラー" の値の修正を、状態を変更せずに削除することもできます。  
  
 **[クレンジング]** アクティビティの **[結果の管理と表示]** ページでインタラクティブなデータ クレンジングを実行する際には、 **[結果の管理と表示]** ページの **[無効]** タブに "無効" と "エラー" の両方の値が含まれます。  
  
##  <a name="Display"></a> How to Display the Appropriate Values  
 次のようにして表示を変更することができます。  
  
-   **[フィルター]** ボックスの一覧で状態を選択して、テーブルに表示する結果を状態に基づいて**絞り込み**ます。  
  
-   **[検索]** する 1 つ以上の文字を **[検索]** ボックスに入力して、確認または変更するデータを検索します。 それらの文字が、含まれている場所に関係なく、表示されている値で強調表示されます。  
  
-   **[新規のみ表示]** をクリックします。テーブルに表示される値が、以前のセッションではなく現在のセッションで検出された値のみに制限されます。  
  
-   **[すべて展開]** をクリックして、シノニムのグループのすべての値を表示します (現在折りたたまれている場合)。  
  
-   **[すべて折りたたみ]** をクリックして、シノニムのグループの値を先頭の値以外すべて非表示にします (現在展開されている場合)。  
  
-   **[ドメイン値の変更履歴パネルの表示/非表示]** をクリックして、"値" テーブルの下部に表示されるプレビュー ポップアップで、ドメイン値のコレクションに加えられた最近の変更を確認します。  
  
##  <a name="Profiler"></a> プロファイラーの統計情報  
 [プロファイラー] タブには、ソース データの品質を示す統計情報が表示されます。 これらの統計情報は、ナレッジ ベースの品質を測定するものではありません。 ナレッジ検出のプロファイリングは、完全性と一意性を調査するものであり、 精度を測定するものではありません。 ナレッジ マネージメントのプロファイリングは、ナレッジ ベースのナレッジの構築および強化に対するデータ ソースの利用価値を評価するのに役立ちます。  
  
 **[プロファイラー]** タブには、検出プロセスの以下の統計情報がフィールド別およびドメイン別に表示されます。  
  
-   **レコード**: データ サンプルで検出されたレコードの数  
  
-   **合計値**: 各フィールドおよび全体で検出された値の合計  
  
-   **新しい値**: 各フィールドおよびマップされたすべてのフィールドの合計値に占める前回の検出プロセス以降の新しい値の数および割合  
  
-   **一意の値**: 各フィールドおよびマップされたすべてのフィールドの合計値に占める一意の値の数および割合  
  
-   **新しい一意の値**: 各フィールドおよびマップされたすべてのフィールドの一意の値に占める前回の検出プロセス以降の新しい値の数および割合  
  
-   **ドメイン値で有効**: 各フィールドおよびマップされたすべてのフィールドの合計値に占める有効な値の数および割合  
  
 フィールドの統計情報には、次の情報が含まれます。  
  
-   **フィールド**: ソース データベースのフィールドの名前  
  
-   **ドメイン**: フィールドにマップされるドメインの名前  
  
-   **新規**: 新しい値の数と、フィールドの既存の値に対する割合  
  
-   **一意**: フィールドの一意のレコードの数と、全体に占める割合  
  
-   **ドメインで有効**: 有効なドメイン値の数と、全体に占める割合  
  
-   **完全**: 照合のテストのためにマップされた各ソース フィールドの完全性  
  
 ナレッジ検出のプロファイリングでは、完全性について調べることができます。 プロファイリングの結果、比較的不完全であることがわかったフィールドは、データ品質プロジェクトのナレッジ ベースから削除することができます。 複合ドメインでは、プロファイリングから得られる完全性の統計情報を必ずしも信頼できません。 完全性の統計情報が必要な場合は、複合ドメインの代わりに単一ドメインを使用します。 複合ドメインを使用する必要がある場合は、プロファイリング用に単一ドメインのナレッジ ベースを作成して完全性を確認し、クレンジング プロセス用に複合ドメインのドメインを別途作成します。 たとえば、複合ドメインを使用したプロファイリングで住所レコードの完全性が 95% と示されたとしても、それよりはるかに不完全な列 (郵便番号の列など) がレコードに含まれている可能性があります。 この例では、単一ドメインを使用して郵便番号の列の完全性を測定することができます。 精度は複数の列でまとめて測定できるため、プロファイリングから得られる複合ドメインの精度の統計情報は信頼できます。 このデータの値は合成集約に含まれるため、複合ドメインで精度を測定できます。  
  
 統計情報は、次のフェーズで [プロファイラー] タブに表示されます。  
  
-   " **レコードの前処理中** " フェーズ: データが読み込まれてインデックスが設定されます。 この処理は 1 レコードずつ (または 1 バッチずつ) 行われるため、レコードごとに進行状況が表示されます。 この手順の実行中に、 **[ドメインで有効]** の値を除くほとんどのプロファイル データが生成されます。  
  
-   " **ドメイン ルールを実行中** " フェーズ: すべてのドメイン ルールが各ドメイン値のアトミック単位として実行されるため、 **[ドメインで有効]** 列の値が設定されます。  
  
-   " **検出を実行中** " フェーズ: [プロファイラー] タブのデータは更新されません。検出された構文エラーは、ウィザードの次の手順 (**[ドメイン値の管理]** フェーズ) で確認できます。  
  
 ナレッジ検出アクティビティでは、以下の状況で通知が生成されます。  
  
-   フィールドに新しい値がない場合。そのフィールドをマッピングから除去することをお勧めします。  
  
-   フィールドに新しい値がほとんどない場合。そのフィールドをマッピングから除去できます。  
  
-   フィールドが空の場合。そのフィールドをマッピングから除去することをお勧めします。  
  
-   フィールドの完全性スコアが非常に低い場合。そのフィールドをマッピングから除去できます。  
  
-   フィールド内のすべての値が無効である場合。マッピングと、ドメイン ルールとフィールドの内容の関連を確認する必要があります。  
  
-   フィールド内の有効な値が少ない場合。マッピングと、ドメイン ルールとフィールドの内容の関連を確認する必要があります。  
  
 プロファイリングの詳細については、「 [DQS でのデータ プロファイルと通知](../../2014/data-quality-services/data-profiling-and-notifications-in-dqs.md)」を参照してください。  
  
  