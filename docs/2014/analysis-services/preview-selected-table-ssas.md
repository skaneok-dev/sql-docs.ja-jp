---
title: 選択したテーブル (SSAS) のプレビュー |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.previewselecttable.f1
ms.assetid: b6b34b5a-43b3-4a75-9f3b-b2ad1084b1b6
caps.latest.revision: 11
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 49207b2d1574593c14ca6b005febebb28864dec3
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37314992"
---
# <a name="preview-selected-table-ssas"></a>[選択したテーブルのプレビュー] (SSAS)
  **テーブルのインポート ウィザード** のこのページを使用すると、選択したテーブルのデータのプレビュー、データ インポートに含める列の選択、および選択した列のデータのフィルター処理を行うことができます。 [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]からウィザードにアクセスするには、 **[モデル]** メニューの **[データ ソースからのインポート]** をクリックします。  
  
 テーブルのすべての行が表示されるわけではありません。 ただし、設定したフィルターはインポート時にテーブルのすべてのデータに適用されます。  
  
 Windows 認証を使用したデータ ソースの場合、[プレビューとフィルター] ダイアログに表示されたデータは、現在のユーザーの資格情報を使用してフェッチされます。 その他のデータ ソースについては、接続文字列に指定された資格情報を使用してデータがフェッチされます。  
  
 このページに表示されるデータは、インポートの成功を保証するものではありません。 [権限借用情報] ページで指定されたユーザー名に、選択したデータベースの読み取り権限がないと、インポートは失敗します。  
  
## <a name="uielement-list"></a>UI 要素の一覧  
 **列ヘッダーのチェック ボックス**  
 列をデータ インポートの対象にする場合は、チェック ボックスをオンにします。 列をデータ インポートの対象から除外する場合は、チェック ボックスをオフにします。  
  
 **列ヘッダーの矢印ボタンをクリックします。**  
 列のデータをフィルター処理します。  
  
 **行フィルターをクリアします。**  
 列のデータに適用されているすべてのフィルターを削除します。  
  
  