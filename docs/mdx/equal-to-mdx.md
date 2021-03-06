---
title: = (等しい) (MDX) |Microsoft ドキュメント
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 1fac06690d811c3ae3d4b00a82ad9088b2df4aae
ms.sourcegitcommit: 97bef3f248abce57422f15530c1685f91392b494
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34739831"
---
# <a name="-equal-to-mdx"></a>= (等しい) (MDX)


  1 つの多次元式 (MDX) 式の値が、別の MDX 式の値と等しいかどうかを判別する比較演算を実行します。  
  
> [!NOTE]  
>  オブジェクトを比較する場合、 [IS &#40;MDX&#41; ](../mdx/is-mdx.md)演算子。 たとえば、クエリ軸上の現在のメンバーが特定のメンバーかどうかを確認する場合に IS 演算子を使用します。  
  
## <a name="syntax"></a>構文  
  
```  
  
MDX_Expression = MDX_Expression   
```  
  
#### <a name="parameters"></a>パラメーター  
 *MDX_Expression*  
 有効な MDX 式です。  
  
## <a name="return-value"></a>戻り値  
 以下の条件に基づくブール値です。  
  
-   **true**最初のパラメーターの値が 2 番目のパラメーターの値に等しい場合。  
  
-   **false**最初のパラメーターの値が 2 番目のパラメーターの値と等しくない場合。  
  
-   **true**かどうか両方のパラメーターが null、または 1 つのパラメーターが null とその他のパラメーターが 0 です。  
  
## <a name="examples"></a>使用例  
 次のクエリでは、これらの条件の例を示します。  
  
 `With`  
  
 `--Returns true`  
  
 `Member [Measures].bool1 as 1=1`  
  
 `--Returns false`  
  
 `Member [Measures].bool2 as 1=0`  
  
 `--Returns true`  
  
 `Member [Measures].bool3 as null=null`  
  
 `--Returns true`  
  
 `Member [Measures].bool4 as 0=null`  
  
 `--Returns false`  
  
 `Member [Measures].bool5 as 1=null`  
  
 `Select {[Measures].bool1,[Measures].bool2,[Measures].bool3,[Measures].bool4,[Measures].bool5}`  
  
 `On 0`  
  
 `From [Adventure Works]`  
  
## <a name="see-also"></a>参照  
 [MDX 演算子リファレンス&#40;MDX&#41;](../mdx/mdx-operator-reference-mdx.md)  
  
  
