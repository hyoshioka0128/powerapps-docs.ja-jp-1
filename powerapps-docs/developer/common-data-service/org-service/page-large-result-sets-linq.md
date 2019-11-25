---
title: LINQ による大量の結果セットのページング (Common Data Service) | Microsoft Docs
description: Take および Skip 演算子を使用して大規模な .NET 統合言語クエリ (LINQ) のクエリ結果をページングする方法について説明します。
ms.custom: ''
ms.date: 10/31/2018
ms.reviewer: ''
ms.service: powerapps
ms.topic: article
author: JimDaly
ms.author: jdaly
manager: ryjones
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 386708448701c05a0896fcf05333c9054c350743
ms.sourcegitcommit: 8185f87dddf05ee256491feab9873e9143535e02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "2748966"
---
# <a name="page-large-result-sets-with-linq"></a>LINQ による大量の結果セットのページング

Common Data Service では、 `Take` および `Skip`  演算子を使用して大規模な .NET 言語統合クエリ (LINQ) の結果をページングできます。 `Take` 演算子は指定された数の結果を取得し、`Skip` 演算子は指定された数の結果をスキップします。  
  
## <a name="linq-paging-example"></a>LINQ ページングの例  

次の例は、LINQ クエリの結果を `Take` 演算子と `Skip` 演算子を使用してページングする方法を示しています。  
  
```csharp
int pageSize = 5;

var accountsByPage = (from a in svcContext.AccountSet
                      select new Account
                      {
                       Name = a.Name,
                      });
System.Console.WriteLine("Skip 10 accounts, then Take 5 accounts");
System.Console.WriteLine("======================================");
foreach (var a in accountsByPage.Skip(2 * pageSize).Take(pageSize))
{
 System.Console.WriteLine(a.Name);
}

```
  
### <a name="see-also"></a>関連項目  
 [LINQ (.NET Language-Integrated Query) を使用してクエリを作成する](build-queries-with-linq-net-language-integrated-query.md)   
 [LINQ クエリの例](linq-query-examples.md)