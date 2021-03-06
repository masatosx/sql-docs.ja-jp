---
title: sys.filetable_system_defined_objects (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.filetable_system_defined_objects_TSQL
- filetable_system_defined_objects
- filetable_system_defined_objects_TSQL
- sys.filetable_system_defined_objects
dev_langs:
- TSQL
helpviewer_keywords:
- sys.filetable_system_defined_objects catalog view
ms.assetid: 62022e6b-46f6-495f-b14b-53f41e040361
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: d18b3c20a78c4f819827a389a3811946bfef33ce
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47660760"
---
# <a name="sysfiletablesystemdefinedobjects-transact-sql"></a>sys.filetable_system_defined_objects (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  FileTable に関連するシステム定義のオブジェクトの一覧が表示されます。 システム定義のオブジェクトごとに 1 行のデータを格納します。  
  
 FileTable を作成すると、関連するオブジェクト (制約、インデックスなど) が同時に作成されます。 これらのオブジェクトを変更または削除することはできません。これらは、FileTable 自体が削除されると一緒に削除されます。  
  
 FileTables について詳しくは、「[FileTables &#40;SQL Server&#41;](../../relational-databases/blob/filetables-sql-server.md)」をご覧ください。  
  
|[列]|データ型|説明|  
|------------|---------------|-----------------|  
|**object_id**|**int**|FileTable に関連するシステム定義オブジェクトのオブジェクト ID。<br /><br /> オブジェクト参照**sys.objects**します。|  
|**parent_object_id**|**int**|親 FileTable のオブジェクト ID。<br /><br /> オブジェクト参照**sys.objects**します。|  
  
## <a name="see-also"></a>参照  
 [FileTable の作成、変更、および削除](../../relational-databases/blob/create-alter-and-drop-filetables.md)   
 [FileTable の管理](../../relational-databases/blob/manage-filetables.md)  
  
  
