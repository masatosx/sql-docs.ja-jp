---
title: SET IDENTITY_INSERT (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- SET IDENTITY_INSERT
- SET_IDENTITY_INSERT_TSQL
- IDENTITY_INSERT_TSQL
- IDENTITY_INSERT
dev_langs:
- TSQL
helpviewer_keywords:
- IDENTITY_INSERT option
- SET IDENTITY_INSERT statement
- identity values [SQL Server], explicit values
- identity columns [SQL Server], explicit values
ms.assetid: a5dd49f2-45c7-44a8-b182-e0a5e5c373ee
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: d9ff472bed80096f0d7e10da2cc5019b3b31c399
ms.sourcegitcommit: b58d514879f182fac74d9819918188f1688889f3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2018
ms.locfileid: "50970753"
---
# <a name="set-identityinsert-transact-sql"></a>SET IDENTITY_INSERT (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

> [!div class="nextstepaction"]
> [SQL Server ドキュメントの改善にご協力ください。](https://80s3ignv.optimalworkshop.com/optimalsort/36yyw5kq-0)

テーブルの ID 列に明示的な値を追加することを許可します。  

 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
SET IDENTITY_INSERT [ [ database_name . ] schema_name . ] table_name { ON | OFF }  
```  
  
## <a name="arguments"></a>引数  
 *database_name*  
 指定したテーブルが含まれているデータベースの名前を指定します。  
  
 *schema_name*  
 テーブルが所属するスキーマの名前を指定します。  
  
 *table_name*  
 ID 列があるテーブルの名前を指定します。  
  
## <a name="remarks"></a>Remarks  
 IDENTITY_INSERT プロパティを ON に設定できるのは、セッション内の 1 つのテーブルのみです。 1 つのテーブルで既にこのプロパティが ON に設定されている状態で、別のテーブルに対して SET IDENTITY_INSERT ON ステートメントを実行すると、[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] では SET IDENTITY_INSERT が既に ON であるというエラー メッセージが返され、このプロパティが ON に設定されているテーブルがレポートされます。  
  
 挿入する値がテーブルの現在の ID 値よりも大きい場合、[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] では新しく挿入された値が現在の ID 値として自動的に使用されます。  
  
 SET IDENTITY_INSERT は、解析時ではなく実行時に設定されます。  
  
## <a name="permissions"></a>アクセス許可  
 ユーザーはテーブルを所有しているか、テーブルに対する ALTER 権限を持っている必要があります。  
  
## <a name="examples"></a>使用例  
 次の例では、ID 列を含むテーブルを作成した後、`SET IDENTITY_INSERT` ステートメントによって ID 値に発生したギャップを、`DELETE` の設定を使用して調整しています。  
  
```  
USE AdventureWorks2012;  
GO  
-- Create tool table.  
CREATE TABLE dbo.Tool(  
   ID INT IDENTITY NOT NULL PRIMARY KEY,   
   Name VARCHAR(40) NOT NULL  
);  
GO  
-- Inserting values into products table.  
INSERT INTO dbo.Tool(Name)   
VALUES ('Screwdriver')  
        , ('Hammer')  
        , ('Saw')  
        , ('Shovel');  
GO  
  
-- Create a gap in the identity values.  
DELETE dbo.Tool  
WHERE Name = 'Saw';  
GO  
  
SELECT *   
FROM dbo.Tool;  
GO  
  
-- Try to insert an explicit ID value of 3;  
-- should return a warning.  
INSERT INTO dbo.Tool (ID, Name) VALUES (3, 'Garden shovel');  
GO  
-- SET IDENTITY_INSERT to ON.  
SET IDENTITY_INSERT dbo.Tool ON;  
GO  
  
-- Try to insert an explicit ID value of 3.  
INSERT INTO dbo.Tool (ID, Name) VALUES (3, 'Garden shovel');  
GO  
  
SELECT *   
FROM dbo.Tool;  
GO  
-- Drop products table.  
DROP TABLE dbo.Tool;  
GO  
```  
  
## <a name="see-also"></a>参照  
 [CREATE TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/create-table-transact-sql.md)   
 [IDENTITY &#40;Property&#41; &#40;Transact-SQL&#41;](../../t-sql/statements/create-table-transact-sql-identity-property.md)   
 [SCOPE_IDENTITY &#40;Transact-SQL&#41;](../../t-sql/functions/scope-identity-transact-sql.md)   
 [INSERT &#40;Transact-SQL&#41;](../../t-sql/statements/insert-transact-sql.md)   
 [SET ステートメント &#40;Transact-SQL&#41;](../../t-sql/statements/set-statements-transact-sql.md)  
  
  
