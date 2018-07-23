---
title: プログラムによるパッケージの実行と管理 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- docset-sql-devref
- integration-services
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 1a08c75e-ce8c-45ee-81bd-32248bbdb2b2
caps.latest.revision: 24
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 659952d44fa2c530a313a4f6bd29cfbfddf9d236
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37239152"
---
# <a name="running-and-managing-packages-programmatically"></a>プログラムによるパッケージの実行と管理
  開発環境以外で [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] パッケージを管理および実行する必要がある場合は、プログラムでパッケージを操作できます。 その場合、次に示すいくつかの方法があります。  
  
-   既存のパッケージを読み込んで、変更せずに実行します。  
  
-   既存のパッケージを読み込み、再構成 (異なるデータ ソースなどに対して) してから実行します。  
  
-   新しいパッケージを作成し、オブジェクト単位やプロパティ単位でコンポーネントを追加および構成し、保存してから実行します。  
  
 数行のコードを記述するだけで、クライアント アプリケーションから既存のパッケージを読み込んで実行することができます。  
  
 ここでは、プログラムで既存のパッケージを実行する方法、および他のアプリケーションからデータ フローの出力にアクセスする方法について説明します。 詳細なプログラミング オプションとして、「[プログラムによるパッケージの作成](../building-packages-programmatically/building-packages-programmatically.md)」トピックの説明に従い、1 行ずつプログラムを指定して [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] パッケージを作成できます。  
  
 また、保存されているパッケージ、実行中のパッケージ、およびパッケージ ロールを管理するためにプログラムによって実行できる他の管理タスクについても説明します。  
  
## <a name="running-packages-on-the-integration-services-server"></a>Integration Services サーバー上のパッケージの実行  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] サーバーにパッケージを配置するときに、<xref:Microsoft.SqlServer.Management.IntegrationServices> 名前空間を使用してパッケージをプログラムで実行できます。 Microsoft.SqlServer.Management.IntegrationServices アセンブリは、.NET Framework 3.5 でコンパイルされます。 .NET Framework 4.0 アプリケーションを構築する場合は、プロジェクト ファイルに直接アセンブリ参照を追加する必要がある場合があります。  
  
 名前空間を使用して、[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] サーバーで [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] プロジェクトを配置および管理することもできます。 名前空間とコード スニペットの概要については、blogs.msdn.com のブログ エントリ「[SSIS カタログ マネージド オブジェクト モデルの概要](http://go.microsoft.com/fwlink/?LinkId=253122)」を参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [ローカル実行とリモート実行の相違点について](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md)  
 パッケージをローカルで実行する場合とサーバーで実行する場合の重要な違いについて説明します。  
  
 [プログラムによるローカル パッケージの読み込みと実行](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md)  
 ローカル コンピューターのクライアント アプリケーションから既存のパッケージを実行する方法について説明します。  
  
 [プログラムによるリモート パッケージの読み込みと実行](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)  
 クライアント アプリケーションから既存のパッケージを実行し、パッケージがサーバーで実行できるようにする方法について説明します。  
  
 [ローカル パッケージの出力の読み込み](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
 ローカル コンピューターでパッケージを実行し、DataReader 変換先および DtsClient 名前空間を使用して、データ フローの出力をクライアント アプリケーションに読み込む方法について説明します。  
  
 [プログラムによる使用可能なパッケージの列挙](../run-manage-packages-programmatically/enumerating-available-packages-programmatically.md)  
 ph x="1" /&gt; サービスによって管理されている使用可能なパッケージを検出する方法について説明します。  
  
 [プログラムによるパッケージとフォルダーの管理](../run-manage-packages-programmatically/managing-packages-and-folders-programmatically.md)  
 パッケージとフォルダーを作成、名前変更、および削除する方法について説明します。  
  
 [プログラムによるパッケージの実行の管理](../run-manage-packages-programmatically/managing-running-packages-programmatically.md)  
 現在実行中のパッケージの一覧表示、プロパティの分析、および実行中のパッケージの停止方法について説明します。  
  
 [プログラムによるパッケージのロールの管理 (SSIS Service)](../run-manage-packages-programmatically/managing-package-roles-programmatically-ssis-service.md)  
 パッケージまたはフォルダーに割り当てられているロールに関する情報を取得または設定する方法について説明します。  
  
## <a name="reference"></a>リファレンス  
 [Integration Services のエラーとメッセージのリファレンス](../integration-services-error-and-message-reference.md)  
 事前に定義されている [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] エラー コードと、そのシンボル名および説明の一覧を示します。  
  
## <a name="related-sections"></a>関連項目  
 [スクリプトによるパッケージの拡張](../extending-packages-scripting/extending-packages-with-scripting.md)  
 スクリプト タスクを使用した制御フローの拡張方法と、スクリプト コンポーネントを使用したデータ フローの拡張方法について説明します。  
  
 [カスタム オブジェクトを使用したパッケージの拡張](../extending-packages-custom-objects/extending-packages-with-custom-objects.md)  
 複数のパッケージで使用するプログラム カスタム タスク、データ フロー コンポーネント、およびその他のパッケージ オブジェクトを作成する方法について説明します。  
  
 [プログラムによるパッケージの作成](../building-packages-programmatically/building-packages-programmatically.md)  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] パッケージをプログラムで作成、構成、および保存する方法について説明します。  
  
![Integration Services のアイコン (小)](../media/dts-16.gif "Integration Services アイコン (小)")**Integration Services の日付を維持します。** <br /> 最新のダウンロード、アーティクル、サンプル、およびビデオの[!INCLUDE[msCoName](../../includes/msconame-md.md)]、およびコミュニティで選択されたソリューションを参照してください、 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] msdn ページ。<br /><br /> [MSDN の Integration Services のページを参照してください。](http://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> これらの更新が自動で通知されるようにするには、ページの RSS フィードを定期受信します。  
  
## <a name="see-also"></a>参照  
 [SQL Server Integration Services](../sql-server-integration-services.md)  
  
  