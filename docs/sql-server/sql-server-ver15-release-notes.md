---
title: SQL Server 2019 リリース ノート | Microsoft Docs
ms.date: 11/06/2018
ms.prod: sql
ms.reviewer: ''
ms.technology: release-landing
ms.topic: article
ms.assetid: 13942af8-5a40-4cef-80f5-918386767a47
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
monikerRange: = sql-server-ver15 || = sqlallproducts-allversions
ms.openlocfilehash: 2c21ac917845b8162348b93fec3b868f1f748592
ms.sourcegitcommit: 50b60ea99551b688caf0aa2d897029b95e5c01f3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "51703860"
---
# <a name="sql-server-2019-preview-release-notes"></a>SQL Server 2019 プレビュー リリース ノート

[!INCLUDE[tsql-appliesto-ssver15-xxxx-xxxx-xxx](../includes/tsql-appliesto-ssver15-xxxx-xxxx-xxx.md)]

この記事では、[!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] Community Technology Preview (CTP) リリースに関する制限事項と既知の問題について説明します。 関連情報については、次を参照してください。
- [SQL Server 2019 の新機能](../sql-server/what-s-new-in-sql-server-ver15.md)

> [!NOTE]
> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] のプレビュー リリースは、次期リリースの機能を体験していただく目的で提供されるものです。 運用環境向けとしては、サポートもライセンスもされません。 次のシナリオは明示的に非サポートとなっています。
>
> - 古いバージョンの [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] とのサイド バイ サイド インストール
> - SQL Server の既存のインスタンスを任意のバージョンからアップグレード

