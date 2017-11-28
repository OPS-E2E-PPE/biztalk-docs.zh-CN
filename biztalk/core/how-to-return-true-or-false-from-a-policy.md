---
title: "如何从一个策略返回 True 或 False |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a7bb9b2-14aa-44e7-a290-e49bf53bc594
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 281d5ab7648545f2e0616095f3c535d7d109136f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-return-true-or-false-from-a-policy"></a><span data-ttu-id="6ce6b-102">如何从一个策略返回 True 或 False</span><span class="sxs-lookup"><span data-stu-id="6ce6b-102">How to Return True or False from a Policy</span></span>
<span data-ttu-id="6ce6b-103">不能直接指定返回类型的策略。</span><span class="sxs-lookup"><span data-stu-id="6ce6b-103">You cannot specify a return type for a policy directly.</span></span> <span data-ttu-id="6ce6b-104">不过，您可以将以下某种类型的事实传递给策略，使策略将事实的值更改为 `true` 或 `false`，然后在执行策略后检查属性/元素/列的值：</span><span class="sxs-lookup"><span data-stu-id="6ce6b-104">However, you can pass one of the following types of facts to the policy, have the policy change the value of the fact to `true` or `false`, and then check the value of the property/element/column after the policy is executed:</span></span>  
  
-   <span data-ttu-id="6ce6b-105">属性类型为 `Boolean` 的 .NET 对象</span><span class="sxs-lookup"><span data-stu-id="6ce6b-105">A .NET object with a property of type `Boolean`</span></span>  
  
-   <span data-ttu-id="6ce6b-106">元素类型为 `Boolean` 的 XML 文档</span><span class="sxs-lookup"><span data-stu-id="6ce6b-106">An XML document with an element of type `Boolean`</span></span>  
  
-   <span data-ttu-id="6ce6b-107">列类型为 `Boolean` 的数据库表</span><span class="sxs-lookup"><span data-stu-id="6ce6b-107">A database table with a column of type `Boolean`</span></span>