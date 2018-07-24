---
title: クライアント側とサーバー側の XML 書式設定 (SQLXML 4.0) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- NESTED mode
- FOR XML clause, formatting
- client-side XML formatting
- server-side XPath
- server-side XML formatting
- AUTO mode
- client-side XPath
ms.assetid: f807ab7a-c5f8-4e61-9b00-23aebfabc47e
caps.latest.revision: 31
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 02875dd402a294e8598e62a5bee5e65f5b344f6d
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37286848"
---
# <a name="client-side-vs-server-side-xml-formatting-sqlxml-40"></a>クライアント側とサーバー側の XML 書式設定 (SQLXML 4.0)
  ここでは、SQLXML における、クライアント側とサーバー側の XML 書式設定の一般的な違いについて説明します。  
  
## <a name="multiple-rowset-queries-not-supported-in-client-side-formatting"></a>クライアント側の書式設定では複数の行セット クエリがサポートされない  
 複数の行セットを生成するクエリは、クライアント側の XML 書式設定を使用するときにはサポートされません。 たとえば、クライアント側の書式設定が指定されている仮想ディレクトリがあるとし、 2 つの SELECT ステートメントが次のサンプル テンプレートで、  **\<sql:query >** ブロック。  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>  
     SELECT FirstName FROM Person.Contact FOR XML Nested;   
     SELECT LastName FROM Person.Contact FOR XML Nested    
  </sql:query>  
</ROOT>  
```  
  
 このテンプレートはアプリケーション コードで実行できます。実行すると、クライアント側の XML 書式設定では複数の行セットの書式設定がサポートされていないため、エラーが返されます。 2 つのクエリを指定する場合は、分離 **\<sql:query >** ブロック、目的の結果が得られます。  
  
## <a name="timestamp-maps-differently-in-client--vs-server-side-formatting"></a>クライアント側とサーバー側の XML 書式設定では timestamp 型のマッピングが異なる  
 サーバー側の XML 書式設定では、XMLDATA オプションがクエリで指定される場合、`timestamp` 型のデータベース列が i8 XDR 型にマップされます。  
  
 クライアント側の XML 書式設定では、バイナリの base64 オプションがクエリで指定されているかどうかに従って、`timestamp` 型のデータベース列が `uri` または `bin.base64` XDR 型にマップされます。 `bin.base64` XDR 型は、この型に変換されますので、アップデート グラムや一括読み込み機能を使用する場合に便利です、 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `timestamp`型。 この方法で、挿入、更新、または削除操作が成功します。  
  
## <a name="deep-variants-are-used-in-server-side-formatting"></a>サーバー側の書式設定ではサブタイプの VARIANT 型も使用される  
 サーバー側の XML 書式設定では、サブタイプの VARIANT 型も使用されます。 クライアント側の XML 書式設定を使用する場合、variant は Unicode 文字列に変換され、サブタイプの VARIANT は使用されません。  
  
## <a name="nested-mode-vs-auto-mode"></a>NESTED モードと AUTO モード  
 クライアント側の FOR XML の NESTED モードは、サーバー側の FOR XML の AUTO モードに似ていますが、次の点が異なります。  
  
### <a name="when-you-query-views-using-auto-mode-on-the-server-side-the-view-name-is-returned-as-the-element-name-in-the-resulting-xml"></a>サーバー側で AUTO モードを使用してビューにクエリを実行すると、ビュー名が結果の XML 内の要素名として返されます。  
 たとえば、AdventureWorksdatabase 内の Person.Contact テーブルに次のビューが作成されたことを想定します。  
  
```  
CREATE VIEW ContactView AS (SELECT ContactID as CID,  
                               FirstName  as FName,  
                               LastName  as LName  
                        FROM Person.Contact)  
```  
  
 次のテンプレートでは、ContactView ビューに対するクエリと、サーバー側の XML 書式設定が指定されています。  
  
```  
 <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="0">  
    SELECT *  
    FROM   ContactView  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 テンプレートを実行すると、次の XML が返されます。 ここでは一部の結果のみが表示されています。クエリの実行対象のビューの名前が要素名になっていることに注意してください。  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <ContactView CID="1" FName="Gustavo" LName="Achong" />   
  <ContactView CID="2" FName="Catherine" LName="Abel" />   
...  
</ROOT>  
```  
  
 クライアント側の書式設定を、対応する NESTED モードで指定すると、ベース テーブル名が結果の XML 内の要素名として返されます。 たとえば、次の更新後のテンプレートは、同じ SELECT ステートメントを実行しますが、XML の書式設定がクライアント側で実行 (つまり、**クライアント側の xml**に設定されているテンプレートの場合は true)。  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="1">  
    SELECT *  
    FROM   ContactView  
    FOR XML NESTED  
  </sql:query>  
</ROOT>  
```  
  
 このテンプレートを実行するには、次の XML が生成されます。 この場合、ベース テーブル名が要素名になっていることに注意してください。  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact CID="1" FName="Gustavo" LName="Achong" />   
  <Person.Contact CID="2" FName="Catherine" LName="Abel" />   
