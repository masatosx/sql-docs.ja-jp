---
title: キューブ オブジェクト (Analysis Services - 多次元データ) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
helpviewer_keywords:
- cubes [Analysis Services], objects
ms.assetid: 5cee362e-3f95-4467-bc6c-29b1518ecbf3
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 47befc9fb80f84318cd090bb673b6b6906da6508
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48047612"
---
# <a name="cube-objects-analysis-services---multidimensional-data"></a>Cube オブジェクト (Analysis Services - 多次元データ)
    
## <a name="introducing-cube-objects"></a>Cube オブジェクトの導入  
 簡単な <xref:Microsoft.AnalysisServices.Cube> オブジェクトは、基本情報、ディメンション、およびメジャー グループで構成されます。 基本情報には、キューブの名前、キューブの既定のメジャー、データ ソース、ストレージ モードなどが含まれます。  
  
 Dimensions コレクションには、データベースのディメンション コレクションのキューブで使用される、実際のディメンションのセットが含まれています。 すべてのディメンションは、キューブ内で参照される前に、データベースのディメンション コレクション内で定義されている必要があります。 プライベート ディメンションでは使用できない[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]します。  
  
 メジャー グループは、キューブ内のメジャーのセットです。 メジャー グループは、共通のデータ ソース ビューと共通のディメンション セットを持つ、メジャーのコレクションです。 メジャー グループは、メジャーの処理単位です。メジャー グループは個別に処理されてから参照できます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
|||  
|-|-|  
|トピック||  
|[アクション&#40;Analysis Services - 多次元データ&#41;](../multidimensional-models/actions-analysis-services-multidimensional-data.md)||  
|[集計と集計デザイン](aggregations-and-aggregation-designs.md)||  
|[計算](calculations.md)||  
|[キューブ セル&#40;Analysis Services - 多次元データ&#41;](cube-cells-analysis-services-multidimensional-data.md)||  
|[キューブ プロパティ](cube-properties-multidimensional-model-programming.md)||  
|[キューブのストレージ&#40;Analysis Services - 多次元データ&#41;](cube-storage-analysis-services-multidimensional-data.md)||  
|[キューブの翻訳](cube-translations.md)||  
|[ディメンション リレーションシップ](dimension-relationships.md)||  
|[主要業績評価指標&#40;Kpi&#41;多次元モデル](../multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md)||  
|[メジャーおよびメジャー グループ](../multidimensional-models/measures-and-measure-groups.md)||  
|[パーティション&#40;Analysis Services - 多次元データ&#41;](partitions-analysis-services-multidimensional-data.md)||  
|[パースペクティブ](perspectives.md)||  
  
  
