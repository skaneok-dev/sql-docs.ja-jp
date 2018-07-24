---
title: 履歴属性オプション (緩やかに変化するディメンション ウィザード) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.histattriboption.f1
ms.assetid: a176ec66-ec39-4c99-99d1-c1afa8450e1e
caps.latest.revision: 21
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 7f9b7b2819eec76f3ccc913debea3773cad0b9e4
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37328082"
---
# <a name="historical-attribute-options-slowly-changing-dimension-wizard"></a>[履歴属性オプション] (緩やかに変化するディメンション ウィザード)
  **[履歴属性オプション]** ダイアログ ボックスを使用すると、開始日や終了日によって履歴属性を表示したり、専用に作成された列に履歴属性を記録したりできます。  
  
 このウィザードの詳細については、「 [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md)」を参照してください。  
  
## <a name="options"></a>および  
 **[現在のレコードと有効期限が切れたレコードを 1 列で表示する]**  
 1 列を使用して履歴属性のステータスを記録する場合は、次のオプションを使用できます。  
  
|オプション|説明|  
|------------|-----------------|  
|**[現在のレコードを示す列]**|現在のレコードを示す列を選択します。|  
|**[現時点での値]**|**[True]** または **[Current]** を使用してレコードが現在のレコードであるかどうかを示します。|  
|**[有効期限切れの値]**|**[False]** または **[Expired]** を使用してレコードが履歴の値であるかどうかを示します。|  
  
 **[開始日と終了日を使用して現在のレコードと有効期限が切れたレコードを識別する]**  
 このオプションのディメンション テーブルには、日付列を含める必要があります。 履歴属性を開始日および終了日を使用して示す場合は、次のオプションを使用できます。  
  
|オプション|説明|  
|------------|-----------------|  
|**[開始日の列]**|ディメンション テーブルで開始日を含む列を選択します。|  
|**[終了日の列]**|ディメンション テーブルで終了日を含む列を選択します。|  
|**[日付の値を設定する変数]**|日付の変数を一覧から選択します。|  
  
## <a name="see-also"></a>参照  
 [緩やかに変化するディメンション ウィザードを使用して出力を構成する](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  