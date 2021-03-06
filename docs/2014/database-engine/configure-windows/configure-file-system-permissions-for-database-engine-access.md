---
title: データベース エンジン アクセスのファイル システム アクセス許可の構成 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
helpviewer_keywords:
- file system permissions
- service account [SQL Server], file system permissions
- permissions [SQL Server], file system
ms.assetid: 78bba43c-4edb-4216-84ac-d6246ae5546d
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 137f2f2e02e7e1dd91e93a246401108c68d00a11
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48074402"
---
# <a name="configure-file-system-permissions-for-database-engine-access"></a>データベース エンジン アクセスのファイル システム権限の構成
  このトピックでは [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]にデータベース ファイルの格納場所へのファイル システム アクセス権を付与する方法について説明します。 [!INCLUDE[ssDE](../../includes/ssde-md.md)] サービスには、データベース ファイルが格納されているファイル フォルダーにアクセスするための Windows ファイル システム権限が必要です。 既定の場所への権限は、セットアップ中に構成されます。 別の場所にデータベース ファイルを配置した場合は、次の手順に従って、 [!INCLUDE[ssDE](../../includes/ssde-md.md)] にその場所へのフル コントロール権限を付与する必要がある場合があります。  
  
 [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] 以降では、権限は各サービスのサービスごとの SID に割り当てられます。 このシステムはサービスの分離と多層防御を提供するのに役立ちます。 サービスごとの SID はサービス名から取得され、各サービスに固有です。 トピック「 [Windows サービス アカウントと権限の構成](configure-windows-service-accounts-and-permissions.md) 」にはサービスごとの SID についての記載があり、「 **Windows の特権および権限**」で名前が指定されています。 サービスごとの SID に対して、ファイルの場所へのアクセス権を割り当てる必要があります。  
  
## <a name="to-grant-file-system-permission-to-the-per-service-sid"></a>サービスごとの SID にファイル システム権限を付与するには  
  
1.  エクスプローラーを使用して、データベース ファイルが格納されているファイル システムの場所に移動します。 ファイル システム フォルダーを右クリックし、 **[プロパティ]** をクリックします。  
  
2.  **[セキュリティ]** タブで **[編集]** をクリックし、 **[追加]** をクリックします。  
  
3.  **[ユーザー、コンピューター、サービス アカウント、またはグループの選択]** ダイアログ ボックスで、場所の一覧の上部にある **[場所]** をクリックし、コンピューター名を選択して、 **[OK]** をクリックします。  
  
4.  **を選択するオブジェクト名の入力**ボックスで、サービスごとの SID の名前、オンライン ブックのトピックに記載する「 **Windows サービス アカウントの構成とアクセス許可**します。 (の[!INCLUDE[ssDE](../../includes/ssde-md.md)]サービスごとの SID を使用して**NT service \mssqlserver**の既定のインスタンス、または**NT service \mssql$ InstanceName**名前付きインスタンスです)。  
  
5.  **[名前の確認]** をクリックして、このエントリを検証します。 検証は多くの場合に失敗し、名前が見つからないことが示される場合があります。 **[OK]** をクリックすると、 **[複数の名前が見つかりました]** ダイアログ ボックスが表示されます。  
  
6.  か、サービスごとの SID を選択**MSSQLSERVER**または**NT service \mssql$ InstanceName**、 をクリックし、 **OK**。  
  
7.  をクリックして**OK**に戻るにもう一度、**アクセス許可** ダイアログ ボックス。  
  
8.  **グループまたはユーザー**名ボックスで、サービスごとの SID を選択し、**のアクセス許可**\<名 > ボックスで、選択、**許可**のチェックボックス**フル コントロール**します。  
  
9. **[適用]** をクリックし、 **[OK]** を 2 回クリックして終了します。  
  
## <a name="see-also"></a>参照  
 [データベース エンジン サービスの管理](manage-the-database-engine-services.md)   
 [システム データベースの移動](../../relational-databases/databases/system-databases.md)   
 [ユーザー データベースの移動](../../relational-databases/databases/move-user-databases.md)  
  
  
