---
title: テンプレートから単一予測クエリを作成 |Microsoft ドキュメント
ms.date: 05/01/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: data-mining
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: baa6153adde1a5cc5aaeaad5f8b04366dcb2dad8
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
ms.locfileid: "34019769"
---
# <a name="create-a-singleton-prediction-query-from-a-template"></a>テンプレートからの単一予測クエリの作成
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  単一クエリは、予測に使用するモデルがあり、それを外部入力データ セットにマップしたり一括予測を行ったりしない場合に役立ちます。 単一クエリでは、モデルに 1 つまたは複数の値を提供し、予測される値を即時に参照できます。  
  
 たとえば、次の DMX クエリは、メーリング対象モデル TM_Decision_Tree に対する単一クエリを表しています。  
  
```  
SELECT * FROM [TM_Decision_tree] ;  
NATURAL PREDICTION JOIN  
(SELECT '2' AS [Number Children At Home], '45' as [Age])  
AS [t]  
```  
  
 次の手順では、 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] でテンプレート エクスプローラーを使用してこのクエリを迅速に作成する方法について説明します。  
  
### <a name="to-open-the-analysis-services-templates-in-sql-server-management-studio"></a>SQL Server Management Studio で Analysis Services テンプレートを開くには  
  
1.  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]で、 **[表示]** メニューの **[テンプレート エクスプローラー]** をクリックします。  
  
2.  キューブ アイコンをクリックして、 **[分析サーバー]** テンプレートを開きます。  
  
### <a name="to-open-a-prediction-query-template"></a>予測クエリ テンプレートを開くには  
  
1.  **[テンプレート エクスプローラー]** の分析サーバー テンプレートの一覧から **[DMX]** を展開し、 **[予測クエリ]** を展開します。  
  
2.  **[単一予測]** をダブルクリックします。  
  
3.  **[Analysis Services への接続]** ダイアログ ボックスで、クエリの対象であるマイニング モデルを含む [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] インスタンスのあるサーバー名を入力します。  
  
4.  **[接続]** をクリックします。  
  
5.  指定したデータベースでテンプレートが開き、データ マイニング関数と、データ マイニング構造および関連するモデルの一覧を示す、マイニング モデルのオブジェクト ブラウザーが表示されます。  
  
### <a name="to-customize-the-singleton-query-template"></a>単一クエリ テンプレートをカスタマイズするには  
  
1.  テンプレートで、 **[使用できるデータベース]** ドロップダウン リストをクリックし、一覧から Analysis Services インスタンスをクリックします。  
  
2.  **[マイニング モデル]** ボックスの一覧から、クエリの対象とするマイニング モデルをクリックします。  
  
     マイニング モデルの列の一覧がオブジェクト ブラウザーの **[メタデータ]** ペインに表示されます。  
  
3.  **[クエリ]** メニューの **[テンプレート パラメーターの値の指定]** をクリックします。  
  
4.  **select list** 行に「*」と入力するとすべての列が返され、列と式のコンマ区切りの一覧を入力すると特定の列が返されます。  
  
     「*」と入力すると、予測可能列と、手順 6. で新しい値を指定する列が返されます。  
  
     このトピックの冒頭に示したサンプル コードでは、 **select list** 行を * に設定していました。  
  
5.  **mining model** 行には、 **オブジェクト エクスプローラー**に表示されるマイニング モデルの一覧からマイニング モデルの名前を入力します。  
  
     このトピックの冒頭に示したサンプル コードでは、 **mining model** 行に **TM_Decision_Tree**という名前を設定していました。  
  
6.  **value** 行には、予測を行う新しいデータを入力します。  
  
     このトピックの冒頭に示したサンプル コードでは、 **value** 行を **2** に設定し、世帯の子供の数に基づいて自転車の購買行動を予測しました。  
  
7.  **column** 行には、新しいデータをマップするマイニング モデルの列名を入力します。  
  
     このトピックの冒頭に示したサンプル コードでは、 **column** 行を **Number Children at Home**に設定していました。  
  
    > [!NOTE]  
    >  **[テンプレート パラメーターの値の指定]** ダイアログ ボックスを使用する場合、列名を角かっこで囲む必要はありません。 角かっこは自動的に追加されます。  
  
8.  **input alias** は **t**のままにしてください。  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
10. クエリのテキスト ペインで、コンマと省略記号の下に構文エラーを示す赤い波線がある箇所を見つけます。 省略記号を削除し、必要なクエリ条件を追加します。 他の条件を追加しない場合はコンマを削除します。  
  
     このトピックの冒頭に示したサンプル コードでは、追加のクエリ条件として **'45' as [Age]** を設定していました。  
  
11. **[実行]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [予測 & #40; を作成します。基本的なデータ マイニング チュートリアル & #41;](http://msdn.microsoft.com/library/a8410ed2-bb98-4d51-a9eb-b239be1201c2)  
  
  
