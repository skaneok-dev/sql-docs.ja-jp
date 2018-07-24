---
title: Configuration 要素 (DTA) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Configuration element
ms.assetid: 1478e56f-57c4-4441-bac9-1ac91453839b
caps.latest.revision: 16
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: b0383bc1c8bef5a84b77c8b63fb424995a2181ba
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37241752"
---
# <a name="configuration-element-dta"></a>Configuration 要素 (DTA)
  ワークロードのチューニング時にデータベース エンジン チューニング アドバイザーが分析する、既存の仮想物理設計構造から成るユーザー指定の構成を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
<DTAInput>  
    <Server>...</Server>  
    <Workload>...</Workload>  
    <TuningOptions>...</TuningOptions  
    <Configuration [SpecificationMode="Relative" | "Absolute"]>  
    ...code removed here...  
    </Configuration>  
</DTAInput>  
```  
  
## <a name="element-attributes"></a>要素の属性  
  
|Configuration の属性|説明|  
|-----------------------------|-----------------|  
|`SpecificationMode`|任意。 データベース エンジン チューニング アドバイザーが、指定された構成を既存の構成との関連で分析を行うか、それともまったく新しい独立した構成として分析を行うかを指定します。 この属性を指定するには **string** データ型を使用します。指定できる値は次のいずれかです。<br /><br /> `Relative`[ ] : <br />                  指定された構成を、チューニングしているデータベースにある物理設計構造の現在の既存構成 (インデックス、インデックス付きビュー、パーティション) との関連で評価します。 以下に例を示します。 <br />`<Configuration SpecificationMode="Relative">`<br /><br /> `Absolute`[ ] : <br />                  指定された構成を、独立した構成として評価します。 Absolute が指定されると、データベース エンジン チューニング アドバイザーは既存の構成を考慮しません。 以下に例を示します。<br />`<Configuration SpecificationMode="Absolute">`|  
  
## <a name="element-characteristics"></a>要素の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|**データ型と長さ**|[なし] :|  
|**既定値**|[なし] :|  
|**個数**|任意。 ごとに 1 回使用できます`DTAInput`要素。|  
  
## <a name="element-relationships"></a>要素の関係  
  
|リレーションシップ|要素|  
|------------------|--------------|  
|**親要素**|[DTAInput 要素&#40;DTA&#41;](dtainput-element-dta.md)|  
|**子要素**|[Configuration の server 要素&#40;DTA&#41;](server-element-for-configuration-dta.md)|  
  
## <a name="example"></a>例  
 この要素の使用例については、「[ユーザー指定の構成を指定した XML 入力ファイルのサンプル &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [XML 入力ファイル リファレンス &#40;データベース エンジン チューニング アドバイザー&#41;](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  