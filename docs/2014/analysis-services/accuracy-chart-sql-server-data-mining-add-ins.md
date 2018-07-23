---
title: 精度チャート (SQL Server データ マイニング アドイン) |Microsoft Docs
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
- accuracy chart
- mining models, validating
- mining models, charting
- lift chart
- mining models, testing
- lift [data mining]
ms.assetid: 303973b4-71c0-4cfc-b7bc-92218b52509d
caps.latest.revision: 19
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: d331c1acb84b67a19eba2c6aacebfe68b947b217
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37222322"
---
# <a name="accuracy-chart-sql-server-data-mining-add-ins"></a>精度チャート (SQL Server データ マイニング アドイン)
  ![データ マイニング リボンで精度チャート ボタン](media/dmc-accchart.gif "データ マイニング リボンで、精度チャート ボタン")  
  
 精度チャートでは、新しいデータ セットにモデルを適用し、そのモデルの精度を評価できます。 このウィザードで作成される精度チャートは、*リフト チャート*、データ マイニング モデルの精度を測定に頻繁に使用されるグラフの種類であります。 このタイプの精度チャートには、ランダムな予測と理想的な予測 (100% 正確な予測) を基準とし、それらと比べた場合に特定のデータ マイニング モデルを使用することによって、どの程度の改善を見込めるかがグラフィカルに表示されます。 1 つのチャートで複数のモデルを比較できます。  
  
## <a name="example"></a>例  
 Adventure Works Cycles 社のマーケティング部門がターゲット メーリング キャンペーンの導入を検討しています。 これまでのキャンペーンの結果から、反応率は 10% 程度であることがわかっています。 データベースのテーブルには、10,000 人の潜在顧客のリストが保存されています。 一般的な反応率が 10% なので、このうち 1,000 人の顧客から何らかの反応があると予測できます。  
  
 しかし、今回は予算の都合上、広告を郵送できる顧客が 5,000 人に限られています。そこで、同社のマーケティング部門では、マイニング モデルを使用して、最も効果が期待できる 5,000 人の顧客を抽出することにしました。  
  
 5,000 人の顧客をランダムに選択した場合は、500 件の反応しか期待できません。これは、一般にターゲットとされた顧客の 10% しか反応しないためです。 このシナリオは、リフト チャートのランダム線によって示されています。  
  
 マイニング モデルを使って対象顧客を絞り込んだ場合はどうでしょうか。このモデルの予測が 100% 正確であると仮定した場合、このモデルが提示する 1,000 人の潜在顧客に広告を郵送すれば、1,000 件の反応を得られることになります。 このシナリオは、リフト チャートの理想線によって示されています。  
  
## <a name="using-the-accuracy-chart-wizard"></a>精度チャート ウィザードの使用  
 精度チャートを作成するには、既存のデータ マイニング構造を参照する必要があります。 モデルの予測対象が同じであれば、この構造に基づく複数のモデルの精度を測定できます。  
  
 使用可能な構造がわからない場合は、サーバーを参照できます。 詳細については、次を参照してください。 [Excel におけるモデルの参照&#40;SQL Server データ マイニング アドイン&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md)します。  
  
#### <a name="to-create-an-accuracy-chart"></a>精度チャートを作成するには  
  
1.  をクリックして、**データ マイニング クライアント**リボンです。  
  
2.  **精度と検証**グループで、**精度チャート**します。  
  
3.  **選択構造またはモデル** ダイアログ ボックスで、評価するモデルを選択します。 **[次へ]** をクリックします。  
  
    > [!NOTE]  
    >  テスト対象のデータに最も適合するモデルを選択する必要があります。  
  
4.  **Predict を予測する値の列の指定** ダイアログ ボックスで、該当する場合は、予測する列と対象の値を選択します。 **[次へ]** をクリックします。  
  
     たとえば、上の例では、顧客の反応をモデル化した列を選択し、ターゲット値として "Probably Will Buy" を指定します。  
  
    > [!NOTE]  
    >  連続値を予測することはできません。 ただし、値を不連続な範囲に分割することで、列を離散化することができます。 この操作はデータ マイニング モデルを作成する前に実行する必要があります。  
  
5.  **ソース データの選択** ダイアログ ボックスで、予測を作成するには、モデルに渡すデータのソースを指定します。  
  
6.  データ、およびモデルでは、格納されているテスト データではなく、外部ソースを使用している場合、**リレーションシップの指定**データ マイニング モデルの列に新しいソース データ内の列が使用されるダイアログ ボックスで、マップします。  
  
     列名が似ている場合、ウィザードによって自動的にマッピングされます。 入力データ内の列には、分析に無関係で無視できる列と、データ マイニング モデルで入力を処理するために必要な列があります。 このような列には、トランザクション ID、ターゲット値、または予測に使用される列が含まれます。 必要な列を割り当てなかった場合は、ウィザードに警告メッセージが示されます。  
  
7.  **[完了]** をクリックします。  
  
     ウィザードにより、リフト チャートおよび基になるデータを含んだレポートが作成されます。  
  
### <a name="requirements"></a>要件  
 不連続の値を予測する場合は、予測対象のターゲット値を選択する必要があります。 たとえば、"Yes: Buy" という反応が 1 で、"No: Do Not Buy" という反応が 2 のようにデータが分類されている場合は、予測値として 1 または 2 を指定する必要があります。 これに対し、特定の範囲の値を予測する場合、一度に比較できる値は 2 つまでです。 たとえば、5 以上のスコアを予測する場合は、ソース データを再定義し、結果を 5 以上と 5 未満という 2 つのグループに分類する新しいモデルを作成する必要があります。 その上で、この 2 つのグループの精度を比較できます。  
  
## <a name="understanding-accuracy"></a>精度について  
 作成できるチャートは 2 種類あります。1 つは予測可能な列の状態を指定するチャート、もう 1 つは状態を指定しないチャートです。  
  
 予測可能な列の状態を指定する場合、チャートの X 軸は、予測を比較するために使用されるテスト データ セットの割合を示します。 チャートの Y 軸は、指定された状態になると予測される値の割合を示します。  
  
 予測可能な列の状態を指定しない場合は、想定されるすべての予測に対するモデルの精度がチャートに示されます。  
  
 リフト チャートの機能、およびランダム予測線と理想予測線に基づく精度の計算方法については、[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] オンライン ブックの「リフト チャート」を参照してください。  
  
## <a name="see-also"></a>参照  
 [モデルの検証と予測用モデルの使用&#40;データ マイニング Excel 用アドイン&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md)  
  
  