---
title: 構成、PowerPivot 自動データ更新アカウント (PowerPivot for SharePoint) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 81401eac-c619-4fad-ad3e-599e7a6f8493
caps.latest.revision: 10
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: beb9bc2a3dfcd20a12ad387b8192ff1694d77f8d
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37297532"
---
# <a name="configure-the-powerpivot-unattended-data-refresh-account-powerpivot-for-sharepoint"></a>PowerPivot 自動データ更新アカウントの構成 (PowerPivot for SharePoint)
  PowerPivot 自動データ更新アカウントは、SharePoint ファームで PowerPivot データ更新ジョブを実行するために指定されたアカウントです。 これを構成して有効にすると、**データ更新アカウントの管理者によって構成を使用**オプション、データ更新スケジュール ページ (下記参照)。 データ更新をスケジュールするブックの作成者は、データ更新ジョブの実行に PowerPivot 自動データ更新アカウントを使用したい場合に、このオプションを選択できます。 データ更新スケジュールで、資格情報オプションを表示する方法の詳細については、次を参照してください。[データ更新のスケジュール&#40;PowerPivot for SharePoint&#41;](schedule-a-data-refresh-powerpivot-for-sharepoint.md)します。  
  
 ![SSAS_PowerpivotKJ_DataRefreshCreds](media/ssas-powerpivotkj-datarefreshcreds.gif "SSAS_PowerpivotKJ_DataRefreshCreds")  
  
 **[!INCLUDE[applies](../includes/applies-md.md)]**  SharePoint 2010  
  
 サーバーを構成するときに選択したオプションによっては、自動データ更新アカウントが既に作成されている場合もあります。 既定の構成では、最初に自動データ更新アカウントの ID がファーム アカウントに設定されます。 別のユーザーとして実行するようにアカウントを変更すると、配置のセキュリティを強化できます。 アカウントを変更する次の手順に従って:[既存の PowerPivot で使用される資格情報を更新する自動データ更新アカウント](#bkmk_editUA)します。  
  
 その他のすべてのインストール シナリオでは、次の手順に従ってアカウントを手動で構成する必要があります。  
  
 このトピックには、次のセクションが含まれます。  
  
 [前提条件](#bkmk_prereq)  
  
 [手順 1: ターゲット アプリケーションを作成し、資格情報の設定](#bkmk_create)  
  
 [手順 2: PowerPivot サーバー構成ページで自動アカウントを指定します。](#bkmk_specifyUA)  
  
 [手順 3: 許可がアカウントへのアクセス許可を投稿します。](#bkmk_grant)  
  
 [手順 4: 読み取りデータの更新で使用される外部データ ソースにアクセスする権限の付与](#bkmk_dbread)  
  
 [手順 5: 確認のアカウントを使用できるデータ更新構成ページ](#bkmk_verify)  
  
 [PowerPivot 自動データ更新を使用するアカウント](#bkmk_use)  
  
 [既存の PowerPivot で使用される資格情報を更新する自動データ更新アカウント](#bkmk_editUA)  
  
##  <a name="bkmk_prereq"></a> 前提条件  
 Secure Store Service を有効にして構成し、マスター キーを生成する必要があります。 これを行う方法の詳細については、次を参照してください[SharePoint 2010 で PowerPivot データ更新。](powerpivot-data-refresh-with-sharepoint-2010.md)  
  
 PowerPivot 自動データ更新アカウントとして使用する Windows ドメイン ユーザー アカウントを事前に決めておく必要があります。 ここでは、使用方法を確認できるように、PowerPivot 自動データ更新アカウント専用に作成されたアカウントを使用する必要があります。  
  
 PowerPivot System サービスのアプリケーション ID を把握しておく必要があります。 このサービス アカウントに付ける**フルコントロール**手順 1. でそのターゲット アプリケーションを作成するときに、自動データへのアクセス権がアカウントを更新します。 これらの権限により、PowerPivot System サービスは、データ更新中に自動データ更新アカウントの資格情報を取得できます。 必要なサービス アカウント情報を取得するには、開く、**サービス アカウントの構成**サーバーの全体管理ページし、PowerPivot サービス アプリケーションによって使用されるサービス アプリケーション プールを選択します。 既定では、これは、**サービス アプリケーション プール-SharePoint Web サービスのシステム**します。  
  
## <a name="configure-the-unattended-powerpivot-data-refresh-account"></a>自動 PowerPivot データ更新アカウントの構成  
 PowerPivot サービス アプリケーションごとに構成できる PowerPivot 自動データ更新アカウントは 1 つだけです。 アカウント情報はターゲット アプリケーションの Secure Store Service に保存され、定義済みの Windows ドメイン ユーザー アカウントに設定されます。 ターゲット アプリケーションが作成されたら、PowerPivot サービス アプリケーションの構成ページで、そのアプリケーションを PowerPivot データ更新アカウントとして指定できます。  
  
> [!NOTE]  
>  データ更新を自動データ更新アカウントで実行すると、自動データ更新に使用した Windows ユーザー アカウントに対して、使用状況レポートとデータ更新履歴が記録されます。 データ更新を要求しているユーザーやスケジュールを所有しているユーザーについて、より正確な記録が必要になる場合は、データ更新を実行する場合に他のいずれかのオプションを検討してください。 つまり、ユーザーに各自の資格情報を指定させるか (既定)、データ更新用にすべての Windows 資格情報を保存するための追加のターゲット アプリケーションを作成します。 詳細については、次を参照してください。[格納されている資格情報の構成の PowerPivot データ更新&#40;PowerPivot for SharePoint&#41;](configure-stored-credentials-data-refresh-powerpivot-sharepoint.md)します。  
  
 自動データ更新アカウントの作成には、次の 5 つの段階があります。  
  
-   Secure Store Service でアカウントのターゲット アプリケーションを作成し、資格情報を指定する。  
  
-   PowerPivot サーバー構成ページで自動データ更新アカウント用のターゲット アプリケーション ID を指定する。  
  
-   アカウントに投稿権限を付与する。  
  
-   データ更新中に外部データ ソースにアクセスするための読み取り権限をアカウントに付与する。  
  
-   [データ更新の管理] スケジュール ページで、パブリッシュされた PowerPivot ブックのアカウントが使用できることを確認する。  
  
###  <a name="bkmk_create"></a> 手順 1: ターゲット アプリケーションを作成し、資格情報の設定  
  
1.  サーバーの全体管理で、[アプリケーション構成の管理] の **[サービス アプリケーションの管理]** をクリックします。  
  
2.  クリックして**Secure Store Service**します。  
  
3.  ターゲット アプリケーションの管理 をクリックして**新規**します。  
  
4.  ターゲット アプリケーション id では、次のように入力します。 **PowerPivotDataRefresh**します。  
  
5.  表示名を入力**PowerPivot データ更新**します。  
  
6.  [連絡先の電子メール] に、自分の電子メール アドレスを入力します。  
  
7.  ターゲット アプリケーションの種類の選択**個々**します。  
  
    > [!NOTE]  
    >  PowerPivot サービス アプリケーションだけが PowerPivot 自動データ更新アカウントの資格情報を要求するため、このシナリオでは [個人] アカウントの種類を指定するのが適切です。 実際には、サービス アプリケーションは自動データ更新アカウントの唯一のユーザーであるため、[個人] アカウントの種類がこのターゲット アプリケーションに対して最適な選択肢になります。  
  
8.  [対象アプリケーションのページ URL] はスキップします。 PowerPivot データ更新では使用されません。  
  
9. **[次へ]** をクリックします。  
  
10. **、Secure Store ターゲット アプリケーションの資格情報フィールドを指定** ページで、既定値をそのまま使用します。 フィールドの名前と種類は、Windows ユーザー名と Windows パスワードにする必要があります。  
  
11. **[次へ]** をクリックします。  
  
12. [ターゲット アプリケーションの管理者] で、PowerPivot サービス アプリケーションのアプリケーション プール ID を指定します。 サービスに必要な**フルコントロール**自動データ取得できるようにアクセス許可は、実行時にアカウント情報を更新します。 さらに、アプリケーション設定に対する管理アクセス権を必要とする他の SharePoint ユーザーの Windows ドメイン ユーザー アカウントを指定します。  
  
13. **[OK]** をクリックします。  
  
14. 作成したターゲット アプリケーションを選択して、下矢印をクリックしておよび選択**資格情報の設定。**  
  
15. **資格情報の所有者**、資格情報の更新を許可する Windows ドメイン ユーザー アカウントを入力します。 データ更新アクションの資格情報を使用し、**資格情報の所有者**資格情報を変更する権限します。  
  
16. **[OK]** をクリックします。  
  
###  <a name="bkmk_specifyUA"></a> 手順 2: PowerPivot サーバー構成ページで自動アカウントを指定します。  
  
1.  サーバーの全体管理で、[アプリケーション構成の管理] の **[サービス アプリケーションの管理]** をクリックします。  
  
2.  PowerPivot サービス アプリケーションを探します。 サービス アプリケーションは、型で識別できます。 PowerPivot サービス アプリケーションの型は、 **[PowerPivot サービス アプリケーション]** です。  
  
3.  PowerPivot サービス アプリケーションの名前をクリックします。 PowerPivot 管理ダッシュボードが表示されるまで待ちます。  
  
4.  アクションで、右下隅の上部にある クリックして**サービス アプリケーションの設定を構成する**します。  
  
5.  PowerPivot 自動データ更新アカウント、データ更新、前の手順で作成したターゲット アプリケーション ID を入力: **PowerPivotDataRefresh**します。  
  
6.  **[OK]** をクリックします。  
  
###  <a name="bkmk_grant"></a> 手順 3: 許可がアカウントへのアクセス許可を投稿します。  
 PowerPivot 自動データ更新アカウントを使用する前に、使用する任意の PowerPivot ブックに対する投稿権限をこのアカウントに割り当てる必要があります。 この権限レベルは、ライブラリからブックを開き、データの更新後に再度ライブラリに保存するために必要です。  
  
 権限の割り当ては、サイト コレクションの管理者が実行する手順です。 SharePoint の権限は、ルート サイト コレクションで割り当てるか、ルート サイト コレクションより下位の任意のレベル (個々のドキュメントやアイテムを含む) で割り当てることができます。 権限の設定方法は、権限をどのくらい細かく設定する必要があるかによって異なります。 次の手順は、権限を付与する方法の一例を示しています。  
  
1.  サイトの操作での SharePoint サイト をクリックして**サイトのアクセス許可**します。  
  
2.  **[アクセス許可の付与]** をクリックします。  
  
3.  [ユーザーの選択] に、PowerPivot 自動データ更新アカウントとして指定した Windows ドメイン ユーザー アカウントの名前を入力します。 これは、Secure Store Service でターゲット アプリケーションに指定した Windows ドメイン ユーザー アカウントの名前です。  
  
4.  アクセス許可の付与、次のように選択します。**ユーザー アクセス許可を直接付与**します。  
  
5.  選択**投稿**、 をクリックし、 **OK**。  
  
###  <a name="bkmk_dbread"></a> 手順 4: 読み取りデータの更新で使用される外部データ ソースにアクセスする権限の付与  
 データを PowerPivot ブックにインポートする場合、通常、外部データへの接続は、信頼関係接続か、(現在のユーザーの ID を使用してデータ ソースに接続する) 権限を借用した接続に基づきます。 これらの種類の接続は、現在のユーザーがインポートする対象のデータに対する読み取り権限を持つ場合にのみ有効です。  
  
 データ更新シナリオでは、データをインポートするために使用された接続文字列が、データを更新するために再利用されます。 接続文字列が現在のユーザーを想定している (たとえば、Integrated_Security=SSPI を含む文字列) 場合、PowerPivot System サービスは、PowerPivot 自動データ更新アカウントのユーザー ID を現在のユーザーとして渡します。 この接続は、外部データ ソースに対する読み取り権限が PowerPivot 自動データ更新アカウントに付与されている場合にのみ成功します。  
  
 このため、自動アカウントで実行されるすべてのデータ更新操作で使用されるすべての外部データ ソースに対する読み取り専用権限を、PowerPivot 自動データ更新アカウントに付与する必要があります。  
  
 組織で使用しているデータ ソースの管理者であれば、ログインを作成し、必要な権限を付与することができます。 管理者でない場合は、データの所有者に対してアカウント情報を連絡する必要があります。 PowerPivot 自動データ更新アカウントにマップされる Windows ドメイン ユーザー アカウントを必ず指定してください。 これは、このトピックの「(手順 1): ターゲット アプリケーションを作成して資格情報を設定する」で指定したアカウントです。  
  
###  <a name="bkmk_verify"></a> 手順 5: 確認のアカウントを使用できるデータ更新構成ページ  
  
1.  PowerPivot データが含まれているパブリッシュ済みのブックのデータ更新構成ページを開きます。 ページを開く方法の詳細については、次を参照してください。[データ更新のスケジュール&#40;PowerPivot for SharePoint&#41;](schedule-a-data-refresh-powerpivot-for-sharepoint.md)します。  
  
2.  いることを確認、**データ更新アカウントの管理者によって構成を使用**データ更新構成ページでオプションを有効にします。  
  
3.  選択、**も、できるだけ早く更新**チェック ボックスをオン をクリックし、 **ok**。  
  
4.  ブックが含まれているライブラリでブックを選択、右にある下矢印をクリックし、 **PowerPivot データ更新の管理**します。 データ更新ジョブが返すデータ量が多い場合は、数分待つことが必要な場合があります。  
  
 エラーが発生する場合はクリックして**スケジュールの構成**データ更新履歴 ページに別の資格情報をお試しください。 元のブックのデータ ソース接続情報を調べて、データ更新時に使用される接続文字列を表示することが必要な場合もあります。 接続文字列は、問題のトラブルシューティングに使用できるサーバーの場所とデータベースに関する情報を提供します。  
  
 トラブルシューティングの詳細については、次を参照してください。 [PowerPivot データ更新のトラブルシューティング](http://go.microsoft.com/fwlink/p/?LinkID=223279)、TechNet Wiki にします。  
  
##  <a name="bkmk_use"></a> PowerPivot 自動データ更新を使用するアカウント  
 PowerPivot データ更新スケジュール ページの 3 つの資格情報オプションのうち、自動データ更新アカウントに対応するのは最初のオプションだけです。 データ更新スケジュールを設定する場合は、必ずこのオプションを選択してください。  
  
 ![SSAS_PowerpivotKJ_DataRefreshCreds](media/ssas-powerpivotkj-datarefreshcreds.gif "SSAS_PowerpivotKJ_DataRefreshCreds")  
  
 PowerPivot 自動データ更新アカウントへのアクセスには第 3 の資格情報オプション (ターゲット アプリケーション ID の入力を必要とするオプション) を使用しないでください。 このオプションで実行される追加の権限借用チェックにより、このオプションを PowerPivot 自動データ更新アカウント (または、[個人] アカウントの種類に基づくターゲット アプリケーション) と共に使用しようとすると検証エラーが発生します。 3 番目のオプションを使用する方法の詳細については、次を参照してください。[格納されている資格情報の構成の PowerPivot データ更新&#40;PowerPivot for SharePoint&#41;](configure-stored-credentials-data-refresh-powerpivot-sharepoint.md)します。  
  
##  <a name="bkmk_editUA"></a> 既存の PowerPivot で使用される資格情報を更新する自動データ更新アカウント  
 セットアップまたは管理者によって自動データ更新アカウントが既に構成されている場合は、資格情報が保存されているターゲット アプリケーションを編集することで、ユーザー名またはパスワードを更新できます。 以前に PowerPivot 自動データ更新アカウントに関連付けられていた元の Windows ID は、Secure Store Service で資格情報を編集するときに表示されません。 期限切れのパスワードを更新するか、別のアカウントを指定するかにかかわらず、常に Secure Store Service でそのターゲット アプリケーションのユーザー名とパスワードの両方を再入力する必要があります。  
  
1.  サーバーの全体管理で、[アプリケーション構成の管理] の **[サービス アプリケーションの管理]** をクリックします。  
  
2.  クリックして**Secure Store Service**します。  
  
3.  次のチェック ボックスをオン**PowerPivotDataRefresh**します。  
  
4.  [資格情報] をクリックして**設定**します。  
  
5.  **資格情報の所有者**、資格情報の更新を許可する Windows ドメイン ユーザー アカウントを入力します。 データ更新アクションの資格情報を使用し、**資格情報の所有者**資格情報を変更する権限します。  
  
6.  [ユーザー名] に、自動データ更新資格情報の一部となる Windows ドメイン ユーザー アカウントを入力します。  
  
7.  [パスワード] に、アカウントのパスワードを入力し、確認のためもう一度パスワードを入力します。  
  
8.  **[OK]** をクリックします。  
  
 パスワードだけでなく、アカウントのユーザー名も変更する場合、通常は外部データ ソースに対する読み取り権限や PowerPivot ブックを更新するための SharePoint 権限の付与などの追加の構成手順を実行する必要があります。 手順については、PowerPivot 自動データ更新アカウントの構成には、この手順を参照してください:[手順 3: Grant、アカウントへのアクセス許可の貢献](#bkmk_grant)、し、検証の終了時、残りすべての手順を続行する、アカウントが正しく構成されています。  
  
## <a name="see-also"></a>参照  
 [SharePoint 2010 で PowerPivot データ更新](powerpivot-data-refresh-with-sharepoint-2010.md)   
 [データ更新のスケジュール&#40;PowerPivot for SharePoint&#41;](schedule-a-data-refresh-powerpivot-for-sharepoint.md)   
 [PowerPivot のデータ更新](power-pivot-sharepoint/power-pivot-data-refresh.md)  
  
  