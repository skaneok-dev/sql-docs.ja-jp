---
title: KeepExisting 要素 (DTA) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- KeepExisting element
ms.assetid: e67aae61-d06d-4a03-85ba-6516c3502dce
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 8691e57b9750447b1740c79337b75500febd9549
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48070742"
---
# <a name="keepexisting-element-dta"></a>KeepExisting 要素 (DTA)
  データベース エンジン チューニング アドバイザーが、推奨設定を生成するときに保持しなければならない物理設計構造 (インデックス、インデックス付きビュー、パーティション分割) を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <KeepExisting>...</KeepExisting>  
```  
  
## <a name="element-characteristics"></a>要素の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|**データ型と長さ**|`string`。長さの制限は、サーバーによって決まります。|  
|**指定できる値**|**NONE**<br /> 既存の構造を保持しません。<br /><br /> **ALL**<br /> 既存の構造をすべて保持します。<br /><br /> **ALIGNED**<br /> パーティションで固定された構造をすべて保持します。<br /><br /> **CL_IDX**<br /> テーブルのクラスター化インデックスをすべて保持します。<br /><br /> **IDX**<br /> テーブルのクラスター化インデックスと非クラスター化インデックスをすべて保持します。<br /><br /> この要素では、上記の値のいずれか 1 つを使用してください。|  
|**既定値**|[なし] :|  
|**個数**|任意。 それぞれに 1 回だけ使用できます`TuningOptions`要素。|  
  
## <a name="element-relationships"></a>要素の関係  
  
|リレーションシップ|要素|  
|------------------|--------------|  
|**親要素**|[TuningOptions 要素&#40;DTA&#41;](tuningoptions-element-dta.md)|  
|**子要素**|[なし] :|  
  
## <a name="example"></a>例  
 この要素の使用例については、「[XML 入力ファイルの簡単なサンプル &#40;DTA&#41;](simple-xml-input-file-sample-dta.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [XML 入力ファイル リファレンス &#40;データベース エンジン チューニング アドバイザー&#41;](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
