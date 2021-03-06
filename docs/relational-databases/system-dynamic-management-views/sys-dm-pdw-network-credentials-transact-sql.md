---
title: sys.dm_pdw_network_credentials (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.prod_service: pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: d4fee3ad-6285-4ea5-8513-5e6eb617abb0
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: '>= aps-pdw-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: 0661b5bd203cd1bca26ed6fb5bf380d6882dc5e5
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47609920"
---
# <a name="sysdmpdwnetworkcredentials-transact-sql"></a>sys.dm_pdw_network_credentials (TRANSACT-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md.md)]

  格納されているすべてのネットワーク資格情報の一覧を返します、[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]アプライアンスのすべての対象サーバーです。 結果は、コントロールのノード、およびすべてのコンピューティング ノードの一覧に表示されます。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|pdw_node_id|**int**|ノードに関連付けられている一意の数値 id です。|  
|target_server_name|**nvarchar(32)**|ターゲット サーバーの IP アドレスを[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]はユーザー名とパスワード資格情報を使用してアクセスします。|  
|username|**nvarchar(32)**|ユーザー名が、パスワードが保存されます。|  
|last_modified|**datetime**|資格情報を変更する最後の操作の日付と時刻。|  
  
## <a name="permissions"></a>アクセス許可  
 VIEW SERVER STATE が必要です。  
  
## <a name="general-remarks"></a>全般的な解説  
 この動的管理ビューのキーは、 *pdw_node_id* plus *target_server_name*します。  
  
## <a name="see-also"></a>参照  
 [SQL Data Warehouse と Parallel Data Warehouse の動的管理ビュー &#40;TRANSACT-SQL&#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  
