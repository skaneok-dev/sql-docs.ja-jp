---
title: SQL Server 2016 におけるデータベース エンジン機能の重大な変更 | Microsoft Docs
ms.custom: ''
ms.date: 11/27/2016
ms.prod: sql
ms.prod_service: high-availability
ms.reviewer: ''
ms.technology: release-landing
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], what's new
- breaking changes [SQL Server]
ms.assetid: 47edefbd-a09b-4087-937a-453cd5c6e061
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 83725ee74e17a91465356b426b13afc0c265f851
ms.sourcegitcommit: 2429fbcdb751211313bd655a4825ffb33354bda3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "52536383"
---
# <a name="breaking-changes-to-database-engine-features-in-sql-server-2016"></a>SQL Server 2016 におけるデータベース エンジン機能の重大な変更
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  このトピックでは、[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] および以前のバージョンの [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] に関する重要な変更について説明します。 これらの変更によって、以前のバージョンの [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]に基づくアプリケーション、スクリプト、または機能が使用できなくなる場合があります。 この問題は、アップグレードするときに発生することがあります。  
  
##  <a name="SQL15"></a> [!INCLUDE[ssSQL15](../includes/sssql15-md.md)] における重大な変更  
  
-   sys.dm_io_virtual_file_stats の sample_ms 列が **int** データ型から **bigint** データ型に拡張されました。  
  
-   sys.fn_virtualfilestats の TimeStamp 列が **int** データ型から **bigint** データ型に拡張されました。  

-   MD2、MD4、MD5、SHA、または SHA1 ハッシュ アルゴリズム (非推奨) を使用するには、データベース互換性レベルを 130 より前に設定する必要があります。  

-   データベース互換性レベル 130 の下で、 **datetime** から **datetime2** にデータ型を暗黙的に変換するとき、精度が上がります。小数ミリ秒が計算に入り、結果的にさまざまな変換値が生成されます。 datetime データ型と datetime2 データ型の間で混合比較シナリオが存在する場合、datetime2 データ型への明示的型変換を使用します。 詳細については、この [Microsoft サポート技術情報](https://support.microsoft.com/help/4010261)を参照してください。

## <a name="previous-versions"></a> 以前のバージョン  

SQL Server バージョン 2014 およびそれより前の一部のバージョンでの破壊的変更については、「[SQL Server 2014 におけるデータベース エンジン機能の重大な変更](https://docs.microsoft.com/sql/database-engine/breaking-changes-to-database-engine-features-in-sql-server-2016?view=sql-server-2014#SQL14)」をご覧ください。

#### <a name="archived-documentation-for-very-old-versions-of-sql-server"></a>SQL Server の非常に古いバージョンのアーカイブされたドキュメント

[!INCLUDE[Archived documentation for very old versions of SQL Server](../includes/paragraph-content/previous-versions-archive-documentation-sql-server.md)]

## <a name="see-also"></a>参照  
 [SQL Server 2016 データベース エンジンの非推奨の機能](../database-engine/deprecated-database-engine-features-in-sql-server-2016.md)   
 [SQL Server 2016 で廃止されたデータベース エンジンの機能](../database-engine/discontinued-database-engine-functionality-in-sql-server-2016.md)   
 [SQL Server データベース エンジンの旧バージョンとの互換性](../database-engine/sql-server-database-engine-backward-compatibility.md)   
 [ALTER DATABASE 互換性レベル &#40;Transact-SQL&#41;](../t-sql/statements/alter-database-transact-sql-compatibility-level.md)   
 [いくつかのデータ型と一般的でない操作を処理するときの SQL Server と Azure の SQL データベースの機能強化](https://support.microsoft.com/help/4010261)
  
  
