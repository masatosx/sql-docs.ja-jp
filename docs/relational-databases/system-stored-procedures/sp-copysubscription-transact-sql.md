---
title: sp_copysubscription (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology:
- replication
ms.topic: language-reference
f1_keywords:
- sp_copysubscription
- sp_copysubscription_TSQL
helpviewer_keywords:
- sp_copysubscription
ms.assetid: 3c56cd62-2966-4e87-a986-44cb3fd0b760
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 8a0bb6f6614e1a19108faf2be780772508627af1
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47702380"
---
# <a name="spcopysubscription-transact-sql"></a>sp_copysubscription (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

    
> [!IMPORTANT]  
>  これはアタッチ可能なサブスクリプション機能ですが、非推奨とされており、将来のリリースで削除されます。 新しい開発作業でこの機能を使用しない必要があります。 パラメーター化されたフィルターを使用してパーティション分割されたマージ パブリケーションでは、パーティション スナップショットの新しい機能を使用することをお勧めします。この機能を使用すると、多数のサブスクリプションの初期化を簡単に実行できます。 詳しくは、「 [Snapshots for Merge Publications with Parameterized Filters](../../relational-databases/replication/snapshots-for-merge-publications-with-parameterized-filters.md)」をご覧ください。 パーティション分割されていないパブリケーションでは、バックアップを使用してサブスクリプションを初期化できます。 詳細については、「 [Initialize a Transactional Subscription Without a Snapshot](../../relational-databases/replication/initialize-a-transactional-subscription-without-a-snapshot.md)を使用して、サブスクリプションを手動で初期化する方法について説明します。  
  
 プル サブスクリプションはあるがプッシュ サブスクリプションはないサブスクリプション データベースをコピーします。 単一ファイルのデータベースのみをコピーできます。 このストアド プロシージャは、サブスクライバー側でサブスクリプション データベースについて実行されます。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sp_copysubscription [ @filename = ] 'file_name'  
    [ , [ @temp_dir = ] 'temp_dir' ]  
    [ , [ @overwrite_existing_file = ] overwrite_existing_file]  
```  
  
## <a name="arguments"></a>引数  
 [ **@filename =**] **'***file_name***'**  
 データ ファイル (.mdf) のコピーを保存する場所を表す、ファイル名を含む完全なパスの文字列を指定します。 *ファイル名*は**nvarchar (260)**、既定値はありません。  
  
 [  **@temp_dir=**] **'***temp_dir***'**  
 一時ファイルを格納するディレクトリの名前を指定します。 *temp_dir*は**nvarchar (260)**、既定値は NULL です。 NULL の場合、 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]既定のデータ ディレクトリが使用されます。 このディレクトリは、すべてのサブスクライバー データベース ファイルを合わせたファイル サイズを格納できるだけの領域を備えている必要があります。  
  
 [  **@overwrite_existing_file=**] **'***overwrite_existing_file***'**  
 指定された同じ名前の既存のファイルを上書きするかどうかを指定する省略可能なブール型フラグは、  **@filename**します。 *overwrite_existing_file*は**ビット**、既定値は**0**します。 場合**1**、によって指定されたファイルが上書きされます **@filename**存在します場合。 場合**0**、ストアド プロシージャ、ファイルが存在して、ファイルが上書きされない場合は失敗します。  
  
## <a name="return-code-values"></a>リターン コードの値  
 **0** (成功) または**1** (失敗)  
  
## <a name="remarks"></a>コメント  
 **sp_copysubscription**サブスクライバーでスナップショットを適用する代わりに、サブスクリプション データベースをファイルにコピーするすべての種類のレプリケーションで使用します。 データベースは、プル サブスクリプションのみをサポートするように構成する必要があります。 適切な権限を持つユーザーは、サブスクリプション データベースのコピーを作成し、サブスクリプション ファイル (.msf) を別のサブスクライバーに電子メールで送信、コピー、または転送できます。受信側のサブスクライバーでは、ファイルをサブスクリプションとしてアタッチできます。  
  
 コピーされるサブスクリプション データベースのサイズは 2 ギガバイト (GB) 未満でなければなりません。  
  
 **sp_copysubscription**はクライアント サブスクリプションを持つデータベースのみサポートされており、データベースはサーバー サブスクリプションを持つ場合に実行されることはできません。  
  
## <a name="permissions"></a>アクセス許可  
 メンバーのみ、 **sysadmin**固定サーバー ロールが実行できる**sp_copysubscription**します。  
  
## <a name="see-also"></a>参照  
 [スナップショット フォルダーの代替位置](../../relational-databases/replication/alternate-snapshot-folder-locations.md)   
 [システム ストアド プロシージャ &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