**[!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] をお試しください**
- [![Evaluation Center からダウンロードする](../includes/media/download2.png)](https://go.microsoft.com/fwlink/?LinkID=862101) [[!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] をダウンロードして Windows にインストールする](https://go.microsoft.com/fwlink/?LinkID=862101)
- [Red Hat Enterprise Server](../linux/quickstart-install-connect-red-hat.md)、[SUSE Linux Enterprise Server](../linux/quickstart-install-connect-suse.md)、および [Ubuntu](../linux/quickstart-install-connect-ubuntu.md) の Linux にインストールする。
- [Docker で SQL Server 2019 を実行する](../linux/quickstart-install-connect-docker.md)。

## <a name="ctp-21-november-2018"></a>CTP 2.1 (2018 年 11 月)
[!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] CTP 2.1 は、[!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] の最新のパブリック リリースです。

[!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] CTP 2.1 は評価版としてのみ使用可能です。 他のエディションは提供されません。 CTP 2.1 のサポートについては、ご利用のインストール メディアの license_Eval.rtf で説明されています。

限定的なサポートは、次のいずれかの場所で提供される場合があります。

- フォーラム
  - [SQL Server フィードバック](https://aka.ms/sqlfeedback)
  - [SQL Server の概要](https://social.msdn.microsoft.com/Forums/sqlserver/en-US/home?forum=sqlgetstarted)
  - [Transact-SQL](https://social.msdn.microsoft.com/Forums/sqlserver/en-US/home?forum=transactsql)
  - [SQL Server のドキュメント](https://social.msdn.microsoft.com/Forums/sqlserver/en-US/home?forum=sqldocumentation)

- または、[#sqlhelp](https://twitter.com/search?q=%23sqlhelp) を付けて [@SQLServer](https://twitter.com/SQLServer) にツイートしてください

### <a name="documentation-ctp-21"></a>ドキュメント (CTP 2.1)

- **問題およびユーザーへの影響:** SQL Server 2019 (15.x) のドキュメントは制限されており、コンテンツは [!INCLUDE[ssSQL17](../includes/sssql17-md.md)] ドキュメント セットに付属しています。 記事の中で SQL Server 2019 (15.x) に固有のコンテンツは、**適用対象**で言及されています。

- **問題およびユーザーへの影響**: [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]ドキュメントはバージョンによってフィルター処理できます。 各ドキュメント ページの左上にあるコントロールを使用し、要件に応じてフィルター処理してください。 

- **問題およびユーザーへの影響:** SQL Server 2019 (15.x) の場合、オフライン コンテンツを利用できません。

### <a name="hardware-and-software-requirements"></a>ハードウェアとソフトウェアの要件

- **問題およびユーザーへの影響**: ハードウェア要件とソフトウェア要件は現在レビュー段階であり、製品リリース用の最終版ではありません。

  - **ハードウェア**
    - [Windows - プロセッサ、メモリ、およびオペレーティング システムの要件](../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md#pmosr)
    - [Linux - システム要件](../linux/sql-server-linux-setup.md#system)
  - **ソフトウェア**
    - Windows Server 2016 以降。 その他の要件については、[SQL Server のインストール要件](../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md)に関する記事をご覧ください
    - Microsoft .NET Framework 4.6.2。 [ダウンロード センター](https://www.microsoft.com/download/details.aspx?id=53344)から入手できます。
    - Linux については、[サポートされている Linux プラットフォーム](../linux/sql-server-linux-setup.md#supportedplatforms)に関する記事をご覧ください

### <a name="floating-point-results"></a>浮動小数点の結果

- **問題およびユーザーへの影響**: SQL Server 2019 プレビューでは、最新のコンパイラを使用して、SQL Server がビルドされます。 新しいコンパイラでコンパイルされたコードからは、SQL Server の以前のバージョンとは異なる浮動小数点の数値が返される場合があります。 動作の変更は、今後の CTP での新しい互換性レベル (150) に制限されます。

- **回避策**: なし

- **適用対象**: SQL Server 2019 CTP 2.1

### <a name="sql-server-integration-services-ssis-page-deployment-after-switching-db-to-single-user-mode-and-then-switching-back"></a>DB をシングル ユーザー モードに切り替えてから再び元のモードに切り替えた後での SQL Server Integration Services (SSIS) ページの配置

- **問題およびユーザーへの影響**: SSISB をシングル ユーザー モードから再びマルチ ユーザー モードに切り替えた後、パッケージを配置すると、次のエラーが報告される場合があります。

  `Cannot continue the execution because the session is in the kill state.`

- **回避策**: SQL Server のインスタンスを停止し、再起動してから、SSISDB をマルチ ユーザー モードに切り替えます。 

- **適用対象**: SQL Server 2019 プレビュー CTP 2.1


### <a name="udf-inlining"></a>UDF のインライン化 

- **問題およびユーザーへの影響**: インライン化されたユーザー定義関数の呼び出しを入れ子にすると、セキュリティが正しく検証されないというコーナー ケースのシナリオがあります。
  
- **回避策**: そのような UDF については、`INLINE = OFF` 設定を使用して UDF のインライン化を無効にします。

- **適用対象**: SQL Server 2019 CTP 2.1

### <a name="lightweight-query-profiling-infrastructure"></a>軽量クエリ プロファイリング インフラストラクチャ

- **問題およびユーザーへの影響**: コマンド `ALTER DATABASE SCOPED CONFIGURATION SET LIGHTWEIGHT_QUERY_PROFILING = ON` を実行すると構文エラーが返されます。 このコマンドの実行に依存するシナリオはすべて失敗します。

  > [!NOTE]
  > 現時点では、軽量クエリ プロファイリング インフラストラクチャ (LWP) を個別のデータベース レベルで制御することはできません。すべてのデータベースについて既定で有効になります。 LWP の詳細については、「[SQL Server 2019 の新機能](../sql-server/what-s-new-in-sql-server-ver15.md)」を参照してください。

- **回避策**: [!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] CTP では回避策はありません。

- **適用対象**: [!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] CTP 2.1 および CTP 2.0。

### <a name="utf-8-collations"></a>UTF-8 対応の照合順序

- **問題およびユーザーへの影響**: UTF-8 対応の照合順序は、他の [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] 機能とは併用できない場合があります。 UTF-8 は、次の [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] 機能が使用されている場合にはサポートされません。

  - SQL Server のレプリケーション
  - Linked Server
  - インメモリ OLTP
  - PolyBase 用の外部テーブル

    また、Azure Data Studio および SSDT では、UTF-8 対応の照合順序を選択するための UI は現在のところサポートされていません。 最新バージョンの SSMS では、UTF-8 対応の照合順序を UI で選択することができます。

- **回避策**: [!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] CTP では回避策はありません。

- **適用対象**: [!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] CTP 2.1、CTP 2.0。

### <a name="sql-graph"></a>SQL Graph

- **問題およびユーザーへの影響**: DacFx に依存しているツール (インポート/エクスポートなど) は、新しいグラフ機能 (エッジ制約や DML マージ) に対しては機能しません。 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] でのスクリプト記述は機能しない可能性があります。

- **回避策**: [!INCLUDE[tsql](../includes/tsql-md.md)] スクリプトを記述し、[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] または SQLCMD を使用して、それらをサーバーに対して実行することは可能です。 エッジ制約を作成したり、新しいマージ DML 構文を使用したり、あるいはグラフ オブジェクトに基づく派生テーブル/ビューを作成したりするデータベース オブジェクトについては、エクスポートやインポートは機能しません。 このようなオブジェクトは、[!INCLUDE[tsql](../includes/tsql-md.md)] スクリプトを使用して、データベース内に手動で作成する必要があります。 

- **適用対象**: [!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] CTP 2.1、2.0。

### <a name="always-encrypted-with-secure-enclaves"></a>セキュア エンクレーブを使用する Always Encrypted

- **問題およびユーザーへの影響**: 高度な計算は、いくつかのパフォーマンス最適化について保留中であり、機能が制限 (インデックス作成がないなど) されていて、現在既定で無効になっています。

- **回避策**: 高度な計算を有効にするには、`DBCC traceon(127,-1)` を実行します。 詳細については、[高度な計算の有効化](../relational-databases/security/encryption/configure-always-encrypted-enclaves.md#configure-a-secure-enclave)に関する記事をご覧ください。

- **適用対象**: [!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] CTP 2.1、2.0。

### <a name="sql-server-integration-service---fuzzy-lookup-transformation"></a>SQL Server Integration Service - あいまい参照変換

- **問題およびユーザーへの影響**: インデックスを再利用するようにあいまい参照変換が設定されている場合、そのあいまい参照変換は失敗し、次のエラーが返されます。

  `The specified delimiters do not match the delimiters used to build the pre-existing match index "...". This error occurs when the delimiters used to tokenize fields do not match. This can have unknown effects on the matching behavior or results.`

- **回避策**: なし

- **詳細情報**: なし  

- **適用対象**: [!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] CTP2.1

## <a name="ctp-20-september-2018"></a>CTP 2.0 (2018 年 9 月)

[!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] CTP 2.0 は、[!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] の最初のパブリック リリースです。

### <a name="sql-server-integration-services-ssis-transfer-database-task"></a>SQL Server Integration Services (SSIS) の Transfer Database Task

- **問題およびユーザーへの影響**: `Transfer Database Task` が `Database Online` モードでデータベースを転送するように構成されている場合、次のエラーが発生し、処理が失敗する可能性があります。

  >タスクの Execute メソッドが失敗し、エラー コード 0x80131500 (データの転送中にエラーが発生しました。 詳細については、内部例外を参照してください。) が返されました。 タスクの Execute メソッドは成功し、"out" パラメーターを使用して結果が示される必要があります。

- **回避策**: サーバーで `DBCC TRACEON (7416,-1)` を実行し、もう一度やり直してください。

- **適用対象**: [!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] CTP 2.0。

[!INCLUDE[get-help-options-msft-only](../includes/paragraph-content/get-help-options.md)]

![MS_Logo_X-Small](../sql-server/media/ms-logo-x-small.png)
