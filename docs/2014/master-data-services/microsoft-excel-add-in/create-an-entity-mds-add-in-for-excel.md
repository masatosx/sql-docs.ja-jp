---
title: エンティティの作成 (Excel 用 MDS アドイン) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: d354abb3-88fe-4b40-a374-f6256b84ffae
caps.latest.revision: 7
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: b82d170d7af35d21f19fd90d2328ccbdd07f4a3a
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37213312"
---
# <a name="create-an-entity-mds-add-in-for-excel"></a>エンティティの作成 (Excel 用 MDS アドイン)
  [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]の管理者は、新しいエンティティを作成してデータを格納することができます。 エンティティを作成する場合、少なくとも、格納するデータのサンプリングを読み込む必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには  
  
-   **[システム管理]** および **[エクスプローラー]** 機能領域に対する権限が必要です。  
  
-   モデル管理者である必要があります。 詳細については、「[Administrators &#40;Master Data Services&#41; (管理者 &#40;マスター データ サービス&#41;)](../administrators-master-data-services.md)」を参照してください。  
  
-   エンティティの作成先となる既存のモデルが存在する必要があります。 詳細については、「[モデルを作成する (マスター データ サービス)](../create-a-model-master-data-services.md)」を参照してください。  
  
-   データが次の要件を満たしていることを確認します。  
  
    -   データにはヘッダー行が必要です。  
  
    -   **[名前]** 列と **[コード]** 列があると便利です。 **[コード]** は、各行の一意の識別子です。  
  
    -   ヘッダー以外に、少なくとも 1 行のデータが必要です。 すべての列が値を持つ必要はありませんが、そのデータはエンティティに含まれるデータを代表するものである必要があります。  
  
    -   一意の識別子 (MDS の場合は " **コード**") を含む列がある場合は、その値が一意であることを確認します。 識別子を含む列がない場合は、エンティティを作成するときに自動的にこれらの列を生成できます。  
  
    -   式を含むセルがないことを確認します。  
  
    -   時刻の値を含むセルがないことを確認します。 MDS では日付の値は保存できますが、時刻の値は保存できません。  
  
### <a name="to-create-an-entity-and-load-data"></a>エンティティを作成してデータを読み込むには  
  
1.  読み込むデータを含む Excel ワークシートを開くか、作成します。  
  
2.  新しいエンティティに読み込むセルを選択します。  
  
3.  **[マスター データ]** タブで、 **[モデルの構築]** グループの **[エンティティの作成]** をクリックします。  
  
4.  MDS リポジトリへの接続を求めるメッセージが表示された場合は、接続します。  
  
5.  **[エンティティの作成]** ダイアログ ボックスで、既定の範囲のままにするか、読み込むデータに合うように範囲を変更します。  
  
6.  **[データにヘッダーが含まれている]** チェック ボックスはオフにしないでください。  
  
7.  **[モデル]** ボックスの一覧からモデルを選択します。  
  
8.  **[バージョン]** ボックスの一覧からバージョンを選択します。  
  
9. **[新しいエンティティ名]** ボックスに、エンティティの名前を入力します。  
  
10. **[コード]** ボックスの一覧から、一意の識別子または自動的に生成されたコードを含む列を選択します。  
  
11. 任意。 **[名前]** ボックスの一覧から、各メンバーの名前を含む列を選択します。  
  
12. **[OK]** をクリックします。 エンティティが正常に作成されると、新しいヘッダー行が表示され、セルが強調表示されます。シート名は、エンティティ名と一致するように更新されます。  
  
## <a name="next-steps"></a>次の手順  
  
-   発生したエラーを確認するには、 **[パブリッシュと検証]** グループの **[状態の表示]** をクリックします。 ValidationStatus 列と InputStatus 列が表示されます。 詳細については、「[データの検証 (Excel 用 MDS アドイン)](validating-data-mds-add-in-for-excel.md)」を参照してください。  
  
-   想定していたデータ型として属性が作成されたことを確認します。  
  
## <a name="see-also"></a>参照  
 [ドメイン ベースの属性の作成 &#40;Excel 用 MDS アドイン&#41;](create-a-domain-based-attribute-mds-add-in-for-excel.md)  
  
  