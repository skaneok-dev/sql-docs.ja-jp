---
title: 更新、削除、またはブックマークによるフェッチ |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- updating by bookmarks [ODBC]
- result sets [ODBC], bookmarks
- fetches [ODBC], by bookmarks [ODBC]
- deleting by bookmarks [ODBC]
- bookmarks [ODBC]
ms.assetid: e2ee58d7-c28f-435f-b537-06207215dd2f
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: c5af3cad39739c3b85a0c6298d682d8e75a5918d
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47765815"
---
# <a name="updating-deleting-or-fetching-by-bookmark"></a>ブックマークによる更新、削除、またはフェッチ
ブックマークを設定すると、結果を行セットのバッファー セットからフェッチを行った結果から削除された結果セットに更新するデータを識別するために使用できます。 呼び出しによってこれらの操作は実行**SQLBulkOperations**で、*オプション*SQL_UPDATE_BY_BOOKMARK、SQL_DELETE_BY_BOOKMARK、または SQL_FETCH_BY_BOOKMARK の引数。 これらの操作で使用されるブックマークは、列 0 の行セットのバッファーに格納されます。 ブックマークによる更新、行セットのバッファーから取得する結果セット列のデータが更新されます。 詳細については、次を参照してください。 [SQLBulkOperations を使ったデータの更新](../../../odbc/reference/develop-app/updating-data-with-sqlbulkoperations.md)します。
