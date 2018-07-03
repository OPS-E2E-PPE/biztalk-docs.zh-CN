---
title: BizTalk ESB 工具包的体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41674f5-5ea4-4a8f-a270-b67fd6854028
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a701b2c0170b8687e48ff61c369ac25ef41ab6bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999382"
---
# <a name="architecture-of-the-biztalk-esb-toolkit"></a>BizTalk ESB 工具包的体系结构
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]系列进行互操作支持和实现松散耦合的消息传送环境可简化构建基于消息的企业应用程序组件组成。 服务和组件很自然地划分为以下七个类别：  
  
- **Web 服务。** 这些公开内部服务，例如路线处理、 异常管理终结点和映射，BizTalk Server 操作、 通用描述、 发现和集成 (UDDI) 互操作和转换消息内容的解决方法.  
  
- **路线服务。** 其中包括用于执行转换和消息路由基于业务流程和基于消息的服务。 在路线处理过程中，可以创建自定义参与的服务。 其中包括用于执行转换和消息路由基于业务流程和基于消息的服务。 在路线处理过程中，可以创建自定义参与的服务。  
  
- **路线接入。** 这些接收外部消息、 附加为每个消息，适当的旅行计划和执行路线处理;它们使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]冲突解决程序和适配器提供程序框架，用于动态解析的终结点和元数据。  
  
- **接入。** 与不同的路线接入，这些接收外部消息格式和传输，如 HTTP、 Java 消息服务 (JMS)、 IBM WebSphere MQ (WMQ)、 文件传输协议 (FTP)、 平面文件和 XML 的范围内。 它们是典型的 BizTalk Server 接收位置 （可选） 使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]互操作的管道组件和[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]冲突解决程序和适配器提供程序框架，用于动态解析的终结点和元数据。  
  
- **接出点。** 这些实现的发送端口使用的格式和传输如 WCF、 JMS、 WMQ、 FTP、 HTTP、 平面文件、 XML 或任何其他自定义格式的消息传递。 它们是典型的 BizTalk Server 会直接绑定的动态发送端口消息框中，还可以选择使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]互操作的管道组件和[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]冲突解决程序和适配器提供程序框架，用于动态解析的终结点和元数据。  
  
- **异常管理框架。** 这包括异常 Web 服务、 异常管理 API，以及组件的丰富、 处理，并将异常详细信息传递到 ESB 管理门户。  
  
- **ESB 管理门户。** 此示例应用程序提供注册预配、 异常中介、 警报通知和分析。  
  
  许多这些组件和服务的依赖功能由 BizTalk Server 中，例如业务流程、 转换和业务规则引擎和 Messagebox 数据库实现。 图 1 显示了示意图类别、 组件和服务通常发生在每个类别中，并通过使用核心 BizTalk Server 系统组件[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。  
  
  ![ESB 体系结构](../esb-toolkit/media/esbarchitecture.gif "ESBArchitecture")  
  
  **图 1**  
  
  **体系结构和组件 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a>BizTalk ESB 工具包的工作原理  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]接受入站的消息并对其进行操作，可能是 （但不是总是） 通过执行进程，例如转换，路由，或任何其他自定义进程。 若要指定的操作需要，核心处理组件需要每条消息具有传送名单，其中包含关联的说明或定义应用的进程的元数据和要使用消息内容执行的任务。 这些路由滑动称为路线和可以自动解决，检索从中央存储库，和附加到消息时接收到的途径。  
  
 此路由的名单方法提供服务，这意味着 ESB 不需要事先了解的特定处理每条消息之间的松散耦合。 它只须了解可能的进程范围是什么以及如何将应用每个进程。 用于指定可用进程及进程与消息中说明间映射的选项众多，它们提供了一个配置和调整行为的灵活机制，不需要更改代码和重新部署组件。  
  
## <a name="design-patterns"></a>设计模式  
 使用 ESB，其中进程 Messagebox 数据库中存放消息和订阅服务器中选取它们基于在消息中，处理指令的体系结构有效地实现状态机设计模式。 此外，ESB 实现，并在面向服务的方式，包括对外部应用程序通过一系列核心 Web 服务中公开其核心功能。  
  
 这松散耦合的设计 BizTalk Server 的方法和[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]-基于应用程序生成高度灵活的解决方案和已经成为行业接受的最佳做法。