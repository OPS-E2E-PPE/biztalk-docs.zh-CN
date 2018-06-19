---
title: 使用动态路由 |Microsoft 文档
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
ms.openlocfilehash: 38b668f53ba87a461441b0dbb498ae0677fa5956
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295693"
---
# <a name="using-dynamic-routing"></a>使用动态路由
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]支持动态路由的消息使用内置的过程和泛型传递代理; 它还支持动态路由的消息传递层使用 ESB 调度程序或 ESB 调度程序反汇编管道组件上的消息。  
  
## <a name="overview"></a>概述  
 中的动态解析机制[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]当消息到达时立即之前将消息传递，或者启用的终结点的发现。  
  
## <a name="how-it-works"></a>它是如何工作  
 使用提供的泛型传递代理[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]是示例，开发和动态路由技术的使用情况的指南。 可轻松创建其他传递代理或实现传递代理包含只发送端口 （从而未实现业务流程）。 默认情况下，ESB 调度和 ESB 调度反汇编程序管道组件提供更多优化动态路由功能。  
  
 泛型传递代理本身实现业务流程中订阅了消息其中**名称**属性的当前**服务实例**路线中的元素是**Microsoft.Practices.ESB.Services.Routing**。 代理可执行以下操作序列：  
  
1.  接收非类型化的消息 (System.Xml.XmlDocument)。  
  
2.  它尝试解析 n 数量的终结点使用的解析程序管理器。  
  
3.  它使用的适配器管理器来设置消息上下文和逻辑的动态端口的终结点属性。  
  
4.  它将发布通过直接绑定发送端口，随即将会触发 BizTalk Server 订阅服务器上的动态发送端口获得进一步的消息路由消息。  
  
## <a name="how-to-configure-dynamic-routing"></a>如何配置动态路由  
 有关如何配置动态路由使用路线设计器的详细信息，请参阅创建路线使用路线设计器。  
  
## <a name="dynamic-routing-errors"></a>动态路由错误  
 动态路由机制将创建并发布[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]在以下情况下的错误消息：  
  
-   传递代理不能在实时 (JIT) 解析期间确定的终结点。  
  
-   传送失败时发生。  
  
-   没有任何订户存在输出消息。  
  
-   会发生任何系统异常。