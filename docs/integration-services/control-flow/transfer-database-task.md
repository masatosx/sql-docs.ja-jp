---
title: データベース転送タスク | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql13.dts.designer.transferdatabasetask.f1
- sql13.dts.designer.transferdatabasetask.general.f1
- sql13.dts.designer.transferdatabasetask.database.f1
- sql13.dts.designer.transferdatabasetask.sourcedbfiles.f1
- sql13.dts.designer.transferdatabasetask.destdbfiles.f1
helpviewer_keywords:
- Transfer Database task [Integration Services]
ms.assetid: b9a2e460-cdbc-458f-8df8-06b8b2de3d67
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 4b7e72842412f829a51a0c7befdea30818d903ac
ms.sourcegitcommit: 2429fbcdb751211313bd655a4825ffb33354bda3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "52512074"
---
# <a name="transfer-database-task"></a>データベース転送タスク
  データベース転送タスクは、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] の 2 つのインスタンスの間で [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]データベースを転送します。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] オブジェクトをコピーして転送するだけの他のタスクに対し、データベース転送タスクでは、データベースをコピーまたは移動できます。 このタスクを使用して、同じサーバー内でデータベースをコピーすることもできます。  
  
## <a name="offline-and-online-modes"></a>オフライン モードとオンライン モード  
 データベースは、オンライン モードまたはオフライン モードで転送できます。 オンライン モードでは、データベースがアタッチされたまま、SQL 管理オブジェクト (SMO) を使用して転送され、データベース オブジェクトがコピーされます。 オフライン モードでは、データベースがデタッチされた後、データベース ファイルがコピーまたは移動されます。転送が正常に完了した後、データベースが転送先にアタッチされます。 データベースのコピーの場合、コピーが正常に完了するとデータベースは転送元に再びアタッチされます。 オフライン モードでは、データベースは短時間にコピーされますが、転送が行われている間はデータベースを利用できなくなります。  
  
 オフライン モードを使用する場合は、転送元サーバーと転送先サーバー上でデータベース ファイルを格納するネットワーク ファイル共有を指定する必要があります。 このフォルダーが共有されていてユーザーがフォルダーにアクセスできる場合、 \\\computername\Program Files\myfolder\\という構文を使用してネットワーク共有を参照できます。 それ以外の場合は、 \\\computername\c$\Program Files\myfolder\\という構文を使用する必要があります。 後者の構文を使用するには、転送元と転送先のネットワーク共有に対する書き込みアクセスがユーザーに許可されている必要があります。  
  
