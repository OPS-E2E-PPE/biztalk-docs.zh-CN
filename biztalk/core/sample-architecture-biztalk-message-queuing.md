---
title: 示例体系结构： BizTalk 消息队列 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, security
- Message Queuing binary protocol
- architecture, examples
- security, examples
- security, architecture
- examples, architecture
- MSMQ adapters, security
- architecture, security
- MSMQ adapters, architecture examples
- servers, Windows Message Queuing
- Windows Message Queuing
- message queuing adapters
ms.assetid: a660c798-1c45-4759-a6c8-f11550683a31
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f38d373680fd1b47722fc1ac52c56b113ef59cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269789"
---
# <a name="sample-architecture-biztalk-message-queuing"></a>示例体系结构： BizTalk 消息队列
本主题将介绍使用 BizTalk 消息队列适配器发送和接收消息时的示例结构。  
  
 当你使用的 BizTalk 消息队列的适配器时下, 图显示将 BizTalk Server 中的各组成部分示例体系结构。  
  
 **显示 BizTalk 消息队列的适配器的图 1 示例体系结构**  
  
 ![为 BizTalk 消息队列示例体系结构](../core/media/tdi-sec-refarch-msmq.gif "TDI_Sec_RefArch_MSMQ")  
  
 此示例结构包含以下各部分所讨论的组件。  
  
## <a name="perimeter-networkinternet"></a>外围网络 ― Internet  
 我们不建议通过 Internet 使用消息队列的二进制协议。 不应允许通过防火墙 1 任何消息队列通信。 如果你想要使用的 BizTalk 消息队列适配器通过 Internet 接收消息，请执行以下操作：  
  
-   外围网络中使用的消息队列服务器。  
  
-   通过 Internet 使用消息队列 HTTP 协议。  
  
-   在外围网络，选择从消息队列服务器的消息，并将其转发给 BizTalk 消息队列适配器，通过使用二进制协议中有转发应用程序。  
  
    > [!IMPORTANT]
    >  即使使用 BizTalk 消息队列从 Internet 接收消息，则应保留 BizTalk 消息队列使用的端口在防火墙 1 关闭。  
  
## <a name="perimeter-networkintranet"></a>外围网络 ― Intranet  
 当使用 BizTalk 消息队列适配器从 intranet 接收消息时，没有将消息队列通信转发到 BizTalk 服务器运行的 BizTalk 消息队列的适配器的主机实例的 Windows 消息队列服务器。  
  
 如果 intranet 和电子商务域共享常见的 Active Directory，一条消息将经历一系列消息队列路由器，直至到达正确的目标 （运行 BizTalk 消息队列的主机实例的 BizTalk 服务器接收适配器）。 因为它是比第一个不太安全，此选项不会显示在关系图。  
  
## <a name="e-business-domain"></a>电子商务域  
 此域中的服务器如下：  
  
-   **BizTalk Server （处理、 BizTalk 消息队列适配器和跟踪主机）。** 此服务器安装有 BizTalk Server 运行时，并具有包含 BizTalk 业务流程、管道、业务规则引擎以及其他业务程序的主机实例。 BizTalk Server 端口、接收位置、管道、映射、架构以及程序集均在此服务器上接收、路由、处理和发送消息。 此服务器还具有支持的运行状况监视和监视数据的业务的跟踪的主机的主机实例。 此外，此主机包含主机运行 BizTalk 消息队列发送和接收适配器的实例。  
  
    > [!NOTE]
    >  当需要提高性能时，你可向处理主机的实例环境添加更多的 BizTalk Server。  
  
-   **主密钥服务器。** 作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **SQL Server。** 作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **域控制器。** 作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **管理工具。** 作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
## <a name="see-also"></a>另请参阅  
 [对于小型和中型公司示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)