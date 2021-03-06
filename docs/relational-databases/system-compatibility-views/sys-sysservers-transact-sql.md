---
title: sys.sysservers (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.sysservers
- sysservers_TSQL
- sysservers
- sys.sysservers_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysservers system table
- sys.sysservers compatibility view
ms.assetid: d02f186f-c00f-44a6-b38d-dc78a3d2145b
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: ede7e1a97ca121073760eaa0c5dcd309b5e3e412
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47608078"
---
# <a name="syssysservers-transact-sql"></a>sys.sysservers (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインスタンスが OLE DB データ ソースとしてアクセスできるサーバーごとに、1 行のデータを格納します。  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**srvid**|**smallint**|リモート サーバーの ID (ローカル専用)。|  
|**srvstatus**|**smallint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**srvname**|**sysname**|サーバー名。|  
|**srvproduct**|**sysname**|リモート サーバーの製品名。|  
|**providername**|**nvarchar(128)**|サーバーへのアクセスを提供する OLE DB プロバイダー名。|  
|**datasource**|**nvarchar (4000)**|OLE DB データ ソース値。|  
|**location**|**nvarchar (4000)**|OLE DB ロケーション値。|  
|**providerstring**|**nvarchar (4000)**|OLE DB プロバイダー文字列値。|  
|**schemadate**|**datetime**|この行が前回更新された日付。|  
|**topologyx**|**int**|使用されていません。|  
|**topologyy**|**int**|使用されていません。|  
|**catalog**|**sysname**|OLE DB プロバイダーに接続するときに使用するカタログ。|  
|**srvcollation**|**sysname**|サーバーの照合順序。|  
|**connecttimeout**|**int**|サーバー接続に対するタイムアウトの設定。|  
|**querytimeout**|**int**|サーバーに対するクエリのタイムアウトの設定。|  
|**srvnetname**|**char(30)**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**isremote**|**bit**|1 = サーバーはリモート サーバー。<br /><br /> 0 = サーバーはリンク サーバー。|  
|**rpc**|**bit**|1 = **sp_serveroption@rpc**設定**true**または**で**します。<br /><br /> 0 = **sp_serveroption@rpc**設定**false**または**オフ**します。|  
|**pub**|**bit**|1 = **sp_serveroption@pub**設定**true**または**で**します。<br /><br /> 0 = **sp_serveroption@pub**設定**false**または**オフ**します。|  
|**sub**|**bit**|1 = **sp_serveroption@sub**設定**true**または**で**します。<br /><br /> 0 = **sp_serveroption@sub**設定**false**または**オフ**します。|  
|**dist**|**bit**|1 = **sp_serveroption@dist**設定**true**または**で**します。<br /><br /> 0 = **sp_serveroption@dist**設定**false**または**オフ**します。|  
|**dpub**|**bit**|1 = **sp_serveroption@dpub**設定**true**または**で**します。<br /><br /> 0 = **sp_serveroption@dpub**設定**false**または**オフ**します。|  
|**rpcout**|**bit**|1 =  **sp_serveroption@rpcアウト**に設定**true**または**で**します。<br /><br /> 0 =  **sp_serveroption@rpcアウト**設定**false**または**オフ**します。|  
|**dataaccess**|**bit**|1 =  **sp_serveroption@dataアクセス**設定**true**または**で**します。<br /><br /> 0 =  **sp_serveroption@dataアクセス**設定**false**または**オフ**します。|  
|**collationcompatible**|**bit**|1 =  **sp_serveroption@collation互換性のある**設定**true**または**で**します。<br /><br /> 0 =  **sp_serveroption@collation互換性のある**設定**false**または**オフ**します。|  
|**system**|**bit**|1 = **sp_serveroption@system**設定**true**または**で**します。<br /><br /> 0 = **sp_serveroption@system**設定**false**または**オフ**します。|  
|**useremotecollation**|**bit**|1 =  **sp_serveroption@remote照合順序**設定**true**または**で**します。<br /><br /> 0 =  **sp_serveroption@remote照合順序**設定**false**または**オフ**します。|  
|**lazyschemavalidation**|**bit**|1 =  **sp_serveroption@lazyスキーマ検証**に設定**true**または**で**します。<br /><br /> 0 =  **sp_serveroption@lazyスキーマ検証**設定**false**または**オフ**します。|  
|**collation**|**sysname**|サーバー照合順序によって設定**sp_serveroption@collation名前**します。|  
|**nonsqlsub**|bit|0 = サーバーは [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインスタンス。<br /><br /> 1 = サーバーは、のインスタンスではありません [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
  
## <a name="see-also"></a>参照  
 [システム ビューへのシステム テーブルのマッピング&#40;TRANSACT-SQL&#41;](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [互換性ビュー &#40;Transact-SQL&#41;](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
