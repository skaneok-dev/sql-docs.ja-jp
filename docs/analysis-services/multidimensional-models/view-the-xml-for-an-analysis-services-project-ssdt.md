---
title: ビュー、XML では、Analysis Services のプロジェクト (SSDT) |Microsoft ドキュメント
ms.date: 05/02/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: multidimensional-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: b1542c33d67c95c1c7154d08dbffd550b5f8cc72
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
ms.locfileid: "34025139"
---
# <a name="view-the-xml-for-an-analysis-services-project-ssdt"></a>Analysis Services のプロジェクトでの XML の表示 (SSDT)
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] のデータベースをプロジェクト モードで操作している場合は、[!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] によって各オブジェクトの XML 定義がプロジェクト フォルダー内に作成されます。 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]内で各オブジェクトの XML ファイルの内容を見ることができます。 また、XML ファイルを直接編集することもできますが、変更によって XML を [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]で読み取れなくなる可能性があるため、ほとんどの状況ではお勧めできません。  
  
> [!NOTE]  
>  オブジェクトごとにファイルが異なるため、プロジェクト全体の xml コードは表示できませんが、各オブジェクトのコードを確認します。 プロジェクトをビルドし、ASSL を表示するのには、プロジェクト全体のコードを表示する唯一の方法のコードで、\<プロジェクト名 > .asdatabase ファイル。  
  
### <a name="to-view-the-xml-code-for-an-object"></a>オブジェクトの XML コードを表示するには  
  
1.  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] で [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]プロジェクトを開きます。  
  
2.  ソリューション エクスプローラーでオブジェクトを右クリックし、 **[コードの表示]** をクリックします。  
  
     オブジェクトの XML コードが [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]に表示されます。  
  
## <a name="see-also"></a>参照  
 [Analysis Services プロジェクトのビルドと #40 です。SSDT & #41;](../../analysis-services/multidimensional-models/build-analysis-services-projects-ssdt.md)  
  
  
