---
title: 追加の参照 ダイアログ ボックス (Analysis Services - 多次元データ) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.addreference.f1
- sql12.asvs.bidevstudio.assembly.addassembly.f1
helpviewer_keywords:
- Add Reference dialog box
ms.assetid: 457958c4-6baa-474d-99a0-34c195ceba09
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: a2a44c1f7a37cc7e7e010ea15c72d35255b443e4
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48174182"
---
# <a name="add-reference-dialog-box-analysis-services---multidimensional-data"></a>[参照の追加] ダイアログ ボックス (Analysis Services - 多次元データ)
  **の** [参照の追加] [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] ダイアログ ボックスを使用すると、 [!INCLUDE[msCoName](../includes/msconame-md.md)] .NET Framework アセンブリに参照を追加することも、開発プロジェクトに別の開発プロジェクトを追加することもできます。 **[参照の追加]** ダイアログ ボックスを表示するには、**ソリューション エクスプローラー**で [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] プロジェクトの **[アセンブリ]** フォルダーを右クリックして、ショートカット メニューから **[新しいアセンブリ参照]** を選択します。  
  
## <a name="options"></a>および  
  
|項目|定義|  
|----------|----------------|  
|**.NET**|登録されているコンポーネントに参照を追加するには、このタブを選択します。 このタブには、登録されている .NET Framework コンポーネントの一覧を含むグリッドが表示されます。 グリッドから 1 つ以上の項目を選択して **[追加]** をクリックし、選択した .NET コンポーネントを **[選択されたプロジェクトとコンポーネント]** に追加します。 このグリッドには次の列が含まれています。<br /><br /> **[コンポーネント名]**: コンポーネントの正確な名前、または通称です。 コンポーネント名で並べ替えるには、タイトルを選択します。<br /><br /> **バージョン**: コンポーネントの一覧表示されているバージョン番号。 バージョンで並べ替えるには、タイトルを選択します。<br /><br /> **ランタイム**: コンポーネントが基づく .NET Framework のバージョン。 ランタイムのバージョンで並べ替えるには、タイトルを選択します。<br /><br /> **パス**: コンポーネントおよびそれが配置されるパスのファイル名。 パスで並べ替えるには、タイトルを選択します。|  
|**[参照]**|**[.NET]** タブや **[最近使用したファイル]** タブに表示されていないアセンブリをファイル システムから参照する場合にクリックします。 このタブには次のオプションが表示されます。<br /><br /> **検索対象**: このドロップダウン リストからフォルダーを選択します。 この一覧でフォルダーを選択すると、そのフォルダーの内容が主要ペインに表示されます。<br /><br /> **最後に表示したフォルダーに移動して**: 返します**ファイルの場所**前の場所にします。<br /><br /> **1 つ上位レベル**: 階層の [次へ] の上のフォルダーを検索します。<br /><br /> **新しいフォルダーを作成する**: で選択したフォルダーの下に新しい子フォルダーを作成する場合に選択**検索**します。<br /><br /> **メニューを表示**: 選択すると、主要ペインの内容の表示を変更します。  **[表示メニュー]** のオプションの詳細については、 [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows ドキュメントの「ファイルとフォルダーの表示の概要」を参照してください。 使用できるオプションは以下のとおりです。<br />[縮小表示]<br />[大きいアイコン]<br />[小さいアイコン]<br />リスト<br />詳細<br /><br /> **主要ペイン**: で選択したフォルダーの内容を表示**検索**します。 1 つまたは複数の項目を選択し、クリックして**追加**を選択したファイルを追加する**選択された製品とコンポーネント**します。 主要ペインのオプションおよびショートカット メニューの詳細については、Windows ドキュメントの「ファイルとフォルダーの表示の概要」を参照してください。<br /><br /> **ファイル名**: このオプションを使用して、ファイルと表示されているフォルダーをフィルター処理します。 フィルターを適用する上のすべてまたは一部のファイル名を入力します。 ワイルドカードとしてアスタリスク (\*) を使用できます。 複数のファイルを選択するには、複数のファイル名を入力します。各ファイル名を二重引用符 (") で囲んで、スペースで区切ります。 以前に使用したファイルを選択するには、ドロップダウン リストからファイル名を選択します。 ヒント: 見つかります Web サーバーやネットワーク コンピューターでの URL またはネットワーク パスを入力して**ファイル名**します。 たとえば、「 http://mywebsite 」と入力した場合は、"mywebsite" という Web の場所で利用可能なファイルが表示され、「\\\myserver\myshare」と入力した場合は、"myserver" の "myshare" という場所で利用可能なファイルが表示されます。<br /><br /> **ファイルの種類**: このオプションを使用して、フォルダーまたはで選択したディレクトリの内容をフィルター処理**ファイルの場所**の特定のファイルの種類。|  
|**最近**|[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]でプロジェクトに最近追加されたコンポーネント参照の一覧が表示されます。 選択した .NET Framework アセンブリを **[選択されたプロジェクトとコンポーネント]** に追加するには、グリッドから 1 つ以上の項目を選択して **[追加]** をクリックします。 このグリッドには次の列が含まれています。<br /><br /> **[コンポーネント名]**: コンポーネントの正確な名前、または通称です。 コンポーネント名で並べ替えるには、タイトルを選択します。<br /><br /> **バージョン**: コンポーネントの一覧表示されているバージョン番号。 バージョンで並べ替えるには、タイトルを選択します。<br /><br /> **ランタイム**: コンポーネントが基づく .NET Framework のバージョン。 ランタイムのバージョンで並べ替えるには、タイトルを選択します。<br /><br /> **パス**: コンポーネントおよびそれが配置されるパスのファイル名。 パスで並べ替えるには、タイトルを選択します。|  
|**[追加]**|クリックすると、 **[.NET]** タブ、 **[参照]** タブ、または **[最近使用したファイル]** タブで選択されているコンポーネントが **[選択されたプロジェクトとコンポーネント]** に追加されます。|  
|**[削除]**|クリックすると、 **[選択されたプロジェクトとコンポーネント]** で選択されているコンポーネントが削除されます。|  
|**選択されたプロジェクトとコンポーネント**|[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] の [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]プロジェクトに追加されるコンポーネント参照の一覧が表示されます。 選択したコンポーネントをグリッドから削除するには、1 つ以上の項目を選択して **[削除]** をクリックします。 このグリッドには次の列が含まれています。<br /><br /> **[コンポーネント名]**: コンポーネントの正確な名前、または通称です。 コンポーネント名で並べ替えるには、タイトルを選択します。<br /><br /> **バージョン**: コンポーネントの一覧表示されているバージョン番号。 バージョンで並べ替えるには、タイトルを選択します。<br /><br /> **ランタイム**: コンポーネントが基づく .NET Framework のバージョン。 ランタイムのバージョンで並べ替えるには、タイトルを選択します。<br /><br /> **パス**: コンポーネントおよびそれが配置されるパスのファイル名。 パスで並べ替えるには、タイトルを選択します。|  
  
## <a name="see-also"></a>参照  
 [Analysis Services のデザイナーおよびダイアログ ボックス&#40;多次元データ&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)   
 [多次元モデルのアセンブリの管理](multidimensional-models/multidimensional-model-assemblies-management.md)  
  
  
