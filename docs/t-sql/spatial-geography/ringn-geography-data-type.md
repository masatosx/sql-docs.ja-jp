---
title: RingN (geography データ型) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- RingN
- RingN_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- RingN method
ms.assetid: 30f47275-2727-4d22-bbec-c0c54bcb3ac2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: b1f115c4a0e9d210c1f668434986d903c65f70b4
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47837380"
---
# <a name="ringn-geography-data-type"></a>RingN (geography データ型)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  `1 ≤ n ≤ NumRings()` の範囲で、**geography** インスタンスの指定したリングを返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
.RingN (expression )  
```  
  
## <a name="arguments"></a>引数  
 *式 (expression)*  
 1 から **polygon** インスタンス内のリング数までの **int** 式です。  
  
## <a name="return-value"></a>戻り値  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 戻り値の型: **geography**  
  
 CLR の戻り値の型: **SqlGeography**  
  
## <a name="remarks"></a>Remarks  
 リング インデックス **n** の値が 1 未満の場合、このメソッドは、**ArgumentOutOfRangeException** をスローします。 リング インデックス値は、1 以上、かつ `NumRings()` で返される数値以下である必要があります。  
  
## <a name="examples"></a>使用例  
 2 つのリングを含む `Polygon` インスタンスを作成し、2 番目のリングを返す例を次に示します。  
  
```  
DECLARE @g geography;  
SET @g = geography::STGeomFromText('POLYGON((-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653), (-122.357 47.654, -122.357 47.657, -122.349 47.657, -122.349 47.650, -122.357 47.654))', 4326);  
SELECT @g.RingN(2).ToString();  
```  
  
## <a name="see-also"></a>参照  
 [Geography インスタンスの拡張メソッド](../../t-sql/spatial-geography/extended-methods-on-geography-instances.md)   
 [NumRings &#40;geography データ型&#41;](../../t-sql/spatial-geography/numrings-geography-data-type.md)  
  
  
