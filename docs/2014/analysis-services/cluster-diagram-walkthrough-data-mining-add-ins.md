---
title: クラスター ダイアグラムのチュートリアル (データ マイニング アドイン) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Visio shapes, cluster
- diagram, cluster
- shapes, data mining
- shapes, cluster
- data mining layout toolbar
ms.assetid: 761bef6a-37d4-4b19-944e-f2aadc75a242
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: b617305a8766ff94a699a054ac394be406dc7873
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48057092"
---
# <a name="cluster-diagram-walkthrough-data-mining-add-ins"></a>クラスター ダイアグラムのチュートリアル (データ マイニング アドイン)
  クラスタ リング モデルを作成した後を使用して Visio にインポートできる、**クラスター**図形、カスタマイズおよび強化、レイアウトに進みます。 **Visio 用データ マイニング図形**データ マイニング ダイアグラムを操作するため、次のカスタム コントロールが含まれます。  
  
-   クラスター ダイアグラムの描画コントロール  
  
     これらのオプションの一部である、**クラスター ウィザード**Visio ワークスペースに図形をドロップすると起動されます。  
  
-   **データ マイニング レイアウト**ツールバー  
  
     これは、データ マイニング図形の操作に役立つように Visio ワークスペースに追加されます。 オプションは、使用しているデータ マイニング モデルの種類に応じて異なります。  
  
