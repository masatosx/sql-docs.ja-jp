---
title: コレクション アクセス許可 (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology:
- master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services], permissions
- permissions [Master Data Services], collections
ms.assetid: 703e1bf5-4b4b-4830-8a5b-f979b09f677d
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: aa360d47553f539438843ab1872fedc270ac1e99
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47749698"
---
# <a name="collection-permissions-master-data-services"></a>コレクション権限 (Master Data Services)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  コレクション権限は、エンティティのすべてのコレクションに適用されます。 特定のコレクションに権限を与えることはできません。つまり、権限はすべてのコレクションに適用されます。  
  
> [!NOTE]  
>  これらの権限は、ユーザー インターフェイスの **[エクスプローラー]** 機能領域にのみ適用されます。  
  
|権限|[説明]|  
|----------------|-----------------|  
|**読み取り**|ユーザーがコレクションのメンバーとメンバーの属性を読み取ることができます。|  
|**作成**|ユーザーがコレクションのメンバーを作成して属性値を割り当てることができます。|  
|**Update**|ユーザーがコレクションのメンバー、属性、リレーションシップを更新できます。|  
|**削除**|ユーザーがコレクションのメンバーを削除できます。|  
|**Deny**|コレクション メンバーに対するアクセスをすべて拒否します。|  
  
 読み取り、作成、更新、削除の各権限は組み合わせることができます。 作成、更新、削除が割り当てられると、読み取り権限が自動的に割り当てられます。  
  
## <a name="see-also"></a>参照  
 [モデル オブジェクト権限を割り当てる (マスター データ サービス)](../master-data-services/assign-model-object-permissions-master-data-services.md)   
 [コレクション (マスター データ サービス)](../master-data-services/collections-master-data-services.md)   
 [モデル オブジェクト権限 (マスター データ サービス)](../master-data-services/model-object-permissions-master-data-services.md)  
  
  
