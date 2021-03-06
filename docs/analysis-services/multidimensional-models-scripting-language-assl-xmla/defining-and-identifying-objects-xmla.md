---
title: 定義と識別 (XMLA) のオブジェクト |Microsoft Docs
ms.date: 05/02/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 48223f9718ae4eb87b0880c2f266c886ec7abbb0
ms.sourcegitcommit: 7fe14c61083684dc576d88377e32e2fc315b7107
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2018
ms.locfileid: "50145268"
---
# <a name="defining-and-identifying-objects-xmla"></a>オブジェクトの定義と識別 (XMLA)
  XML for Analysis (XMLA) コマンド内では、オブジェクト識別子とオブジェクト参照を使用してオブジェクトが識別されます。また、XMLA コマンド内では、Analysis Services Scripting Language (ASSL) 要素を使用してオブジェクトが定義されます。  
  
## <a name="object-identifiers"></a>オブジェクト識別子  
 インスタンスで定義されているオブジェクトの一意の識別子を使用して、オブジェクトが識別される[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]します。 オブジェクト識別子は明示的に指定されるか、[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] でオブジェクトが作成されるときに [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] インスタンスによって決定されます。 使用することができます、 [Discover](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover)オブジェクト識別子を取得するメソッドを後続**Discover**または[Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute)メソッドの呼び出し。  
  
## <a name="object-references"></a>オブジェクトの参照  
 いくつかの XMLA コマンドなど[削除](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/delete-element-xmla)または[プロセス](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/process-element-xmla)、オブジェクト参照を使用して、明確な方法でオブジェクトを参照してください。 オブジェクト参照には、コマンドの実行対象となるオブジェクトのオブジェクト識別子と、そのオブジェクトの先祖のオブジェクト識別子が含まれます。 たとえば、パーティションのオブジェクト参照には、パーティションのオブジェクト識別子と、そのパーティションの親メジャー グループ、キューブ、およびデータベースのオブジェクト識別子が含まれます。  
  
## <a name="object-definitions"></a>オブジェクト定義  
 [作成](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla)と[Alter](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) xmla コマンドを作成または変更、それぞれ、オブジェクトで、[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]インスタンス。 これらのオブジェクトの定義がによって表される、 [ObjectDefinition](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/objectdefinition-element-xmla) ASSL の要素を含む要素。 オブジェクト識別子は明示的に指定するすべての主要なと多くの副次オブジェクトを使用して、 [ID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla)要素。 場合、 **ID**要素は使用されず、[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]インスタンスを識別するオブジェクトに依存している名前付け規則の一意の識別子を提供します。 使用する方法についての詳細、**作成**と**Alter** 、オブジェクトを定義するためのコマンドを参照してください[を変更するオブジェクトの作成と&#40;XMLA&#41;](../../analysis-services/multidimensional-models-scripting-language-assl-xmla/creating-and-altering-objects-xmla.md)します。  
  
## <a name="see-also"></a>参照  
 [要素をオブジェクト&#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla)   
 [ParentObject 要素&#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla)   
 [Source 要素&#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla)   
 [Target 要素&#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/target-element-xmla)   
 [Analysis Services での XMLA による開発](../../analysis-services/multidimensional-models-scripting-language-assl-xmla/developing-with-xmla-in-analysis-services.md)  
  
  
