---
title: '[新しいエージェント プロファイル] | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.profiles.newperfprofile.f1
helpviewer_keywords:
- New Agent Profile dialog box
ms.assetid: ebf59330-a421-45a5-9020-0484a96852bc
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: f817afb2364728b93718f9dc5831b501f681d9f0
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48070612"
---
# <a name="new-agent-profile"></a>[新しいエージェント プロファイル]
  **[新しいエージェント プロファイル]** ダイアログ ボックスを使用すると、新しいプロファイルを作成できます。 新しいプロファイルは常に既存のプロファイルに基づきますが、アプリケーション要件に一致するように変更することもできます。 プロファイルを作成したら、 **[エージェント プロファイル]** ダイアログ ボックスで、既存のエージェントおよび今後のエージェントのジョブに適用できます。 エージェントのパラメーター値は、[\<**AgentProfileName> のプロパティ]** ダイアログ ボックスで編集できます。  
  
## <a name="options"></a>および  
 **名前**  
 プロファイルの名前を入力します。  
  
 **Description**  
 プロファイルの説明を入力します。  
  
 **パラメーター**  
 プロファイルに含まれるエージェント パラメーターです。 新しいプロファイルが基づくプロファイルは、必ずしもパラメーターごとの値を指定する必要はありません。 指定されたエージェントで有効なパラメーターをすべて表示するには、 **[このプロファイルに使用されているパラメーターのみ表示する]** チェック ボックスをオフにします。 各パラメーターの詳細については、次を参照してください。  
  
-   [Replication Snapshot Agent](agents/replication-snapshot-agent.md)  
  
-   [レプリケーション ログ リーダー エージェント](agents/replication-log-reader-agent.md)  
  
-   [Replication Distribution Agent](agents/replication-distribution-agent.md)  
  
-   [レプリケーション マージ エージェント](agents/replication-merge-agent.md)  
  
-   [レプリケーション キュー リーダー エージェント](agents/replication-queue-reader-agent.md)  
  
 **既定値**  
 各エージェント パラメーターの既定値です。  
  
 **値**  
 新しいプロファイルが基づくプロファイル内のパラメーターに対して指定された値です。 パラメーター値を変更するには、このフィールドを編集します。  
  
 **[このプロファイルに使用されているパラメーターのみ表示する]**  
 指定されたエージェントに有効なパラメーターをすべて表示するにはオフにします。  
  
## <a name="see-also"></a>関連項目  
 [レプリケーション エージェント プロファイルの操作](agents/work-with-replication-agent-profiles.md)   
 [レプリケーション エージェントの概要](agents/replication-agents-overview.md)   
 [レプリケーション エージェント プロファイル](agents/replication-agent-profiles.md)  
  
  
