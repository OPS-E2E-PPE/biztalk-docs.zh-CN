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
# <a name="how-to-return-true-or-false-from-a-policy"></a>如何从一个策略返回 True 或 False
不能直接指定返回类型的策略。 不过，您可以将以下某种类型的事实传递给策略，使策略将事实的值更改为 `true` 或 `false`，然后在执行策略后检查属性/元素/列的值：  
  
-   属性类型为 `Boolean` 的 .NET 对象  
  
-   元素类型为 `Boolean` 的 XML 文档  
  
-   列类型为 `Boolean` 的数据库表