---
title: ROUND (SSIS 式) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
helpviewer_keywords:
- rounding expressions
- ROUND function [SSIS]
ms.assetid: 376f1947-4fc5-4611-ad86-823e4db1b468
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 950d2c8aa3bd67327eb184017a71bc3851cb2abf
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48212262"
---
# <a name="round-ssis-expression"></a>ROUND (SSIS 式)
  指定された長さまたは有効桁数に丸めた数値式を返します。 length パラメーターは整数に評価される必要があります。  
  
## <a name="syntax"></a>構文  
  
```  
  
ROUND(numeric_expression,length)  
```  
  
## <a name="arguments"></a>引数  
 *numeric_expression*  
 有効な数値型の式です。 詳細については、「 [Integration Services Data Types](../data-flow/integration-services-data-types.md)」を参照してください。  
  
 *長さ*  
 整数式です。 *numeric_expression* の丸め結果とする有効桁数です。  
  
## <a name="result-types"></a>戻り値の型  
 *numeric*_*expression.* と同じ型。  
  
## <a name="remarks"></a>コメント  
 *length* 引数は正の整数または 0 に評価される必要があります。  
  
 引数が NULL の場合、ROUND は NULL を返します。  
  
## <a name="expression-examples"></a>式の例  
 この例では、数値リテラルを 3 桁に丸めます。 最初の結果は 137.1570 を返し、次の結果は 137.1580 を返します。  
  
```  
ROUND(137.1574,3)  
ROUND(137.1575,3)  
```  
  
## <a name="see-also"></a>参照  
 [関数&#40;SSIS 式&#41;](functions-ssis-expression.md)  
  
  
