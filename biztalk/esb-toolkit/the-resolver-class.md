---
title: "解析程序类 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9ebd6c2-fd86-471a-bc50-b1b89f701fab
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1359bcbb9c6c918fc0ee6d5e67bacb8e3559c84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-resolver-class"></a>解析程序类
**冲突解决程序**类是一个简单结构，它公开一个名称/值对。 冲突解决程序 Web 服务从其方法返回此类的实例的泛型集合。  
  
 ESB 核心安装程序安装并注册**Microsoft.Practices.ESB.Resolver.dll**与在全局程序集缓存中的解析程序类的程序集。  
  
 使用基于字典的名称/值接近的使其更易于在将来添加新项，释放并避免包含依赖于的解析方法和当前的冲突解决程序类型的非相关属性的解析结果的大小降至最低。  
  
 **冲突解决程序**类公开两个属性：  
  
-   **名称**。 这是一个名称/值对，包含解决连接字符串后返回的信息的名称。  
  
-   **值**。 这是名称/值对的名称对应的值。