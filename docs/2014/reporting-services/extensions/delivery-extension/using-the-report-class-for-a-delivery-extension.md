---
title: 配信拡張機能での Report クラスの使用 | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], report information
- Report class
ms.assetid: 1145ac63-eafd-452a-82af-16f85b1676dd
caps.latest.revision: 34
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 42bb83e2f4420419f82489193dcf022a08783e77
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37301702"
---
# <a name="using-the-report-class-for-a-delivery-extension"></a>配信拡張機能での Report クラスの使用
  <xref:Microsoft.ReportingServices.Interfaces.Report> クラスは、レポート サーバー データベースのレポートを表します。 すべてのサブスクリプションは特定のレポートに関連付けられます。 レポートは通知に含まれます。 配信拡張機能では、通知の一部である <xref:Microsoft.ReportingServices.Interfaces.Report> オブジェクトを使用してレポートを生成できます。 <xref:Microsoft.ReportingServices.Interfaces.Report> オブジェクトには、レポート サーバーのレポートの URL やレポート名など、レポート固有のプロパティも含まれています。 これらのプロパティすべてを配信プロバイダーの一部として使用できます。  
  
 <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> クラスの <xref:Microsoft.ReportingServices.Interfaces.Report> メソッドを使用して、レポートを表示できます。 <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> メソッドは、1 つの表示レポートを構成する <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> オブジェクトの配列を 1 つ以上返します。 1 番目の <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> オブジェクトが表示レポートです。 その他の <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> オブジェクトは、レポート データと一緒に配信される必要があるリソースです (HTML ファイルや関連付けられた画像など)。 表示拡張機能がシングル ストリーム表示拡張機能である場合は (IMAGE、PDF、MHTML、および Excel)、配列の <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> オブジェクトを 1 つだけ返します。  
  
 レポート ストリームを含む <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> オブジェクトは、配信の一部として含めることができます。  
  
 <xref:Microsoft.ReportingServices.Interfaces.Report> クラスの使用例については、「[SQL Server Reporting Services Product Samples](http://go.microsoft.com/fwlink/?LinkId=177889)」 (SQL Server Reporting Services 製品サンプル) を参照してください。  
  
## <a name="see-also"></a>参照  
 [配信拡張機能の実装](implementing-a-delivery-extension.md)   
 [Reporting Services 拡張機能ライブラリ](../reporting-services-extension-library.md)   
 [配信拡張機能での RenderedOutputFile クラスの使用](using-the-renderedoutputfile-class-for-a-delivery-extension.md)  
  
  