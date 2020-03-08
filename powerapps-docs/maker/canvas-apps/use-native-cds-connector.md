---
title: ネイティブ Common Data Service コネクタを使用するためのアップグレード |Microsoft Docs
description: ''
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/03/2020
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: e77bf1304ac7d1083348dce18d7d78189dfef306
ms.sourcegitcommit: 56c8c7cc64695ccb00e0d021c9f98cf70b69b4a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78845378"
---
# <a name="common-data-service-and-the-improved-data-source-experience"></a>Common Data Service と強化されたデータソースエクスペリエンス

## <a name="overview"></a>概要

2019年11月より前に Common Data Service コネクタでキャンバスアプリを作成した場合、最新バージョンの Common Data Service の利点が得られない可能性があります。 

**データソースエクスペリエンスの向上** オプションと ビューの Common Data Service オプションには、次の利点があります。

1. 速度が大幅に向上します。
2. 信頼性の向上。
3. Common Data Service**ビュー** 、**ファイルおよびイメージのフィールド属性**へのアクセス。

詳細設定] セクションに、 **[データソースエクスペリエンスの向上]** オプションと [ビューの Common Data Service オプションが表示されます。

![データソースエクスペリエンスの向上とビューの Common Data Service](media/use-native-cds-connector/improved-data-source-setting.png)

[非推奨の機能] セクションに、 **Common Data Service のリレーショナルデータ、オプションセット、およびその他の新機能**が表示されるようになりました。

## <a name="how-do-i-upgrade"></a>操作方法アップグレードしますか?

次の手順に従って、機能の設定を調べてアプリをアップグレードします。

### <a name="improve-data-source-experience-and-common-data-service-views-is-on"></a>*データソースのエクスペリエンスを向上させ、Common Data Service ビュー*をオンにします。

この機能を使用するようにキャンバスアプリを既に変換したか、またはこの機能に対して *[オン*] の既定の設定を使用してアプリを開始しました。 これ以上の操作は必要ありません。 

また、**明示的な列の選択**機能を有効にすることもできます。

![明示的な列の選択](media/use-native-cds-connector/explicit-column-selection.png)

> [!NOTE]
> [Windows 用 Power Apps](https://www.microsoft.com/p/power-apps/9nblggh5z8f3)では **、データソースエクスペリエンスの向上と Common Data Service ビュー**はサポートされていません。 Windows 用の Power Apps を使用する場合は、この機能を*オフ*にする必要があります。

### <a name="relational-data-option-sets-and-other-new-features-for-common-data-service-is-off"></a>*リレーショナルデータ、オプションセット、および Common Data Service のその他の新機能は、次の*とおりです。

[*詳細設定*] の [*非推奨の機能*] をオンにします。  *Off*に設定されている場合は、変換の最初の手順として次の手順に進みます。 

> [!IMPORTANT]
> *[詳細設定*] で**Common Data Service のリレーショナルデータ、オプションセット、およびその他の新機能**が表示されない場合、または既*にオンに*なっている場合は、次の手順をスキップして[次のセクション](#improve-data-source-experience-and-common-data-service-views-is-off)に進みます。

- **手順 1**: [**表示名を使用**する] 機能**を有効に**する:
    
    1. [**表示名を使用**する] 機能*を*有効にします。
    1. ヘルスモニターがアプリの分析を完了するまで待ちます。
    1. アプリを保存して閉じ、再度開きます。
    1. すべての数式エラーを解決します。
    1. アプリを保存して閉じ、再度開きます。
    
    *考えられるエラーと提案*:
    
    新しく表示された表示名の一部が、他のエンティティ、フィールド、またはコントロールの表示名と競合する可能性があります。 たとえば、同じ名前のコントロールとフィールドがあるとします。 コントロールの名前を変更して、一意の値を修正することができます。
    
    フィールドとエンティティの表示名が競合している場合は、エンティティを予期していますが、ローカルスコープのフィールド名に解決される数式が表示されることがあります。

    エンティティに解決されるようにグローバルスコープを示すには、角かっこを **@** 記号と共に使用します。たとえば、 **[@entityName]** のようになります。
    
    
- **手順 2**: **Common Data Service のリレーショナルデータ、オプションセット、およびその他の新機能**を有効にし、の文字列**機能で**は**なく GUID データ型を使用**します。
    
    1. の**Common Data Service 機能のリレーショナルデータ、オプションセット、およびその他の新機能**を有効*にします。*
    1. で**は、文字列の代わりに GUID データ型を使用**する機能*を*有効にします。
    1. ヘルスモニターがアプリの分析を完了するまで待ちます。
    1. すべての数式エラーを解決します。
    1. アプリを保存して閉じ、再度開きます。  
    
    *考えられるエラーと提案*:
    
    オプションセットフィールドまたはハードコーディングされた GUID テキスト値を使用している場合、この段階でエラーが発生する可能性があります。  <br><br> 
    
    - *オプションの設定*値: オプションセットの値に対してテキスト識別子を持つオプションセットフィールドを使用する場合は、代わりにドット表記を使用して、オプションセットの値を参照します。 たとえば、`Patch(Accounts, OptionSet1 = “12345”)` を `Patch(Accounts, OptionSet.Item1)` に変更し、`Item1` が `12345` 値に対応するようにします。 <br>
    詳細については、「[詳細な例](#detailed-examples)」を参照してください。
    - *Guid*: `015e45e1044e49f388115be07f2ee116`などの静的 GUID 文字列を使用している場合は、guid オブジェクトを返す関数に変換します。たとえば、`GUID(“015e45e1044e49f388115be07f2ee116”)`です。 
    - *参照*: 参照関数を使用して `Lookup(Contacts, ‘contactID’ = ThisItem.ContactID”)`などの最初のレベルの参照値を取得する場合は、代わりに `ThisItem.PrimaryContacts` (primarycontacts がエンティティの名前) を使用することを検討してください。

### <a name="improve-data-source-experience-and-common-data-service-views-is-off"></a>*データソースのエクスペリエンスを向上させ、Common Data Service ビュー*をオフにします。

次の手順に従って、の**データソースエクスペリエンスと Common Data Service ビュー**機能*の*向上を有効にします。

1. 既存の Common Data Service のデータソース接続を削除します。 
1. **[データソースエクスペリエンスの向上とビューの Common Data Service]** 機能*を*オンにします。
1. 新しいデータソースの選択エクスペリエンスを使用して、Common Data Service 接続を追加します。
1. アプリケーションを保存します。

> [!NOTE]
> アプリケーションのサイズが非常に大きい場合、データソースの接続を追加し直すと、しばらく時間がかかることがあります。 このプロセス中はアプリケーションを閉じないでください。

## <a name="converting-canvas-apps-with-the-dynamics-365-connector"></a>Dynamics 365 コネクタを使用したキャンバスアプリの変換

Dynamics 365 コネクタを使用するアプリを変換するには、データソースへの接続を削除して追加する必要があります。 接続をデータソースに変換するには、次の手順を使用します。

1. **データソースエクスペリエンスの向上と Common Data Service ビュー**機能が有効*に*なっていることを確認します。
2. 既存の Dynamics 365 データソース接続を削除します。
3. 新しいデータソースの選択エクスペリエンスを使用して、データソースへの接続を Common Data Service に追加します。 

    > [!NOTE] 
    > (現在以外の) 他の環境に接続している場合は、[*エンティティ*] カテゴリを選択し、[ *More* (...)] オプションを選択して環境を変更します。 次に、別の環境からエンティティを選択して、アプリケーションに追加できます。 クロステナント接続は、強化されたネイティブコネクタでは機能しません。 データのクロステナントにアクセスするには、データ統合を使用する必要があります。
4.  アプリケーションを保存します。

*考えられるエラーと提案*:

表示名を使用していない場合、GUID 文字列を使用している場合、またはオプションセットのフィールドを使用している場合は、変換時にエラーが発生する可能性があります。

- コントロール名が競合する場合は、コントロールの名前を異なる一意の名前に変更します。 
- フィールドとエンティティの表示名が競合している場合は、エンティティを予期しているものの、よりローカルにスコープが設定されたフィールド名に解決している数式が表示されることがあります。 エンティティに解決されるようにグローバルスコープを示すには、角かっこを *@* 記号と共に使用します。たとえば、 **[@entityName]** のようになります。
- *オプションの設定*値: オプションセットの値に対してテキスト識別子を持つオプションセットフィールドを使用する場合は、代わりにドット表記を使用して、オプションセットの値を参照します。 たとえば、`Patch(Accounts, OptionSet1 = “12345”)` を `Patch(Accounts, OptionSet.Item1)` に変更し、`Item1` が `12345` 値に対応するようにします。 <br>
詳細については、「[詳細な例](#detailed-examples)」を参照してください。
- *Guid*: `015e45e1044e49f388115be07f2ee116`などの静的 GUID 文字列を使用している場合は、guid オブジェクトを返す関数に変換します。たとえば、`GUID(“015e45e1044e49f388115be07f2ee116”)`です。 
- *参照*: `Lookup(Contacts, ‘contactID’ = ThisItem.ContactID”)`などの最初のレベルの参照値を取得するために参照関数を使用する場合は、代わりに `ThisItem.PrimaryContacts` (primarycontacts がエンティティの名前) を使用することを検討してください。
- ポリモーフィックな参照については、以下の「詳細な例」のセクションを参照してください。 

## <a name="detailed-examples"></a>詳細な例

新しい**オプションセット**と**2 つのオプション**のデータ型を使用するようにアプリケーションを変換することは、新しい強化された*データソースエクスペリエンスと Common Data Service ビュー*機能を使用するようにアプリをアップグレードする際には困難な場合があります。

### <a name="option-sets"></a>オプションセット

前のオプションセットには、`_myfield` フィールドと `_myfield_label` フィールドが個別に使用されていました。 ここでは、ロケールに依存しない比較とロケール固有のラベルを取得するために使用できる1つの `myfield` があります。

#### <a name="removing-and-adding-option-set-data-cards"></a>オプションセットデータカードの削除と追加

既存のデータカードを削除して、オプションセットを操作できるように戻すことをお勧めします。 たとえば、Account エンティティと Category オプションを設定して作業している場合、データカードの*DataField*プロパティが `_accountcategorycode_label`に設定されていることがわかります。 データカードの種類が*文字列*であることが、フィールドの一覧に表示されます。

![古いスタイル名を使用した OptionSet](./media/use-native-cds-connector/OptionSet-with-old-style-name.png)

新しい強化された*データソースエクスペリエンスと Common Data Service ビュー*機能により、`_accountcategorycode_label`が表示されなくなりました。 `accountcategorycode`に置き換えられます。 これで、カードは**カスタム**としてマークされるようになり、エラーが表示されます。 古いデータカードを削除し、*オプションセット*を再び追加します。 新しいデータカードは、*オプションセット*を認識するように設定されています。

![古いスタイル名を使用した OptionSet](./media/use-native-cds-connector/OptionSet-with-new-style-name.png)

#### <a name="editing-the-option-set-filter-expressions-to-use-new-syntax"></a>新しい構文を使用するようにオプションセットのフィルター式を編集する

以前は、フィルター式でオプションセットの値を使用する場合は、[*値*] フィールドを使用する必要がありました。 例 :

```powerapps-dot
Filter(Account,'Category Value' = "1")
```

この数式を編集する必要があります。 オプションセットのテキスト識別子は、値に使用されなくなりました。 この式は、次のように更新する必要があります。

```powerapps-dot
Filter(Account, Category= ‘Category (Accounts)’.’Preferred Customer’)
```

' Category (Accounts) ' は、Accounts エンティティの Category フィールドで使用される列挙型の名前です。 これはローカルオプションセットです。  ローカルオプションセットとグローバルオプションセットの詳細については、「[グローバルオプションセット」](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-global-option-sets)を参照してください。

#### <a name="editing-option-set-patch-statements-to-use-new-syntax"></a>新しい構文を使用するためのオプション Set Patch ステートメントの編集

次に、オプションセットの前の Patch ステートメントの例を示します。

```powerapps-dot
Patch( Accounts, First(Accounts), { ‘Category Value’: 1 } ) )
```

次の形式に従ってステートメントを更新する必要があります。

```powerapps-dot
Patch( Accounts, First(Accounts), { Category: ‘Category (Accounts)’.’Preferred Customer’ } )
```

#### <a name="option-set-disambiguation"></a>オプションセットのあいまいを解消する

オプションセット**フィールド**の表示名とオプションセットの名前が同じ場合は、その数式を明確にする必要があります。 アカウントカテゴリコードの例を引き続き使用するために、 **@** はフィールドではなく、オプションセットを使用することを意味します。

```powerapps-dot
Filter(Accounts, 'Category Code' = [@’Category Code’].'Preferred Customer')
```

### <a name="two-options"></a>2 つのオプション

#### <a name="removing-and-adding-two-option-set-data-cards"></a>2つのオプションセットデータカードの削除と追加

2つのオプションセットを使用するには、既存のデータカードを削除してからもう一度追加する必要があります。 データ型は、前の例のように単純なブール値として認識されていました。たとえば、true/on、false/off はラベルがありません。

![2つのオプションセット-old スタイル](./media/use-native-cds-connector/TwoOptionSet-Old.png)

新しい改良された*データソースエクスペリエンスと Common Data Service ビュー*機能により、カードは**カスタム**としてマークされるようになり、エラーが表示されます。  古いデータカードを削除し、オプションセットを再び追加します。 を追加すると、既定で2つのオプションを含むエディットコントロールが表示されます。

![TwoOptionSet-新規](./media/use-native-cds-connector/TwoOptionSet-New.png)

ブール値フィールドのトグルスイッチを使用する場合は、データカードのロックを解除し、データカード内のコントロールを代わりに切り替えることができます。  また、トグルでこれらのプロパティを設定する必要があります。

```powerapps-dot
Toggle1.Default = ThisItem.’Do not allow Bulk Emails’
Toggle1.TrueText = ‘Do not allow Bulk Emails (Accounts)’.’Do Not Allow’
Toggle1.FalseText = ‘Do not allow Bulk Emails (Accounts)’.Allow
DataCard.Value = If( Toggle1.Value,
    ‘Do not allow Bulk Emails (Accounts)’.’Do Not Allow’,
    ‘Do not allow Bulk Emails (Accounts)’.Allow )
```

![2つのオプションの切り替えスイッチ](./media/use-native-cds-connector/TwoOption-Toggle.png)

#### <a name="refining-two-option-patch-statements"></a>2つの Option Patch ステートメントの再設定

[Patch](./functions/function-patch.md)関数を2つのオプションと共に使用する場合は、' as ' として機能します。 ブール型と同様に、true と false の直接使用をサポートしています。 唯一の違いは、前に true と false を示したラベルコントロールに値を配置した場合です。2つのオプションラベルが表示されるようになります。

### <a name="polymorphic-lookups"></a>ポリモーフィック参照

次のガイドラインは、[ポリモーフィック](working-with-references.md)フィールドを参照している場合にアプリケーションをアップグレードするのに役立ちます。 同じフィールドからのポリモーフィックな参照では、複数のエンティティの制限付きセットへの参照がサポートされます。  他の言語の参照と同様に、レコード参照は特定のエンティティ内の特定のレコードへのポインターです。 レコード参照は、エンティティ情報を使用して、複数の異なるエンティティ内のレコードを指すことができます。これは、1つのエンティティ内のレコードのみを指す通常の参照とは異なります。  

#### <a name="access-set-and-filter-on-the-owner-field-of-a-record"></a>レコードの Owner フィールドに対するアクセス、設定、およびフィルター処理

たとえば、エンティティの Owner フィールドは、Users エンティティまたは Teams エンティティ内のレコードを参照できます。 異なるレコードの同じルックアップフィールドが、異なるエンティティ内のレコードを参照している可能性があります。
 
![ポリモーフィック所有者フィールド](./media/use-native-cds-connector/Polymorphic1.png)
 
##### <a name="polymorphic-with-filter-and-patch"></a>フィルターとパッチを使用したポリモーフィック

レコード参照は、完全なレコードと同じように使用できます。

```powerapps-dot
Filter( Accounts, Owner = First( Teams ) )
Patch( Accounts, First( Accounts ), { Owner: First( Users ) })
```

##### <a name="polymorphic-with-a-gallery-displaying-owner-name"></a>所有者名を表示するギャラリーを含むポリモーフィック

参照は異なるエンティティを指すことがあるため、固有のものである必要があります。 **ThisItem.Owner.Name**を使用することはできません。これは、**チーム**エンティティの 名前 フィールドが **チーム名** で、**ユーザー**エンティティの 名前 フィールドが **フルネーム** であるためです。 アプリを実行するまで、お客様が参照している検索の種類は、Power Apps によって認識されません。

この問題を修正するには、次の操作を行います。 

1. 所有者として使用できるエンティティ型のデータソースを追加します。現在の例では、ユーザーとチーム)。
2. 目的を明確にするために、追加の関数を使用します。

次の2つの新しい関数を使用できます。

- IsType –レコード参照が特定のエンティティ型であるかどうかを確認します。
- AsType: レコード参照を特定のエンティティ型にキャストします。

これらの関数を使用すると、所有者のエンティティ型に基づいて、2つの異なる名前付きフィールドから取得した所有者の名前を表示する数式を作成できます。

```powerapps-dot
If( IsType( ThisItem.Owner,  [@Teams]), 
    AsType( ThisItem.Owner, [@Teams]).'Team Name', 
    AsType( ThisItem.Owner, [@Users]).'Full Name' )
```

![型としてのギャラリー](./media/use-native-cds-connector/Polymorphic-And-AsType-in-Gallery.png)

グローバルエンティティ型を参照するために、`[@Teams]` と `[@Users]` のグローバルなあいまいさを排除する演算子を使用します。 ただし、この場合は必要ありませんが、常に明確にすることをお勧めします。 1対多のリレーションシップは、多くの場合、ギャラリーのレコードのスコープ内で競合するため、混乱を避けることができます。
 
#### <a name="access-and-set-the-company-name-field-a-customer-data-type-of-the-contacts-entity"></a>連絡先エンティティの会社名フィールド (顧客データ型) にアクセスして設定する

顧客参照フィールドは、所有者に似た別のポリモーフィックなルックアップです。 エンティティごとに所有者フィールドを1つだけ設定できます。 ただし、エンティティには、0、1、または複数の顧客参照フィールドを含めることができます。 Contacts システムエンティティには、顧客参照フィールドである "会社名" フィールドが含まれています。 詳細については[、「顧客のフィールドを表示する](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-references#show-the-fields-of-a-customer)」を参照してください。
 
#### <a name="access-and-set-the-regarding-field-of-activity-entities-such-as-faxes-phone-calls-email-messages"></a>Fax、電話、電子メールメッセージなどのアクティビティエンティティの関連フィールドにアクセスして設定する

ポリモーフィックな参照は、アカウントと連絡先に限定されません。 エンティティの一覧は、カスタムエンティティで拡張できます。 たとえば、Fax エンティティには、アカウント、連絡先、およびその他のエンティティを参照することが可能な、相互に関連するルックアップフィールドがあります。 データソースが Fax に設定されているギャラリーがある場合は、次の式を使用して、[関連する参照] フィールドに関連付けられている名前を表示できます。 
 
 ```powerapps-dot
If( IsBlank( ThisItem.Regarding ), "",
    IsType( ThisItem.Regarding, [@Accounts] ),
        "Account: " & AsType( ThisItem.Regarding, [@Accounts] ).'Account Name',
    IsType( ThisItem.Regarding, [@Contacts] ),
        "Contacts: " & AsType( ThisItem.Regarding, [@Contacts] ).'Full Name',
    "" )
```

![関連するギャラリー](./media/use-native-cds-connector/Polymorphic-With-Regarding.png)
 
詳細については、[参照フィールド](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-references#understand-regarding-lookup-fields)と[リレーションシップ](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-references#understand-regarding-relationships)に関する情報を参照してください。

#### <a name="access-the-list-of-all-activities-for-a-record"></a>レコードのすべてのアクティビティの一覧にアクセスする

Common Data Service では、Fax、タスク、電子メール、メモ、電話、文字、チャットなどのエンティティが[アクティビティ](https://docs.microsoft.com/powerapps/developer/common-data-service/activity-entities)として指定されます。 独自の[カスタムアクティビティエンティティ](https://docs.microsoft.com/powerapps/developer/common-data-service/custom-activities)を作成することもできます。

特定の種類 (Fax や税金など) の活動、または account などのエンティティに関連付けられているすべての活動を表示できます。 キャンバスアプリに表示する予定のデータを持つアクティビティエンティティとその他の個々のエンティティを追加します。

(Tasks エンティティなどの) にレコードを追加するたびに、すべてのアクティビティエンティティに共通するフィールドを持つアクティビティエンティティ内のレコードが作成されます。 詳細については、「[アクティビティエンティティ](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-references#activity-entity)の読み取り」を参照してください。

次の例は、アカウントを選択すると、そのアカウントに関連付けられているすべてのアクティビティが表示されることを示しています。
 
![ポリモーフィックアクティビティ](./media/use-native-cds-connector/Polymorphic-Activities.png) 
 
レコードがアクティビティエンティティから表示されています。 ただし、 [istype](./functions/function-astype-istype.md)関数を使用して、アクティビティの種類を特定することもできます。 ここでも、エンティティ型で IsType 種類を使用する前に、必要なデータソースを追加する必要があります。
 
この数式を使用すると、ギャラリー内のラベルコントロールにレコードの種類を表示できます。

 ```powerapps-dot
If( IsType( ThisItem, [@Faxes] ), "Fax",
    IsType( ThisItem, [@'Phone Calls'] ), "Phone Call",
    IsType( ThisItem, [@'Email Messages'] ), "Email Message",
    IsType( ThisItem, [@Chats] ), "Chat",
    "Unknown")
```

 ![ポリモーフィック-IsType](./media/use-native-cds-connector/Polymorphic-IsType.png)

#### <a name="access-the-list-of-notes-for-a-record"></a>レコードのメモの一覧にアクセスする

エンティティを作成するときに、添付ファイルを有効にすることができます。 添付ファイルを有効にするためのチェックボックスをオンにした場合は、次の図に示すように、Note エンティティとの関連関係を作成します。

![メモ-フィールド](./media/use-native-cds-connector/Notes-Field.png)

##### <a name="filtering"></a>フィルター

[関連] フィールドに基づいて、読み取りやフィルター処理を行うことはできません。 ただし、逆メモの一対多リレーションシップは使用できます。 Account エンティティに関連付けられているすべてのメモを一覧表示するには、次の式を使用します。

```powerapps-dot
First( Accounts ).Notes
```

##### <a name="patch"></a>修正プログラム

Patch を使用してエンティティの [メモ] フィールドを設定することはできません。 エンティティの Notes テーブルにレコードを追加するには、関連付け関数を使用します。 次の例のように、最初にメモを作成します。

```powerapps-dot
Relate( ThisItem.Notes, Patch( Notes, Defaults( Notes ), { Title: "A new note", isdocument:'Is Document (Notes)'.No } ) )
```

## <a name="next-steps"></a>次のステップ:

- [数式のリファレンス](https://docs.microsoft.com/powerapps/maker/canvas-apps/formula-reference)
- [コントロールのリファレンス](https://docs.microsoft.com/powerapps/maker/canvas-apps/reference-properties)

### <a name="see-also"></a>参照

[Common Data Service とは](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