## <a name="build-a-cluster-diagram"></a>クラスター ダイアグラムの作成  
 このチュートリアルでは、Visio でクラスター図を作成してカスタマイズする方法を示します。  
  
 続行するには、使用可能なクラスター モデルが既に存在する必要があります。 モデルがないを使用して、[クラスター ウィザード&#40;Excel 用データ マイニング アドインで&#41;](cluster-wizard-data-mining-add-ins-for-excel.md)ウィザードとすべての既定値を使用して、サンプル ブックで、トレーニング データ セットを使用して、モデルを作成します。  
  
#### <a name="use-the-cluster-visio-shape-wizard"></a>Visio クラスター図形ウィザードを使用して、  
  
1.  表示されない場合**Microsoft データ マイニング図形**で、**図形**一覧で、**その他の図形**を選択します**ステンシルを開く**、開くと、既定のインストール場所からのテンプレート。  
  
     \<ドライブ >: \Program files\Microsoft SQL Server 2012 DM Add-ins  
  
2.  ドラッグ、**クラスター**図形をページ。  
  
3.  ようこそ ページで、**クラスター Visio 図形ウィザード**、 をクリックして**次**します。  
  
4.  **データ ソースの選択**のページ、**クラスター ウィザード**への接続を選択、[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]視覚化するデータ マイニング モデルを含むサーバーです。  
  
5.  適切なマイニング モデルを選択し、クリックして**次**します。  
  
     クラスタ リング モデルを選択するようにするには、説明をレビューして、**プロパティ**ウィンドウ。  
  
6.  接続が成功すると、ページで場合、**クラスター ダイアグラムのオプション**、Visio プレゼンテーションに含めるクラスター ダイアグラムの種類を決定します。  
  
     **クラスター図形のみを表示します。**  
     選択した四角形などの図形で各クラスターが表現される単純なクラスター ダイアグラムを作成します。  
  
     **特性グラフと共にクラスターを表示します。**  
     上と同じグラフを作成しますが、図形の内部にクラスターの特性を表すヒストグラムを表示します。  
  
     ![Visio でのクラスター特性グラフの例](media/dm13-visio-cluster-samplecharshape.gif "Visio でのクラスター特性グラフの例")  
  
     **識別グラフと共にクラスターを表示します。**  
     クラスター ダイアグラムと同じ図を作成しますが、他のクラスターとの区別に最も役立つ現在のクラスターの特性を一覧表示します。  
  
     ウィザードがダイアグラムを作成した後、クラスターを右クリックして、新しいグラフの種類を選択すると、別の種類のグラフに切り替えることができます。 ここでは、選択、オプションの**特性グラフと共にクラスターを表示する**します。  
  
7.  オプションでは、状態のまま**グラフ内の行の数**、5 として。  
  
     このオプションは、モデル内のクラスターの数を変更しません。各クラスターの特徴として表示できる属性の数を制限するだけです。  
  
     ただし、グラフ データに対するフィルターとして機能するので、後から項目の数を増やすことはできません。  
  
8.  **[詳細設定]** をクリックします。  
  
     **クラスター オプション** ダイアログ ボックスは、図で図形の外観をカスタマイズします。 グラフで使用する色と、クラスターに使用する図形を変更できます。  
  
     **網掛け変数**コントロールは、Office 2013 では機能しません。  
  
     ![[詳細設定] 図形の色を選択する](media/dm13-visio-clusteroptions-advanced.gif "図形の色を選択する [詳細設定] をクリックします。")  
  
     **ヒント:** Visio の配色テーマと図形編集コントロールを使用して一部の色を後で変更できます。 ただし、Visio の配色テーマは選択した色の一部をオーバーライドするため、最初は既定の色で使い、徐々に変更することをお勧めします。  
  
9. をクリックして**完了**グラフを作成します。  
  
     ウィザードがデータ マイニング モデルから情報を取得して図形を描画し、各クラスターに属性と値を設定します。  
  
     ![依存関係ネットワーク](media/dm13-visiodepnet-defaultgraph.gif "依存関係ネットワーク")  
  
## <a name="explore-and-modify-the-finished-diagram"></a>完成したダイアグラムの調査と変更  
 ダイアグラムの完成後、次の例に示すように、引き続き Visio コントロールを使用して外観をカスタマイズすることができます。  
  
 ![クラスター ダイアグラムを Visio でカスタマイズして](media/dm13-visio-clustercomplete1.gif "Visio を使用してカスタマイズしたクラスター ダイアグラム")  
  
 基本的なクラスター図形はすべて、ウィザードによって生成されます。ダイアグラムの更新とカスタマイズには、以下のツールを使用します。  
  
1.  スライダーをドラッグ、**クラスター オプション**弱いリレーションシップを除外し、ダイアグラムを簡略化する、制御します。  
  
2.  Visio を使用して、**再レイアウト ページ**異なるクラスター レイアウトを実験するにはオプションです。  
  
3.  使用して、**コネクタ**オプション、**デザイン**クラスターと交差から行を保持するコネクタのスタイルを変更するには、タブ。  
  
4.  をクリックして、**アドイン**リボンで、データ マイニング ダイアグラムを操作するために使用するカスタム ツールバーを表示します。  
  
     **レイアウト**  
     クラスターを並べ替えて現在のページに収まるように最適化します。  
  
     **ページのサイズ変更します。**  
     このコントロールは、HTML の以前のバージョンを対象としたものです。 代わりに、Visio のページのサイズ変更コントロールを使用してください。  
  
     **Description**  
     クラスターが選択されている場合、このオプションをクリックすると、クラスターに関する詳細が表示されます。  
  
     ![説明は、クラスターに関する詳細を取得する をクリックして](media/dm13-visio-cluster-description-control.gif "クラスターに関する情報を取得の説明をクリックします。")  
  
     **枠の太さ**  
     クラスターを結ぶ線の信頼スコアが表示されます。  
  
     ただし、背景も含めて、ウィザードが生成した既定値以外の特殊な書式設定を適用した場合は、この数字が表示されないことがあります。  
  
     **スライダー**  
     クラスターを結ぶ線を絞り込みます。 スライダーを上へ移動すると、最も重要な関連付けだけを残して、すべての線が削除されます。  
  
     **網掛け**  
     このコントロールは、Office 2013 では機能しません。  
  
5.  使用して、**パンやズーム**コントロールを**作業ウィンドウ**Visio の領域**ビュー**リボンで、クラスターのセットに集中し、ダイアグラム内を移動します。  
  
6.  クラスターを右クリックして、クラスター図形に固有のオプションを表示します。  
  
    -   グラフの種類を変更します。  
  
    -   クラスター特性グラフを追加します。  
  
    -   クラスター識別グラフを追加します。  
  
## <a name="see-also"></a>関連項目  
 [Visio データ マイニング図形のトラブルシューティング&#40;SQL Server データ マイニング アドイン&#41;](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
