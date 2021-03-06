---
title: 自動推論 (Excel 用テーブル分析ツール) |Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- fill from example
ms.assetid: dac57d8f-1c65-4878-8ea0-9c680df5e4fb
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 5f5ca47ac10549a727f284eb412ba2b35127a518
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48160904"
---
# <a name="fill-from-example-table-analysis-tools-for-excel"></a>自動推論 (Excel 用のテーブル分析ツール)
  ![テーブル分析ツールで推論ボタン](media/tat-fillex.gif "テーブル分析ツールの例の全体適用ボタン")  
  
 **推論**ツールを使用して、既存の値に基づいてデータの新しい列を作成できます。  
  
 たとえば、データが含まれています、**購入額**列、**注文数量**列、および**上得意客**一部数式を使用してに基づいている列、その他の列。 場合、**上得意客**列に多数の空白行が含まれています、使用する可能性があります、**購入額**と**注文数量**欠損値を推測する、入力として列。 このツールは、データ内の既存のパターンを、ユーザーが入力したサンプルと組み合わせて分析し、各顧客にどのカテゴリを割り当てるかを予測します。  
  
 結果に満足できない場合は、より多くのサンプルを入力することにより、結果の精度を高めることができます。  
  
## <a name="using-the-fill-from-example-tool"></a>自動推論ツールの使用  
  
1.  **分析**リボンで、をクリックして**推論**します。  
  
2.  挿入対象となる列は、データの分析に基づいて自動的に選択されますが、それを受け入れるか、別の列を選択するかはユーザーが判断できます。  
  
3.  新しいデータの列を作成し、予測したいデータのサンプルを入力します。 予測する値ごとに、少なくとも 1 つのサンプル データが必要です。 既存の列にデータを挿入する場合は、欠損値の存在する列を選択します。  
  
4.  必要に応じてクリックして**分析で使用する列の選択**します。 **高度な列の選択** ダイアログ ボックスで、欠損値の予測に最も可能性のある列を指定します。  
  
     たとえば、欠損値の存在する列との間に因果効果のある列が経験的にわかっている場合は、他の列の選択を解除することによって、より精度の高い結果を得ることができます。  
  
     **[OK]** をクリックします。  
  
5.  **[実行]** をクリックします。  
  
     ツールを作成し、新しい分析が完了したら、**パターン**分析の結果を含むワークシートです。 レポートには、見つかったルール (主要な影響元) が一覧表示され、各ルールの確率が表示されます。  
  
     また、新しい値を含む列が、元のデータ テーブルに自動的に追加されます。 挿入された値を元の状態と比較しながら確認できます。  
  
### <a name="requirements"></a>要件  
 処理できるのは、列方向に格納されたデータだけです。 自動推論によって挿入する一連のデータが行として格納されている場合は、Excel の Paste、Transpose 関数を使用して、データを列形式に変換できます。  
  
## <a name="understanding-the-pattern-report"></a>パターン レポートについて  
 実行すると、**推論**ツール、レポートが作成され、検出されたパターンに関する情報を提供します。 これらのパターンは、新しいデータ値を推定するときに使用されます。  
  
 パターン レポートには、予測された値ごとに主要な影響元が示されます。 個々の影響元 (ルール) は、列とその値、および、そのルールの予測に対する相対的影響として表されます。  
  
 たとえば、注文の配送距離が記されたワークシートに対してデータを挿入しようとする場合、配送距離に強く影響するのは、配送先となる目的地です。 この場合、レポートには、次のような行が表示されます。  
  
|[列]|値|[優先]|相対的影響|  
|------------|-----------|------------|---------------------|  
|StateProvinceCode|AB|>500 km|80%|  
  
 値が AB でこれにより、 **StateProvinceCode**列は、配送距離を厳密に予測 > 500 キロメートル単位。  
  
 通常、ここで示した例よりも、はるかに複雑なパターンに基づいて予測が行われます。したがって、予測ごとに出力されるルールの行数も、もっと多くなります。 予測値は、こうしたすべてのルールの影響を組み合わせることによって導かれます。  
  
> [!NOTE]  
>  **相対的影響**網掛けされたバーとして表示されます。 棒グラフが長いほど、そのルールが、適切な挿入値を予測できる確率が高いことを示します。  
  
 このツールは、という名前の元のデータ テーブルに新しい列を追加するも\<列名 > 拡張します。  
  
 元のデータ列に値が存在した場合、その値が、この新しい列にコピーされます。 ただし、元の列が空白セルであった場合、新しい列には、ウィザードによって予測された値が格納されます。  
  
## <a name="related-tools-and-information"></a>関連ツールと情報  
 使用することも、[データの探索](explore-data-sql-server-data-mining-add-ins.md)ウィザード、Excel の列の値の分布を調べるの Excel 用データ マイニング クライアントで使用できます。 詳細については、次を参照してください。[調査とデータのクリーニング](exploring-and-cleaning-data.md)します。  
  
## <a name="see-also"></a>参照  
 [Excel 用テーブル分析ツール](table-analysis-tools-for-excel.md)  
  
  
