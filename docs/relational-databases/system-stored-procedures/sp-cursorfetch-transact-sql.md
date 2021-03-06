---
title: sp_cursorfetch (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_cursorfetch
- sp_cursorfetch_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_cursorfetch
ms.assetid: 14513c5e-5774-4e4c-92e1-75cd6985b6a3
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 43cf13284789fa599c3f2f7b8841d7fe54e3b2e7
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47732127"
---
# <a name="spcursorfetch-transact-sql"></a>sp_cursorfetch (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  データベースから 1 つ以上の行のバッファーをフェッチします。 このバッファー内の行のグループは、カーソルのと呼ばれる*フェッチ バッファー*します。 sp_cursorfetch は、ID を指定して呼び出される、表形式のデータ ストリーム (TDS) パケットで 7 を = です。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sp_cursorfetch cursor  
    [ , fetchtype[ , rownum [ , nrows] ]]   
```  
  
## <a name="arguments"></a>引数  
 *カーソル (cursor)*  
 *処理*によって生成される値[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]sp_cursoropen から返されるとします。 *カーソル*が必要なパラメーターです、 **int**値を入力します。 詳細については、このトピックの後半の「解説」を参照してください。  
  
 *fetchtype*  
 フェッチするカーソル バッファーを指定します。 *fetchtype*省略可能なパラメーターで、次の整数入力値のいずれかが必要です。  
  
|値|名前|説明|  
|-----------|----------|-----------------|  
|0x0001|FIRST|最初のバッファーをフェッチ*nrows*行。 場合*nrows*が 0 と等しい、カーソルが結果セットの前に、行は返されません。|  
|0x0002|NEXT|次のバッファーをフェッチ*nrows*行。|  
|0x0004|PREV|以前のバッファーをフェッチ*nrows*行。<br /><br /> 注: は、FORWARD_ONLY がのみ 1 つの方向のスクロールをサポートしているために、エラー メッセージを返します、FORWARD_ONLY カーソルに対して PREV を使用します。|  
|0x0008|LAST|最後のバッファーをフェッチ*nrows*行。 場合*nrows*が 0 と等しい、カーソルが結果セットし、行は返されません。<br /><br /> 注: は、FORWARD_ONLY がのみ 1 つの方向のスクロールをサポートしているために、エラー メッセージを返します、FORWARD_ONLY カーソルに対して LAST を使用します。|  
|0x10|ABSOLUTE|バッファーをフェッチ*nrows*で始まる行、 *rownum*行。<br /><br /> 注: は、FORWARD_ONLY がのみ 1 つの方向のスクロールをサポートしているために、エラー メッセージを返します、動的カーソルまたは FORWARD_ONLY カーソルに対して ABSOLUTE を使用します。|  
|0x20|RELATIVE|バッファーをフェッチ*nrows*として指定されている行で始まる行、 *rownum*現在のブロックの最初の行からの行の値。 ここで*rownum*負の数を指定できます。<br /><br /> 注: は、FORWARD_ONLY がのみ 1 つの方向のスクロールをサポートしているために、エラー メッセージを返します、FORWARD_ONLY カーソルに対して RELATIVE を使用します。|  
|0x80|REFRESH|基になるテーブルのデータをバッファーに再読み込みします。|  
|0x100|INFO|カーソルについての情報を取得します。 使用してこの情報が返されます、 *rownum*と*nrows*パラメーター。 そのため、情報を指定した場合、 *rownum*と*nrows*出力パラメーターになります。|  
|0x200|PREV_NOADJUST|PREV と同じように使用されます。 ただし、途中で結果セットの先頭に到達した場合に結果が変わる可能性があります。|  
|0x400|SKIP_UPDT_CNCY|その他のいずれかで使用する必要があります*fetchtype* INFO 以外の値。|  
  
> [!NOTE]  
>  値 0x40 はサポートされていません。  
  
 詳細については、このトピックの後半の「解説」を参照してください。  
  
 *rownum*  
 ABSOLUTE または INFO の行の位置を指定するために使用するオプションのパラメーターは、 *fetchtype*入力または出力、あるいはその両方の整数値のみを使用して値。 *rownum*行オフセットとして機能、 *fetchtype*ビット値が RELATIVE です。 *rownum*の他のすべての値は無視されます。 詳細については、このトピックの後半の「解説」を参照してください。  
  
 *nrows*  
 フェッチする行数を指定するために使用される省略可能なパラメーターです。 場合*nrows*が指定されていない、既定値は 20 行です。 データを返さずに位置を設定するには、値 0 を指定します。 ときに*nrows*に適用される、 *fetchtype* INFO であるクエリ、そのクエリで行の合計数を返しますにします。  
  
> [!NOTE]  
>  *nrows*更新では無視されて*fetchtype*ビット値。  
>   
>  詳細については、このトピックの後半の「解説」を参照してください。  
  
## <a name="return-code-values"></a>リターン コードの値  
 ビット値 INFO を指定した場合の戻り値を次の表に示します。  
  
> [!NOTE]  
>  行が返されない場合と同様に、バッファーの内容が残ります。  
  
|*\<rownum >*|を設定します。|  
|------------------|------------|  
|開いていない場合|0|  
|結果セットより前の場合|0|  
|結果セットより後ろの場合|-1|  
|KEYSET カーソルおよび STATIC カーソルの場合|結果セット内の現在位置の絶対行番号。|  
|DYNAMIC カーソルの場合|1|  
|ABSOLUTE の場合|-1 を指定すると、セット内の最後の行が返されます。<br /><br /> -2 を指定すると、セット内の最後から 2 番目の行が返されます (以降、同様に続きます)。<br /><br /> 注: ここでフェッチする 1 つ以上の行が要求された場合、結果セットの最後の 2 つの行が返されます。|  
  
|*\<nrows >*|を設定します。|  
|-----------------|------------|  
|開いていない場合|0|  
|KEYSET カーソルおよび STATIC カーソルの場合|通常は現在のキーセットのサイズ。<br /><br /> **– m**カーソルが非同期に作成される場合*m*行には、このポイントが見つかりませんでした。|  
|DYNAMIC カーソルの場合|-1|  
  
## <a name="remarks"></a>コメント  
  
## <a name="cursor-parameter"></a>cursor パラメーター  
 フェッチ操作がまだ一度も行われていないときのカーソルの既定の位置は、結果セットの最初の行の前です。  
  
## <a name="fetchtype-parameter"></a>fetchtype パラメーター  
 Skip_upd_cncy を除き、 *fetchtype*値は相互に排他的です。  
  
 SKIP_UPDT_CNCY を指定すると、行がフェッチまたは更新されるときに timestamp 列の値が keyset テーブルに書き込まれません。 行が更新された場合は timestamp 列の値が前の値のままになり、 行が挿入された場合は timestamp 列の値が未定義になります。  
  
 その結果、KEYSET カーソルでは、keyset テーブルの値が、前回通常の FETCH が実行されたときに設定された値か (通常の FETCH が実行されている場合)、 作成時に設定された値になります (通常の FETCH が実行されていない場合)。  
  
 DYNAMIC カーソルでは、REFRESH でスキップが行われる場合には KEYSET と同じ結果になりますが、 その他の fetchtype では keyset テーブルが切り捨てられます  (行が挿入され、timestamp 列の値が未定義になります)。 このため、DYNAMIC カーソルで sp_cursorfetch を実行する際には、REFRESH 以外の操作に対して SKIP_UPDT_CNCY を使用しないようにしてください。  
  
 要求したカーソル位置が結果セットの範囲を超えていたためにフェッチ操作が失敗した場合は、カーソル位置が最後の行の直後に設定されます。 要求したカーソル位置が結果セットより前だったためにフェッチ操作が失敗した場合は、カーソル位置が最初の行の前に設定されます。  
  
## <a name="rownum-parameter"></a>rownum パラメーター  
 使用すると*rownum*、指定した行で始まる、バッファーを入力します。  
  
 *Fetchtype*値の位置を指す絶対*rownum*全体の結果内で設定します。 ABSOLUTE で負の値を指定すると、結果セットの末尾から行がカウントされます。  
  
 *Fetchtype*値が相対の位置を指す*rownum*現在のバッファーの先頭にカーソルの位置に関連します。 RELATIVE で負の値を指定すると、カーソルが現在のカーソル位置から後方に移動します。  
  
## <a name="nrows-parameter"></a>nrows パラメーター  
 *Fetchtype* REFRESH および INFO の値は、このパラメーターを無視します。  
  
 指定すると、 *fetchtype*を持つ最初の値、 *nrow*値 0、カーソルがフェッチ バッファー内の行を持たない結果セットの前に配置されます。  
  
 指定すると、 *fetchtype*を持つ最後の値、 *nrow* 0 の場合、カーソルの値が現在のフェッチ バッファー内の行を持たない結果セットの後に配置します。  
  
 *Fetchtype*次へ、PREV、ABSOLUTE、RELATIVE、および PREV_NOADJUST では、値、 *nrow* 0 の値が無効です。  
  
## <a name="rpc-considerations"></a>RPC に関する考慮事項  
 RPC の戻りステータスでは、キーセット サイズのパラメーターが final かどうか (keyset テーブル (一時テーブル) が非同期に作成されるかどうか) が示されます。  
  
 RPC 状態パラメーターは、次のいずれかの値に設定されます。  
  
|値|Description|  
|-----------|-----------------|  
|0|プロシージャが正常に実行されました。|  
|0x0001|プロシージャは失敗しました。|  
|0x0002|負の方向のフェッチにより、カーソル位置が結果セットの先頭に設定されました (論理的には、結果セットの前でフェッチが行われるはずでした)。|  
|0x10|高速順方向カーソルが自動的に閉じられました。|  
  
 行は、通常の結果セットとして返されます (列の形式 (0x2a)、行 (0xd1)、完了 (0xfd))。 メタデータ トークンは、sp_cursoropen に指定したのと同じ形式で送信されます (SQL Server 7.0 ユーザーの場合は 0x81、0xa5、および 0xa4 など)。 行の状態インジケーターは、ブラウズ モードのように、各行の末尾の非表示の列として送信されます (列名は rowstat、データ型は INT4)。 この rowstat 列には、次のいずれかの値が含まれます。  
  
|値|説明|  
|-----------|-----------------|  
|0x0001|FETCH_SUCCEEDED|  
|0x0002|FETCH_MISSING|  
  
 TDS プロトコルでは、前の列を送信せずに末尾の状態列だけを送信することはできないため、欠けている行に対してはダミー データが送信されます (NULL 値許容フィールドは NULL に設定され、固定長フィールドは 0、空白、または列の既定値に設定されます)。  
  
 DONE rowcount 常に 0 になります。 DONE メッセージに結果セットの実際の行数が含まれます。TDS メッセージの間にエラー メッセージや情報メッセージが表示される場合もあります。  
  
 カーソルの選択リストに関するメタデータを TDS ストリームで返すように要求するには、RPC の RETURN_METADATA 入力フラグを 1 に設定します。  
  
## <a name="examples"></a>使用例  
  
### <a name="a-using-prev-to-change-a-cursor-position"></a>A. PREV を使用してカーソル位置を変更する  
 カーソル h2 で、次の内容を含む結果セットが生成されるとします。current position は現在の位置を示します。  
  
```  
row 1 contents      
row 2 contents  
row 3 contents  
row 4 contents  <-- current position  
row 5 contents   
row 6 contents  
```  
  
 次に、sp_cursorfetch PREV を持つ、 *nrows*結果セットの最初の行の前に 2 つのカーソルの行を位置は論理的に 5 の値。 このような場合、カーソルが最初の行で開始されるように調整されて、要求した数の行が返されます。 その結果、通常は、前のフェッチ バッファーに含まれていた行が返されることになります。  
  
> [!NOTE]  
>  これは、RPC 状態パラメーターが 2 に設定される典型的な例です。  
  
### <a name="b-using-prevnoadjust-to-return-fewer-rows-than-prev"></a>B. PREV_NOADJUST を使用して PREV より少ない行を返す  
 PREV_NOADJUST では、返される行のブロックに現在のカーソル位置以降の行が含まれることはありません。 PREV が現在の位置より後に行を返す場合、PREV_NOADJUST に行数で要求されたより少なくなりますが返されます*nrows*します。 現在位置の例に、以前のバージョンを PREV を適用した場合、sp_cursorfetch (h2, 4, 1, 5)、次の行がフェッチされます。  
  
```  
row1 contents   
row2 contents  
row3 contents  
row4 contents  
row5 contents  
```  
  
 ただし、PREV_NOADJUST を適用した場合、sp_cursorfetch (h2, 512, 6, 5) 次の行のみがフェッチされます。  
  
```  
row1 contents   
row2 contents  
row3 contents   
```  
  
## <a name="see-also"></a>参照  
 [sp_cursoropen &#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/sp-cursoropen-transact-sql.md)   
 [システム ストアド プロシージャ &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
