---
title: キャッシュ、更新、およびレプリケーション モニターのパフォーマンス | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], Replication Monitor
- cache [SQL Server], replication
- Replication Monitor, caching
- refreshing data
- Replication Monitor, refreshing
ms.assetid: a2d8b666-ed41-4f86-b2b8-c8e118416ab7
caps.latest.revision: 11
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: f0816ea29b873777c54d77e34d691c909c8e6208
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37256134"
---
# <a name="caching-refresh-and-replication-monitor-performance"></a>キャッシュ、更新、およびレプリケーション モニターのパフォーマンス
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] レプリケーション モニターは、運用システム内の多数のコンピューターを効率的に監視することを目的に設計されています。 計算の実行、およびデータの収集のためにレプリケーション モニターによって使用されるクエリは、定期的にキャッシュおよび更新されます。 キャッシュによってレプリケーション モニターでさまざまなページを表示する際に必要なクエリと計算の数が削減され、監視のスケーラビリティが向上し、複数のユーザーに対応できるようになります。  
  
 キャッシュの更新は、 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] エージェント ジョブである **ディストリビューションのレプリケーション モニターの状態更新機能**によって処理されます。 このジョブは継続的に実行されますが、キャッシュの更新スケジュールは、前回の更新後の待機時間に基づいて設定されます。  
  
-   前回のキャッシュの作成時以降にエージェント履歴が変更された場合、待機時間は、最短の 4 秒、または前回のキャッシュが作成されたときにかかった時間になります。  
  
-   前回のキャッシュ作成時以降に (他の種類の変更があったとしても) エージェント履歴が変更されなかった場合、待機時間は、最長の 30 秒、または前回のキャッシュが作成されたときにかかった時間になります。  
  
## <a name="refreshing-the-replication-monitor-user-interface"></a>レプリケーション モニターのユーザー インターフェイスの更新  
 レプリケーション モニターのユーザー インターフェイスは、以下の方法で更新できます。  
  
-   レプリケーション モニターのメイン ウィンドウ (すべてのタブが含まれます) は、既定では、5 秒間隔で自動的に更新されます。 自動更新によって、キャッシュの更新が強制的に行われることはありません。ユーザー インターフェイスには、キャッシュからの最新のバージョンのデータが表示されます。 パブリッシャーの設定を編集することによって、パブリッシャーに関連付けられているすべてのウィンドウに使用される更新頻度をカスタマイズできます。 また、パブリッシャーの自動更新を無効にすることもできます。  
  
-   レプリケーション モニターから起動される詳細ウィンドウは、既定では自動的に更新されません (ただし、同期されているマージ サブスクリプションに関連付けられているウィンドウは、例外です)。 詳細ウィンドウが自動的に更新されるように指定すると、レプリケーション モニターのメイン ウィンドウと同じスケジュールで更新されます。  
  
-   すべてのウィンドウは、F5 キーを押すか、またはレプリケーション モニターのツリー内でノードを右クリックし、 **[更新]** をクリックすることによって、手動で更新できます。 手動の更新を行うと、キャッシュは強制的に更新されます。  
  
 詳細については、「[レプリケーション モニターのデータの更新](refresh-data-in-replication-monitor.md)」を参照してください。  
  
## <a name="performance-considerations"></a>パフォーマンスに関する考慮事項  
 レプリケーション モニターは効率的に実行することを目的に設計されていますが、以下の点に注意してください。  
  
-   多数のパブリケーションとサブスクリプションがある場合は、ユーザー インターフェイスの自動更新スケジュールの頻度を少なくすることを検討してください。  
  
-   レプリケーション モニターの複数のインスタンスを同時に実行しないでください。  
  
-   多数のディストリビューターを登録しないようにしてください。また、レプリケーション モニターがそれらのすべてに自動的に接続するような設定にしないでください。  
  
## <a name="see-also"></a>参照  
 [レプリケーション メンテナンス ジョブの実行 &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md)   
 [レプリケーションの監視](../monitoring-replication.md)  
  
  