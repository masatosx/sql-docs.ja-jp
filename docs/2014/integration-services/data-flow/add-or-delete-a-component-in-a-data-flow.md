---
title: データ フローでコンポーネントを追加または削除する | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
helpviewer_keywords:
- adding components
- components [Integration Services], data flow
ms.assetid: d99124f9-0994-4f40-a48e-fdca6a4383e7
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: c1a94a9d0dfddde667d2e52d3f612cda41e00a1c
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48150288"
---
# <a name="add-or-delete-a-component-in-a-data-flow"></a>データ フローでコンポーネントを追加または削除する
  データ フロー コンポーネントとは、データ フロー内の変換元、変換、および変換先のことです。 コンポーネントをデータ フローに追加するには、データ フロー タスクを事前にパッケージ制御フローに含める必要があります。  
  
 次の手順では、パッケージのデータ フローでコンポーネントを追加または削除する方法について説明します。  
  
### <a name="to-add-a-component-to-a-data-flow"></a>データ フローにコンポーネントを追加するには  
  
1.  [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]で、目的のパッケージが含まれている [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] プロジェクトを開きます。  
  
2.  ソリューション エクスプローラーで、パッケージをダブルクリックして開きます。  
  
3.  **[制御フロー]** タブをクリックし、コンポーネントを追加するデータ フローが含まれているデータ フロー タスクをダブルクリックします。  
  
4.  ツールボックスで、 **[データ フローの変換元]**、 **[データ フロー変換]**、または **[データ フローの変換先]** を展開し、次にデータ フロー アイテムを **[データ フロー]** タブのデザイン画面にドラッグします。  
  
5.  更新したパッケージを保存するには、 **[ファイル]** メニューの **[選択されたファイルを上書き保存]** をクリックします。  
  
### <a name="to-delete-a-component-from-a-data-flow"></a>データ フローからコンポーネントを削除するには  
  
1.  [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]で、目的のパッケージが含まれている [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] プロジェクトを開きます。  
  
2.  ソリューション エクスプローラーで、パッケージをダブルクリックして開きます。  
  
3.  **[制御フロー]** タブをクリックし、コンポーネントを削除するデータ フローが含まれているデータ フロー タスクをダブルクリックします。  
  
4.  データ フロー コンポーネントを右クリックし、 **[削除]** をクリックします。  
  
5.  削除操作を確認します。  
  
6.  更新したパッケージを保存するには、 **[ファイル]** メニューの **[選択されたファイルを上書き保存]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [データ フロー内のコンポーネントを接続します。](data-flow.md)   
 [データ フロー コンポーネントでエラー出力を構成します。](../configure-an-error-output-in-a-data-flow-component.md)   
 [データ フロー](data-flow.md)  
  
  
