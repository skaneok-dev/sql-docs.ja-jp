---
title: クラスターの管理ポータルを使用してクラスターの監視 |Microsoft Docs
description: ''
author: yualan
ms.author: alayu
manager: craigg
ms.date: 10/01/2018
ms.topic: conceptual
ms.prod: sql
ms.openlocfilehash: 3ae85c9e9078b91589b828d1bee9d3218b5316cc
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48796406"
---
# <a name="introduction-to-the-cluster-administration-portal"></a>クラスターの管理ポータルの概要
監視や、SQL Server のビッグ データ クラスターをトラブルシューティングする場合は、クラスターの管理ポータルを使用します。 

クラスターの管理ポータルを使用するできます。
- ポッドが実行されていると、問題の数をすばやく表示します。
- 展開ステータスの監視
- 使用可能なサービス エンドポイントの表示
- ビュー コント ローラーと SQL Server のマスター インスタンス
- ポッド、Grafana ダッシュ ボードと Kibana ログへのアクセスなどについてをドリルダウンします。

## <a name="access-the-cluster-administration-portal"></a>クラスターの管理ポータルにアクセスします。
に従って、 [、ビッグ データ クラスターをデプロイするクイック スタート](quickstart-big-data-cluster-deploy.md)に到達するまで、**クラスター管理ポータル**セクション。 Mssqlctl で実行されているビッグ データ クラスターを作成したら、次の手順に従います。

コント ローラーのポッドが実行されている展開の監視、クラスターの管理ポータルを使用できます。 外部 IP アドレスとポート番号を使用してポータルにアクセスすることができます、 `service-proxy-lb` (例: **https://\<ip アドレス\>: 30777**)。 値の管理ポータルにアクセスするための資格情報`CONTROLLER_USERNAME`と`CONTROLLER_PASSWORD`上で指定した環境変数。
> [!NOTE]
> セキュリティの警告を自動生成された SSL 証明書を使用しているため、web ページにアクセスするときになるがあります。 将来のリリースは、独自の署名証明書を提供する機能。

## <a name="overview"></a>概要
![概要](./media/cluster-admin-portal/portal-overview.png)

ポータルを最初に入力したときにで実行されるポッドの数をすばやく表示できます。
- コントローラー
- マスター インスタンス
- プールをコンピューティングします。
- 記憶域プール
- データ プール

問題があるか、既知の問題へのリンクが開くことができます。 左側のナビゲーション ウィンドウを使用すると、問題がある場合は、特定のプールに移動します。

## <a name="deployment"></a>展開
![展開](./media/cluster-admin-portal/portal-deployment.png)

展開を監視するには、左側の [展開] タブをクリックします。 、デプロイのツリー ビューを表示し、展開で問題がある場合。

## <a name="service-endpoints"></a>サービス エンドポイント
![エンドポイント](./media/cluster-admin-portal/portal-endpoints.png)

使用可能なサービス エンドポイントを表示するには、左側のナビゲーション ウィンドウで、[エンドポイント] タブをクリックします。

Spark のエンドポイント、Grafana ダッシュ ボードへのリンクが含まれます、Kibana ログに記録します。

## <a name="controller"></a>コントローラー
![コント ローラー](./media/cluster-admin-portal/portal-controller.png)

コント ローラーは、コント ローラーに関連するすべてのポッドを示しています。 コント ローラーに関する詳細については、[ここです。](concept-controller.md)

それぞれのポッドで追加の詳細についてをクリックすることができます**メトリック**Grafana ダッシュ ボードを表示する列。

ログに問題があるポッドの詳細についてをクリックすることができます、**ログ**列。

## <a name="master-instance"></a>マスター インスタンス
![エンドポイント](./media/cluster-admin-portal/portal-master.png)

マスター インスタンスは、SQL Server のマスター インスタンスに関連するすべてのポッドを示しています。 SQL Server のマスター インスタンスに関する詳細については、[ここです。](concept-master-instance.md)

それぞれのポッドで追加の詳細についてをクリックすることができます**メトリック**Grafana ダッシュ ボードを表示する列。

ログに問題があるポッドの詳細についてをクリックすることができます、**ログ**列。

## <a name="pool-and-pod-pages"></a>プールと Pod ページ
![プール](./media/cluster-admin-portal/portal-data-pool.png)

をクリックして (コンピューティング、ストレージ、およびデータ) は各プール ページ上の各ポッド ページにドリルダウンできます**既定**

![pod 型](./media/cluster-admin-portal/portal-data-default-pool.png)

これには、ドリル ダウン パスの上部にある階層リンクが表示されます。

それぞれのポッドで追加の詳細についてをクリックすることができます**メトリック**Grafana ダッシュ ボードを表示する列。

ログに問題があるポッドの詳細についてをクリックすることができます、**ログ**列。

各プールの詳細を表示します。
- [プールをコンピューティングします。](concept-compute-pool.md)
- [記憶域プール](concept-storage-pool.md)
- [データ プール](concept-data-pool.md)

## <a name="about-page"></a>ページについて
![に関しては](./media/cluster-admin-portal/portal-about.png)

ここで、ドキュメントを別のバージョン番号、コンテナー、およびリンクなど、クラスターに関する情報を表示できます。