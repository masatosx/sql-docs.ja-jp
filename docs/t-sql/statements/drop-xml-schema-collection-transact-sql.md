---
title: DROP XML SCHEMA COLLECTION (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 11/25/2015
ms.prod: sql
ms.prod_service: sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- DROP XML SCHEMA COLLECTION
- DROP_XML_SCHEMA_COLLECTION_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- deleting XML schema collections
- XML schema collections [SQL Server], removing
- schema collections [SQL Server], removing
- removing XML schema collections
- dropping XML schema collections
- DROP XML SCHEMA COLLECTION statement
ms.assetid: d686f2f5-e03a-4ffe-a566-6036628f46f1
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 320c11c78f95f644e373b1cd410858a81e72edad
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47804490"
---
# <a name="drop-xml-schema-collection-transact-sql"></a>DROP XML SCHEMA COLLECTION (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  XML スキーマ コレクション全体とそのすべてのコンポーネントを削除します。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
DROP XML SCHEMA COLLECTION [ relational_schema. ]sql_identifier  
```  
  
## <a name="arguments"></a>引数  
 *relational_schema*  
 リレーショナル スキーマ名を指定します。 指定しない場合、既定のリレーショナル スキーマが使用されます。  
  
 *sql_identifier*  
 削除する XML スキーマ コレクションの名前を指定します。  
  
## <a name="remarks"></a>Remarks  
 XML スキーマ コレクションの削除は、トランザクション操作です。 つまり、トランザクション内で XML スキーマ コレクションを削除し、後でトランザクションをロールバックすると、XML スキーマ コレクションは削除されなかったことになります。  
  
 XML スキーマ コレクションは、使用中は削除できません。 つまり、削除するコレクションに、次のものは指定できません。  
  
-   いずれかに関連付けられている **xml** パラメーターまたは列を入力します。  
  
-   任意のテーブル制約で指定されているコレクション。  
  
-   スキーマ バインド関数またはストアド プロシージャで参照されているコレクション。 たとえば、次の関数では `WITH SCHEMABINDING` が指定されるので、XML スキーマ コレクション `MyCollection` はロックされます。 このコレクションを削除すると、XML SCHEMA COLLECTION のロックはなくなります。  
  
    ```  
    CREATE FUNCTION dbo.MyFunction()  
    RETURNS int  
    WITH SCHEMABINDING  
    AS  
    BEGIN  
       ...  
       DECLARE @x XML(MyCollection)  
       ...  
    END;  
    ```  
  
## <a name="permissions"></a>アクセス許可  
 XML SCHEMA COLLECTION を削除するには、コレクションに対する DROP 権限が必要です。  
  
## <a name="examples"></a>使用例  
 次の例では、XML スキーマ コレクションを削除します。  
  
```  
DROP XML SCHEMA COLLECTION ManuInstructionsSchemaCollection;  
GO  
```  
  
## <a name="see-also"></a>参照  
 [CREATE XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](../../t-sql/statements/create-xml-schema-collection-transact-sql.md)   
 [ALTER XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](../../t-sql/statements/alter-xml-schema-collection-transact-sql.md)   
 [EVENTDATA &#40;Transact-SQL&#41;](../../t-sql/functions/eventdata-transact-sql.md)   
 [型指定された XML と型指定されていない XML の比較](../../relational-databases/xml/compare-typed-xml-to-untyped-xml.md)   
 [サーバー上の XML スキーマ コレクションの要件と制限](../../relational-databases/xml/requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
