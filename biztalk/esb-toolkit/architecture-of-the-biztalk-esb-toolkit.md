---
title: "BizTalk ESB 工具包的体系结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a41674f5-5ea4-4a8f-a270-b67fd6854028
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 068eddfdd2138fbc92ad4821b2eaf9491ad39000
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-of-the-biztalk-esb-toolkit"></a>BizTalk ESB 工具包的体系结构
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]支持和实现松散耦合的消息传递环境，它使更轻松地生成基于消息的企业应用程序的组件进行互操作的一系列组成。 服务和组件自然地划分为以下的七种类别：  
  
-   **Web 服务。** 这些公开内部服务，如路线处理、 异常管理、 解析终结点以及地图，[!INCLUDE[prague](../includes/prague-md.md)]操作、 通用、 描述、 发现和集成 (UDDI) 互操作和转换消息内容。  
  
-   **路线服务。** 其中包括用于执行转换和路由消息的基于业务流程的和基于消息的服务。 你可以在路线处理过程中创建参与的自定义服务。 其中包括用于执行转换和路由消息的基于业务流程的和基于消息的服务。 你可以在路线处理过程中创建参与的自定义服务。  
  
-   **路线上的渐变。** 这些接收外部消息、 附加相应路线每条消息，并执行路线处理;它们使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]解析器和用于动态解析终结点以及元数据适配器提供程序框架。  
  
-   **渐变。** 与不同的路线上-渐变，这些格式和传输协议，如 HTTP、 Java 消息服务 (JMS)、 IBM WebSphere MQ (WMQ)、 文件传输协议 (FTP)、 平面文件和 XML 的一系列中接收外部的消息。 它们是典型的 BizTalk Server 接收 （可选） 使用的位置[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]互操作管道组件和[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]解析器和用于动态解析终结点以及元数据适配器提供程序框架。  
  
-   **关闭渐变。** 这些实现发送端口使用的格式和传输如 WCF、 JMS、 WMQ、 FTP、 HTTP、 平面文件、 XML 或任何其他自定义格式的消息传递。 它们是动态发送端口被直接绑定到消息框和 （可选） 使用的典型 BizTalk Server[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]互操作管道组件和[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]解析器和用于动态终结点解析适配器提供程序框架和元数据。  
  
-   **异常管理框架。** 这包括异常 Web 服务、 异常管理 API 和扩充、 处理和传递给 ESB 管理门户的异常详细信息的组件。  
  
-   **ESB 管理门户。** 此示例应用程序提供注册表设置、 异常中介，警报通知和分析。  
  
 这些组件和服务的许多依赖于由实现的功能[!INCLUDE[prague](../includes/prague-md.md)]，如业务流程、 转换和业务规则引擎和消息框数据库。 图 1 显示的类别、 组件和服务中每个类别，通常发生的示意图和核心 BizTalk Server 系统组件由[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。  
  
 ![ESB 体系结构](../esb-toolkit/media/esbarchitecture.gif "ESBArchitecture")  
  
 **图 1**  
  
 **体系结构和组件[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a>BizTalk ESB 工具包的工作原理  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]接受入站的消息，并对它们，可能 （但不是总是） 通过执行转换等的进程，路由，或任何其他自定义过程。 若要指定的操作需要，核心处理组件需要每条消息都有一个传送名单，其中包含关联的说明或定义要应用的进程的元数据和用于执行与消息内容的任务。 这些路由滑动称为路线和可以自动解决、 检索从中央存储库，和它接收到入口时附加到消息。  
  
 此路由滑动方法提供服务，这意味着 ESB 不需要为每个消息事先了解特定的处理之间的松散耦合。 它只是必须知道进程的可能范围以及如何将应用每个进程。 用于指定可用进程及进程与消息中说明间映射的选项众多，它们提供了一个配置和调整行为的灵活机制，不需要更改代码和重新部署组件。  
  
## <a name="design-patterns"></a>设计模式  
 ESB 使用，其中进程存款消息在消息框数据库和订阅服务器中选取它们基于在消息中，处理指令的体系结构有效地实现的状态机设计模式。 此外，ESB 实现，并以面向服务的方式，其中包括与外部应用程序可以通过一组核心 Web 服务公开其核心功能。  
  
 这松散耦合方法的设计 BizTalk Server 和[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]-基于应用程序生成的高度灵活的解决方案，并且已变得行业认可的最佳做法。