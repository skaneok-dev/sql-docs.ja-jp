---
title: 明示的なキャップを持つ派生階層 (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Master Data Services], derived hierarchies with explicit caps
- explicit hierarchies, derived hierarchies with explicit caps
- derived hierarchies, derived hierarchies with explicit caps
ms.assetid: 6a82ff66-c137-4757-99bb-787d189b4295
caps.latest.revision: 6
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: dde0270cd369c5074f966978370fd95db14df726
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37203572"
---
# <a name="derived-hierarchies-with-explicit-caps-master-data-services"></a>明示的なキャップを持つ派生階層 (Master Data Services)
  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]の、派生階層の最上位レベルとして使用される明示的階層のレベルは、明示的なキャップを持つ派生階層と呼ばれます。  
  
 明示的階層は、派生階層の最上位のエンティティと同じエンティティに基づく必要があります。  
  
 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] のユーザー インターフェイス (UI) で明示的階層を派生階層の最上位にドラッグして、この種類の階層を作成します。  
  
 ![mds_conc_explicit_cap_UI_structure](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-structure.gif "mds_conc_explicit_cap_UI_structure")  
  
## <a name="derived-hierarchy-with-explicit-cap-example"></a>明示的なキャップを持つ派生階層の例  
 この例では、明示的階層のメンバーは Subcategory エンティティのメンバーです。 派生階層の最上位レベルのメンバーも Subcategory エンティティのメンバーです。  
  
 ![mds_conc_explicit_cap_UI_example](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-example.gif "mds_conc_explicit_cap_UI_example")  
  
 明示的階層を派生階層の最上位で使用することにより、派生階層は不規則になります。  
  
## <a name="rules"></a>ルール  
  
-   明示的キャップを持つ 1 つの派生階層に設定できる明示的階層は 1 つだけです。  
  
-   同じ明示的階層を複数の派生階層のキャップとして使用できます。  
  
-   明示的なキャップを持つ派生階層に階層メンバーの権限を割り当てることはできません。 権限を明示的階層または派生階層に個々に割り当てた場合、権限は両方の階層に影響します。  
  
## <a name="related-tasks"></a>Related Tasks  
  
|タスクの説明|トピック|  
|----------------------|-----------|  
|派生階層を作成する。|[派生階層を作成&#40;マスター データ サービス&#41;](create-a-derived-hierarchy-master-data-services.md)|  
|明示的階層を作成する。|[明示的階層を作成&#40;マスター データ サービス&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)|  
|既存の派生階層を削除する。|[派生階層を削除&#40;マスター データ サービス&#41;](../../2014/master-data-services/delete-a-derived-hierarchy-master-data-services.md)|  
|||  
  
## <a name="related-content"></a>関連コンテンツ  
  
-   [派生階層&#40;マスター データ サービス&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md)  
  
-   [明示的階層&#40;マスター データ サービス&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)  
  
  