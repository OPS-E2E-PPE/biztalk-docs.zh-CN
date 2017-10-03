---
title: "什么是 SWIFTNet？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b074385-352c-40f4-b73e-1891c627aa4e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1668c1f568a6cfb853957b3598b41f1cbdf6e33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-swiftnet"></a>什么是 SWIFTNet？
作为一般用途，金融业的行业标准解决方案 SWIFTNet 提供全局财务社区参与的所有机构中的所有连接的应用程序的应用程序无关的、 单一窗口接口。 实际的访问控制由业务策略决策的每个服务管理员，而不是基础结构的技术限制。  
  
 SWIFTNet 为确保业务连续性和灾难恢复任务关键型跨机构边界的财务应用程序的基础结构奠定了基础。 SWIFTNet 旨在满足制度社区执行关键任务的财务软件解决方案的互操作性要求。  
  
 到互连的业务应用程序，SWIFTNet 提供以下功能：  
  
-   基础结构可靠性保证  
  
-   可用性  
  
-   基于角色的和非基于角色的访问控制  
  
-   通信和消息身份验证  
  
-   消息的完整性  
  
-   保密性  
  
-   不可否认性支持  
  
-   消息验证  
  
-   存储和转发  

SWIFTNet 使用**SWIFTNet 链接**(SNL) 作为到 SWIFTNet 服务，并使用了应用程序编程接口**SWIFTAlliance 网关**连接和可用性。 有关本主题中的这些资源的更多信息。

## <a name="swiftnet-link-overview"></a>SWIFTNet 链接概述

商业软件应用程序使用 SWIFTNet 链接 (SNL) 应用程序编程接口 (API) 访问和使用 SWIFTNet 服务。 SNL 是 SWIFTNet 的必需的网络接口。 SWIFTNet 所有外部接口的要求 SNL。 SNL 还包括支持消息传送、 安全性和服务管理功能的后台进程。 SNL 并入 SWIFTAlliance WebStation 和 SWIFTAlliance 网关 （压降）。  
  
 SNL 松散耦合的客户端/服务器之间建立关系业务应用程序组件。 而不是直接调用方法或函数，交互是面向消息的： 客户端和服务器之间传递结构化的消息。 业务应用程序通常用于 SWIFTNet 服务包含一组客户端和服务器。 同一个客户端或相同的服务器进程可以启动多次。 请注意，你无法预测到的进程将直接发送的同一个应用程序的传入消息请求的实例。 在客户端进程内的多个线程可以调用 SwCall API 函数。 服务器进程可以拥有多个线程也;但是，只有一个线程可以调用 SwCallback。 客户端和服务器进程不能组合相同的进程中。  
  
 SNL 提供了一套专为高可用性和高吞吐量环境设计的传输级功能。 这些功能包括：  
  
-   负载平衡  
  
-   位置透明度和路由、 屏蔽从基础传输技术的应用程序组件  
  
-   传输级身份验证和保密性，打包在 SNL，以透明方式提供给应用程序  
  
-   安全函数由哪些业务应用程序软件可能需要建立端到端安全性 （对用户应用程序是用户应用程序） 上，在需要时。  
  
 在源代码级使用 c + + 或 Java 进行编程，方面有只有两个函数： SwCall 和 SwCallback。 SwCall 客户端应用程序用于通过 SWIFTNet 访问服务器应用程序。 服务器应用程序使用 SwCallback 以响应客户端通过 SWIFTNet。  
  
 SwCall 和 SwCallback 函数通过传递结构化的 XML 消息传入和传出 SWIFTNet 访问 SWIFTNet 的功能。 在运行时 SNL 包括这两个软件库-作为业务应用程序客户端或服务器进程的同一个地址空间内执行的代码-和运行在其自己的独立进程 （守护程序或服务） 中，地址空间。 软件库是可通过 SNL Api 访问。  

## <a name="swiftalliance-gateway-overview"></a>SWIFTAlliance 网关概述
  
SWIFTAlliance 网关 （压降） 是 SWIFTNet 接口产品。 它融合了 SWIFTNet 链接的所有功能。 此外，它提供几个不同的连接和可用性功能用于 SWIFTNet 用户，提供集成问题的各种系统的解决方案。  
  
 压降支持几个不同的操作模式。 其中一种，严格 SWIFTNet 链接模式，是专门针对 for SWIFT FileAct 和交互适配器。 在严格 SWIFTNet 链接模式下，压降显示功能上等效于 SWIFTNet 链接接口述在所有这些主题的消息传递接口。  
  
 压降用作消息集中器。 它与其他各种应用程序接收消息，并将它们传递通过 SWIFTNet。 它将接收这些消息通过主机适配器，包括 WebSphere MQ 主机适配器，从而使业务应用程序运行在各种不同类型的计算平台上为将通过 SWIFTNet 的消息传递。  
 
 ## <a name="next-reading"></a>下一步读取
 
 [什么是 FileAct 适配器？](../../adapters-and-accelerators/fileact-interact/what-is-the-fileact-adapter.md)  
 [什么是交互适配器？](../../adapters-and-accelerators/fileact-interact/what-is-the-interact-adapter.md)  
 [BizTalk FileAct 和交互适配器端到端教程](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md)
 
 ## <a name="see-also"></a>另请参阅
 [了解 FileAct 和交互适配器体系结构](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md)