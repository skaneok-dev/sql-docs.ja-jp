---
title: 外部結合 |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- outer join escape sequences [ODBC]
- escape sequences [ODBC], outer join
ms.assetid: be1a0203-5da9-4871-9566-4bd3fbc0895c
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: cd35a8bd0e2a9280d16614a3979dc2af05487e42
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47619610"
---
# <a name="outer-joins"></a>外部結合
ODBC は、sql-92 左、右、および完全外部結合の構文をサポートします。 外部結合のエスケープ シーケンスします。  
  
 **{oj** *外部-結合 * * *}**  
  
 場所*外部結合*は  
  
 *テーブル参照*{**左 &#124; です。右 &#124; です。FULL} OUTER JOIN** {*テーブル参照*&#124; です。*外部結合*} **ON** *検索条件*  
  
 *テーブル参照*テーブル名を指定し、*検索条件*間の結合条件を指定します、*テーブル参照*。  
  
 外部結合要求が後に表示する必要があります、 **FROM**キーワードとする前に、**場所**句 (存在する場合。 完全な構文については、次を参照してください。[外部結合エスケープ シーケンス](../../../odbc/reference/appendixes/outer-join-escape-sequence.md)付録 c: SQL の文法でします。  
  
 たとえば、次の SQL ステートメントは、すべての顧客の一覧に未処理注文が表示されるのと同じ結果セットを作成します。 最初のステートメントでは、エスケープ シーケンス構文を使用します。 2 番目のステートメントでは、Oracle のネイティブの構文を使用して、相互運用可能なではありません。  
  
```  
SELECT Customers.CustID, Customers.Name, Orders.OrderID, Orders.Status  
   FROM {oj Customers LEFT OUTER JOIN Orders ON Customers.CustID=Orders.CustID}  
   WHERE Orders.Status='OPEN'  
  
SELECT Customers.CustID, Customers.Name, Orders.OrderID, Orders.Status  
   FROM Customers, Orders  
   WHERE (Orders.Status='OPEN') AND (Customers.CustID= Orders.CustID(+))  
```  
  
 データソースとドライバーをサポートする外部結合の種類を判断するには、アプリケーションが呼び出す**SQLGetInfo** SQL_OJ_CAPABILITIES フラグします。 サポート可能性のある外部結合の種類、left、right、完全なまたは外部結合は; を入れ子になった外部結合を内の列名で、 **ON**句内のそれぞれのテーブル名と同じ順序がない、 **OUTER JOIN**句; 外部結合は; を使用して外部結合と組み合わせて内部結合任意の ODBC 比較演算子。 SQL_OJ_CAPABILITIES 情報の種類では、0 を返します、外部結合句はサポートされません。
