---
title: "リテラル プレフィックスおよびサフィックス |Microsoft ドキュメント"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQL statements [ODBC], interoperability
- interoperability of SQL statements [ODBC], literal prefixes and suffixes
- literals [ODBC], prefixes and suffixes
ms.assetid: 29f468f2-f557-4a92-b31d-569c63cc6272
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: ff05f946dee8f6034d04c5d719ada475255ba643
ms.contentlocale: ja-jp
ms.lasthandoff: 09/09/2017

---
# <a name="literal-prefixes-and-suffixes"></a>リテラル プレフィックスおよびサフィックス
SQL ステートメントで、*リテラル*実際のデータ値の文字表現です。 たとえば、次のステートメントで ABC、FFFF、および 10 はリテラルです。  
  
```  
SELECT CharCol, BinaryCol, IntegerCol FROM MyTable  
   WHERE CharCol = 'ABC' AND BinaryCol = 0xFFFF AND IntegerCol = 10  
```  
  
 一部のデータ型のリテラルは、特別なプレフィックスおよびサフィックスが必要です。 前の例では、文字リテラル (ABC) では、プレフィックスとサフィックスの両方として単一引用符 (') が必要です、バイナリ リテラル (FFFF) には 0 x プレフィックス、および整数リテラル (10) としてから、プレフィックスを必要とまたはサフィックスが付いていない文字が必要です。  
  
 日付、時刻、およびタイムスタンプを除くすべてのデータ型の相互運用可能なアプリケーションが、LITERAL_PREFIX および LITERAL_SUFFIX 列で作成された結果セットで返される値を使用します。 **SQLGetTypeInfo**です。 日付、時刻、タイムスタンプ、および datetime 間隔のリテラル、相互運用可能アプリケーションは、前のセクションで説明されているエスケープ シーケンスを使用する必要があります。