---
title: unwrap メソッド (SQLServerXADataSource) |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: d97c99b3-2224-4abb-8b32-40aff49fe759
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: a9a364c883d0057386b583b5d25eff63bf87679a
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47727330"
---
# <a name="unwrap-method-sqlserverxadatasource"></a>unwrap メソッド (SQLServerXADataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  指定されたインターフェイスを実装するオブジェクトを返します。このメソッドから返されたオブジェクトを使用することで、[!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] 固有のメソッドにアクセスできます。  
  
## <a name="syntax"></a>構文  
  
```  
  
public <T> T unwrap(Class<T> iface)  
```  
  
#### <a name="parameters"></a>パラメーター  
 *iface*  
  
 インターフェイスを定義する **T** 型のクラスです。  
  
## <a name="return-value"></a>戻り値  
 指定されたインターフェイスを実装するオブジェクトです。  
  
## <a name="exceptions"></a>例外  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 [unwrap](../../../connect/jdbc/reference/unwrap-method-sqlserverxadatasource.md) メソッドは、JDBC 4.0 仕様で導入された java.sql.Wrapper インターフェイスで定義されています。  
  
 アプリケーションは [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] に固有の JDBC API 拡張機能にアクセスする必要がある場合があります。 unwrap メソッドは、クラスがベンダー拡張を公開する場合、このオブジェクトが拡張するパブリック クラスへのアンラッピングをサポートします。  
  
 [SQLServerXADataSource](../../../connect/jdbc/reference/sqlserverxadatasource-class.md) クラスは、[SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md) クラスから拡張された [SQLServerConnectionPoolDataSource](../../../connect/jdbc/reference/sqlserverconnectionpooldatasource-class.md) クラスを拡張します。 このメソッドが呼び出されると、オブジェクトは [SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)、[SQLServerConnectionPoolDataSource](../../../connect/jdbc/reference/sqlserverconnectionpooldatasource-class.md)、および [SQLServerXADataSource](../../../connect/jdbc/reference/sqlserverxadatasource-class.md) の各クラスにアンラップされます。  
  
 詳細については、次を参照してください。[ラッパーとインターフェイス](../../../connect/jdbc/wrappers-and-interfaces.md)します。  
  
## <a name="see-also"></a>参照  
 [SQLServerXADataSource のメソッド](../../../connect/jdbc/reference/sqlserverxadatasource-methods.md)   
 [SQLServerXADataSource のメンバー](../../../connect/jdbc/reference/sqlserverxadatasource-members.md)   
 [SQLServerXADataSource クラス](../../../connect/jdbc/reference/sqlserverxadatasource-class.md)  
  
  
