---
title: SWIFTNet 是什么？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b074385-352c-40f4-b73e-1891c627aa4e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02f09a1ccc9b67b084a6f683125bacaec5eae77c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989334"
---
# <a name="what-is-swiftnet"></a>SWIFTNet 是什么？
作为常规用途，金融业的行业标准解决方案 SWIFTNet 提供全局财务社区中参与的所有机构中的所有连接的应用程序独立于应用程序的单个窗口界面。 实际的访问控制的业务策略决策的每个服务管理员，而不是基础结构的技术限制。  
  
 SWIFTNet 为确保不受影响的基础结构的跨机构边界的关键财务应用程序的业务连续性和灾难恢复提供了基础。 SWIFTNet 旨在满足关键财务软件解决方案的互操作性的机构社区要求。  
  
 相互关联的业务应用程序，到 SWIFTNet 提供以下功能：  
  
-   基础结构的可靠性保证  
  
-   可用性  
  
-   基于角色的和非基于角色的访问控制  
  
-   响应方返回和消息身份验证  
  
-   消息完整性  
  
-   保密性  
  
-   不可否认性的支持  
  
-   消息验证  
  
-   存储和转发  

使用 SWIFTNet **SWIFTNet 链接**(SNL) 作为到 SWIFTNet 服务，并使用了应用程序编程接口**SWIFTAlliance 网关**连接性和可用性。 详细了解本主题中的这些资源。

## <a name="swiftnet-link-overview"></a>SWIFTNet 链接概述

业务软件应用程序使用 SWIFTNet 链接 (SNL) 应用程序编程接口 (API) 访问和使用 SWIFTNet 服务。 SNL 是 SWIFTNet 必需的网络接口。 SWIFTNet 需要的所有外部接口 SNL。 SNL 还包括支持消息传送、 安全性和服务管理功能的后台进程。 SNL 合并到 SWIFTAlliance WebStation 和 SWIFTAlliance 网关 （压降）。  
  
 SNL 建立业务应用程序组件之间的松散耦合的客户端/服务器关系。 而不是直接调用方法或函数的交互是面向消息的： 结构化的消息传递客户端和服务器之间。 通常为 SWIFTNet 服务而设计的业务应用程序包含的一组客户端和服务器。 同一个客户端或相同的服务器进程可以启动多个时间。 请注意，不能预测到哪个进程将直接发送相同的应用程序的传入消息请求的实例。 客户端进程中的多个线程可以调用 SwCall API 函数。 服务器进程都可以有多个线程也;但是，只有一个线程可以调用 SwCallback。 不能在同一进程中结合使用客户端和服务器进程。  
  
 SNL 提供了一组用于高可用性和高吞吐量环境而设计的传输级功能。 这些功能包括：  
  
- 负载平衡  
  
- 位置透明度和路由，屏蔽与基础传输技术的应用程序组件  
  
- 传输级身份验证和保密性，打包在 SNL 和以透明方式提供给应用程序  
  
- 业务应用程序软件可能会建立端到端安全性 （对用户应用程序用户应用程序，） 的安全功能时所需。  
  
  在使用 c + + 或 Java 源代码级进行编程，方面有只有两个函数： SwCall 和 SwCallback。 客户端应用程序使用 SwCall 通过 SWIFTNet 访问服务器应用程序。 SwCallback 是服务器应用程序用于响应通过 SWIFTNet 客户端。  
  
  SwCall 和 SwCallback 函数访问 SWIFTNet 的功能通过将传递到和从 SWIFTNet 结构化的 XML 消息。 在运行时 SNL 包括这两个软件库-作为业务应用程序客户端或服务器进程的相同地址空间内的代码执行 — 和运行在其自己的独立进程 （守护程序或服务），地址空间。 软件库都可通过 SNL Api 访问。  

## <a name="swiftalliance-gateway-overview"></a>SWIFTAlliance 网关概述
  
SWIFTAlliance 网关 （压降） 是 SWIFTNet 接口产品。 它集成了 SWIFTNet 链接的所有功能。 此外，它提供几个不同的连接和可用性功能对于 SWIFTNet 用户，提供集成问题的系统的各种解决方案。  
  
 压降支持多个不同的操作模式。 其中一种严格 SWIFTNet 链接模式，是专门针对用于 SWIFT 的 FileAct 和 InterAct 适配器。 在严格 SWIFTNet 链接模式下，压降显示是功能上等效于 SWIFTNet 链接接口，因为它在这些主题中所述的消息传递接口。  
  
 压降用作消息集中器。 它从各种其他应用程序接收消息并将其传递通过 SWIFTNet。 它将接收这些消息通过主机适配器，包括 WebSphere MQ 主机适配器，从而使业务应用程序运行在各种不同类型的计算平台上为将通过 SWIFTNet 消息传递。  
 
 ## <a name="next-reading"></a>下一步读取
 
 [FileAct 适配器概述](../../adapters-and-accelerators/fileact-interact/what-is-the-fileact-adapter.md)  
 [InterAct 适配器概述](../../adapters-and-accelerators/fileact-interact/what-is-the-interact-adapter.md)  
 [BizTalk FileAct 和 InterAct 适配器端到端教程](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md)
 
 ## <a name="see-also"></a>另请参阅
 [了解 FileAct 和 InterAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md)