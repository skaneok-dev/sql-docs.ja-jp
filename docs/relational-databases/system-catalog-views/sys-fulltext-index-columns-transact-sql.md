---
title: sys.fulltext_index_columns (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.fulltext_index_columns
- fulltext_index_columns
- sys.fulltext_index_columns_TSQL
- fulltext_index_columns_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- full-text indexes [SQL Server], columns
- sys.fulltext_index_columns catalog view
- full-text indexes [SQL Server], properties
ms.assetid: c34b8625-e53c-4281-ace6-d46230d5cb84
author: douglaslMS
ms.author: douglasl
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 08279891640407371c19884d4384fabb61786b54
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47857150"
---
# <a name="sysfulltextindexcolumns-transact-sql"></a>sys.fulltext_index_columns (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  フルテキスト インデックスの一部となっている列ごとに 1 行のデータを格納します。    
 
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**object_id**|**int**|列が属するオブジェクトの ID。|  
|**column_id**|**int**|フルテキスト インデックスの一部となっている列の ID。|  
|**type_column_id**|**int**|特定の行にあるドキュメント関するユーザー指定ドキュメント ファイル拡張子 (".doc"、".xls" など) を格納する型列の ID。 型列は、フルテキスト インデックスの作成中にフィルター選択する必要のあるデータを含む列に対してのみ指定されます。 該当しない場合は NULL になります。 詳細については、「 [検索用フィルターの構成と管理](../../relational-databases/search/configure-and-manage-filters-for-search.md)」を参照してください。|  
|**language_id**|**int**|このフルテキスト列にインデックスを付けるために使用するワード ブレーカーの言語の LCID。<br /><br /> 0 = ニュートラル。<br /><br /> 詳細については、次を参照してください。 [sys.fulltext_languages &#40;TRANSACT-SQL&#41;](../../relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql.md)します。|  
|**statistical_semantics**|**int**|1 = この列では、フルテキスト インデックス作成に加えて、統計的セマンティクスが有効になっています。|  
  
## <a name="permissions"></a>アクセス許可  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)]  
  
## <a name="see-also"></a>参照  
 [オブジェクト カタログ ビュー &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [カタログ ビュー &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
