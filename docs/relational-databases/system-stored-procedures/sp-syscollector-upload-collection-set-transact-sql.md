---
title: sp_syscollector_upload_collection_set (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_syscollector_upload_collection_set
- sp_syscollector_upload_collection_set_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_syscollector_upload_collection_set
- data collector [SQL Server], stored procedures
ms.assetid: eed9232c-2b0a-4b6a-8ba0-76b7c99f48dc
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 9017209ef2e4b500ee6a90e14830b520ed2a588d
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47780902"
---
# <a name="spsyscollectoruploadcollectionset-transact-sql"></a>sp_syscollector_upload_collection_set (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  コレクション セットが有効になっている場合、コレクション セット データのアップロードを開始します。  
  
> [!IMPORTANT]  
>  このストアド プロシージャは、キャッシュ モードのデータ収集およびアップロード用に構成されているコレクション セットに対してのみ使用できます。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sp_syscollector_upload_collection_set [[ @collection_set_id = ] collection_set_id ]  
          , [[ @name = ] 'name' ]   
```  
  
## <a name="arguments"></a>引数  
 [ **@collection_set_id =** ] *collection_set_id*  
 コレクション セットの一意なローカル識別子を指定します。 *collection_set_id*は**int**場合、値が必要と*名前*は NULL です。  
  
 [ **@name =** ] **'***name***'**  
 コレクション セットの名前を指定します。 *名前*は**sysname**場合、値が必要と*collection_set_id*は NULL です。  
  
## <a name="return-code-values"></a>リターン コードの値  
 **0** (成功) または**1** (失敗)  
  
## <a name="remarks"></a>コメント  
 いずれか*collection_set_id*または*名前*する必要があります、値はどちらも NULL をすることはできません。  
  
 このプロシージャは、実行しているコレクション セットのオンデマンドのアップロードを開始する場合に使用できます。 また、キャッシュ モードのデータ収集およびアップロード用に構成されているコレクション セットに対してのみ使用できます。 このプロシージャを使用すると、ユーザーは分析に必要なデータを、予定されているアップロードを待たずに取得できます。  
  
## <a name="permissions"></a>アクセス許可  
 メンバーシップが必要です、 **dc_operator** (EXECUTE 権限) を持つ固定データベース ロールにこのプロシージャを実行します。  
  
## <a name="example"></a>例  
 `Simple Collection Set` という名前のコレクション セットのオンデマンドのアップロードを実行します。  
  
```  
USE msdb;  
GO  
EXEC sp_syscollector_upload_collection_set @name = 'Simple Collection Set' ;  
```  
  
## <a name="see-also"></a>参照  
 [システム ストアド プロシージャ &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [[データ コレクション]](../../relational-databases/data-collection/data-collection.md)  
  
  