...  
</ROOT>  
```  
  
### <a name="when-you-use-auto-mode-of-the-server-side-for-xml-the-table-aliases-specified-in-the-query-are-returned-as-element-names-in-the-resulting-xml"></a>サーバー側の FOR XML を AUTO モードで使用すると、クエリで指定されたテーブルの別名が、結果の XML 内の要素名として返されます。  
 たとえば、次のテンプレートを考えてみます。  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="0">  
    SELECT FirstName as fname,  
           LastName as lname  
    FROM   Person.Contact C  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 このテンプレートを実行すると、次の XML が生成されます。  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <C fname="Gustavo" lname="Achong" />   
  <C fname="Catherine" lname="Abel" />   
...  
</ROOT>   
```  
  
 クライアント側の FOR XML を NESTED モードで使用すると、テーブル名が、結果の XML 内の要素名として返されます。 クエリで指定されたテーブルの別名は使用されません。たとえば、次のテンプレートを考えてみます。  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="1">  
    SELECT FirstName as fname,  
           LastName as lname  
    FROM   Person.Contact C  
    FOR XML NESTED  
  </sql:query>  
</ROOT>  
```  
  
 このテンプレートを実行すると、次の XML が生成されます。  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact fname="Gustavo" lname="Achong" />   
  <Person.Contact fname="Catherine" lname="Abel" />   
...  
</ROOT>  
```  
  
### <a name="if-you-have-a-query-that-returns-columns-as-dbobject-queries-you-cannot-use-aliases-for-these-columns"></a>列を dbobject クエリとして返すクエリでは、これらの列に対して別名は使用できません。  
 たとえば、次のテンプレートを考えてみます。このテンプレートには、製品写真 ID と写真を返すクエリが含まれています。  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<sql:query client-side-xml="1">  
   SELECT ProductPhotoID, LargePhoto as P  
   FROM   Production.ProductPhoto  
   WHERE  ProductPhotoID=5  
   FOR XML NESTED, elements  
</sql:query>  
</ROOT>  
```  
  
 このテンプレートを実行すると、Photo 列が dbobject クエリとして返されます。 この dbobject クエリでは、`@P` で存在しない列名が参照されています。  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Production.ProductPhoto>  
    <ProductPhotoID>5</ProductPhotoID>  
    <LargePhoto>dbobject/Production.ProductPhoto[@ProductPhotoID='5']/@P</LargePhoto>  
  </Production.ProductPhoto>  
</ROOT>  
```  
  
 XML の書式設定は、サーバーで実行している場合 (**クライアント側の xml =「0」**)、dbobject クエリ (別名を指定した) 場合の実際のテーブルと列名が返されますが返す列の別名を使用することができます。 たとえば、次のテンプレートが、クエリを実行し、XML の書式設定は、サーバーで実行 (、**クライアント側の xml**オプションが指定されていないと、 **Run On Client**のオプションが選択されていない、仮想ルート)。 このクエリでは、クライアント側の NESTED モードではなく AUTO モードも指定されています。  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<sql:query   
   SELECT ProductPhotoID, LargePhoto as P  
   FROM   Production.ProductPhoto  
   WHERE  ProductPhotoID=5  
   FOR XML AUTO, elements  
</sql:query>  
</ROOT>  
```  
  
 このテンプレートを実行すると、次の XML ドキュメントが返されます。LargePhoto 列に対する dbobject クエリでは、別名が使用されていないことに注意してください。  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Production.ProductPhoto>  
    <ProductPhotoID>5</ProductPhotoID>  
    <LargePhoto>dbobject/Production.ProductPhoto[@ProductPhotoID='5']/@LargePhoto</LargePhoto>  
  </Production.ProductPhoto>  
</ROOT>  
```  
  
### <a name="client-side-vs-server-side-xpath"></a>クライアント側とサーバー側の XPath  
 クライアント側の XPath とサーバー側の XPath は類似していますが、次の点が異なります。  
  
-   クライアント側の XPath クエリを使用するときに適用されるデータ変換は、サーバー側の XPath クエリを使用するときに適用されるものとは異なります。 クライアント側の XPath では、CONVERT モード 126 の代わりに CAST が使用されます。  
  
-   指定すると**クライアント側の xml =「0」** (false)、テンプレートで、要求しているサーバー側の XML 書式設定します。 したがって、サーバーでは NESTED オプションが認識されないので、FOR XML NESTED は指定できません。 これにより、エラーが発生します。 この場合、サーバーで認識される AUTO、RAW、または EXPLICIT モードを使用する必要があります。  
  
-   指定すると**クライアント側の xml =「1」** (true)、テンプレートで、要求しているクライアント側の XML 書式設定します。 この場合、FOR XML NESTED を指定できます。 ですが、サーバー側で発生 XML 書式設定を FOR XML AUTO を指定する場合**クライアント側の xml =「1」** はテンプレートで指定します。  
  
## <a name="see-also"></a>参照  
 [XML のセキュリティに関する考慮事項の&#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md)   
 [クライアント側の XML 書式設定&#40;SQLXML 4.0&#41;](client-side-xml-formatting-sqlxml-4-0.md)   
 [サーバー側の XML 書式設定&#40;SQLXML 4.0&#41;](server-side-xml-formatting-sqlxml-4-0.md)  
  
  