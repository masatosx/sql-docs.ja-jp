---
title: MDX クエリの基礎 (Analysis Services) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- statements [MDX]
- Multidimensional Expressions [Analysis Services], statements
- Multidimensional Expressions [Analysis Services], queries
- MDX [Analysis Services], statements
- MDX queries [Analysis Services]
- MDX [Analysis Services], queries
- queries [MDX]
ms.assetid: a560383b-bb58-472e-95f5-65d03d8ea08b
caps.latest.revision: 29
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: cd81b9489e7b73f9897cd557999df3021e8f9e8d
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37163418"
---
# <a name="mdx-query-fundamentals-analysis-services"></a>MDX クエリの基礎 (Analysis Services)
  多次元式 (MDX) を使用すれば、多次元オブジェクト (たとえばキューブ) をクエリして、キューブ データが格納された多次元セル セットを返すことができます。 このトピックとサブトピックでは、MDX クエリの概要を説明します。  
  
 以下のトピックでは、MDX クエリとクエリが作成するセル セットについて、および基本的な MDX 構文の詳細について説明します。  
  
> [!NOTE]  
>  MDX クエリおよび計算に関連するパフォーマンスの問題の詳細については、「 [SQL Server 2005 Analysis Services パフォーマンス ガイド](http://go.microsoft.com/fwlink/?LinkId=81621)」の「効率的な MDX の記述」セクションを参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
|トピック|説明|  
|-----------|-----------------|  
|[MDX の基本的なクエリ&#40;MDX&#41;](mdx-query-the-basic-query.md)|MDX SELECT ステートメントの基本的な構文について説明します。|  
|[クエリ軸とスライサー軸によるクエリの制限 &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md)|クエリ軸とスライサー軸、およびそれらを指定する方法について説明します。|  
|[クエリ内のキューブ コンテキストの確立&#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md)|MDX SELECT ステートメントでの FROM 句の用途を説明します。|  
|[名前付き MDX のセットを構築&#40;MDX&#41;](mdx-named-sets-building-named-sets.md)|MDX での名前付きセットの用途と、名前付きセットを MDX クエリ内で作成および使用するために必要なテクニックについて説明します。|  
|[MDX の計算されるメンバーを構築&#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md)|MDX での計算されるメンバーに関する情報と、計算されるメンバーを MDX 式内で作成および使用するために必要なテクニックについて説明します。|  
|[MDX でのセル計算の構築&#40;MDX&#41;](../../multidimensional-models-olap-logical-cube-objects/calculations.md)|計算されるセルを作成および使用する処理の詳細について説明します。|  
|[作成して、プロパティ値を使用して&#40;MDX&#41;](../../creating-and-using-property-values-mdx.md)|ディメンション、レベル、メンバー、およびセルの各プロパティの作成時および使用時の処理の詳細について説明します。|  
|[データを操作する&#40;MDX&#41;](mdx-data-manipulation-manipulating-data.md)|ドリルスルーとロールアップを使ったデータ操作の基礎について、および MDX でのパス順序と解決順序について説明します。|  
|[データの変更&#40;MDX&#41;](mdx-data-modification-modifying-data.md)|書き戻しを使って多次元データを一時的または永続的に変更する方法について説明します。|  
|[変数とパラメーターを使用して&#40;MDX&#41;](using-variables-and-parameters-mdx.md)|MDX クエリ内での変数およびパラメーターの使用方法について説明します。|  
  
## <a name="see-also"></a>参照  
 [多次元式&#40;MDX&#41;リファレンス](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  