---
title: Reporting Services モバイル レポートのカスタム マップ | Microsoft Docs
ms.date: 03/30/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: mobile-reports
ms.topic: conceptual
ms.assetid: 59a4ebad-587a-4770-afcd-c69216b8afd9
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: a3786fcf92c767905c6295dffc8a24e7a86d2cbe
ms.sourcegitcommit: 9ece10c2970a4f0812647149d3de2c6b75713e14
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2018
ms.locfileid: "51813945"
---
# <a name="custom-maps-in-reporting-services-mobile-reports"></a>Reporting Services モバイル レポートのカスタム マップ
SQL Server Mobile Report Publisher の地理的マップは、*ESRI シェープファイル*と呼ばれる形式で定義されます。  
  
この形式は、もともとは一企業によって設計されたものですが、広く普及した準オープン形式として GIS アプリケーションの大部分で使用されるようになりました。 この形式に従い、Mobile Report Publisher でマップを定義するときは、次の 2 つのファイルを提供する必要があります。  
  
- 図形ジオメトリ用の .SHP ファイル  
- メタデータ用の .DBF ファイル  
  
ベース ファイル名は一致する必要があります (例: *canada.shp* と *canada.dbf*)。 メタデータには、マップにデータを設定するときに使用する対応する図形の名前 (キー) を値として含む *NAME* フィールドを含める必要があります。  
  
> **注**: SHP と DBF の2 つのマップ ファイルのサイズの合計が 512 KB 以下である必要があります。 マップ ファイルが大きすぎる場合は、[https://mapshaper.org/](https://mapshaper.org/) などのツールを使用してサイズを小さくします。  
  
[モバイル レポートにカスタムのマップを追加](../../reporting-services/mobile-reports/add-a-custom-map-to-a-reporting-services-mobile-report.md)する方法を確認してください。  
  
## <a name="technical-information"></a>技術情報  
  
- 公式の仕様: [https://www.esri.com/library/whitepapers/pdfs/shapefile.pdf](https://www.esri.com/library/whitepapers/pdfs/shapefile.pdf)  
- Wikipedia のシェープファイルの記事: [https://en.wikipedia.org/wiki/Shapefile](https://en.wikipedia.org/wiki/Shapefile)  
  
## <a name="creating--editing-map-geometry"></a>マップ ジオメトリの作成および編集  
  
シェープファイルの作成と編集プロセスは複雑であり、このドキュメントの範囲外です。 役に立つリソースとアプリケーションを次に示します。  
  
- ArcGIS: [https://www.arcgis.com/](https://www.arcgis.com/)  
- Adobe Illustrator 用 MAPublisher プラグイン: [https://www.avenza.com/mapublisher](https://www.avenza.com/mapublisher)  
- QuantumGIS (無料): [https://www.qgis.org/](https://www.qgis.org/)  
- Manco ShapeFile Editor: [https://www.mancosoftware.com/ShapeFileEditor](https://www.mancosoftware.com/ShapeFileEditor)  
  
## <a name="existing-shapefiles"></a>既存のシェープファイル  
  
次のような Web サイトから多くの既存のシェープファイルをダウンロードできます。  
  
- Diva-GIS: [https://www.diva-gis.org/Data](https://www.diva-gis.org/Data)  
- OpenStreetMap: [https://openstreetmapdata.com/data](https://openstreetmapdata.com/data)  
  
### <a name="see-also"></a>参照  
- [Maps in Reporting Services mobile reports](../../reporting-services/mobile-reports/maps-in-reporting-services-mobile-reports.md)  
- [Create and publish mobile reports with SQL Server Mobile Report Publisher (SQL Server Mobile Report Publisher でモバイル レポートを作成し発行する)](../../reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher.md)   
  
  
  
