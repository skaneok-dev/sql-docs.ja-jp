---
title: "CurrentOrdinal (MDX) |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- kbMDX
helpviewer_keywords:
- functions [MDX], CurrentOrdinal
ms.assetid: f127e0f1-c3f5-4cae-ad4c-b851e8728036
caps.latest.revision: 16
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: f9fc3eb51cfca14e1c543b86bdcff564c5844aa6
ms.contentlocale: ja-jp
ms.lasthandoff: 08/02/2017

---
# <a name="currentordinal-mdx"></a>CurrentOrdinal (MDX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  繰り返し処理中に、セット内の現在の繰り返し数を返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
Set_Expression.CurrentOrdinal  
```  
  
## <a name="arguments"></a>引数  
 *Set_Expression*  
 セットを返す有効な多次元式 (MDX) です。  
  
## <a name="remarks"></a>解説  
 反復処理に使用して、セットなどのときに、 [Filter (MDX)](../mdx/filter-mdx.md)または[Generate (MDX)](../mdx/generate-mdx.md) 、関数、 **CurrentOrdinal**は繰り返しの数を返します。  
  
## <a name="examples"></a>使用例  
 単純な例を次にどのように**CurrentOrdinal**で使用できる**生成**セット内での位置と、セット内の各項目の名前を含む文字列を返します。  
  
 `WITH SET MySet AS [Customer].[Customer Geography].[Country].MEMBERS`  
  
 `MEMBER MEASURES.CURRENTORDINALDEMO AS`  
  
 `GENERATE(MySet, CSTR(MySet.CURRENTORDINAL) + ") " + MySet.CURRENT.ITEM(0).NAME, ", ")`  
  
 `SELECT MEASURES.CURRENTORDINALDEMO ON 0`  
  
 `FROM [Adventure Works]`  
  
 実際に CurrentOrdinal が使用されるのは、非常に複雑な計算に限られます。 次の例では、製品の数を返しますを使用して、一意のセットで、**順序**関数を使用する前に空の組を順序付ける、**フィルター**関数。 **CurrentOrdinal**を比較し、関係を排除する関数を使用します。  
  
```  
WITH MEMBER [Measures].[PrdTies] AS Count  
   (Filter  
      (Order  
        (NonEmpty  
          ([Product].[Product].[Product].Members  
          , {[Measures].[Reseller Order Quantity]}  
          )  
       , [Measures].[Reseller Order Quantity]  
       , BDESC  
       ) AS OrdPrds  
    , NOT((OrdPrds.CurrentOrdinal < OrdPrds.Count   
       AND [Measures].[Reseller Order Quantity] =   
          ( [Measures].[Reseller Order Quantity]  
            , OrdPrds.Item  
               (OrdPrds.CurrentOrdinal  
               )  
            )  
         )  
         OR (OrdPrds.CurrentOrdinal > 1   
            AND [Measures].[Reseller Order Quantity] =   
               ([Measures].[Reseller Order Quantity]  
               , OrdPrds.Item  
                  (OrdPrds.CurrentOrdinal-2)  
                )  
             )  
          ))  
       )  
SELECT {[Measures].[PrdTies]} ON 0  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>参照  
 [MDX 関数リファレンス & #40 です。MDX と #41 です。](../mdx/mdx-function-reference-mdx.md)  
  
  
