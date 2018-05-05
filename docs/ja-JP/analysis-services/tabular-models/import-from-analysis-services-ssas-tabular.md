---
title: Analysis Services からのインポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/01/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: ''
ms.component: data-mining
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: b9a21b23-3a06-4ef8-bc06-9c79cdc54870
caps.latest.revision: 19
author: Minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: c1ec65ae85b329f0cd1002f8bfb8895dd7379de7
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="import-from-analysis-services"></a>Analysis Services からのインポート 
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]
  この記事の内容が、サーバーからインポート プロジェクト テンプレートでを使用して、既存のテーブル モデルからメタデータをインポートして新しいテーブル モデル プロジェクトを作成する方法について説明します[!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]です。  
  
## <a name="create-a-new-model-by-importing-metadata-from-an-existing-model-in-analysis-services"></a>Analysis Services の既存のモデルからのメタデータのインポートによる新しいモデルの作成  
 Analysis Services サーバーの既存のテーブル モデルからメタデータをコピーして、新しいテーブル モデル プロジェクトを作成するには、サーバーからインポート プロジェクト テンプレートを使用します。 新しいプロジェクトは、インポート元のモデルと同じデータ ソース接続、テーブル、リレーションシップ、メジャー、KPI、ロール、階層、パースペクティブ、およびパーティションを使用して作成されます。 ただし、データは既存のモデルから新しいモデル ワークスペースにコピーされません。 インポート プロセスが完了し、新しいモデル プロジェクトが作成された後、[すべて処理] を実行し、データ ソースから新しいモデル プロジェクト ワークスペース データベースにデータを読み込む必要があります。  
  
#### <a name="to-create-a-new-model-by-importing-metadata-from-an-existing-model"></a>既存のモデルからのメタデータのインポートによって、新しいモデルを作成するには  
  
1.  [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]の **[ファイル]** メニューの **[新規作成]** をクリックし、 **[プロジェクト]** をクリックします。  
  
2.  **[新しいプロジェクト]** ダイアログ ボックスの **[インストールされているテンプレート]** で **[ビジネス インテリジェンス]** をクリックし、 **[サーバーからインポート]** をクリックします。  
  
3.  **[名前]** でプロジェクトの名前を入力し、場所とソリューション名を指定してから **[OK]** をクリックします。  
  
4.  **[Analysis Services からのインポート]** ダイアログ ボックスの **[サーバー名]** で、インポートするモデル メタデータを含む Analysis Services サーバーの名前を指定します。  
  
5.  **[データベース名]** で、インポートするモデル メタデータを含むテーブル モデル データベースを選択し、 **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [プロジェクトのプロパティ](../../analysis-services/tabular-models/project-properties-ssas-tabular.md)  
  
  