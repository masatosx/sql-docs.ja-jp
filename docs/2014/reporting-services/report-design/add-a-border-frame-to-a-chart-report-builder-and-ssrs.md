---
title: グラフへの枠線の追加 (レポート ビルダーおよび SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- reporting-services-native
ms.topic: conceptual
ms.assetid: ca0c5040-40bb-4cb7-bc2b-5bcbe73858bb
author: maggiesMSFT
ms.author: maggies
manager: craigg
ms.openlocfilehash: 4eeac09776fec458b1f887769cc690e158eab40b
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48160072"
---
# <a name="add-a-border-frame-to-a-chart-report-builder-and-ssrs"></a>グラフへの枠線の追加 (レポート ビルダーおよび SSRS)
  グラフの視覚効果を高めるには、グラフの外枠に罫線の使用を検討してください。 枠線を選択するには、 **[グラフのプロパティ]** ダイアログ ボックスを使用するか、プロパティ ペインを使用します。 グラフの枠線を他のデータ領域に適用することはできません。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-apply-a-border-to-a-chart"></a>グラフに罫線を適用するには  
  
1.  グラフ上の任意の場所を右クリックし、表示されるオプションから **[グラフのプロパティ]** を選択します。  
  
    > [!NOTE]  
    >  **[グラフのプロパティ]** が表示されていない場合は、ショートカット メニューの **[グラフ]** をポイントし、 **[グラフのプロパティ]** 選択します。  
  
2.  **[罫線]** を選択し、グラフに適用する罫線の種類をクリックします。  
  
3.  (省略可) 罫線のスタイルを表す値を選択するか、式を入力します。  
  
4.  (省略可) グラフの周囲に外枠として描く線の色を指定します。  
  
    > [!NOTE]  
    >  **[線の色]** ボックスの一覧には一般的な色が含まれています。 他の色を選択するには、一覧の **[その他の色]** をクリックし、一覧の横にある式 (**[fx]**) ボタンをクリックして **[式]** エディターを表示します。  
  
5.  (省略可) 罫線の幅を指定します。 有効な値は 0.25pt から 20pt までです。 優れた視覚効果を得るには、罫線のサイズを 1pt から 3pt までの間に維持することを検討してください。  
  
6.  (省略可) レポートの背景が白以外の場合、ページの色を同じ色に定義することを検討してください。 ページの色は、罫線の外の背景色です。  
  
7.  (省略可) フレームの種類を選択している場合、フレーム タイプと色を指定します。 **[フレームの塗りつぶしの色]** ボックスの一覧には一般的な色が含まれています。  
  
## <a name="see-also"></a>参照  
 [グラフ &#40;レポート ビルダーおよび SSRS&#41;](charts-report-builder-and-ssrs.md)   
 [グラフの書式設定 (レポート ビルダーおよび SSRS)](formatting-a-chart-report-builder-and-ssrs.md)   
 [グラフへの傾斜、エンボス、およびテクスチャのスタイルの追加 &#40;レポート ビルダーおよび SSRS&#41;](chart-effects-add-bevel-emboss-or-texture-report-builder.md)  
  
  
