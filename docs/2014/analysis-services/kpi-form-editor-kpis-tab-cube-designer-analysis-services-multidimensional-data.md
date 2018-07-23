---
title: KPI フォーム エディター ([Kpi] タブ、キューブ デザイナー) (Analysis Services - 多次元データ) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.kpidefinitionpane.f1
ms.assetid: 45c6453a-bbe2-4ca5-836e-c7ef11cfcb65
caps.latest.revision: 23
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 284ccc63f98624e1a64b114d31b69215d8e6b1be
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37224842"
---
# <a name="kpi-form-editor-kpis-tab-cube-designer-analysis-services---multidimensional-data"></a>KPI フォーム エディター (キューブ デザイナーの [KPI] タブ) (Analysis Services - 多次元データ)
  キューブ デザイナーの **[KPI]** タブの **KPI フォーム エディター** ペインを使用すると、選択した主要業績評価指標 (KPI) を変更したり作成したりできます。  
  
> [!NOTE]  
>  このペインはフォーム ビューでのみ表示されます。  
  
## <a name="options"></a>および  
 **名前**  
 KPI の名前を入力します。  
  
 **関連付けられたメジャー グループ**  
 KPI に関連付けられているメジャー グループを選択します。 クライアント アプリケーションでこの情報を使用して、ユーザーがこの KPI を参照するときに使用できるディメンションを判別できます。  
  
 **値式**  
 展開すると、KPI の値を返す多次元式 (MDX) を表示したり、編集したりできます。  
  
 KPI の値を返す MDX 式を入力します。  
  
 選択した要素を **[計算ツール]** ペインからこのオプションへドラッグして、選択した要素に対して MDX 構文を含めます。  
  
 **目標式**  
 展開すると、KPI の目標値を返す MDX 式を表示したり、編集したりできます。  
  
 KPI を実行したときの目標値を返す MDX 式を入力します。  
  
 選択した要素を **[計算ツール]** ペインからこのオプションへドラッグして、選択した要素に対して MDX 構文を含めます。  
  
 **ステータス**  
 展開すると、 **[状態マーク]** および **[状態式]** のオプションが表示されます。  
  
 **Statusgraphic**  
 クライアント アプリケーションで状態値をグラフィカルに表すために使用されるグラフィックを選択します。  
  
> [!NOTE]  
>  選択したグラフィックがクライアント アプリケーションでサポートされない場合、適切なグラフィックに置き換えてください。  
  
 **状態式**  
 KPI を実行したときの状態値を返す MDX 式を入力します。  
  
 選択した要素を **[計算ツール]** ペインからこのオプションへドラッグして、選択した要素に対して MDX 構文を含めます。  
  
 この式が -1 ～ 1 の間の 10 進数値を返すようにすることをお勧めします。 低い数値が悪い状況を表し、高い数値が良い状況を表すようにします。  
  
> [!NOTE]  
>  -1 よりも小さな値や 1 よりも大きな値を返すことも可能ですが、サード パーティ製のクライアント アプリケーションで正しく解釈されない可能性があります。  
  
 **傾向**  
 展開すると、 **[傾向マーク]** および **[傾向式]** のオプションが表示されます。  
  
 **傾向マーク**  
 クライアント アプリケーションで傾向値をグラフィカルに表すために使用されるグラフィックを選択します。  
  
> [!NOTE]  
>  選択したグラフィックがクライアント アプリケーションでサポートされない場合、適切なグラフィックに置き換えてください。  
  
 **傾向式**  
 KPI の傾向値を返す MDX 式を入力します。  
  
 選択した要素を **[計算ツール]** ペインからこのオプションへドラッグして、選択した要素に対して MDX 構文を含めます。  
  
 指定されたビジネス コンテキストで有効な時間ベースの条件に基づく傾向式を作成できます。 この式が -1 ～ 1 の間の 10 進数値を返すようにすることをお勧めします。 低い数値が一定期間の悪い傾向を表し、高い数値が一定期間の良い傾向を表すようにします。  
  
> [!NOTE]  
>  -1 よりも小さな値や 1 よりも大きな値を返すことも可能ですが、サード パーティ製のクライアント アプリケーションで正しく解釈されない可能性があります。  
  
 **[追加のプロパティ]**  
 展開すると、 **[フォルダーの表示]**、 **[親 KPI]**、 **[現在の時間メンバー]**、 **[加重]**、 **[説明]** のオプションが表示されます。  
  
 **表示フォルダー**  
 表示のためにクライアント アプリケーションで使用される KPI の分類を入力します。  
  
 表示フォルダー内のフォルダー名は円記号 (\\) を使用して区切り、複数の表示フォルダーはセミコロン (;) を使用して区切ります。 たとえば、「 `Category\Goal\Scientific;Category\Goal\Metric`」のように入力します。  
  
 **親 KPI**  
 クライアント アプリケーションで使用する KPI を分類するための、既存の KPI を選択します。  
  
> [!NOTE]  
>  このオプションを既存の KPI に設定した場合、 **[フォルダーの表示]** は無視されます。  
  
 **現在の時間メンバー**  
 KPI の一時的なコンテキストを識別するメンバーを返す MDX 式を入力します。  
  
 選択した要素を **[計算ツール]** ペインからこのオプションへドラッグして、選択した要素に対して MDX 構文を含めます。  
  
> [!IMPORTANT]  
>  この MDX 式では、 **[関連付けられたメジャー グループ]** で指定されたメジャー グループに関連付けられている時間ディメンション内の、メンバーの一意の名前が返される必要があります。  
  
 **Weight**  
 展開すると、KPI の重み計数を返す MDX 式を表示したり、編集したりできます。  
  
 選択した要素を **[計算ツール]** ペインからこのオプションへドラッグして、選択した要素に対して MDX 構文を含めます。  
  
 **[説明]**  
 KPI の説明をオプションで入力します。  
  
## <a name="see-also"></a>参照  
 [Kpi&#40;キューブ デザイナー&#41; &#40;Analysis Services - 多次元データ&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md)  
  
  