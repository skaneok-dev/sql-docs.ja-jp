---
title: SQL Server Compact Edition 接続マネージャー | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Compact, connection manager
- connections [Integration Services], SQL Server Compact
- connection managers [Integration Services], SQL Server Compact
ms.assetid: ba627d4d-41f4-49fc-a921-f534cde67770
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 4fd067d6f01c168861a42895c36024cb4c0a9aa5
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48082792"
---
# <a name="sql-server-compact-edition-connection-manager"></a>SQL Server Compact Edition 接続マネージャー
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact 接続マネージャーを使用すると、パッケージは [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact データベースに接続できます。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]  [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Compact 変換先は、この接続マネージャーを使用して、データを [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact データベースに接続できます。  
  
> [!NOTE]  
>  64 ビット コンピューターでは、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact データ ソースに接続するパッケージを 32 ビット モードで実行する必要があります。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] が [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Compact データ ソースへの接続に使用する [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact Provider は、32 ビット版でのみ使用できます。  
  
## <a name="configuration-the-sql-server-compact-edition-connection-manager"></a>SQL Server Compact Edition 接続マネージャーの構成  
 追加すると、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact 接続マネージャーをパッケージに[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]接続を解決するマネージャーを作成、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact 接続、実行時に、接続マネージャーのプロパティを設定し、接続マネージャーを追加します、`Connections`パッケージのコレクション。  
  
 `ConnectionManagerType`接続マネージャーのプロパティに設定されて`SQLMOBILE`します。  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact 接続マネージャーは、次の方法で構成できます。  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact データベースの場所を指定する接続文字列を指定します。  
  
-   パスワードで保護されているデータベースのパスワードを指定します。  
  
-   データベースが格納されるサーバーを指定します。  
  
-   接続マネージャーから作成される接続を、実行時に保持するかどうかを指定します。  
  
 プロパティを設定するには [!INCLUDE[ssIS](../../includes/ssis-md.md)] デザイナーから行うか、またはプログラムによって設定します。  
  
 [!INCLUDE[ssIS](../../includes/ssis-md.md)] デザイナーで設定できるプロパティの詳細については、次のトピックのいずれかを参照してください。  
  
-   [SQL Server Compact Edition 接続マネージャー エディター&#40;接続 ページ&#41;](../sql-server-compact-edition-connection-manager-editor-connection-page.md)  
  
-   [SQL Server Compact Edition 接続マネージャー エディター&#40;すべて ページ&#41;](../sql-server-compact-edition-connection-manager-editor-all-page.md)  
  
 プログラムによる接続マネージャーの構成方法の詳細については、次を参照してください。<xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>と[プログラムによる接続の追加](../building-packages-programmatically/adding-connections-programmatically.md)します。  
  
  
