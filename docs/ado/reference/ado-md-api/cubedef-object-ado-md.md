---
title: CubeDef オブジェクト (ADO MD) |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- CubeDef
helpviewer_keywords:
- CubeDef object [ADO MD]
ms.assetid: feb2581c-fc41-471c-bb69-29f8a55fda70
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: d1027fc76cb09f7b846e1b8edad52a3cb5dbf2bc
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47694066"
---
# <a name="cubedef-object-ado-md"></a>CubeDef オブジェクト (ADO MD)
関連するディメンションのセットを含む多次元スキーマからキューブを表します。  
  
## <a name="remarks"></a>コメント  
 コレクションのプロパティと、 **CubeDef**オブジェクトを次を行うことができます。  
  
-   識別、 **CubeDef**で、[名前](../../../ado/reference/ado-md-api/name-property-ado-md.md)プロパティ。  
  
-   使用してキューブを表す文字列を返す、[説明](../../../ado/reference/ado-md-api/description-property-ado-md.md)プロパティ。  
  
-   使用してキューブを構成するディメンションを返す、[ディメンション](../../../ado/reference/ado-md-api/dimensions-collection-ado-md.md)コレクション。  
  
-   に関する追加情報を取得、 **CubeDef**標準の ADO を使用した[プロパティ](../../../ado/reference/ado-api/properties-collection-ado.md)コレクション。  
  
 **プロパティ**コレクションには、プロバイダーが指定したプロパティが含まれています。 次の表は、使用可能な可能性があるプロパティを一覧表示します。 実際のプロパティの一覧は、プロバイダーの実装によって異なる場合があります。 使用可能なプロパティの詳細な一覧については、プロバイダーのドキュメントを参照してください。  
  
|名前|説明|  
|----------|-----------------|  
|CatalogName|このキューブが所属するカタログの名前。|  
|CreatedOn|キューブの作成日時。|  
|CubeGUID|キューブの GUID です。|  
|CubeName|キューブの名前。|  
|CubeType|キューブの種類。|  
|DataUpdatedBy|最終データ更新を実行するユーザーのユーザー ID。|  
|説明|キューブのわかりやすい説明。|  
|LastSchemaUpdate|スキーマの最終更新日時。|  
|SchemaName|このキューブが所属するスキーマの名前。|  
|SchemaUpdatedBy|スキーマの最終更新を実行するユーザーのユーザー ID。|  
  
 このセクションには、次のトピックが含まれています。  
  
-   [プロパティ、メソッド、およびイベント](../../../ado/reference/ado-md-api/cubedef-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>参照  
 [CubeDef の例 (VBScript)](../../../ado/reference/ado-md-api/cubedef-example-vbscript.md)   
 [Catalog オブジェクト (ADO MD)](../../../ado/reference/ado-md-api/catalog-object-ado-md.md)   
 [CubeDefs コレクション (ADO MD)](../../../ado/reference/ado-md-api/cubedefs-collection-ado-md.md)   
 [Dimensions コレクション (ADO MD)](../../../ado/reference/ado-md-api/dimensions-collection-ado-md.md)   
 [Properties コレクション (ADO)](../../../ado/reference/ado-api/properties-collection-ado.md)
