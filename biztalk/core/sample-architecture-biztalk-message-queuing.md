---
title: 示例体系结构：BizTalk 消息队列 |Microsoft Docs
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
ms.openlocfilehash: 9424562425854dba532e0c1650c6c9070469be0f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393953"
---
# <a name="sample-architecture-biztalk-message-queuing"></a>示例体系结构：BizTalk 消息队列
使用 BizTalk 消息队列适配器发送和接收消息时，本主题介绍对示例结构。  
  
 使用 BizTalk 消息队列适配器时下, 图显示的 BizTalk Server 组件的示例体系结构。  
  
 **图 1 显示了 BizTalk 消息队列适配器的示例结构**  
  
 ![用于 BizTalk 消息队列的示例体系结构](../core/media/tdi-sec-refarch-msmq.gif "TDI_Sec_RefArch_MSMQ")  
  
 此示例结构包含的组件，如以下各节中所述。  
  
## <a name="perimeter-networkinternet"></a>外围网络 ― internet  
 我们不建议通过 Internet 使用消息队列二进制协议。 应允许通过防火墙 1 任何消息队列通信。 如果你想要使用的 BizTalk 消息队列适配器通过 Internet 接收消息，请执行以下操作：  
  
-   在外围网络中使用的消息队列服务器。  
  
-   通过 Internet 使用消息队列的 HTTP 协议。  
  
-   提取从消息队列服务器的消息并将其转发到 BizTalk 消息队列适配器通过使用二进制协议的外围网络中有一个转发应用程序。  
  
    > [!IMPORTANT]
    >  即使使用 BizTalk 消息队列从 Internet 接收消息，BizTalk 消息队列使用应保留的端口将关闭防火墙 1 中。  
  
## <a name="perimeter-networkintranet"></a>外围网络 ― intranet  
 当 BizTalk 消息队列适配器用于接收来自 intranet 的消息时，没有将消息队列通信转发到运行的 BizTalk 消息队列适配器的主机实例的 BizTalk 服务器的 Windows 消息队列服务器。  
  
 如果 intranet 和电子商务域共享常见的 Active Directory，消息将通过一系列消息队列路由器，直至到达正确的目标 （BizTalk Server 运行主机实例的 BizTalk 消息队列接收适配器）。 此选项不在关系图中表示，因为它是比第一个不太安全。  
  
## <a name="e-business-domain"></a>电子商务域  
 此域中的服务器是：  
  
-   **BizTalk Server （处理、 BizTalk 消息队列适配器和跟踪主机）。** 此服务器安装了 BizTalk Server 运行时，并具有包含 BizTalk 业务流程、 管道、 业务规则引擎和其他业务流程主机实例。 这是其中 BizTalk Server 端口、 接收位置、 管道、 映射、 架构和程序集位于要接收、 路由、 处理和发送消息。 此服务器还具有支持跟踪运行状况监视和业务监视数据的主机的主机实例。 此外，此主机包含运行 BizTalk 消息队列发送和接收适配器的主机实例。  
  
    > [!NOTE]
    >  根据性能需求的增加，您可以添加更多 BizTalk Server 对您的环境的处理主机的主机实例。  
  
-   **主密钥服务器。** 中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **SQL Server。** 中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **域控制器。** 中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **管理工具。** 中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
## <a name="see-also"></a>请参阅  
 [对于小型和中型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)