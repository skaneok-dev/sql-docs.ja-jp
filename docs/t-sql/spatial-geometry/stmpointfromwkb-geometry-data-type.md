---
title: "STMPointFromWKB (geometry データ型) |Microsoft ドキュメント"
ms.custom: 
ms.date: 08/03/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- STMPointFromWKB (geometry Data Type)
- STMPointFromWKB_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- STMPointFromWKB (geometry Data Type)
ms.assetid: 01d4117f-01a0-4bc3-8762-7382a1cdbd6c
caps.latest.revision: 17
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 026d0a0452cfc362e2e112a307f9790c78633f62
ms.contentlocale: ja-jp
ms.lasthandoff: 09/01/2017

---
# <a name="stmpointfromwkb-geometry-data-type"></a>STMPointFromWKB (geometry データ型)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

返します、 **geometryMultiPoint** Open Geospatial Consortium (OGC) Well-Known Binary (WKB) 表現からのインスタンス。
  
## <a name="syntax"></a>構文  
  
```  
  
STMPointFromWKB ( 'WKB_multipoint' , SRID )  
```  
  
## <a name="arguments"></a>引数  
 *WKB_multipoint*  
 WKB 表現です、 **geometryMultiPoint**インスタンスを取得します。 *WKB_multipoint*は、 **varbinary (max)**式。  
  
 *SRID*  
 **Int** 、空間を表す式の ID (SRID) を参照、 **geometryMultiPoint**インスタンスを取得します。  
  
## <a name="return-types"></a>戻り値の型  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]型を返す:**ジオメトリ**  
  
 CLR の戻り値の型: **SqlGeometry**  
  
 OGC の型: **MultiPoint**  
  
## <a name="remarks"></a>解説  
 このメソッドはスロー、 **FormatException**入力が適切な形式でない場合。  
  
## <a name="examples"></a>使用例  
 次の例で`STMPointFromWKB()`を作成する、`geometry`インスタンス。  
  
```  
DECLARE @g geometry;   
SET @g = geometry::STMPointFromWKB(0x010400000002000000010100000000000000000059400000000000005940010100000000000000000069400000000000006940, 0);  
SELECT @g.STAsText();  
```  
  
## <a name="see-also"></a>参照  
 [OGC の静的なジオメトリ メソッド](../../t-sql/spatial-geometry/ogc-static-geometry-methods.md)  
  
  

