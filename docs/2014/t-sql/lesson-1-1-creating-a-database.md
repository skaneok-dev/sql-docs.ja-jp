---
title: データベースの作成 (チュートリアル) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- tutorial creating a database
ms.assetid: e1e2c83f-dfad-4bb8-aa7a-09d3f69517ae
caps.latest.revision: 11
author: edmacauley
ms.author: edmaca
manager: craigg
ms.openlocfilehash: c4f5933c5e653ee4c219e289dc71a8032b056f34
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37196592"
---
# <a name="creating-a-database-tutorial"></a>データベースの作成 (チュートリアル)
  多くの [!INCLUDE[tsql](../includes/tsql-md.md)] ステートメント同様、CREATE DATABASE ステートメントには、必須パラメーターがあります。必須パラメーターはデータベースの名前です。 また、CREATE DATABASE には、データベース ファイルを配置するディスクの場所など、多くのオプションのパラメーターがあります。 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] でオプション パラメーターを指定せずに CREATE DATABASE を実行すると、これらの多くのパラメーターでは既定の値が使用されます。 このチュートリアルでは、オプションの構文パラメーターをほとんど使用しません。  
  
### <a name="to-create-a-database"></a>データベースを作成するには  
  
1.  クエリ エディターのウィンドウで、次のコードを入力します。ただし実行しないでください。  
  
    ```  
    CREATE DATABASE TestData  
    GO  
    ```  
  
2.  ポインターを使用して `CREATE DATABASE`の語句を選択し、 **F1**キーを押します。 SQL Server オンライン ブックの CREATE DATABASE のトピックが開きます。 この方法を使用して、このチュートリアルで使用する CREATE DATABASE やその他のステートメントの全構文を見つけることができます。  
  
3.  クエリ エディターで、 **F5** キーを押してステートメントを実行し、 `TestData`という名前のデータベースを作成します。  
  
 データベースを作成すると、 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] によって **モデル** データベースのコピーが作成され、その名前がデータベース名に変更されます。 オプション パラメーターでデータベースに大きな初期サイズを指定しなければ、この操作は数秒で完了します。  
  
> [!NOTE]  
>  GO キーワードは、複数のステートメントを単一のバッチで送信した場合に、ステートメントを区切ります。 GO は、バッチにステートメントが 1 つしか入っていない場合はオプションです。  
  
## <a name="next-task-in-lesson"></a>このレッスンの次の作業  
 [テーブルを作成する&#40;チュートリアル&#41;](lesson-1-2-creating-a-table.md)  
  
## <a name="see-also"></a>参照  
 [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
  