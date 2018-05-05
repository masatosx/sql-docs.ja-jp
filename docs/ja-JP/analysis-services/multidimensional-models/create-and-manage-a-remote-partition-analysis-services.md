---
title: 作成し、管理、リモート パーティション (Analysis Services) |Microsoft ドキュメント
ms.date: 05/02/2018
ms.prod: sql
ms.technology: analysis-services
ms.component: multidimensional-models
ms.topic: article
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: fb19c147010f0492122e88b21bd12efb43c05376
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="create-and-manage-a-remote-partition-analysis-services"></a>リモート パーティションの作成と管理 (Analysis Services)
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  メジャー グループをパーティション分割する場合は、パーティションのストレージとして [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] のリモート インスタンスでセカンダリ データベースを構成できます。  
  
 キューブ (master データベースと呼ばれます) のリモート パーティションは、 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] のリモート インスタンス上の専用の [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] データベース (セカンダリ データベースと呼ばれます) に格納されています。  
  
 専用のセカンダリ データベースは、1 つの master データベースのみのリモート パーティションを格納できます。これに対し、master データベースは、すべてのセカンダリ データベースが [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]の同一のリモート インスタンスに存在する場合に限り、複数のセカンダリ データベースを使用できます。 リモート パーティション専用のデータベース内のディメンションは、リンク ディメンションとして作成されます。  
  
## <a name="prerequisites"></a>前提条件  
 リモート パーティションを作成するには、次の条件を満たしている必要があります。  
  
-   パーティションを格納するために、もう 1 つの [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] インスタンスと専用データベースが必要です。 セカンダリ データベースには、master データベースのリモート パーティションのストレージを提供するという専用の目的があります。  
  
-   両方のサーバー インスタンスが同じバージョンであることが必要です。 両方のデータベースの機能レベルは同じである必要があります。  
  
-   両方のインスタンスが TCP 接続用に構成されている必要があります。 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]HTTP プロトコルを使用してリモート パーティションの作成はできません。  
  
-   両方のコンピューターのファイアウォール設定は、外部接続を許可するように設定されている必要があります。 ファイアウォールの設定の詳細については、「 [Analysis Services のアクセスを許可するための Windows ファイアウォールの構成](../../analysis-services/instances/configure-the-windows-firewall-to-allow-analysis-services-access.md)」を参照してください。  
  
-   master データベースを実行するインスタンスのサービス アカウントには、 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]のリモート インスタンスに対する管理アクセス権が必要です。 サービス アカウントが変更された場合は、サーバーとデータベース両方に対する権限を更新する必要があります。  
  
-   両方のコンピューターで [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 管理者である必要があります。  
  
-   災害復旧計画がリモート パーティションのバックアップと復元に対応していることを確認する必要があります。 リモート パーティションを使用すると、バックアップ操作と復元操作が複雑になる場合があります。 必要なデータを復元できるように、計画を十分にテストしてください。  
  
## <a name="configure-remote-partitions"></a>リモート パーティションの構成  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] のインスタンスを実行している異なる 2 台のコンピューターはそれぞれ、1 台をマスター サーバー、もう 1 台を下位サーバーとして指定するリモート パーティションの配置を作成するために必要です。  
  
 次の手順では、マスター サーバーにキューブ データベースが配置されている、2 つのサーバー インスタンスがあることを前提としています。 この手順では、キューブ データベースを db-master と呼びます。 リモート パーティションが含まれているストレージ データベースを db-storage と呼びます。  
  
 この手順を完了するには、 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] と [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] の両方を使用します。  
  
> [!NOTE]  
>  リモート パーティションとマージできるのは、他のリモート パーティションのみです。 ローカル パーティションとリモート パーティションを組み合わせて使用している場合は、別の方法として、結合したデータを含む新しいパーティションを作成し、今後使用しないパーティションを削除する方法もあります。  
  
#### <a name="specify-valid-server-names-for-cube-deployment-in-ssdt"></a>キューブの配置に有効なサーバー名を指定する (SSDT)  
  
1.  マスター サーバー: ソリューション エクスプローラーでソリューション名を右クリックし、 **[プロパティ]** をクリックします。 **[プロパティ]** ダイアログ ボックスで、 **[構成プロパティ]**、 **[配置]**、 **[サーバー]** の順にクリックし、マスター サーバーの名前を設定します。  
  
2.  下位サーバー: ソリューション エクスプローラーでソリューション名を右クリックし、 **[プロパティ]** をクリックします。 **[プロパティ]** ダイアログ ボックスで、 **[構成プロパティ]**、 **[配置]**、 **[サーバー]** の順にクリックし、下位サーバーの名前を設定します。  
  
#### <a name="create-and-deploy-a-secondary-database-in-ssdt"></a>セカンダリ データベースを作成および配置する (SSDT)  
  
1.  下位サーバー: ストレージ データベース用に新しい Analysis Services プロジェクトを作成します。  
  
2.  下位サーバー: ソリューション エクスプローラーで、キューブ データベース db-master を指す新しいデータ ソースを作成します。 プロバイダーに **[ネイティブ OLE DB\Microsoft OLE DB Provider for Analysis Services 11.0]** を使用します。  
  
3.  下位サーバー: ソリューションを配置します。  
  
#### <a name="enable-features-in-ssms"></a>機能を有効にする (SSMS)  
  
