---
title: "sys.dm_repl_tranhash (TRANSACT-SQL) |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.dm_repl_tranhash
- sys.dm_repl_tranhash_TSQL
- dm_repl_tranhash_TSQL
- dm_repl_tranhash
dev_langs: TSQL
helpviewer_keywords: sys.dm_repl_tranhash dynamic management view
ms.assetid: 0cc52338-e805-4ed4-9835-b19bbf72448e
caps.latest.revision: "13"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 40d5bdff43e1022e62f20092b8b3d8dff1928231
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmrepltranhash-transact-sql"></a>sys.dm_repl_tranhash (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  トランザクション パブリケーションでレプリケートされるトランザクションに関する情報を返します。  
  
||  
|-|  
|**適用対象**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] から [現在のバージョン](http://go.microsoft.com/fwlink/p/?LinkId=299658)まで)。|  
  
|column_name|data_type|description|  
|------------------|----------------|-----------------|  
|**バケット**|**bigint**|ハッシュ テーブルに含まれるバケット数。|  
|**hashed_trans**|**bigint**|現在のバッチでレプリケートされるコミット済みトランザクションの数。|  
|**completed_trans**|**bigint**|これまでに完了したトランザクションの数。|  
|**compensated_trans**|**bigint**|部分ロールバックを含むトランザクションの数。|  
|**first_begin_lsn**|**nvarchar(64)**|現在のバッチで最も早い開始ログ シーケンス番号 (LSN)。|  
|**last_commit_lsn**|**nvarchar(64)**|現在のバッチで最後にコミットされた LSN。|  
  
## <a name="permissions"></a>Permissions  
 呼び出す、パブリケーション データベースに対する VIEW DATABASE STATE 権限が必要**dm_repl_tranhash**です。  
  
## <a name="remarks"></a>解説  
 返される情報は、レプリケーション アーティクル キャッシュに現在読み込まれている、レプリケートされたデータベース オブジェクトの情報だけです。  
  
## <a name="see-also"></a>参照  
 [動的管理ビューと動的管理関数 &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [レプリケーション関連の動的管理ビュー &#40;です。TRANSACT-SQL と #41 です。](../../relational-databases/system-dynamic-management-views/replication-related-dynamic-management-views-transact-sql.md)  
  
  