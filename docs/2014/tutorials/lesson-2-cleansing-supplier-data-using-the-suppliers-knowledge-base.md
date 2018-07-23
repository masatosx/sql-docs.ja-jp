---
title: 'レッスン 2: Suppliers ナレッジ ベースを使用して仕入先データのクレンジング |Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- data-quality-services
- integration-services
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 215c14de-fc3f-46de-a022-bf69b9ea2a96
caps.latest.revision: 7
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 5708dfe72d3eaa745d1ffefd88147b3e72b7c46c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37191222"
---
# <a name="lesson-2-cleansing-supplier-data-using-the-suppliers-knowledge-base"></a>レッスン 2: Suppliers ナレッジ ベースを使用して仕入先データをクレンジングする
  このレッスンでを使用して Excel ファイルの仕入先データをクレンジングする、 **Suppliers**最初のレッスンで作成したナレッジ ベース。 DQS でのデータ クレンジングが含まれています、**コンピューター支援型プロセス**データは、ナレッジ ベース内のナレッジに準拠する方法を分析し、**対話型プロセス**確認および変更することができますコンピューター支援型プロセスの結果。 データ クレンジング機能は、データ ソース内の不適切なデータを識別し、不適切なデータを修正するか、修正を提案します。 また、ドメイン値、シノニムの先頭の値、ドメイン ルール、用語ベースのリレーション、および参照データを使用して、顧客データを標準化および拡充します。 対話形式で、コンピューター支援型プロセスによって提案された変更を承認または拒否できます。 参照してください[データ クレンジング](http://msdn.microsoft.com/library/gg524800.aspx)の詳細。  
  
 コンピューター支援型のプロセスでは、DQS クライアントのメイン ページで [構成] オプションを使用して構成できる次のしきい値が使用されます。  
  
-   **提案の最小スコア:** 最小スコア (信頼レベル) の値を提案するために DQS によって使用されます。  
  
-   **自動修正の最小スコア:** 最小スコアまたは信頼レベルでは自動的に値を修正するために DQS によって使用されます。  
  
 参照してください[クレンジングと照合のしきい値の値を構成する](http://msdn.microsoft.com/library/hh510415.aspx)これらの設定を構成する方法の詳細について。  
  
 このレッスンでは、次のタスクを実行して、Suppliers ナレッジ ベースを使用して入力データをクレンジングします。  
  
1.  クレンジングのデータ品質プロジェクトを作成し、Excel ファイルのソース データの解析とクレンジングに使用するナレッジ ベースとして Suppliers ナレッジ ベースを選択して、クレンジング アクティビティを選択します。  
  
2.  クレンジング対象の Excel の列を、ナレッジ ベースの適切な DQS ドメイン/複合ドメインにマップします。  
  
3.  コンピューター支援型のクレンジング アクティビティを実行します。 コンピューター支援型のプロセスでは、データ品質クライアントにデータ品質情報が表示され、ここではインタラクティブなデータ クレンジングを実行できます。  
  
4.  クレンジング アクティビティの結果を表示および管理します。 コンピューター支援型のプロセスによって、正しい、正しくないが修正済み、提示された変更内容が正しくない、または無効であると検出された値を確認できます。 変更を承認または拒否するには、"次に修正" フィールドを使用して、コンピューター支援型のプロセスからの提案を修正またはオーバーライドします。  
  
5.  クレンジング プロセスから Excel ファイルに結果をエクスポートします。  
  
6.  クレンジング プロジェクトからドメインに値をインポートして、新しいルール、値、修正などのナレッジ ベース内のナレッジを拡張します。  
  
## <a name="next-step"></a>次の手順  
 [タスク 1: データ品質プロジェクトを作成する](../../2014/tutorials/task-1-creating-a-data-quality-project.md)  
  
  