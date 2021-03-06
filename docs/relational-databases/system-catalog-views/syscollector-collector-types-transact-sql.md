---
title: syscollector_collector_types (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- syscollector_collector_types
- syscollector_collector_types_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- data collector view
- syscollector_collector_types view
ms.assetid: d5cd30bb-89fd-4814-a7e8-9074f043f90f
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 41ae978e31db70f0cc49469d5ec14ae6f075ab7e
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47650580"
---
# <a name="syscollectorcollectortypes-transact-sql"></a>syscollector_collector_types (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  コレクション アイテムのコレクターの種類に関する情報を提供します。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**collector_type_uid**|**uniqueidentifer**|コレクション型の GUID。 NULL 値は許可されません。|  
|**name**|**sysname**|コレクション型の名前。 NULL 値は許可されません。|  
|**parameter_schema**|**xml**|指定されたコレクターの種類の構成を記述する XML スキーマ。 この XML スキーマは、特定のコレクション アイテム インスタンスに関連付けられた実際の XML 構成を検証するときに使用されます。 NULL 値が許可されます。|  
|**parameter_formatter**|**xml**|コレクション セットのプロパティ ページで使用するために XML を変換するときのテンプレートを指定します。 NULL 値が許可されます。|  
|**collection_package_id**|**uniqueidentifer**|コレクション パッケージの GUID。 NULL 値は許可されません。|  
|**collection_package_path**|**nvarchar (4000)**|コレクション パッケージのパス。 NULL 値が許可されます。|  
|**collection_package_name**|**sysname**|コレクション パッケージの名前。 NULL 値は許可されません。|  
|**upload_package_id**|**uniqueidentifer**|アップロード パッケージの GUID。 NULL 値は許可されません。|  
|**upload_package_path**|**nvarchar (4000)**|アップロード パッケージのパス。 NULL 値が許可されます。|  
|**upload_package_name**|**sysname**|アップロード パッケージの名前。 NULL 値は許可されません。|  
|**is_system**|**bit**|(1) をオンまたはオフ (0) をコレクター型は、データ コレクターで出荷された場合、または後で追加された場合を示すために、 **dc_admin**します。 たとえば、社内またはサード パーティによって開発されたカスタム型が考えられます。 NULL 値は許可されません。|  
  
## <a name="permissions"></a>アクセス許可  
 SELECT 権限が必要**dc_operator**、 **dc_proxy**します。  
  
## <a name="change-history"></a>変更履歴  
  
|変更内容|  
|---------------------|  
|更新**collection_type_uid**列名を**collector_type_uid**します。|  
|説明を修正、 **parameter_schema**列値が null 許容であることを示します。|  
|追加、 **parameter_formatter**列。|  
|データ型を修正、 **collection_package_path**列、値が null 許容であることを示す説明を更新します。|  
|データ型を修正、 **upload_package_path**列、値が null 許容であることを示す説明を更新します。|  
  
## <a name="see-also"></a>参照  
 [データ コレクター ストアド プロシージャ &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql.md)   
 [データ コレクターのビュー &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/data-collector-views-transact-sql.md)   
 [[データ コレクション]](../../relational-databases/data-collection/data-collection.md)  
  
  
