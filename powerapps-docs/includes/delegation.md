---
ms.openlocfilehash: d74254f2536b78a0951c860d803519827d31e446
ms.sourcegitcommit: dd2a8a0362a8e1b64a1dac7b9f98d43da8d0bd87
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2019
ms.locfileid: "74678272"
---
## <a name="delegation"></a>委任
可能な場合、Power Apps はフィルター操作と並べ替え操作をデータソースに委任し、要求に応じて結果をページに表示します。 たとえば、データが入力された **[ギャラリー](../maker/canvas-apps/controls/control-gallery.md)** コントロールが表示されるアプリを起動すると、最初に先頭のレコード セットだけがデバイスに取り込まれます。 ユーザーがスクロールすると、データ ソースから追加のデータが取得されます。 その結果、アプリの起動が速くなり、非常に大規模なデータ セットにすばやくアクセスできます。

ただし、常に委任できるとは限りません。 委任をサポートしている関数と演算子は、データ ソースによって異なります。 数式の完全委任が不可能な場合は、作成時に、委任できない部分に警告が表示されます。 可能であれば、数式を変更して、委任できない関数や演算子を使用しないようにすることを検討してください。  [委任の一覧](../maker/canvas-apps/delegation-list.md)には、委任できるデータ ソースと操作の詳細が記載されています。

委任が不可能な場合、Power Apps は、少数のレコードだけを取得してローカルで作業します。 フィルター関数と並べ替え関数は、削減されたレコード セットを操作します。 **[ギャラリー](../maker/canvas-apps/controls/control-gallery.md)** で使用できるデータが完全でないため、ユーザーが混乱する可能性があります。 

詳細については、[委任の概要](../maker/canvas-apps/delegation-overview.md)に関する記事を参照してください。

