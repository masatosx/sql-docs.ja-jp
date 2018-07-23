---
title: テーブルとビュー (データ ソース ビュー ウィザード) を選択 (Analysis Services) |Microsoft Docs
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
- sql12.asvs.datasourceviewwizard.selecttablesandviews.f1
ms.assetid: ea7d1232-f213-46e9-90d9-0fd616ca003d
caps.latest.revision: 25
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: b0ec6553114e5a6a5a0700a852c56d4be51eba39
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37279508"
---
# <a name="select-tables-and-views-data-source-view-wizard-analysis-services"></a>[テーブルとビューの選択] (データ ソース ビュー ウィザード) (Analysis Services)
  **[テーブルとビューの選択]** ページを使用すると、データ ソース ビューに含めるテーブルまたはビューをデータ ソースから選択できます。  
  
## <a name="options"></a>および  
 **使用可能なオブジェクト**  
 データ ソース スキーマのテーブルおよびビューをリストします。 複数のスキーマが一覧される場合、スキーマ名が各オブジェクトの名前のプレフィックスになります。 スキーマが 1 つしか表示されない場合、スキーマ名はオブジェクトの名前のプレフィックスにはなりません。  
  
 昇順または降順でリストを並べ替えるには、 **[名前]** または **[種類]** をクリックします。  
  
 **含まれるオブジェクト**  
 データ ソース ビューに含めるテーブルとビューを一覧表示します。  
  
 昇順または降順でリストを並べ替えるには、 **[名前]** または **[種類]** をクリックします。  
  
 **Assert**  
 **[使用できるオブジェクト]** にリストされるオブジェクトをフィルターします。 文字列を入力して **[フィルター]** ボタンをクリックすると、指定された文字列を含む名前のみが一覧表示されます。 正確な文字列を検索するには、文字列を二重引用符で囲みます。 大文字と小文字は区別されません。  
  
 次の表に一覧表示されているワイルドカード文字をフィルター文字列に含めることができます。  
  
|ワイルドカード文字|値|  
|------------------------|-----------|  
|**\***|任意の文字列|  
|**%**|任意の文字列|  
|**?**|1 つの文字|  
|**"** *string* **"**|リテラル文字列。 このワイルドカード文字は、オブジェクト名内の任意の部分文字列に一致します。|  
  
 **システム オブジェクトを表示します。**  
 **[使用できるオブジェクト]** にシステム オブジェクトを表示します。 このオプションは、データ ソース プロバイダーがシステム オブジェクトを公開する場合にのみ使用できます。 **[含まれているオブジェクト]** の一覧からシステム オブジェクトを削除すると、自動的にこのオプションが選択されます。  
  
 **関連テーブルを追加します。**  
 **[含まれているオブジェクト]** の一覧に関連するすべてのテーブルを追加します。 このオプションではビューを追加することはできません。 ただし、パーティション テーブルは追加できます。 ウィザードの **[名前の一致]** ページで名前の一致条件を選択した場合、このオプションは選択された条件に従って、論理的な関連テーブルも含みます。 テーブルには、新しく追加された関連テーブルに関連している場合や、元のテーブルと同一の構造を持つ場合のテーブルも含まれます。  
  
## <a name="see-also"></a>参照  
 [データ ソース ビュー ウィザードの F1 ヘルプ&#40;Analysis Services&#41;](data-source-view-wizard-f1-help-analysis-services.md)   
 [多次元モデルのデータ ソース ビュー](multidimensional-models/data-source-views-in-multidimensional-models.md)  
  
  