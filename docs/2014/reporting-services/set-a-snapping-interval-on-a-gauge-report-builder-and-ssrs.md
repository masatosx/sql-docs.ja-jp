---
title: ゲージ (レポート ビルダーおよび SSRS) へのスナップ間隔の設定 |Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- reporting-services-native
ms.topic: conceptual
ms.assetid: 0ece7297-6e2f-47fb-835d-b9e9cce53fe2
author: maggiesmsft
ms.author: douglasl
manager: craigg
ms.openlocfilehash: fecae9ab27cdb354a4f1dad13f8e873e181ea789
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48219982"
---
# <a name="set-a-snapping-interval-on-a-gauge-report-builder-and-ssrs"></a>ゲージへのスナップ間隔の設定 (レポート ビルダーおよび SSRS)
  スナップ間隔とは、値を丸める際の倍数を定義するものです。 既定では、ゲージは、データ ペインで指定したフィールドの正確な値を指し示します。 ただし必要であれば、事前に設定した間隔に合わせて、正確な値を切り上げたり、切り捨てたりすることができます。 たとえば、ゲージの値が 34.2 であるとき、スナップ間隔として 5 を指定した場合、ゲージ ポインターが指し示す値は 35 になります。 ゲージの値が 31.2 であるとき、スナップ間隔として 5 を指定した場合、ゲージ ポインターが指し示す値は 30 になります。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-a-snapping-interval-on-a-gauge"></a>ゲージにスナップ間隔を設定するには  
  
1.  ゲージに表示されている任意の数値をクリックし、スケールを強調表示します。  
  
2.  プロパティ ペインを開きます。  
  
    > [!NOTE]  
    >  プロパティ ペインが表示されない場合に、クリックして、**ビュー**タブを選び、**プロパティ**チェック ボックスをオンします。  
  
3.  **ポインター**プロパティ ([...]) ボタンをクリックします。 ポインター コレクション エディターが開きます。  
  
4.  設定、 **SnappingEnabled**プロパティを`True`します。  
  
5.  設定、 **SnappingInterval**をスナップ間隔を表す値です。 実際の値を指定の倍数に丸めた位置までポインターがスナップされます。  
  
## <a name="see-also"></a>参照  
 [ゲージのスケールの書式設定 &#40;レポート ビルダーおよび SSRS&#41;](report-design/formatting-scales-on-a-gauge-report-builder-and-ssrs.md)   
 [ゲージのポインターの書式設定 &#40;レポート ビルダーおよび SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md)   
 [ゲージ (レポート ビルダーおよび SSRS)](report-design/gauges-report-builder-and-ssrs.md)  
  
  