## <a name="transfer-of-databases-between-versions-of-sql-server"></a>SQL Server のバージョン間でのデータベースの転送  
 データベース転送タスクは、異なるバージョンの [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインスタンス間でデータベースを転送できます。  
  
## <a name="events"></a>イベント  
 データベース転送タスクでは、エラー メッセージ転送の進捗状況は報告されません。0% または 100% 完了した場合のみ報告されます。  
  
## <a name="execution-value"></a>実行値  
 タスクの **ExecutionValue** プロパティで定義される実行値は、値 1 を返します。これは、他の転送タスクとは異なり、データベース転送タスクでは 1 つのデータベースしか転送できないためです。  
  
 データベース転送タスクの **ExecValueVariable** プロパティにユーザー定義変数を割り当てると、エラー メッセージ転送に関する情報をパッケージ内の他のオブジェクトで利用できるようになります。 詳細については、「[Integration Services &#40;SSIS&#41; の変数](../../integration-services/integration-services-ssis-variables.md)」と「[パッケージで変数を使用する](https://msdn.microsoft.com/library/7742e92d-46c5-4cc4-b9a3-45b688ddb787)」を参照してください。  
  
## <a name="log-entries"></a>ログ エントリ  
 データベース転送タスクには、次のカスタム ログ エントリが含まれています。  
  
-   SourceSQLServer: このログ エントリは、転送元サーバーの名前を一覧表示します。  
  
-   DestSQLServer: このログ エントリは、転送先サーバーの名前を一覧表示します。  
  
-   SourceDB: このログ エントリは、転送されたデータベースの名前を一覧表示します。  
  
 さらに、転送先データベースが上書きされたときに、 **OnInformation** イベントのログ エントリが書き込まれます。  
  
## <a name="security-and-permissions"></a>セキュリティおよび権限  
 オフライン モードを使用してデータベースを転送するには、パッケージを実行するユーザーが sysadmin サーバー ロールのメンバーである必要があります。  
  
 オンライン モードを使用してデータベースを転送するには、パッケージを実行するユーザーが sysadmin サーバー ロールのメンバーであるか、または選択されたデータベースのデータベース所有者 (dbo) である必要があります。  
  
## <a name="configuration-of-the-transfer-database-task"></a>データベース転送タスクの構成  
 データベースの転送が失敗した場合に転送元データベースへの再アタッチを試行するかどうかを指定できます。  
  
 さらに、データベース転送タスクでは、転送先に同じ名前のデータベースが存在する場合にそのデータベースを上書きするように構成できます。  
  
 転送プロセスの一部として、転送元データベースの名前を変更することもできます。 転送先の [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインスタンスに同じ名前のデータベースが存在する場合にデータベースを転送するには、転送元データベースの名前を変更することでデータベースを転送できます。 ただし、データベース ファイルの名前も異なっている必要があります。同じ名前のデータベース ファイルが転送先に既に存在すると、タスクは失敗します。  
  
 データベースをコピーする場合、データベースのサイズは、コピー先サーバーの **model** データベースのサイズより小さくすることはできません。 コピーするデータベースのサイズを大きくするか、 **model**データベースのサイズを小さくできます。  
  
 実行時、データベース転送タスクは、1 つまたは 2 つの SMO 接続マネージャーを使用して、転送元サーバーと転送先サーバーに接続します。 同じサーバー上にデータベースのコピーを作成する場合は、SMO 接続マネージャーが 1 つだけ必要です。 これらの SMO 接続マネージャーはデータベース転送タスクとは別に構成され、データベース転送タスクで参照されます。 SMO 接続マネージャーは、サーバーと、タスクがこのサーバーにアクセスするときに使用する認証モードを指定します。 詳細については、「 [SMO 接続マネージャー](../../integration-services/connection-manager/smo-connection-manager.md)」をご覧ください。  
  
 プロパティを設定するには [!INCLUDE[ssIS](../../includes/ssis-md.md)] デザイナーから行うか、またはプログラムによって設定します。  
  
 [!INCLUDE[ssIS](../../includes/ssis-md.md)] デザイナーで設定できるプロパティの詳細については、次のトピックを参照してください。  
  
-   [[式] ページ](../../integration-services/expressions/expressions-page.md)  
  
 [!INCLUDE[ssIS](../../includes/ssis-md.md)] デザイナーでこれらのプロパティを設定する方法については、次のトピックを参照してください。  
  
-   [タスクまたはコンテナーのプロパティを設定する](https://msdn.microsoft.com/library/52d47ca4-fb8c-493d-8b2b-48bb269f859b)  
  
## <a name="programmatic-configuration-of-the-transfer-database-task"></a>プログラムによるデータベース転送タスクの構成  
 プログラムによってこれらのプロパティを設定する方法の詳細については、次のトピックを参照してください。  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferDatabaseTask.TransferDatabaseTask>  
  
## <a name="transfer-database-task-editor-general-page"></a>[データベース転送タスク エディター] ([全般] ページ)
  **[データベース転送タスク エディター]** ダイアログ ボックスの **[全般]** ページを使用すると、データベース転送タスクの名前と説明を入力できます。 データベース転送タスクは、2 つの [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] インスタンスの間で [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]データベースをコピーまたは移動します。 このタスクを使用して、同じサーバー内でデータベースをコピーすることもできます。   
  
### <a name="options"></a>[変数]  
 **名前**  
 データベース転送タスクの一意な名前を入力します。 この名前は、タスク アイコンのラベルとして使用されます。  
  
> [!NOTE]  
>  タスク名はパッケージ内で一意である必要があります。  
  
 **[説明]**  
 データベース転送タスクの説明を入力します。  
  
## <a name="transfer-database-task-editor-databases-page"></a>[データベース転送タスク エディター] ([データベース] ページ)
  **[データベース転送タスク エディター]** ダイアログ ボックスの **[データベース]** ページを使用すると、データベース転送タスクに使用される転送元および転送先のデータベースのプロパティを指定できます。 データベース転送タスクは、2 つの [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] インスタンスの間で [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]データベースをコピーまたは移動します。 このタスクを使用して、同じサーバー内でデータベースをコピーすることもできます。  
  
### <a name="options"></a>[変数]  
 **SourceConnection**  
 SMO 接続マネージャーを一覧から選択するか、**\<[新しい接続...]>** をクリックしてコピー元のサーバーへの新しい接続を作成します。  
  
 **DestinationConnection**  
 SMO 接続マネージャーを一覧から選択するか、**\<[新しい接続...]>** をクリックしてコピー先のサーバーへの新しい接続を作成します。  
  
 **[DestinationDatabaseName]**  
 転送先サーバーの [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] データベースの名前を指定します。  
  
 このフィールドにソース データベースの名前を自動的に入力するには、 **[SourceConnection]** と **[SourceDatabaseName]** を先に指定します。  
  
 転送先サーバー上のデータベースの名前を変更するには、このフィールドに新しい名前を入力します。  
  
 **[DestinationDatabaseFiles]**  
 転送先サーバーにおけるデータベース ファイルの名前と場所を指定します。  
  
 このフィールドにソース データベース ファイルの名前と場所を自動的に入力するには、 **[SourceConnection]**、 **[SourceDatabaseName]**、 **[SourceDatabaseFiles]** を先に指定します。  
  
 データベース ファイルの名前を変更するか、転送先サーバー上の新しい場所を指定するには、このフィールドにソース データベースの情報を入力した後、参照ボタンをクリックします。 **[転送先データベース ファイル]** ダイアログ ボックスで、 **[転送先ファイル]**、 **[転送先フォルダー]**、または **[ネットワーク ファイル共有]** を編集します。  
  
> [!NOTE]  
>  参照ボタンを使用してデータベース ファイルを指定した場合、ファイルの場所はローカル ドライブの表記 (c:\\など) を使用して入力されます。 これをコンピューター名と共有名を含むネットワーク共有の表記に変える必要があります。 既定の管理共有を使用する場合、$ 表記を使用し、その共有に対する管理アクセスを行える必要があります。  
  
 **[DestinationOverwrite]**  
 転送先サーバーのデータベースを上書きできるかどうかを指定します。  
  
 このプロパティには、次の表に示すオプションがあります。  
  
|ReplTest1|Description|  
|-----------|-----------------|  
|**True**|転送先サーバーのデータベースを上書きします。|  
|**False**|転送先サーバーのデータベースを上書きしません。|  
  
> [!CAUTION]  
>  **[DestinationOverwrite]** に **[True]** を指定した場合、転送先サーバーのデータベースのデータが上書きされます。これにより、データが失われる可能性があります。 データが失われないようにするには、データベース転送タスクを実行する前に、転送先サーバーのデータベースを別の場所にバックアップしておきます。  
  
 **操作**  
 タスクによってデータベースを転送先サーバーにコピー ( **[Copy]** ) するのか移動 ( **[Move]** ) するのかを指定します。  
  
 **方法**  
 転送元サーバーのデータベースがオンライン モードのときにタスクを実行するか、オフライン モードのときに実行するかを指定します。  
  
 オフライン モードを使用してデータベースを転送するには、パッケージを実行するユーザーが **sysadmin** 固定サーバー ロールのメンバーである必要があります。  
  
 オンライン モードを使用してデータベースを転送するには、パッケージを実行するユーザーが **sysadmin** 固定サーバー ロールのメンバーであるか、選択されたデータベースのデータベース所有者 (**dbo**) である必要があります。  
  
 **[SourceDatabaseName]**  
 コピーまたは移動されるデータベースの名前を選択します。  
  
 **[SourceDatabaseFiles]**  
 参照ボタンをクリックして、データベース ファイルを選択します。  
  
 **[ReattachSourceDatabase]**  
 失敗した場合に、ソース データベースの再アタッチを試行するかどうかを指定します。  
  
 このプロパティには、次の表に示すオプションがあります。  
  
|ReplTest1|Description|  
|-----------|-----------------|  
|**True**|ソース データベースを再アタッチします。|  
|**False**|ソース データベースを再アタッチしません。|  

## <a name="source-database-files"></a>[転送元のデータベース ファイル]
  **[転送元のデータベース ファイル]** ダイアログ ボックスを使用すると、ソース サーバーのデータベース ファイルの名前と場所を表示したり、データベース転送タスクのネットワーク ファイル共有の場所を指定したりできます。   
  
 このダイアログ ボックスにソース サーバーのデータベース ファイルの名前と場所を入力するには、最初に **[データベース転送タスク エディター]** ダイアログ ボックスの **[データベース]** ページで **[SourceConnection]** および **[SourceDatabaseName]** を指定します。  
  
### <a name="options"></a>[変数]  
 **[転送元ファイル]**  
 転送する対象のソース サーバーのデータベース ファイル名です。 **[転送元ファイル]** は読み取り専用です。  
  
 **[同期元フォルダー]**  
 転送する対象データベース ファイルが存在する転送元サーバーのフォルダーです。 **[転送元フォルダー]** は読み取り専用です。  
  
 **[ネットワーク ファイル共有]**  
 データベース ファイルの転送元となるソース サーバーのネットワーク共有フォルダーです。 **[ネットワーク ファイル共有]** は、データベースをオフライン モードで転送する場合に使用します。 **[データベース転送タスク エディター]** ダイアログ ボックスの **[データベース]** ページの **[Method]** に、 **[DatabaseOffline]** を指定します。  
  
 ネットワーク ファイル共有の場所を入力するか、参照ボタン **([...])** をクリックしてネットワーク ファイル共有の場所を見つけます。  
  
 オフライン モードでデータベースを転送すると、データベースは転送先サーバーに転送される前に、転送元サーバーの **[ネットワーク ファイル共有]** の場所にコピーされます。  

## <a name="destination-database-files"></a>[転送先データベース ファイル]
  **[転送先データベース ファイル]** ダイアログ ボックスを使用すると、転送先サーバーのデータベース ファイルの名前と場所を表示または変更したり、データベース転送タスクのネットワーク ファイルの場所を指定したりできます。  
  
 このダイアログ ボックスで転送元サーバーのデータベース ファイルの名前と場所を自動的に入力するには、最初に **[データベース転送タスク エディター]** ダイアログ ボックスの **[データベース]** ページで、 **[SourceConnection]** 、 **[SourceDatabaseName]** 、および **[SourceDatabaseFiles]** を指定します。  
  
### <a name="options"></a>[変数]  
 **[転送先ファイル]**  
 転送先サーバーの転送されたデータベース ファイルの名前です。  
  
 ファイル名を入力するか、ファイル名をクリックして編集します。  
  
 **[同期先フォルダー]**  
 データベース ファイルの転送先となる転送先サーバーのフォルダーです。  
  
 フォルダー パスを入力するか、フォルダー パスをクリックして編集するか、参照ボタンをクリックしてデータベース ファイルを転送する転送先サーバーのフォルダーを指定します。  
  
 **[ネットワーク ファイル共有]**  
 データベース ファイルの転送先となる転送先サーバーのネットワーク共有フォルダーです。 **[ネットワーク ファイル共有]** は、データベースをオフライン モードで転送する場合に使用します。 **[データベース転送タスク エディター]** ダイアログ ボックスの **[データベース]** ページの **[Method]** に、 **[DatabaseOffline]** を指定します。  
  
 ネットワーク ファイル共有の場所を入力するか、参照ボタンをクリックしてネットワーク ファイル共有の場所を見つけます。  
  
 オフライン モードでデータベースを転送すると、データベース ファイルは **[転送先フォルダー]** で指定した場所に転送される前に、 **[ネットワーク ファイル共有]** で指定した場所にコピーされます。  
