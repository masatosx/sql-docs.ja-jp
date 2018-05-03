---
title: SeekEnum |Microsoft ドキュメント
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: ado
ms.technology:
- drivers
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- SeekEnum
helpviewer_keywords:
- SeekEnum enumeration [ADO]
ms.assetid: f0ec0c92-8253-47c6-9a14-e5dbccbad219
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 0752e2e4e0c840af2601f8946ec473124af8ac4a
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="seekenum"></a>SeekEnum
型を指定[シーク](../../../ado/reference/ado-api/seek-method.md)を実行します。  
  
|定数|値|Description|  
|--------------|-----------|-----------------|  
|**adSeekFirstEQ**|1|最初のキーと等しいをシーク*keyvalues とも*します。|  
|**adSeekLastEQ**|2|最後のキーと等しいをシーク*keyvalues とも*します。|  
|**adSeekAfterEQ**|4|等しいか、キーをシーク*keyvalues とも*または直後に一致するが発生したとします。|  
|**adSeekAfter**|8|Where の直後に、キーをシークとの一致*keyvalues とも*発生します。|  
|**adSeekBeforeEQ**|16|等しいか、キーをシーク*keyvalues とも*かその直前までと一致するが発生したとします。|  
|**adSeekBefore**|32|場所と一致するキーの直前にシーク*keyvalues とも*発生します。|  
  
## <a name="adowfc-equivalent"></a>該当するショートカットは ADO/WFC  
 パッケージ: **com.ms.wfc.data**  
  
|定数|  
|--------------|  
|AdoEnums.Seek.FIRSTEQ|  
|AdoEnums.Seek.LASTEQ|  
|AdoEnums.Seek.AFTEREQ|  
|AdoEnums.Seek.AFTER|  
|AdoEnums.Seek.BEFOREEQ|  
|AdoEnums.Seek.BEFORE|  
  
## <a name="applies-to"></a>適用対象  
 [Seek メソッド](../../../ado/reference/ado-api/seek-method.md)