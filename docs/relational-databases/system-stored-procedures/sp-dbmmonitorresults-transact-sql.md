---
title: sp_dbmmonitorresults (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_dbmmonitorresults
- sp_dbmmonitorresults_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_dbmmonitorresults
- database mirroring [SQL Server], monitoring
ms.assetid: d575e624-7d30-4eae-b94f-5a7b9fa5427e
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 54cf9a13396674c2ac9dd43845c94d7ac657f008
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47702750"
---
# <a name="spdbmmonitorresults-transact-sql"></a>sp_dbmmonitorresults (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  データベース ミラーリング監視履歴が格納されている状態テーブルから、監視対象データベースの状態行を返します。事前に、このプロシージャで最新の状態を取得するかどうかを選択できます。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sp_dbmmonitorresults database_name   
   , rows_to_return  
    , update_status   
```  
  
## <a name="arguments"></a>引数  
 *database_name*  
 ミラーリングの状態を返すデータベースを指定します。  
  
 *rows_to_return*  
 返す行の量を指定します。  
  
 0 = 最新の行  
  
 1 = 過去 2 時間の行  
  
 2 = 過去 4 時間の行  
  
 3 = 過去 8 時間の行  
  
 4 = 最新日付の行  
  
 5 = 過去 2 日間の行  
  
 6 = 100 の最後の行  
  
 7 = 500 の最後の行  
  
 8 = 最後 1,000 行  
  
 9 = 最新 1,000,000 行  
  
 *update_status*  
 プロシージャで結果を返す前の処理を指定します。  
  
 0 = データベースの状態を更新しない。 結果は最新 2 行のみから計算されます。行の古さは状態テーブルが更新された日時を基に判断されます。  
  
 1 = データベースの状態を呼び出して更新**sp_dbmmonitorupdate**結果を計算する前にします。 ただし、状態テーブルが直前の 15 秒、またはユーザー内で更新されている場合はのメンバー、 **sysadmin**固定サーバー ロール、 **sp_dbmmonitorresults**状態を更新することがなく実行されます。  
  
## <a name="return-code-values"></a>リターン コードの値  
 なし  
  
## <a name="result-sets"></a>結果セット  
 指定されたデータベースの履歴の状態に関する情報を、要求された行数分返します。 各行には次の情報が含まれます。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**database_name**|**sysname**|ミラー化されたデータベースの名前。|  
|**role**|**int**|サーバー インスタンスの現在のミラーリング ロール。<br /><br /> 1 = プリンシパル<br /><br /> 2 = ミラー|  
|**mirroring_state**|**int**|データベースの状態。<br /><br /> 0 = 中断状態<br /><br /> 1 = 切断<br /><br /> 2 = 同期中<br /><br /> 3 = フェールオーバーを保留しています<br /><br /> 4 = 同期済み|  
|**witness_status**|**int**|データベースのデータベース ミラーリング セッションにおけるミラーリング監視の接続状態。次のいずれかです。<br /><br /> 0 = 不明<br /><br /> 1 = 接続済み<br /><br /> 2 = 切断|  
|**log_generation_rate**|**int**|このデータベースのミラーリングの状態が前回更新されてからのログ生成率 (KB/秒単位)。|  
|**unsent_log**|**int**|プリンシパルの送信キューにある未送信のログのサイズ (KB 単位)。|  
|**send_rate**|**int**|プリンシパルからミラーへのログの送信率 (KB/秒単位)。|  
|**unrestored_log**|**int**|ミラーの再実行キューのサイズ (KB 単位)。|  
|**recovery_rate**|**int**|ミラーの再実行率 (KB/秒単位)。|  
|**transaction_delay**|**int**|すべてのトランザクションの合計遅延時間 (ミリ秒単位)。|  
|**transactions_per_sec**|**int**|プリンシパル サーバー インスタンスで 1 秒あたりに発生しているトランザクションの数。|  
|**average_delay**|**int**|データベース ミラーリングに起因する、各トランザクションのプリンシパル サーバー インスタンスでの平均遅延時間。 高パフォーマンス モード (SAFETY プロパティが OFF) の場合、通常この値は 0 です。|  
|**time_recorded**|**datetime**|データベース ミラーリング監視で行が記録された時間。 プリンシパルのシステム クロックの時間が使用されます。|  
|**time_behind**|**datetime**|ミラー データベースで現在認識されている、プリンシパルのシステム クロックのおおよその時間。 この値はプリンシパル サーバー インスタンスでのみ意味を持ちます。|  
|**local_time**|**datetime**|この行が更新されたときのローカル サーバー インスタンスのシステム クロック時間。|  
  
## <a name="remarks"></a>コメント  
 **sp_dbmmonitorresults**のコンテキストでのみ実行できる、 **msdb**データベース。  
  
## <a name="permissions"></a>アクセス許可  
 メンバーシップが必要です、 **sysadmin**固定サーバー ロールまたは、 **dbm_monitor**固定データベース ロール、 **msdb**データベース。 **Dbm_monitor**役割は、データベース ミラーリングの状態を表示がない更新しますが、ない表示または構成するデータベース ミラーリング イベントは、そのメンバーを使用できます。  
  
> [!NOTE]  
>  初めて**sp_dbmmonitorupdate**の実行が作成されます、 **dbm_monitor**固定データベース ロール、 **msdb**データベース。 メンバー、 **sysadmin**すべてのユーザーを追加できるは、固定サーバー ロール、 **dbm_monitor**固定データベース ロール。  
  
## <a name="examples"></a>使用例  
 次の例では、データベースの状態を更新せずに、過去 2 時間に記録された行を返します。  
  
```  
USE msdb;  
EXEC sp_dbmmonitorresults AdventureWorks2012, 2, 0;  
```  
  
## <a name="see-also"></a>参照  
 [データベース ミラーリングの監視 &#40;SQL Server&#41;](../../database-engine/database-mirroring/monitoring-database-mirroring-sql-server.md)   
 [sp_dbmmonitorchangemonitoring &#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dbmmonitorchangemonitoring-transact-sql.md)   
 [sp_dbmmonitoraddmonitoring &#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dbmmonitoraddmonitoring-transact-sql.md)   
 [sp_dbmmonitordropmonitoring &#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dbmmonitordropmonitoring-transact-sql.md)   
 [sp_dbmmonitorhelpmonitoring &#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dbmmonitorhelpmonitoring-transact-sql.md)   
 [sp_dbmmonitorupdate &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dbmmonitorupdate-transact-sql.md)  
  
  
