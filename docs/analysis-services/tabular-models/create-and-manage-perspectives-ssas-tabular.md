---
title: 作成し、パースペクティブの管理 |Microsoft ドキュメント
ms.date: 05/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 56c8f35aa15debbc064cacd73205234377224a28
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
ms.locfileid: "34040596"
---
# <a name="create-and-manage-perspectives"></a>作成し、パースペクティブの管理 
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]
  パースペクティブを使用すると、ビジネス固有またはアプリケーション固有のビューポイントをモデルに対して的を絞って作成するための、表示可能なサブセットを定義できます。 このトピックのタスクでは、モデル デザイナーで **[パースペクティブ]** ダイアログ ボックスを使用して、パースペクティブを作成し管理する方法について説明します。  
  
## <a name="tasks"></a>処理手順  
 パースペクティブを作成するには、 **[パースペクティブ]** ダイアログ ボックスを使用します。このダイアログ ボックスでは、パースペクティブの追加、編集、削除、コピー、表示の各操作を実行できます。 **[パースペクティブ]** ダイアログ ボックスを表示するには、 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]で **[モデル]** メニューをクリックし、 **[パースペクティブ]** をクリックします。  
  
###  <a name="bkmk_add"></a> パースペクティブを追加するには  
  
-   新しいパースペクティブを追加するには、 **[新しいパースペクティブ]** をクリックします。 パースペクティブに含めるフィールド オブジェクトのチェック ボックスをオンまたはオフにできます。新しいパースペクティブの名前を指定します。  
  
     すべてのフィールド オブジェクトのフィールドが空のパースペクティブを作成した場合、そのパースペクティブを使用するユーザーには空の "フィールドの一覧" が表示されます。 パースペクティブには 1 つ以上のテーブルおよび列を含める必要があります。  
  
###  <a name="bkmk_edit"></a> パースペクティブを編集するには  
  
-   パースペクティブに対する変更は、パースペクティブの列にあるフィールドをオンまたはオフにして、対応するパースペクティブのフィールド オブジェクトを追加または削除することによって行います。  
  
###  <a name="bkmk_rename"></a> パースペクティブの名前を変更するには  
  
-   パースペクティブの列のヘッダー (パースペクティブの名前) にマウス ポインターを合わせると、 **[名前の変更]** ボタンが表示されます。 パースペクティブの名前を変更するには、 **[名前の変更]** をクリックした後、新しい名前を入力するか、既存の名前を編集します。  
  
###  <a name="bkmk_delete"></a> パースペクティブを削除するには  
  
-   パースペクティブの列のヘッダー (パースペクティブの名前) にマウス ポインターを合わせると、 **[削除]** ボタンが表示されます。 パースペクティブを削除するには、 **[削除]** ボタンをクリックし、確認ウィンドウで **[はい]** をクリックします。  
  
###  <a name="bkmk_copy"></a> パースペクティブをコピーするには  
  
-   パースペクティブの列のヘッダーにマウス ポインターを合わせると、 **[コピー]** ボタンが表示されます。 そのパースペクティブのコピーを作成するには、 **[コピー]** ボタンをクリックします。 既存のパースペクティブの右側に、選択したパースペクティブのコピーが新しいパースペクティブとして追加されます。 新しいパースペクティブは、コピーしたパースペクティブの名前を継承しますが、名前の末尾には " *- コピー* " という注釈が追加されます。 たとえば、 *Sales* というパースペクティブのコピーを作成した場合、新しいパースペクティブの名前は " *Sales – コピー*" になります。  
  
## <a name="see-also"></a>参照  
 [パースペクティブ](../../analysis-services/tabular-models/perspectives-ssas-tabular.md)   
 [階層](../../analysis-services/tabular-models/hierarchies-ssas-tabular.md)  
  
  
