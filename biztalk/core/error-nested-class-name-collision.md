---
title: 错误-嵌套的类名冲突 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.nestedClassNameCollision
ms.assetid: dd636d25-d0c1-41be-a2ba-b38ea97b973d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4a9fa7a9f57088b3fb93e2eb6024e9b6aad49c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---nested-class-name-collision"></a>错误-嵌套的类名冲突
**错误代码**  
  
 BEC2017  
  
 **说明**  
  
 **类型名称**找到此架构的属性会作为相同**RootNode TypeName**之一的架构中的根节点的属性。 C# 不允许嵌套类同名，因此这种情况会导致错误。  
  
 **用户执行任何操作**  
  
 必须更改相关属性值中的一个或两个，以免名称冲突。 请使用以下两种方法之一：  
  
-   在 Microsoft 中选择相关的架构文件[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，然后在属性窗口中，更改**类型名称**为唯一有效的值的属性。  
  
     \- 或 -  
  
-   选择指定的根节点，然后在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，更改**RootNode TypeName**为唯一有效的值的属性。