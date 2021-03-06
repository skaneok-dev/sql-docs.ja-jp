---
title: 時刻および日付関数 (Visual FoxPro ODBC ドライバー) |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- ODBC date functions [ODBC]
- Visual FoxPro ODBC driver [ODBC], time and date functions
- FoxPro ODBC driver [ODBC], time and date functions
- time and date functions [ODBC]
- ODBC time and date functions [ODBC]
- date functions [ODBC]
ms.assetid: c1fb63b7-af50-45d6-8dec-ae6ea7119527
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 7752c1c1d5184ddb1beea26d7c35e29ea5769796
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47644330"
---
# <a name="time-and-date-functions-visual-foxpro-odbc-driver"></a>時刻および日付関数 (Visual FoxPro ODBC ドライバー)
次の表に、Visual FoxPro ODBC ドライバーでサポートされている ODBC の日付と時刻関数ODBC 構文から同じ関数の場合、Visual FoxPro の文法が異なる場合は、Visual FoxPro のと同じですが一覧表示されます。  
  
|ODBC の文法|Visual FoxPro の文法|  
|------------------|---------------------------|  
|CURDATE *)*|日付 *)*|  
|CURTIME *)*|時間 *)*|  
|DAYNAME *(date_exp)*|CDOW *(date_exp)*|  
|DAYOFMONTH (*date_exp)*|1 日 *)*|  
|1 時間 *(time_exp)*||  
|分 *(time_exp)*||  
|1 か月 *(time_exp)*||  
|MONTHNAME *(date_exp)*|CMONTH *(date_exp)*|  
|今すぐ *)*|DATETIME *)*|  
|2 番目 *(time_exp)*|1 秒 *(time_exp)*|  
|週 *(date_exp)*||  
|年 *(date_exp)*||  
  
 次の日付と時刻の関数がサポートされていません。  
  
 DAYOFYEAR *(date_exp)*  
  
 四半期 *(date_exp)*  
  
 TIMESTAMPADD *(間隔、integer_exp、timestamp_exp)*  
  
 TIMESTAMPDIFF *(間隔、timestamp_exp1、timestamp_exp2)*  
  
## <a name="odbc-escape-sequences"></a>ODBC エスケープ シーケンス  
 ドライバーには、日付とタイムスタンプのデータの ODBC エスケープ シーケンスもサポートしています。 エスケープ句の構文は次のとおりです。  
  
```  
--(*vendor(Microsoft),product(ODBC) d 'value' *)—  
--(*vendor(Microsoft),product(ODBC) ts ''value' *)—  
```  
  
 この構文で、 **d**ことを示します*値*の日付、 *- yyyy-mm-dd*形式と**ts**ことを示します*値*のタイムスタンプは、 *- yyyy-mm-dd hh:mm:ss*[.*f.*] 形式。 日付とタイムスタンプのデータの略式の構文は次のとおりです。  
  
```  
{d 'value'}  
{ts 'value'}  
```  
  
 たとえば、日付およびタイムスタンプの略式の構文をサポートされている SQL の UPDATE コマンドを使用して ALLTYPES テーブル、次のステートメントの各更新プログラムします。  
  
```  
UPDATE alltypes  
   SET DAT_COL={d'1968-04-28'}  
   WHERE KEY=111  
  
UPDATE alltypes  
   SET DTI_COL={ts'1968-04-28 12:00:00'}  
   WHERE KEY=111  
```  
  
## <a name="remarks"></a>コメント  
 エスケープ シーケンスの詳細については、次を参照してください。 [odbc エスケープ シーケンス](../../odbc/reference/develop-app/escape-sequences-in-odbc.md)で、 *ODBC プログラマ リファレンス*します。
