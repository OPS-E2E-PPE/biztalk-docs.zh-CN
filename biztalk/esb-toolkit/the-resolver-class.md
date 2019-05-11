---
title: Resolver 类 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b9ebd6c2-fd86-471a-bc50-b1b89f701fab
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f4ad2846396e3e59cd4729d3410038495b2edcd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399714"
---
# <a name="the-resolver-class"></a>冲突解决程序类
**冲突解决程序**类是公开的名称/值对的简单结构。 解析程序 Web 服务从其方法返回此类的实例的泛型集合。  
  
 ESB 核心安装程序安装并注册**Microsoft.Practices.ESB.Resolver.dll**与全局程序集缓存中的冲突解决程序类的程序集。  
  
 使用基于字典的名称/值方法的使其更易于在将来添加新项释放并避免依赖于该解析方法和当前的冲突解决程序类型的非相关属性的包含解析结果的大小降至最低。  
  
 **冲突解决程序**类公开两个属性：  
  
-   **名称**。 这是包含解决的连接字符串后返回的信息的名称/值对的名称。  
  
-   **值**。 这是名称/值对的名称对应的值。