---
title: (Visual Database Tools) ダイアグラムでテーブル間のリレーションシップの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- diagrams [SQL Server], designing
ms.assetid: 28e9630c-dff4-46cc-bb0e-fe77998b6ac2
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 1cb069a1e28a10036ebea2738f5eea81a9f8932c
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48128644"
---
# <a name="create-relationships-between-tables-on-a-diagram-visual-database-tools"></a>ダイアグラムでテーブル間のリレーションシップを作成する方法 (Visual Database Tools)
  ダイアグラム デザイナーでは、テーブル間で列をドラッグすることにより、異なるテーブルの列の間にリレーションシップを作成できます。  
  
### <a name="to-create-a-relationship-graphically"></a>リレーションシップをグラフィカルに作成するには  
  
1.  データベース デザイナーで、別のテーブル内の列に関連付ける 1 つ以上のデータベース列の行セレクターをクリックします。  
  
2.  選択した列を関連テーブルにドラッグします。  
  
3.  **[外部キーのリレーションシップ]** ダイアログ ボックスと **[テーブルと列]** ダイアログ ボックスが表示されます。後者のダイアログ ボックスが手前に表示されます。  
  
4.  **[リレーションシップ名]** には、FK_*localtable*_*foreigntable*という形式の名前が表示されます。 この値は変更できます。  
  
5.  **[主キー テーブル]** に適切なテーブルが指定されていることを確認します。  
  
6.  グリッドには、ローカル列とそれに対応する外部列が表示されます。 テーブル列の追加や削除またはマッピングの変更が可能です。  
  
7.  **[OK]** を選択します。  
  
     **[外部キーのリレーションシップ]** ダイアログ ボックスが表示されます。 **[選択されたリレーションシップ]** には、作成したリレーションシップが表示されます。  
  
8.  グリッド内のリレーションシップのプロパティを変更します。  
  
9. **[OK]** をクリックしてリレーションシップを作成します。  
  
     データベース デザイナーでは、選択した列間のリレーションシップが表示されます。  
  
## <a name="see-also"></a>参照  
 [テーブルと列 ダイアログ ボックス&#40;Visual Database Tools&#41;](visual-database-tools.md)   
 [Unique 制約と Check 制約](../../relational-databases/tables/unique-constraints-and-check-constraints.md)   
 [データベース ダイアグラムでのテーブルの使用 (Visual Database Tools)](work-with-tables-in-database-diagram-visual-database-tools.md)  
  
  
