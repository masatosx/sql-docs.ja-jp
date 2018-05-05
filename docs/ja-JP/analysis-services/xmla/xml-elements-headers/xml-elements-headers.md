---
title: ヘッダー (XMLA) |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- XMLA, headers
- SOAP headers [XML for Analysis]
- XML for Analysis, headers
- headers [XML for Analysis]
ms.assetid: 36407b5c-d98d-47e4-8d36-d8896e15a748
caps.latest.revision: 14
author: Minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 0fd680e1fe5df195752e1618fe23551f4c10f2a2
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="xml-elements---headers"></a>ヘッダーの XML 要素
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]
  XML for Analysis (XMLA) プロトコルでは、セッション サポートやサポートされる機能のネゴシエーションなど、プロトコルレベルの機能を管理するために、SOAP ヘッダー内で XML 要素を使用します。  
  
## <a name="in-this-section"></a>このセクションの内容  
 次のトピックでは、によって実装される XMLA ヘッダー要素[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]です。  
  
|方法|説明|  
|------------|-----------------|  
|[BeginSession 要素 & #40 です。XMLA & #41;](../../../analysis-services/xmla/xml-elements-headers/beginsession-element-xmla.md)|[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] のインスタンス上で新しいセッションを開始するために、SOAP 要求メッセージ内で SOAP ヘッダーを使用します。|  
|[EndSession 要素 & #40 です。XMLA & #41;](../../../analysis-services/xmla/xml-elements-headers/endsession-element-xmla.md)|[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] インスタンス上の既存のセッションを終了するために、SOAP 要求メッセージ内で SOAP ヘッダーを使用します。|  
|[Session 要素 & #40 です。XMLA & #41;](../../../analysis-services/xmla/xml-elements-headers/session-element-xmla.md)|[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] インスタンス上の既存の明示的なセッションを識別するために、SOAP 要求メッセージ内で SOAP ヘッダーを使用します。|  
|[ProtocolCapabilities 要素 & #40 です。XMLA & #41;](../../../analysis-services/xmla/xml-elements-headers/protocolcapabilities-element-xmla.md)|[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] インスタンスとクライアント アプリケーションの間のプロトコル機能を識別するために、SOAP 要求メッセージ内で SOAP ヘッダーを使用します。|  
  
## <a name="see-also"></a>参照  
 [XML 要素 & #40 です。XMLA & #41;](http://msdn.microsoft.com/library/40ab2360-efb6-4ba6-bf23-e84964e51008)   
 [XML データ型 & #40 です。XMLA & #41;](../../../analysis-services/xmla/xml-data-types/xml-data-types-xmla.md)   
 [XML 要素 & #40 です。XMLA & #41;](http://msdn.microsoft.com/library/40ab2360-efb6-4ba6-bf23-e84964e51008)  
  
  