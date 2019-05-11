---
title: 使用动态路由 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caa3a35f-cafa-4524-8b96-f8a333b7ff87
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e30d13458e9c020f66984f42d3a472364bc8b425
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396451"
---
# <a name="using-dynamic-routing"></a>使用动态路由
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]支持动态路由的消息使用内置过程和泛型传递代理; 它还支持动态路由的消息在消息传送层使用 ESB 调度程序或 ESB 调度程序反汇编管道组件。  
  
## <a name="overview"></a>概述  
 中的动态解析机制[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]在消息到达时，或将消息传递之前立即启用的终结点的发现。  
  
## <a name="how-it-works"></a>其工作原理  
 使用提供的泛型传递代理[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]是一个示例和开发以及动态路由技术的使用情况的指南。 可以轻松地创建更多的传递代理或实现包含的只是一个发送端口 （这不会实现业务流程） 的传递代理。 默认情况下，ESB 调度和 ESB 调度拆装器管道组件提供更多优化动态路由功能。  
  
 泛型传递代理本身实现业务流程订阅消息的位置**名称**属性的当前**ServiceInstance**路线中的元素是**Microsoft.Practices.ESB.Services.Routing**。 代理将执行以下一系列操作：  
  
1.  收到非类型化的消息 (System.Xml.XmlDocument)。  
  
2.  尝试解析 n 使用的冲突解决程序管理器终结点的数目。  
  
3.  它使用适配器管理器来设置消息上下文和逻辑的动态端口的终结点属性。  
  
4.  它将发布通过直接绑定的发送端口，这会触发 BizTalk Server 订阅服务器上的更多消息路由的动态发送端口的消息。  
  
## <a name="how-to-configure-dynamic-routing"></a>如何配置动态路由  
 有关如何配置动态路由使用路线设计器的详细信息，请参阅创建路线使用路线设计器。  
  
## <a name="dynamic-routing-errors"></a>动态路由错误  
 动态路由机制将创建并发布[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]在以下情况下的错误消息：  
  
-   发送代理不能在实时 (JIT) 解析期间确定的终结点。  
  
-   传送失败时发生。  
  
-   没有订阅服务器上存在的输出消息。  
  
-   会发生任何系统异常。