---
title: "システム ストアド プロシージャ (TRANSACT-SQL) |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/21/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to: SQL Server (starting with 2016 CTP3)
f1_keywords:
- sql13.TSQLSysNoExpandPortal.f1
- sql13.TSQLSysNoExpandPortal.f1_TSQL
dev_langs: TSQL
helpviewer_keywords:
- stored procedures [SQL Server]
- APIs [SQL Server]
- stored procedures [SQL Server], categories
- system stored procedures [SQL Server], categories
- system stored procedures [SQL Server]
ms.assetid: a5c4d5b8-5a24-4a2d-99b4-d003b546ee3a
caps.latest.revision: "49"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: b3caeee99c777501d79a9e9e39cf38ac2d223616
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="system-stored-procedures-transact-sql"></a>システム ストアド プロシージャ (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] では、システム ストアド プロシージャを使用して、さまざまな管理操作や情報操作を実行できます。 システム ストアド プロシージャは、次の表に示すカテゴリに分類されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
|カテゴリ|Description|  
|--------------|-----------------|  
|[アクティブな Geo レプリケーションのストアド プロシージャ](http://msdn.microsoft.com/library/81658ee4-4422-4d73-bf7a-86a07422cb0d)|Azure SQL データベースでのアクティブ Geo レプリケーションの構成を管理する管理に使用します。|  
|[カタログ ストアド プロシージャ](../../relational-databases/system-stored-procedures/catalog-stored-procedures-transact-sql.md)|ODBC データ辞書関数を実装し、基になるシステム テーブルが変更されても ODBC アプリケーションが影響を受けないように分離する場合に使用します。|  
|[変更データ キャプチャ ストアド プロシージャ](../../relational-databases/system-stored-procedures/change-data-capture-stored-procedures-transact-sql.md)|変更データ キャプチャ オブジェクトの有効化、無効化、またはレポートに使用します。|  
|[カーソル ストアド プロシージャ](../../relational-databases/system-stored-procedures/cursor-stored-procedures-transact-sql.md)|カーソル変数機能の実装に使用します。|  
|[データ コレクター ストアド プロシージャ](../../relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql.md)|データ コレクターや各種コンポーネント (コレクション セット、コレクション アイテム、コレクション型など) を操作するために使用します。|  
|[データベース エンジン ストアド プロシージャ](../../relational-databases/system-stored-procedures/database-engine-stored-procedures-transact-sql.md)|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]の全般的なメンテナンスに使用します。|  
|[データベース メールのストアド プロシージャと #40 です。TRANSACT-SQL と #41 です。](../../relational-databases/system-stored-procedures/database-mail-stored-procedures-transact-sql.md)|インスタンス内から電子メール操作を実行するために使用[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]です。|  
|[データベース メンテナンス プラン ストアド プロシージャ](../../relational-databases/system-stored-procedures/database-maintenance-plan-stored-procedures-transact-sql.md)|データベースのパフォーマンスの管理に必要な基本のメンテナンス タスクを設定する場合に使用します。|  
|[分散クエリ ストアド プロシージャ](../../relational-databases/system-stored-procedures/distributed-queries-stored-procedures-transact-sql.md)|分散クエリの実装と管理に使用します。|  
|[Filestream および FileTable ストアド プロシージャと #40 です。TRANSACT-SQL と #41 です。](http://msdn.microsoft.com/library/54beca08-c012-4ebd-aa68-d8a10d221b64)|FILESTREAM 機能および FileTable 機能の構成と管理に使用します。|  
|[ファイアウォール ルールのストアド プロシージャと #40 です。Azure SQL データベース &#41;](../../relational-databases/system-stored-procedures/firewall-rules-stored-procedures-azure-sql-database.md)|Azure SQL データベース ファイアウォールを構成するために使用します。|  
|[フルテキスト検索ストアド プロシージャ](../../relational-databases/system-stored-procedures/full-text-search-and-semantic-search-stored-procedures-transact-sql.md)|フルテキスト インデックスの実装とクエリに使用します。|  
|[汎用拡張ストアド プロシージャ](../../relational-databases/system-stored-procedures/general-extended-stored-procedures-transact-sql.md)|インスタンスからインターフェイスを提供するために使用[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]さまざまなメンテナンス作業を外部プログラムにします。|  
|[ログ配布ストアド プロシージャ](../../relational-databases/system-stored-procedures/log-shipping-stored-procedures-transact-sql.md)|ログ配布構成の設定、変更、監視に使用します。|  
|[管理データ ウェアハウスのストアド プロシージャと #40 です。TRANSACT-SQL と #41 です。](../../relational-databases/system-stored-procedures/management-data-warehouse-stored-procedures-transact-sql.md)|管理データ ウェアハウスを構成するために使用します。|  
|[OLE オートメーション ストアド プロシージャ](../../relational-databases/system-stored-procedures/ole-automation-stored-procedures-transact-sql.md)|標準のオートメーション オブジェクト、標準的な内での使用を有効にするために使用[!INCLUDE[tsql](../../includes/tsql-md.md)]バッチ。|  
|[ポリシー ベースの管理ストアド プロシージャ](../../relational-databases/system-stored-procedures/policy-based-management-stored-procedures-transact-sql.md)|ポリシー ベースの管理に使用します。|  
|[PolyBase ストアド プロシージャ](http://msdn.microsoft.com/library/a522b303-bd1b-410b-92d1-29c950a15ede)|追加または PolyBase スケール アウトのグループからコンピューターを削除します。|  
|[クエリ ストアのストアド プロシージャと #40 です。TRANSACT-SQL と #41 です。](../../relational-databases/system-stored-procedures/query-store-stored-procedures-transact-sql.md)|パフォーマンスのチューニングに使用されます。|  
|[レプリケーション ストアド プロシージャ](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)|レプリケーションの管理に使用します。|  
|[セキュリティ ストアド プロシージャ](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)|セキュリティの管理に使用します。|  
|[バックアップ スナップショットのストアド プロシージャ](http://msdn.microsoft.com/library/c278db87-5770-4037-a1e6-b9853a943339)|FILE_SNAPSHOT バックアップとそのすべてのスナップショットを削除するか、個別のバックアップ ファイルのスナップショットを削除するために使用します。|  
|[空間インデックス ストアド プロシージャ](http://msdn.microsoft.com/library/1be0f34e-3d5a-4a1f-9299-bd482362ec7a)|分析および空間インデックスのインデックス作成のパフォーマンスを改善するために使用します。|  
|[SQL Server エージェント ストアド プロシージャ](../../relational-databases/system-stored-procedures/sql-server-agent-stored-procedures-transact-sql.md)|[!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] で、パフォーマンスと利用状況の監視に使用します。|  
|[SQL Server Profiler ストアド プロシージャ](../../relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql.md)|によって使用される[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]エージェント スケジュールされたスキャンとイベント ドリブン アクティビティを管理します。|  
|[Stretch Database のストアド プロシージャ](../../relational-databases/system-stored-procedures/stretch-database-extended-stored-procedures-transact-sql.md)|拡大のデータベースの管理に使用されます。|  
|[テンポラル テーブルはストアド プロシージャ](http://msdn.microsoft.com/library/f28ca74e-7876-4592-b794-e78e3690fff6)|一時的なテーブルの使用|  
|[XML ストアド プロシージャ](../../relational-databases/system-stored-procedures/xml-stored-procedures-transact-sql.md)|XML テキストの管理に使用します。|  
  
> [!NOTE]  
>  成功した場合は、特に記述がない限り、すべてのシステム ストアド プロシージャで値 0 が返されます。 失敗した場合は、0 以外の値が返されます。  
  
## <a name="api-system-stored-procedures"></a>API システム ストアド プロシージャ  
 実行するユーザー [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] ADO、OLE DB および ODBC に対してアプリケーションもありますに収録されていないシステム ストアド プロシージャを使用してこれらのアプリケーション、[!INCLUDE[tsql](../../includes/tsql-md.md)]参照します。 これらのストアド プロシージャがによって使用される、 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB プロバイダーと[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Native Client ODBC ドライバー、データベース API の機能を実装します。 ユーザー要求を [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] インスタンスに伝えるための機能を持っています。 これらのストアド プロシージャはプロバイダーまたはドライバーの内部使用のみに提供されており、 明示的に呼び出して、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-ベースのアプリケーションはサポートされていません。  
  
 Sp_createorphan および sp_droporphans ストアド プロシージャは ODBC の使用**ntext**、**テキスト**、および**イメージ**を処理します。  
  
 sp_reset_connection ストアド プロシージャは、[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] でトランザクション内のリモート ストアド プロシージャ呼び出しをサポートする場合に使用します。 また、接続が接続プールから再利用されると、このストアド プロシージャにより、Audit Login イベントおよび Audit Logout イベントも発生します。  
  
 インスタンス内でのみ使用して、次の表に、ストアド プロシージャ システム[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]または Api 想定されていません一般的なクライアントを使用します。 これらは変更されることがあり、互換性は保証されません。  
  
 次のストアド プロシージャについては、『[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]オンライン ブック。  
  
|||  
|-|-|  
|sp_catalogs|sp_column_privileges|  
|sp_column_privileges_ex|sp_columns|  
|sp_columns_ex|sp_databases|  
|sp_cursor|sp_cursorclose|  
|sp_cursorexecute|sp_cursorfetch|  
|sp_cursoroption|sp_cursoropen|  
|sp_cursorprepare|sp_cursorprepexec|  
|sp_cursorunprepare|sp_execute|  
|sp_datatype_info|sp_fkeys|  
|sp_foreignkeys|sp_indexes|  
|sp_pkeys|sp_primarykeys|  
|sp_prepare|sp_prepexec|  
|sp_prepexecrpc|sp_unprepare|  
|sp_server_info|sp_special_columns|  
|sp_sproc_columns|sp_statistics|  
|sp_table_privileges|sp_table_privileges_ex|  
|sp_tables|sp_tables_ex|  
  
 次のストアド プロシージャは、ドキュメントには記載されていません。  
  
|||  
|-|-|  
|sp_assemblies_rowset|sp_assemblies_rowset_rmt|  
|sp_assemblies_rowset2|sp_assembly_dependencies_rowset|  
|sp_assembly_dependencies_rowset_rmt|sp_assembly_dependencies_rowset2|  
|sp_bcp_dbcmptlevel|sp_catalogs_rowset|  
|sp_catalogs_rowset;2|sp_catalogs_rowset;5|  
|sp_catalogs_rowset_rmt|sp_catalogs_rowset2|  
|sp_check_constbytable_rowset|sp_check_constbytable_rowset;2|  
|sp_check_constbytable_rowset2|sp_check_constraints_rowset|  
|sp_check_constraints_rowset;2|sp_check_constraints_rowset2|  
|sp_column_privileges_rowset|sp_column_privileges_rowset;2|  
|sp_column_privileges_rowset;5|sp_column_privileges_rowset_rmt|  
|sp_column_privileges_rowset2|sp_columns_90|  
|sp_columns_90_rowset|sp_columns_90_rowset_rmt|  
|sp_columns_90_rowset2|sp_columns_ex_90|  
|sp_columns_rowset|sp_columns_rowset;2|  
|sp_columns_rowset;5|sp_columns_rowset_rmt|  
|sp_columns_rowset2|sp_constr_col_usage_rowset|  
|sp_datatype_info_90|sp_ddopen;1|  
|sp_ddopen;10|sp_ddopen;11|  
|sp_ddopen;12|sp_ddopen;13|  
|sp_ddopen;2|sp_ddopen;3|  
|sp_ddopen;4|sp_ddopen;5|  
|sp_ddopen;6|sp_ddopen;7|  
|sp_ddopen;8|sp_ddopen;9|  
|sp_foreign_keys_rowset|sp_foreign_keys_rowset;2|  
|sp_foreign_keys_rowset;3|sp_foreign_keys_rowset;5|  
|sp_foreign_keys_rowset_rmt|sp_foreign_keys_rowset2|  
|sp_foreign_keys_rowset3|sp_indexes_90_rowset|  
|sp_indexes_90_rowset_rmt|sp_indexes_90_rowset2|  
|sp_indexes_rowset|sp_indexes_rowset;2|  
|sp_indexes_rowset;5|sp_indexes_rowset_rmt|  
|sp_indexes_rowset2|sp_linkedservers_rowset|  
|sp_linkedservers_rowset;2|sp_linkedservers_rowset2|  
|sp_oledb_database|sp_oledb_defdb|  
|sp_oledb_deflang|sp_oledb_language|  
|sp_oledb_ro_usrname|sp_primary_keys_rowset|  
|sp_primary_keys_rowset;2|sp_primary_keys_rowset;3|  
|sp_primary_keys_rowset;5|sp_primary_keys_rowset_rmt|  
|sp_primary_keys_rowset2|sp_procedure_params_90_rowset|  
|sp_procedure_params_90_rowset2|sp_procedure_params_rowset|  
|sp_procedure_params_rowset;2|sp_procedure_params_rowset2|  
|sp_procedures_rowset|sp_procedures_rowset;2|  
|sp_procedures_rowset2|sp_provider_types_90_rowset|  
|sp_provider_types_rowset|sp_schemata_rowset|  
|sp_schemata_rowset;3|sp_special_columns_90|  
|sp_sproc_columns_90|sp_statistics_rowset|  
|sp_statistics_rowset;2|sp_statistics_rowset2|  
|sp_stored_procedures|sp_table_constraints_rowset|  
|sp_table_constraints_rowset;2|sp_table_constraints_rowset2|  
|sp_table_privileges_rowset|sp_table_privileges_rowset;2|  
|sp_table_privileges_rowset;5|sp_table_privileges_rowset_rmt|  
|sp_table_privileges_rowset2|sp_table_statistics_rowset|  
|sp_table_statistics_rowset;2|sp_table_statistics2_rowset|  
|sp_tablecollations|sp_tablecollations_90|  
|sp_tables_info_90_rowset|sp_tables_info_90_rowset_64|  
|sp_tables_info_90_rowset2|sp_tables_info_90_rowset2_64|  
|sp_tables_info_rowset|sp_tables_info_rowset;2|  
|sp_tables_info_rowset_64|sp_tables_info_rowset_64;2|  
|sp_tables_info_rowset2|sp_tables_info_rowset2_64|  
|sp_tables_rowset;2|sp_tables_rowset;5|  
|sp_tables_rowset_rmt|sp_tables_rowset2|  
|sp_usertypes_rowset|sp_usertypes_rowset_rmt|  
|sp_usertypes_rowset2|sp_views_rowset|  
|sp_views_rowset2|sp_xml_schema_rowset|  
|sp_xml_schema_rowset2||  
  
## <a name="see-also"></a>参照  
 [CREATE PROCEDURE &#40;Transact-SQL&#41;](../../t-sql/statements/create-procedure-transact-sql.md)   
 [ストアド プロシージャ &#40;データベース エンジン&#41;](../../relational-databases/stored-procedures/stored-procedures-database-engine.md)   
 [実行されているストアド プロシージャ &#40;OLE DB&#41;](../../relational-databases/native-client/ole-db/stored-procedures-running.md)   
 [ストアド プロシージャの実行](../../relational-databases/native-client-odbc-stored-procedures/running-stored-procedures.md)   
 [データベース エンジンのストアド プロシージャと #40 です。TRANSACT-SQL と #41 です。](../../relational-databases/system-stored-procedures/database-engine-stored-procedures-transact-sql.md)   
 [ストアド プロシージャの実行](../../relational-databases/native-client-odbc-stored-procedures/running-stored-procedures.md)  
  
  