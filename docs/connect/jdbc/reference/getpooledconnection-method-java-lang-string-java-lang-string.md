---
title: getPooledConnection メソッド (java.lang.String, java.lang.String) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerConnectionPoolDataSource.getPooledConnection (java.lang.String, java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: f2e6391d-9aaf-4b09-ae1c-a27c1ada6301
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 5d6c21fa5df3545b641ccb935c53f6d7a689f580
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47702950"
---
# <a name="getpooledconnection-method-javalangstring-javalangstring"></a>getPooledConnection (java.lang.String, java.lang.String) メソッド
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  渡されたユーザー名とパスワードに基づいて、プールされた接続として使用できる物理データベース接続の確立を試みます。  
  
## <a name="syntax"></a>構文  
  
```  
  
public javax.sql.PooledConnection getPooledConnection(java.lang.String user,  
                                                      java.lang.String password)  
```  
  
#### <a name="parameters"></a>パラメーター  
 *user*  
  
 ユーザー名を含む**文字列**です。  
  
 *passwword*  
  
 パスワードを含む**文字列**です。  
  
## <a name="return-value"></a>戻り値  
 [SQLServerPooledConnection](../../../connect/jdbc/reference/sqlserverpooledconnection-class.md) オブジェクトです。  
  
## <a name="exceptions"></a>例外  
 java.sql.SQLException  
  
## <a name="remarks"></a>Remarks  
 この getPooledConnection メソッドは、javax.sql.ConnectionPoolDataSource インターフェイスで getPooledConnection メソッドによって指定されます。  
  
## <a name="see-also"></a>参照  
 [getPooledConnection](../../../connect/jdbc/reference/getpooledconnection-method-sqlserverconnectionpooldatasource.md)   
 [SQLServerConnectionPoolDataSource のメソッド](../../../connect/jdbc/reference/sqlserverconnectionpooldatasource-methods.md)   
 [SQLServerConnectionPoolDataSource のメンバー](../../../connect/jdbc/reference/sqlserverconnectionpooldatasource-members.md)   
 [SQLServerConnectionPoolDataSource クラス](../../../connect/jdbc/reference/sqlserverconnectionpooldatasource-class.md)  
  
  
