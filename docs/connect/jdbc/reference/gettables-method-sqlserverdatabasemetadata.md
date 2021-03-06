---
title: getTables メソッド (SQLServerDatabaseMetaData) |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDatabaseMetaData.getTables
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: a7514673-3457-4541-9560-28a8284ad9e3
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: caabbe281791120a4f3b162029cb86dd340ffc28
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47730470"
---
# <a name="gettables-method-sqlserverdatabasemetadata"></a>getTables メソッド (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  渡されたカタログ、スキーマ、またはテーブル名のパターンで使用可能なテーブルの記述を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
public java.sql.ResultSet getTables(java.lang.String catalog,  
                                    java.lang.String schema,  
                                    java.lang.String table,  
                                    java.lang.String[] types)  
```  
  
#### <a name="parameters"></a>パラメーター  
 *catalog*  
  
 カタログ名を含む**文字列**です。 このパラメーターに null を指定すると、カタログ名を使用する必要はありません。  
  
 *schema*  
  
 スキーマ名のパターンを含む**文字列**です。 このパラメーターに null を指定すると、スキーマ名を使用する必要はありません。  
  
 *tableName*  
  
 テーブル名のパターンを含む**文字列**です。  
  
 *types*  
  
 含めるテーブルの型を含む文字列の配列です。 null は、すべての型のテーブルを含める必要があることを示します。  
  
## <a name="return-value"></a>戻り値  
 [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) オブジェクトです。  
  
## <a name="exceptions"></a>例外  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 この getTables メソッドは、java.sql.DatabaseMetaData インターフェイスの getTables メソッドで規定されています。  
  
 getTables メソッドによって返される結果セットには、次の情報が含まれます。  
  
|[オブジェクト名]|型|[説明]|  
|----------|----------|-----------------|  
|TABLE_CAT|**String**|指定したテーブルが含まれているデータベースの名前です。|  
|TABLE_SCHEM|**String**|テーブル スキーマ名です。|  
|TABLE_NAME|**String**|テーブル名。|  
|TABLE_TYPE|**String**|テーブルの型です。|  
|REMARKS|**String**|テーブルの説明です。<br /><br /> **注:** [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] では、この列の値は返されません。|  
|TYPE_CAT|**String**|JDBC ドライバーではサポートされていません。|  
|TYPE_SCHEM|**String**|JDBC ドライバーではサポートされていません。|  
|TYPE_NAME|**String**|JDBC ドライバーではサポートされていません。|  
|SELF_REFERENCING_COL_NAME|**String**|JDBC ドライバーではサポートされていません。|  
|REF_GENERATION|**String**|JDBC ドライバーではサポートされていません。|  
  
> [!NOTE]  
>  getTables メソッドによって返されるデータの詳細については、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] オンライン ブックの「sp_tables (Transact-SQL)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、getTables メソッドを使用して、[!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal_md.md)] サンプル データベース内の Person.Contact テーブルのテーブル記述情報を返す方法を示します。  
  
```  
public static void executeGetTables(Connection con) {  
   try {  
      DatabaseMetaData dbmd = con.getMetaData();  
      ResultSet rs = dbmd.getTables("AdventureWorks", "Person", "Contact", null);  
      ResultSetMetaData rsmd = rs.getMetaData();  
  
      // Display the result set data.  
      int cols = rsmd.getColumnCount();  
      while(rs.next()) {  
         for (int i = 1; i <= cols; i++) {  
            System.out.println(rs.getString(i));  
         }  
      }  
      rs.close();  
   }   
  
   catch (Exception e) {  
      e.printStackTrace();  
   }  
}  
```  
  
## <a name="see-also"></a>参照  
 [SQLServerDatabaseMetaData のメソッド](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [SQLServerDatabaseMetaData のメンバー](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [SQLServerDatabaseMetaData クラス](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
