---
title: AppendChunk メソッド (ADO) |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Parameter::AppendChunk
- Field20::AppendChunk
helpviewer_keywords:
- AppendChunk method [ADO]
ms.assetid: c648b5a8-d4f1-4d16-836e-3957feb03617
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 4ac0174a223571e29973ad854f9350a6e60f1de9
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47812000"
---
# <a name="appendchunk-method-ado"></a>AppendChunk メソッド (ADO)
大きなテキストまたはバイナリ データにデータを追加します。[フィールド](../../../ado/reference/ado-api/field-object.md)、または、[パラメーター](../../../ado/reference/ado-api/parameter-object.md)オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
  
object.AppendChunk Data  
```  
  
#### <a name="parameters"></a>パラメーター  
 *object*  
 A**フィールド**または**パラメーター**オブジェクト。  
  
 *データ*  
 A**バリアント**オブジェクトに追加するデータを格納しています。  
  
## <a name="remarks"></a>コメント  
 使用して、 **AppendChunk**メソッドを**フィールド**または**パラメーター**と時間の長いバイナリまたは文字のデータの挿入するオブジェクト。 システム メモリが限られている状況で使用することができます、 **AppendChunk**全体ではなく、特定の部分で長い値を操作するメソッド。  
  
## <a name="field"></a>フィールド  
 場合、 **adFldLong**ビット、[属性](../../../ado/reference/ado-api/attributes-property-ado.md)のプロパティを**フィールド**にオブジェクトが設定されている**true**、使用することができます、 **AppendChunk**そのフィールドのメソッド。  
  
 最初の**AppendChunk**を呼び出す、**フィールド**既存のデータを上書きするオブジェクトは、フィールドにデータを書き込みます。 その後**AppendChunk**呼び出しは、既存のデータに追加します。 場合 1 つのフィールドにデータを追加して、設定したり、現在のレコードの別のフィールドの値を読み取る、ADO では、最初のフィールドにデータを追加操作が完了している前提としています。 呼び出す場合、 **AppendChunk**最初のフィールド、ADO メソッドは、新しい呼び出しを解釈**AppendChunk**操作し、既存のデータを上書きします。 他のフィールドへのアクセス[レコード セット](../../../ado/reference/ado-api/recordset-object-ado.md)最初のクローンではないオブジェクトを**Recordset**オブジェクトを妨害しない**AppendChunk**操作。  
  
 呼び出すと、現在のレコードがない場合**AppendChunk**上、**フィールド**オブジェクト、エラーが発生します。  
  
> [!NOTE]
>  **AppendChunk**についてメソッドは動作しません**フィールド**のオブジェクトを[レコード オブジェクト (ADO)](../../../ado/reference/ado-api/record-object-ado.md)オブジェクト。 操作は実行しないと、実行時エラーが生成されます。  
  
## <a name="parameter"></a>パラメーター  
 場合、 **adParamLong**ビット、**属性**のプロパティを**パラメーター**にオブジェクトが設定されている**true**、使用することができます、 **AppendChunk**メソッド パラメーターにします。  
  
 最初の**AppendChunk**を呼び出す、**パラメーター**の既存のデータを上書きするオブジェクトをパラメーターにデータを書き込みます。 後続**AppendChunk**で呼び出し、**パラメーター**オブジェクトは、既存のパラメーターのデータを追加します。 **AppendChunk**パラメーター データのすべて null 値が渡された呼び出しが破棄されます。  
  
## <a name="applies-to"></a>適用対象  
  
|||  
|-|-|  
|[Field オブジェクト](../../../ado/reference/ado-api/field-object.md)|[Parameter オブジェクト](../../../ado/reference/ado-api/parameter-object.md)|  
  
## <a name="see-also"></a>参照  
 [AppendChunk および GetChunk メソッドの例 (VB)](../../../ado/reference/ado-api/appendchunk-and-getchunk-methods-example-vb.md)   
 [AppendChunk および GetChunk メソッドの例 (vc++)](../../../ado/reference/ado-api/appendchunk-and-getchunk-methods-example-vc.md)   
 [Attributes プロパティ (ADO)](../../../ado/reference/ado-api/attributes-property-ado.md)   
 [GetChunk メソッド (ADO)](../../../ado/reference/ado-api/getchunk-method-ado.md)
