---
title: ResolverDictionary 类 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46deb8a0-0523-4a5c-ac6b-45c506de7a72
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1ec9080b0ad12910cc46a2844836a3b48887967
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399698"
---
# <a name="the-resolverdictionary-class"></a>ResolverDictionary 类
**ResolverDictionary**类是**字典**-基于可以存储的实例的类**冲突解决程序**作为类**字符串**名称 /值对。 创建的实例时**ResolverDictionary**类，必须提供对现有的引用**字典**实例。 **ResolverDictionary**类提供的数据**冲突解决程序**类执行运行时解析时使用。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]安装程序安装并注册**Microsoft.Practices.ESB.Resolver.dll**具有程序集**ResolverDictionary**全局程序集缓存中的类。  
  
 **ResolverDictionary**类公开一种方法和一个属性：  
  
-   **项 (** 键 **)**。 此方法采用一个包含键名称的字符串值。 如果该项不存在在基础返回相应的字符串值或空字符串**字典**实例。  
  
-   **BaseDictionary**。 此属性返回的引用到基础**字典**实例。