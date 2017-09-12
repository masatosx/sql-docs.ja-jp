---
title: "レベルのプロパティ - ユーザー階層 |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- user hierarchies [Analysis Services]
- hierarchies [Analysis Services], user
ms.assetid: dabb7335-887b-442a-b67c-4901ba1242b7
caps.latest.revision: 13
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 7fa44b453e1c91d8a43dde01ec582b59f22d3824
ms.contentlocale: ja-jp
ms.lasthandoff: 09/01/2017

---
# <a name="user-hierarchies---level-properties"></a>ユーザー階層のレベルのプロパティ
  次の表では、ユーザー定義階層におけるレベルのプロパティの一覧および説明を示します。  
  
|プロパティ|Description|  
|--------------|-----------------|  
|Description|レベルの説明を格納します。|  
|HideMemberIf|レベル内のメンバーをクライアント アプリケーションに対して非表示にするかどうかと、そのタイミングを示します。 このプロパティは、以下の値をとります。<br /><br /> Never<br /> メンバーは必ず表示されます。 これが既定値です。<br /><br /> OnlyChildWithNoName<br /> メンバーには、メンバーがその親の唯一の子メンバーの名前が空場合は表示されません。<br /><br /> OnlyChildWithParentName<br /> メンバーがその親の唯一の子で、メンバーの名前が親の名前と同じ場合、メンバーは表示されません。<br /><br /> NoName<br /> メンバーの名前が空の場合、メンバーは表示されません。<br /><br /> ParentName<br /> メンバーの名前がその親の名前と同じである場合、メンバーは表示されません。|  
|ID|レベルの一意の識別子 (ID) を格納します。|  
|名前|レベルの表示名を格納します。 既定では、レベルの名前はソース属性の名前と同じです。|  
|SourceAttribute|レベルの基になるソース属性の名前を格納します。|  
  
## <a name="see-also"></a>参照  
 [ユーザー階層プロパティ](../../analysis-services/multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md)  
  
  