1.  下位サーバー: [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]のオブジェクト エクスプローラーで、接続している [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] インスタンスを右クリックし、 **[プロパティ]** をクリックします。 **[機能\LinkToOtherInstanceEnabled]** と **[機能\LinkFromOtherInstanceEnabled]** の両方を **[True]** に設定します。  
  
2.  下位サーバー: オブジェクト エクスプローラーでサーバー名を右クリックして **[再起動]** をクリックし、サーバーを再起動します。  
  
3.  マスター サーバー: [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]のオブジェクト エクスプローラーで、接続している [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] インスタンスを右クリックし、 **[プロパティ]** をクリックします。 **[機能\LinkToOtherInstanceEnabled]** と **[機能\LinkFromOtherInstanceEnabled]** の両方を **[True]** に設定します。  
  
4.  マスター サーバー: オブジェクト エクスプローラーでサーバー名を右クリックして **[再起動]** をクリックし、サーバーを再起動します。  
  
#### <a name="set-the-masterdatasourceid-database-property-on-the-remote-server-in-ssms"></a>リモート サーバーで MasterDataSourceID データベース プロパティを設定する (SSMS)  
  
1.  下位サーバー: ストレージ データベース db-storage を右クリックし、 **[データベースをスクリプト化]** | **[ALTER]** | **[新しいクエリ エディター ウィンドウ]** をポイントします。  
  
2.  **[MasterDataSourceID]** を XMLA に追加して、キューブ データベース db-master の ID を値として指定します。 XMLA は次のようになります。  
  
    ```  
    <Alter ObjectExpansion="ExpandFull" xmlns="http://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
       <DatabaseID>DB-Storage</DatabaseID>  
    </Object>  
    <ObjectDefinition>  
       <Database xmlns:xsd="http://www.w3.org/2001/XMLSchema" 400"   
          <ID>DB-Storage</ID>  
          <Name>DB-StorageB</Name>  
          <ddl200:CompatibilityLevel>1100</ddl200:CompatibilityLevel>  
          <Language>1033</Language>  
          <Collation>Latin1_General_CI_AS</Collation>  
          <DataSourceImpersonationInfo>  
    <ImpersonationMode>ImpersonateAccount</ImpersonationMode>  
             <Account>*********</Account>  
          </DataSourceImpersonationInfo>  
          <MasterDataSourceID>DB-Master</MasterDataSourceID>  
       </Database>  
    </ObjectDefinition>  
    </Alter>  
    ```  
  
3.  F5 キーを押してスクリプトを実行します。  
  
#### <a name="set-up-the-remote-partition-in-ssdt"></a>リモート パーティションを設定する (SSDT)  
  
1.  マスター サーバー: キューブ デザイナーでキューブを開き、 **[パーティション]** タブをクリックします。メジャー グループを展開します。 メジャー グループが既に複数のパーティションに対して構成されている場合は **[新しいパーティション]** をクリックします。または、[基になる列] の参照ボタン (. の同一のリモート インスタンスに存在する場合に限り、複数のセカンダリ データベースを使用できます。 ) をクリックして既存のパーティションを編集します。  
  
2.  パーティション ウィザードの **[基になる情報の指定]** で、元のデータ ソース ビューとファクト テーブルを選択します。  
  
3.  クエリ バインドを使用する場合は、作成する新しいパーティションにデータを分割する WHERE 句を指定します。  
  
4.  **[処理およびストレージの場所]** の **[処理場所]** で、 **[リモート Analysis Services データ ソース]** を選択し、 **[新規作成]** をクリックして、下位データベース db-storage を指す新しいデータ ソースを作成します。  
  
    > [!NOTE]  
    >  データ ソースがコレクションに存在しないことを示すエラーが発生した場合は、ストレージ データベース db-storage のプロジェクトを開き、master データベース db-master を指すデータ ソースを作成する必要があります。  
  
5.  マスター サーバー: ソリューション エクスプローラーでキューブ名を右クリックし、 **[処理]** を選択してキューブを完全に処理します。  
  
## <a name="administering-remote-partitions"></a>リモート パーティションの管理  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]リモート パーティションの処理を並列および順次の両方をサポートしています。 パーティションが定義された master データベースは、キューブのパーティション処理に参加するすべてのインスタンスのトランザクションを調整します。 処理のレポートは、パーティションを処理するすべてのインスタンスに送信されます。  
  
 リモート パーティションを含むキューブは、 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]の 1 つのインスタンスでそのパーティションと共に管理されます。 ただし、リモート パーティションのメタデータは、パーティションとその親キューブが定義された [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] のインスタンスでのみ表示および更新できます。 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]のリモート インスタンスではリモート パーティションを表示または更新できません。  
  
> [!NOTE]  
>  リモート パーティションの格納専用のデータベースは、スキーマ行セットに対して公開されていませんが、分析管理オブジェクト (AMO) を使用するアプリケーションは、Analysis Discover コマンドの XML を使用して専用データベースを検出できます。 TCP または HTTP クライアントを使用して専用データベースに直接送信された CREATE コマンドまたは DELETE コマンドは成功しますが、操作によりこの厳密管理データベースが損傷する可能性があることを示す警告がサーバーにより返されます。  
  
## <a name="see-also"></a>参照  
 [パーティションと &#40; です。Analysis Services - 多次元データと &#41; です。](../../analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  