---
title: "対称キーの権限 (TRANSACT-SQL) を取り消す |Microsoft ドキュメント"
ms.custom: 
ms.date: 08/10/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- symmetric keys [SQL Server], permissions
- permissions [SQL Server], symmetric keys
- REVOKE statement, symmetric keys
ms.assetid: 091da030-a768-4aa3-9509-cc23bd719cea
caps.latest.revision: 19
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: cf946b948a1bd79fbcf017833e708e545c6ffba5
ms.contentlocale: ja-jp
ms.lasthandoff: 09/01/2017

---
# <a name="revoke-symmetric-key-permissions-transact-sql"></a>REVOKE (対称キーの権限の取り消し) (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  対称キーに対して許可および拒否された権限を取り消します。  
   
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
REVOKE [ GRANT OPTION FOR ] permission [ ,...n ]    
    ON SYMMETRIC KEY :: symmetric_key_name   
        { TO | FROM } <database_principal> [ ,...n ]   
    [ CASCADE ]  
    [ AS <database_principal> ]  
  
<database_principal> ::=   
        Database_user   
    | Database_role   
    | Application_role   
    | Database_user_mapped_to_Windows_User   
    | Database_user_mapped_to_Windows_Group   
    | Database_user_mapped_to_certificate   
    | Database_user_mapped_to_asymmetric_key   
    | Database_user_with_no_login   
```  
  
## <a name="arguments"></a>引数  
 *アクセス許可*  
 対称キーに対して取り消すことができる権限を指定します。 権限の一覧については、後の「解説」を参照してください。  
  
 対称キー:: *asymmetric_key_name*  
 権限を取り消す対称キーを指定します。 スコープ修飾子 (::) が必要です。  
  
 GRANT OPTION  
 指定した権限を他のプリンシパルに許可するための権利が、取り消されます。 その権限自体は失効しません。  
  
> [!IMPORTANT]  
>  指定した権限が GRANT オプションなしでプリンシパルに許可されている場合は、その権限自体が取り消されます。  
  
 CASCADE  
 このプリンシパルによって権限が許可または拒否されている他のプリンシパルからも、同じ権限が取り消されることを示します。  
  
> [!CAUTION]  
>  WITH GRANT OPTION で許可されている権限を CASCADE で取り消すと、その権限の GRANT および DENY の両方が取り消されます。  
  
 {に |FROM} \< *database_principal*>  
 権限を取り消すプリンシパルを指定します。  
  
 AS \<database_principal > このクエリを実行するプリンシパルの権限を取り消す権利の派生元のプリンシパルを指定します。  
  
 *Database_user*  
 データベース ユーザーを指定します。  
  
 *Database_role*  
 データベース ロールを指定します。  
  
 *Application_role*  
 アプリケーション ロールを指定します。  
  
 *Database_user_mapped_to_Windows_User*  
 Windows ユーザーにマップされているデータベース ユーザーを指定します。  
  
 *Database_user_mapped_to_Windows_Group*  
 Windows グループにマップされているデータベース ユーザーを指定します。  
  
 *Database_user_mapped_to_certificate*  
 証明書にマップされているデータベース ユーザーを指定します。  
  
 *Database_user_mapped_to_asymmetric_key*  
 非対称キーにマップされているデータベース ユーザーを指定します。  
  
 *Database_user_with_no_login*  
 対応するサーバー レベルのプリンシパルがないデータベース ユーザーを指定します。  
  
## <a name="remarks"></a>解説  
 対称キーに関する情報は、 [sys.symmetric_keys](../../relational-databases/system-catalog-views/sys-symmetric-keys-transact-sql.md)カタログ ビューです。  
  
 GRANT OPTION で権限が許可されたプリンシパルから権限を取り消すときに CASCADE を指定しない場合、このステートメントは失敗します。  
  
 対称キーは、データベース レベルのセキュリティ保護可能なリソースで、権限の階層で親となっているデータベースに含まれています。 次の表に、対称キーで許可できる権限のうち最も限定的なものを、それらを暗黙的に含む一般的な権限と共に示します。  
  
|対称キー権限|権限が含まれる対称キー権限|権限が含まれるデータベース権限|  
|------------------------------|-----------------------------------------|------------------------------------|  
|ALTER|CONTROL|ALTER ANY SYMMETRIC KEY|  
|CONTROL|CONTROL|CONTROL|  
|REFERENCES|CONTROL|REFERENCES|  
|TAKE OWNERSHIP|CONTROL|CONTROL|  
|VIEW DEFINITION|CONTROL|VIEW DEFINITION|  
  
## <a name="permissions"></a>Permissions  
 対称キーに対する CONTROL 権限、またはデータベースに対する ALTER ANY SYMMETRIC KEY 権限が必要です。 AS オプションを使用する場合は、指定したプリンシパルが対称キーを所有している必要があります。  
  
## <a name="examples"></a>使用例  
 次の例では、対称キー `ALTER` に対する `SamInventory42` 権限を、ユーザー `HamidS` と、`HamidS` が `ALTER` 権限を許可した他のプリンシパルから取り消します。  
  
```  
USE AdventureWorks2012;  
REVOKE ALTER ON SYMMETRIC KEY::SamInventory42 TO HamidS CASCADE;  
GO  
```  
  
## <a name="see-also"></a>参照  
 [sys.symmetric_keys & #40 です。TRANSACT-SQL と #41 です。](../../relational-databases/system-catalog-views/sys-symmetric-keys-transact-sql.md)   
 [対称キーの権限の GRANT & #40 です。TRANSACT-SQL と #41 です。](../../t-sql/statements/grant-symmetric-key-permissions-transact-sql.md)   
 [対称キーの権限 &#40; を拒否します。TRANSACT-SQL と #41 です。](../../t-sql/statements/deny-symmetric-key-permissions-transact-sql.md)   
 [CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;](../../t-sql/statements/create-symmetric-key-transact-sql.md)   
 [アクセス許可 &#40;データベース エンジン&#41;](../../relational-databases/security/permissions-database-engine.md)   
 [プリンシパル &#40;データベース エンジン&#41;](../../relational-databases/security/authentication-access/principals-database-engine.md)   
 [暗号化階層](../../relational-databases/security/encryption/encryption-hierarchy.md)  
  
  

