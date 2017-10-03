---
title: "ResolverDictionary 类 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 46deb8a0-0523-4a5c-ac6b-45c506de7a72
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2dfe0082ffc7f7b68c5c56811a28d5ccd20e93e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-resolverdictionary-class"></a>ResolverDictionary 类
**ResolverDictionary**类是**字典**-基于可以存储的实例的类**冲突解决程序**类作为**字符串**名称 /值对。 创建的实例时**ResolverDictionary**类，你必须提供对现有的引用**字典**实例。 **ResolverDictionary**类提供的数据**冲突解决程序**时它执行运行时解析类使用。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]安装程序安装并注册**Microsoft.Practices.ESB.Resolver.dll**具有程序集**ResolverDictionary**全局程序集缓存中的类。  
  
 **ResolverDictionary**该类会公开一种方法和一个属性：  
  
-   **项 (**密钥**)**。 此方法采用包含键名称的字符串值。 它将返回相应的字符串值或空字符串如果该项不存在于基础**字典**实例。  
  
-   **BaseDictionary**。 此属性返回对基础的引用**字典**实例。