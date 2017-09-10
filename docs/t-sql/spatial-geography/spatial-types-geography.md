---
title: "geography (TRANSACT-SQL) |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- geography
dev_langs:
- TSQL
helpviewer_keywords:
- geography data type [SQL Server], Transact-SQL
- spatial data types [SQL Server]
ms.assetid: d9e4952a-1841-4465-a64b-11e9288dba1d
caps.latest.revision: 18
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 3525cc718e5e0efddd6cef2e3f2cff57247058c2
ms.contentlocale: ja-jp
ms.lasthandoff: 09/01/2017

---
# <a name="spatial-types---geography"></a>空間型、geography
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  地理空間データ型の**geography**は、.NET 共通言語ランタイム (CLR) データ型として実装[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]です。 この型は、球体地球座標系のデータを表します。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **geography** データ型は、GPS の緯度経度座標などの楕円体 (球体地球) データを格納します。  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]メソッドのセットをサポートしている、 **geography**空間データ型。 これは、上のメソッドが含まれます**geography** 、Open Geospatial Consortium (OGC) 標準とのセットで定義されている[!INCLUDE[msCoName](../../includes/msconame-md.md)]その標準の拡張機能です。  
 
 エラーの許容範囲、 **geography**メソッドは 1.0 e サイズであることができます-7 * エクステントです。 エクステントは、点の間のおおよその最大距離を参照してください、 **geography**オブジェクト。
  

## <a name="registering-the-geography-type"></a>geography 型の登録  
 **geography** 型は、各データベースで使用できるように事前に定義されています。 **geography** 型のテーブル列を作成し、システムが提供する他のデータ型を使用するときと同じように **geography** データを操作できます。 保存される計算列と保存されない計算列で使用できます。  
  
## <a name="examples"></a>使用例  
  
### <a name="a-showing-how-to-add-and-query-geography-data"></a>A. geography 型のデータの追加方法とクエリ方法を示す  
 次の例は、geography 型のデータの追加方法とクエリ方法を示しています。 最初の例では、id 列を持つテーブルを作成し、`geography`列、`GeogCol1`です。 3 番目の列で、 `geography` 型の列をその Open Geospatial Consortium (OGC) の Well-Known Text (WKT) 表現で示し、 `STAsText()` メソッドを使用します。 次に 2 つの行が挿入されます。1 つは、 `LineString` の `geography`インスタンスを含む行で、もう 1 つは `Polygon` インスタンスを含む行です。  
  
```  
IF OBJECT_ID ( 'dbo.SpatialTable', 'U' ) IS NOT NULL   
    DROP TABLE dbo.SpatialTable;  
GO  
  
CREATE TABLE SpatialTable   
    ( id int IDENTITY (1,1),  
    GeogCol1 geography,   
    GeogCol2 AS GeogCol1.STAsText() );  
GO  
  
INSERT INTO SpatialTable (GeogCol1)  
VALUES (geography::STGeomFromText('LINESTRING(-122.360 47.656, -122.343 47.656 )', 4326));  
  
INSERT INTO SpatialTable (GeogCol1)  
VALUES (geography::STGeomFromText('POLYGON((-122.358 47.653 , -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))', 4326));  
GO  
```  
  
### <a name="b-returning-the-intersection-of-two-geography-instances"></a>B. 2 つの geography インスタンスが交差する点を返す  
 次の例では、`STIntersection()` メソッドを使用して、前の例で挿入した 2 つの `geography` インスタンスが交差する点を返します。  
  
```  
DECLARE @geog1 geography;  
DECLARE @geog2 geography;  
DECLARE @result geography;  
  
SELECT @geog1 = GeogCol1 FROM SpatialTable WHERE id = 1;  
SELECT @geog2 = GeogCol1 FROM SpatialTable WHERE id = 2;  
SELECT @result = @geog1.STIntersection(@geog2);  
SELECT @result.STAsText();  
```  
  
### <a name="c-using-geography-in-a-computed-column"></a>C. 計算列で geography 型を使用する  
 次の例では、テーブルを作成、保存される計算列を使用すると、 **geography**型です。  
  
```  
IF OBJECT_ID ( 'dbo.SpatialTable', 'U' ) IS NOT NULL   
    DROP TABLE dbo.SpatialTable;  
GO  
  
CREATE TABLE SpatialTable  
(  
    locationId int IDENTITY(1,1),  
    location geography,  
    deliveryArea as location.STBuffer(10) persisted  
)  
```  
  
## <a name="see-also"></a>参照  
 [空間データ &#40;SQL Server&#41;](../../relational-databases/spatial/spatial-data-sql-server.md)   

  
  