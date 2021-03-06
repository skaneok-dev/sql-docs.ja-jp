---
title: Members (String) (MDX) |Microsoft ドキュメント
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 302445cadc829de35eca28db2888aaa01673ca75
ms.sourcegitcommit: 97bef3f248abce57422f15530c1685f91392b494
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34741901"
---
# <a name="members-string-mdx"></a>Members (文字列) (MDX)


  文字列式で指定されたメンバーを返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
Members(Member_Name)   
```  
  
## <a name="arguments"></a>引数  
 *Member_Name*  
 メンバー名を指定する有効な文字列式です。  
  
## <a name="remarks"></a>コメント  
 **Members (String)** 関数を指定する名前を持つ 1 つのメンバーを返します。 通常、使用して、 **Members (String)** を提供する外部の関数と併用、 **Members (String)** 関数、メンバーを識別する文字列と**Members (String)** 関数がその指定したメンバーについて、値を返します。  
  
## <a name="example"></a>例  
 次の例では、 **Members (String)** 関数の有効なメンバーに、指定した文字列を変換して、文字列で指定されたメンバーの既定のメジャーを返します。 指定の文字列は単一引用符で囲まれています。 既定のメジャーは Reseller Sales Amount メジャーです。  
  
```  
SELECT Members ('[Geography].[Geography].[Country].&[United States] ') ON 0  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>参照  
 [MDX 関数リファレンス&#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
