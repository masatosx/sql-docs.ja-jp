---
title: SQL Server インスタンス上のデータベースの一覧表示 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
helpviewer_keywords:
- current databases
- databases currently on server [SQL Server]
- database list [SQL Server]
- viewing database list
- displaying database list
- databases [SQL Server], viewing
- servers [SQL Server], databases listed on
- listing databases
ms.assetid: 7ee7a789-db36-4be9-8a0e-0362a1e152dd
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 737cf7d68ab6de620e6ed524eb6bc10649beecd6
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48160952"
---
# <a name="view-a-list-of-databases-on-an-instance-of-sql-server"></a>SQL Server インスタンス上のデータベースの一覧表示
  このトピックでは、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] または [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] を使用して、 [!INCLUDE[tsql](../../includes/tsql-md.md)]インスタンス上のデータベースの一覧を表示する方法について説明します。  
  
 **このトピックの内容**  
  
-   **作業を開始する準備:**  
  
     [Security](#Security)  
  
-   **以下を使用して SQL Server インスタンス上のデータベースの一覧を表示するには:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> 作業を開始する準備  
  
###  <a name="Security"></a> セキュリティ  
  
####  <a name="Permissions"></a> Permissions  
 **sys.databases** の呼び出し元がデータベースの所有者ではなく、データベースが **master** でも **tempdb**でもない場合、対応する行を表示するには、少なくとも **master** データベースで、ALTER ANY DATABASE または VIEW ANY DATABASE のサーバーレベルの権限、あるいは、CREATE DATABASE の権限が必要です。 呼び出し元が接続しているデータベースは常に **sys.databases**で確認できます。  
  
##  <a name="SSMSProcedure"></a> SQL Server Management Studio の使用  
  
#### <a name="to-view-a-list-of-databases-on-an-instance-of-sql-server"></a>SQL Server インスタンス上のデータベースの一覧を表示するには  
  
1.  **オブジェクト エクスプローラー**で、 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]のインスタンスに接続し、そのインスタンスを展開します。  
  
2.  インスタンス上のすべてのデータベースの一覧を表示するには、 **[データベース]** を展開します。  
  
##  <a name="TsqlProcedure"></a> Transact-SQL の使用  
  
#### <a name="to-view-a-list-of-databases-on-an-instance-of-sql-server"></a>SQL Server インスタンス上のデータベースの一覧を表示するには  
  
1.  [!INCLUDE[ssDE](../../includes/ssde-md.md)]に接続します。  
  
2.  [標準] ツール バーの **[新しいクエリ]** をクリックします。  
  
3.  次の例をコピーしてクエリ ウィンドウに貼り付け、 **[実行]** をクリックします。 この例は、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]のインスタンスに存在するデータベースの一覧を返します。 この一覧には、データベースの名前、ID、および作成日が含まれます。  
  
```tsql  
USE AdventureWorks2012;  
GO  
SELECT name, database_id, create_date  
FROM sys.databases ;  
GO  
  
```  
  
## <a name="see-also"></a>参照  
 [データベースとファイルのカタログ ビュー &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/databases-and-files-catalog-views-transact-sql)   
 [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
