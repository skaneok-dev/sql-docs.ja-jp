---
title: バージョンをロックする (マスター データ サービス) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology:
- master-data-services
ms.topic: conceptual
helpviewer_keywords:
- versions [Master Data Services], locking
- locking versions [Master Data Services]
ms.assetid: 7bb62a84-12d8-4b29-9b6e-6aa25410618e
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: d3211f6d015e70b515201272ca5a54c09af10ff3
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47609980"
---
# <a name="lock-a-version-master-data-services"></a>バージョンをロックする (マスター データ サービス)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]でモデルのバージョンをロックして、モデルのメンバーおよびメンバーの属性に対する変更を防止します。  
  
> [!NOTE]  
>  バージョンをロックしても、スーパー ユーザーおよびモデル管理者は、引き続きメンバーの追加、編集、および削除を行うことができます。 モデルに対する権限を持つその他のユーザーは、メンバーの表示のみを行うことができます。  
  
## <a name="prerequisites"></a>Prerequisites  
 この手順を実行するには  
  
-   モデル管理者である必要があります。 詳細については、「 [管理者 (マスター データ サービス)](../master-data-services/administrators-master-data-services.md)にアクセスすることなくグループに対してユーザーの追加または削除を行うことができます。  
  
-   バージョンのステータスは、 **[未処理]** である必要があります。  
  
-   [バージョン管理] 機能領域にアクセスする権限が必要です。 詳細については、「[機能領域権限 (マスター データ サービス)](../master-data-services/functional-area-permissions-master-data-services.md)」を参照してください。  
  
### <a name="to-lock-a-version"></a>バージョンをロックするには  
  
1.  [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]で **[バージョン管理]** をクリックします。  
  
2.  **[バージョンの管理]** ページで、ロックするバージョンの行を選択します。  
  
3.  **[ロック]** をクリックします。  
  
4.  確認のダイアログ ボックスで **[OK]** をクリックします。  
  
## <a name="next-steps"></a>Next Steps  
  
-   [ビジネス ルールに対してバージョンを検証する (マスター データ サービス)](../master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
-   [バージョンをコミットする (マスター データ サービス)](../master-data-services/commit-a-version-master-data-services.md)  
  
## <a name="see-also"></a>参照  
 [バージョン (マスター データ サービス)](../master-data-services/versions-master-data-services.md)   
 [バージョンをロック解除する (マスター データ サービス)](../master-data-services/unlock-a-version-master-data-services.md)  
  
  
