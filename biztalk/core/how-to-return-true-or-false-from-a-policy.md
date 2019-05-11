---
title: 如何从策略返回 True 或 False |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a7bb9b2-14aa-44e7-a290-e49bf53bc594
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 093d58d97d6ecc2df842118b5a30f9858f4b4b96
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334899"
---
# <a name="how-to-return-true-or-false-from-a-policy"></a>如何从策略返回 True 或 False
不能直接指定返回类型的策略。 但是，可以将一个以下类型的事实传递到该策略，使策略更改为事实的值`true`或`false`，然后检查属性/元素/列的值后执行的策略：  
  
-   具有类型的属性的.NET 对象 `Boolean`  
  
-   使用类型的元素的 XML 文档 `Boolean`  
  
-   数据库表具有的列的类型 `Boolean`