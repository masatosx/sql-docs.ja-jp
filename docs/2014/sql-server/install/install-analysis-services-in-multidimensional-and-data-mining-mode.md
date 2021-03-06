---
title: Analysis Services 多次元およびデータ マイニング モードのインストール |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Analysis Services, about installing Analysis Services
- installing Analysis Services
- SSAS, installing
- Analysis Services, installing
- SQL Server Analysis Services, installing
ms.assetid: 8a1f33e8-2bd6-4fb8-bd46-c86f2a067f60
author: heidisteen
ms.author: heidist
manager: craigg
ms.openlocfilehash: 92460328b9d85ab5818679b12639618ffe2b0a14
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48149902"
---
# <a name="install-analysis-services-in-multidimensional-and-data-mining-mode"></a>多次元モードおよびデータ マイニング モードでの Analysis Services のインストール
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] には、ビジネス インテリジェンス アプリケーション用のオンライン分析処理 (OLAP) 機能とデータ マイニング機能が用意されています。 このリリースで OLAP データベースとデータ マイニング モデルのサポートが利用可能なインストールするときに[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]で*多次元モード*します。 多次元モードは、[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] が実行される 3 つのサーバー モードのうちの 1 つです。 これは既定のモードです。 既定値を使用して [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] をインストールすると、多次元データベースとデータ マイニング モデルを実行するインスタンスがインストールされます。  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] は複数インスタンスに対応します。つまり、1 台のコンピューターに複数の [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] インスタンスをインストールすることも、新しいバージョンの [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] インスタンスを古いバージョンと共存して実行することもできます。 サーバー モードはインスタンスに固有です。 他のモードを使用するには、サーバーの追加インスタンスをインストールする必要があります。  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] は、単体でインストールすることも、他のコンポーネントと共にインストールすることもできます。 インストールする場合[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]を選択すると、次の機能がインストールされている**Analysis Services**の機能の選択 ページで、[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]インストール ウィザード。  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] データベースとデータ マイニング モデルを実行するための [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] サーバー  
  
-   ソース データベースへの [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] データのアクセスに使用されるデータ プロバイダー  
  
-   SQL Server 構成マネージャー  
  
## <a name="choosing-additional-features"></a>追加機能の選択  
 Analysis Services OLAP およびデータ ウェアハウス ソリューションでは、[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] データベースの開発、配置、および管理を可能にするためにその他の [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] コンポーネントもインストールする必要があります。 一般的なユーザー シナリオでは、データベース サービスに加えて次の機能もインストールします。  
  
-   [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]: Analysis Services データ構造およびデータ マイニング モデルの作成と表示に使用されます。  
  
-   クライアント ツール接続コンポーネントは、クライアントと Db-library、ODBC、および OLE DB 用のネットワーク ライブラリなど、サーバー間の通信に使用されます。  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]: データの移動、コピー、および変換に使用される、グラフィカル オブジェクトおよびプログラミング可能なオブジェクトのセットです。  
  
-   管理ツール: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 構成マネージャー、[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]、[!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]、レプリケーション モニターなどです。  
  
## <a name="installation-tasks"></a>インストール作業  
 インストール作業では、次の操作を行います。  
  
|リンク|処理手順|  
|-----------|-----------|  
|[Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md)と[Windows サービス アカウントとアクセス許可構成](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md)します。|セットアップを実行する前に、[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] のインストールの前提条件を確認し、サーバーの準備に使用するアカウントを決定します。|  
|[SQL Server 2014 インストール ウィザードからインストール&#40;セットアップ&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md)します。|SQL Server セットアップを実行して、ソフトウェアをインストールします。|  
|[Analysis Services のアクセスを許可するための Windows ファイアウォールの構成](../../analysis-services/instances/configure-the-windows-firewall-to-allow-analysis-services-access.md)|セットアップが完了したら、ファイアウォールの設定を構成して、サーバーに対するリモート接続を許可する必要があります。|  
|[オブジェクトと操作へのアクセスの承認 &#40;Analysis Services&#41;](../../analysis-services/multidimensional-models/authorizing-access-to-objects-and-operations-analysis-services.md)|Analysis Services データベースにアクセスするユーザーには、サーバー上の少なくとも 1 つのデータベースに対する読み取り権限が必要です。|  
  
## <a name="related-content"></a>関連コンテンツ  
 その他のセットアップ コンテンツは次のトピックで確認できます。  
  
 [表形式モードでの Analysis Services のインストール](../../analysis-services/instances/install-windows/install-analysis-services.md)  
  
 [PowerPivot for SharePoint 2010 のインストール](../../../2014/sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
  
 [Analysis Services インスタンスのサーバー モードの決定](../../analysis-services/instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
 [SQL Server データ マイニング アドイン](http://go.microsoft.com/fwlink/?LinkId=197091)  
  
 既定では、[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のセットアップ時にサンプル データベース、サンプル コード、およびクライアント アプリケーション アドインはインストールされません。 サンプル データベースとサンプル コードをインストールする場合は、 [CodePlex Web サイト](http://go.microsoft.com/fwlink/?LinkId=87843)を参照してください。  
  
## <a name="see-also"></a>参照  
 [SQL Server 2012 の各エディションでサポートされる機能](http://go.microsoft.com/fwlink/?linkid=232473)   
 [言語および照合順序&#40;Analysis Services&#41;](../../../2014/analysis-services/languages-and-collations-analysis-services.md)   
 [Analysis Services のアップグレード](../../database-engine/install-windows/upgrade-analysis-services.md)  
  
  
