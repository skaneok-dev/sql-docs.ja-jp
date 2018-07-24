---
title: 複数のページへの行および列ヘッダーの表示 (レポート ビルダーおよび SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 2422b1e2-822f-4379-9d7f-9afebb350e3f
caps.latest.revision: 6
author: maggiesMSFT
ms.author: maggies
manager: craigg
ms.openlocfilehash: ef91743d7a5a4106b51761901ba6f18b9f24d5a1
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37303672"
---
# <a name="display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs"></a>複数のページへの行および列ヘッダーの表示 (レポート ビルダーおよび SSRS)
  Tablix データ領域が複数のページにわたる場合、各ページで行ヘッダーおよび列ヘッダーを繰り返すかどうかを制御できます。 Tablix データ領域は、テーブル、マトリックス、または一覧のいずれかです。  
  
 行および列を制御する方法は、Tablix データ領域にグループ ヘッダーがあるかどうかによって異なります。 グループ ヘッダーを含む Tablix データ領域内でクリックすると、次の図に示すように点線で Tablix 領域が示されます。  
  
 ![Tablix データ領域部分](../media/rs-tablixareas.gif "Tablix データ領域部分")  
  
 行グループ ヘッダーと列グループ ヘッダーは、テーブルまたはマトリックスの新規作成ウィザードかグラフの新規作成ウィザードでグループを追加するときに、フィールドをグループ化ペインに追加するか、コンテキスト メニューを使用すると、自動的に作成されます。 Tablix データ領域に Tablix 本体領域のみがあり、グループ ヘッダーがない場合、行および列は Tablix メンバーになります。  
  
 静的メンバーの場合、上部にある隣接する行または横にある隣接する列を複数のページに表示できます。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-row-headers-on-multiple-pages"></a>複数のページに行ヘッダーを表示するには  
  
1.  Tablix データ領域の行、列、またはコーナー ハンドルを右クリックし、 **[Tablix のプロパティ]** をクリックします。  
  
2.  **[行のヘッダー]** の **[すべてのページにヘッダー行を表示する]** を選択します。  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-display-column-headers-on-multiple-pages"></a>複数のページに列ヘッダーを表示するには  
  
1.  Tablix データ領域の行、列、またはコーナー ハンドルを右クリックし、 **[Tablix のプロパティ]** をクリックします。  
  
2.  **[列のヘッダー]** の **[すべてのページにヘッダー列を表示する]** を選択します。  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-display-a-static-tablix-member-row-or-column-on-multiple-pages"></a>複数のページに静的な Tablix メンバー (行または列) を表示するには  
  
1.  デザイン画面で、Tablix データ領域の行ハンドルまたは列ハンドルをクリックして選択します。 グループ化ペインに行グループと列グループが表示されます。  
  
2.  グループ化ペインの右側にある下矢印をクリックし、 **[詳細設定モード]** をクリックします。 行グループ ペインに、行グループ階層の静的メンバーおよび動的メンバーが階層的に表示され、列グループ ペインに、列グループ階層のメンバーが同様に表示されます。  
  
3.  スクロール中も表示したままにする静的メンバー (行または列) に対応する静的メンバーをクリックします。 プロパティ ペインに **[Tablix メンバー]** プロパティが表示されます。  
  
     プロパティ ペインが表示されない場合は、レポート ビルダー ウィンドウの上部にある **[表示]** タブをクリックし、 **[プロパティ]** をクリックします。  
  
4.  プロパティ ペインで、 **RepeatOnNewPage** を True に設定します。  
  
5.  **KeepWithGroup** を After に設定します。  
  
6.  繰り返し表示するすべての隣接するメンバーに対して、この手順を繰り返します。  
  
7.  レポートをプレビューします。  
  
 Tablix データ領域が複数のページにわたるレポートで各ページを表示したときに、静的な Tablix メンバーが各ページに繰り返し表示されます。  
  
## <a name="see-also"></a>参照  
 [レポートの検索、表示、管理 (レポート ビルダーおよび SSRS)](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)   
 [レポートのエクスポート&#40;レポート ビルダーおよび SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md)   
 [見出し、列、および行は、改ページの制御&#40;レポート ビルダーおよび SSRS&#41;](controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs.md)   
 [グループ単位でのヘッダーとフッターの表示 &#40;レポート ビルダーおよび SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md)   
 [レポートのスクロール時にヘッダーを表示したまま&#40;レポート ビルダーおよび SSRS&#41;](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md)  
  
  