---
title: 定義済みのレプリケーションの警告の構成 (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server replication]
- predefined replication alerts [SQL Server replication]
ms.assetid: c0414147-7ffe-4f9a-908c-71c1b5201584
caps.latest.revision: 22
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 385f18cdec2ef672bd1be5bafcff0ee5d0efe5f0
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37287138"
---
# <a name="configure-predefined-replication-alerts-sql-server-management-studio"></a>定義済みのレプリケーションの警告の構成 (SQL Server Management Studio)
  レプリケーションには、以下の定義済みの警告が用意されています。これらは、レプリケーション イベントに応答するように構成できます。  
  
-   **レプリケーション: エージェントが成功しました**  
  
-   **レプリケーション: エージェントが失敗しました**  
  
-   **レプリケーション: エージェントを再試行します**  
  
-   **レプリケーション: 有効期限の切れたサブスクリプションを削除しました**  
  
-   **レプリケーション: データ検証で問題が見つかった後、サブスクリプションが再初期化されました**  
  
-   **レプリケーション: サブスクライバーでデータ検証で問題が見つかりました**  
  
-   **レプリケーション: サブスクライバーでデータ検証を正常に終了しました**  
  
-   **レプリケーション: エージェントのカスタム シャットダウン**  
  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] の **[警告]** フォルダーまたはレプリケーション モニターの **[警告]** タブからこれらの警告を構成できます。 このタブにアクセスする方法の詳細については、「[サブスクリプションの情報の表示とタスクの実行 &#40;レプリケーション モニター&#41;](../monitor/view-information-and-perform-tasks-for-a-subscription-replication-monitor.md)」をご覧ください。  
  
 これらの警告に加え、レプリケーション モニターでは、ステータスおよびパフォーマンスに関連する一連の警告を使用できます。 詳細については、次を参照してください。[しきい値の設定とレプリケーション モニターで警告](../monitor/set-thresholds-and-warnings-in-replication-monitor.md)アラート インフラストラクチャ。 詳細については、「[ユーザー定義イベントの作成](../../../ssms/agent/create-a-user-defined-event.md)」を参照してください。  
  
### <a name="to-configure-a-predefined-replication-alert-in-management-studio"></a>Management Studio で定義済みのレプリケーションの警告を構成するには  
  
1.  [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]でディストリビューターに接続して、サーバー ノードを展開します。  
  
2.  **[SQL Server エージェント]** フォルダーを展開して、 **[警告]** フォルダーを展開します。  
  
3.  レプリケーションの警告を右クリックし、 **[プロパティ]** をクリックします。  
  
4.  **[\<AlertName> 警告のプロパティ]** ダイアログ ボックスのオプションを設定します。  
  
    -   **[全般]** ページで **[有効化]** をクリックし、警告を適用するデータベースを指定します。  
  
    -   **[応答]** ページで、電子メールを送信するかどうか、または、ジョブを実行するかどうかを指定します。  
  
         警告が " **レプリケーション: サブスクライバーでデータ検証で問題が見つかりました**" である場合は、レプリケーションがこの警告で使用する応答ジョブを指定できます。 **[ジョブの実行]** を選択し、参照ボタン **[...]** をクリックしてください。 **[ジョブの検索]** ダイアログ ボックスで、 **[参照]** をクリックします。 **[オブジェクトの参照]** ダイアログ ボックスで、 **[データ検証で問題が見つかったサブスクリプションの再初期化]** をクリックします。 両方の開いているダイアログ ボックスで、 **[OK]** をクリックします。 ジョブを実行するとき、サブスクリプションを再初期化するストアド プロシージャへのリモート プロシージャ コール (RPC) が使用されます。 パブリッシャーがリモート ディストリビューターを使用する場合、パブリッシャーでリモート サーバー ログインを定義して、ディストリビューターからパブリッシャーへの RPC を実行可能にする必要があります。  
  
    -   **[オプション]** ページで、応答のテキストをカスタマイズします。  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-configure-an-alert-for-a-threshold-in-replication-monitor"></a>レプリケーション モニターでしきい値に対する警告を構成するには  
  
1.  **[警告]** タブで、 **[警告の構成]** をクリックします。  
  
2.  **[レプリケーションの警告の構成]** ダイアログ ボックスで警告を選択し、 **[構成]** をクリックします。  
  
3.  **[\<AlertName> 警告のプロパティ]** ダイアログ ボックスのオプションを設定します。  
  
    -   **[全般]** ページで **[有効化]** をクリックし、警告を適用するデータベースを指定します。  
  
    -   **[応答]** ページで、電子メールを送信するかどうか、または、ジョブを実行するかどうかを指定します。  
  
         警告が " **レプリケーション: サブスクライバーでデータ検証で問題が見つかりました**" である場合は、レプリケーションがこの警告で使用する応答ジョブを指定できます。 **[ジョブの実行]** を選択し、参照ボタン **[...]** をクリックしてください。 **[ジョブの検索]** ダイアログ ボックスで、 **[参照]** をクリックします。 **[オブジェクトの参照]** ダイアログ ボックスで、 **[データ検証で問題が見つかったサブスクリプションの再初期化]** をクリックします。 両方の開いているダイアログ ボックスで、 **[OK]** をクリックします。 ジョブを実行するとき、サブスクリプションを再初期化するストアド プロシージャへのリモート プロシージャ コール (RPC) が使用されます。 パブリッシャーがリモート ディストリビューターを使用する場合、パブリッシャーでリモート サーバー ログインを定義して、ディストリビューターからパブリッシャーへの RPC を実行可能にする必要があります。  
  
    -   **[オプション]** ページで、応答のテキストをカスタマイズします。  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  **[閉じる]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [レプリケーション エージェント イベントに対する警告の使用](../agents/use-alerts-for-replication-agent-events.md)  
  
  