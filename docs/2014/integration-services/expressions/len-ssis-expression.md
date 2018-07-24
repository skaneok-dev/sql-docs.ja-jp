---
title: LEN (SSIS 式) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- LEN function
- number of characters
ms.assetid: d961398b-e4d0-4936-be17-8f4c5882a640
caps.latest.revision: 36
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 8e0158fef91845d189e9caa0647e23999ab27900
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37195602"
---
# <a name="len-ssis-expression"></a>LEN (SSIS 式)
  文字式の文字数を返します。 文字列の先頭および末尾に空白が含まれる場合、この関数は、それらの空白をカウントに含めます。 1 バイト文字の文字列と 2 バイト文字の文字列が同一の場合、LEN 関数は同一の値を返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
LEN(character_expression)  
```  
  
## <a name="arguments"></a>引数  
 *character_expression*  
 評価の対象となる式です。  
  
## <a name="result-types"></a>戻り値の型  
 DT_I4  
  
## <a name="remarks"></a>コメント  
 *character_expression* 引数には、DT_WSTR、DT_TEXT、DT_NTEXT、または DT_IMAGE データ型を使用できます。 詳細については、「 [Integration Services Data Types](../data-flow/integration-services-data-types.md)」を参照してください。  
  
 *character_expression* が DT_STR データ型の文字列リテラルまたはデータ列である場合は、LEN による演算の実行前に、暗黙的に DT_WSTR データ型にキャストされます。 その他のデータ型は、明示的に DT_WSTR データ型にキャストされる必要があります。 詳細については、「[Cast &#40;SSIS 式&#41;](cast-ssis-expression.md)」をご覧ください。  
  
 DT_TEXT、DT_NTEXT、DT_IMAGE などのバイナリ ラージ オブジェクト (BLOB) データ型に引数が渡された場合、LEN 関数はバイト カウントを返します。  
  
 引数が NULL の場合、LEN は NULL を返します。  
  
## <a name="expression-examples"></a>式の例  
 この例は、文字列リテラルの長さを返します。 返される結果は 12 です。  
  
```  
LEN("Ball Bearing")  
```  
  
 この例は、 **FirstName** と **LastName** 列の値の長さの差を返します。  
  
```  
LEN(FirstName) - LEN(LastName)  
```  
  
 システム変数 **MachineName**を使用して、コンピューター名の長さを返します。  
  
```  
LEN(@MachineName)  
```  
  
## <a name="see-also"></a>参照  
 [関数&#40;SSIS 式&#41;](functions-ssis-expression.md)  
  
  