---
title: "MQSeries 适配器概述  | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, about MQSeries adapters
- MQSeries adapters
ms.assetid: fd3dfa9a-344a-46e5-a342-bc56da7c1c50
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f72d0012050fc8022b53120377aeb648641d21f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-mqseries-adapter"></a>MQSeries 适配器概述 
通过 MQSeries 适配器，您可以在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与 MQSeries 系统之间收发消息。  
  
 该适配器依赖于 MQSeries Server for Windows。 这种设计可确保消息传送的可靠性，因为 MQSeries Server for Windows 支持 Microsoft 分布式事务处理协调器 (MSDTC)。  
  
 该适配器支持群集 MQSeries Server 和群集 MQSeries 队列管理器，以及群集 BizTalk Server。  
  
 使用 MQSeries 适配器，您可以执行以下操作：  
  
-   将消息从 BizTalk Server 发送到 MQSeries 远程定义队列、本地队列、传输队列和别名队列。  
  
-   从 MQSeries 传输队列、本地队列和别名队列接收消息。  
  
-   与 MQSeries Server for Windows 之间收发消息，MQSeries Server 可在 BizTalk Server 所在的同一计算机或远程安装位置上运行。 只需部署一个 MQSAgent（适配器的 COM+ 组件）副本即可支持所有的 BizTalk Server 安装。  
  
-   按等待间隔来轮询 MQSeries Server。  
  
-   使用动态发送端口来控制适配器。  
  
-   在运行时动态创建队列。  
  
-   根据 MQSeries MatchOptions 从队列中动态接收消息。  
  
-   将上下文属性映射到用于传输和接收消息的标头属性。 可以通过 BizTalk Server 上下文属性来获取和设置 MQSeries 标头属性，包括 MQMD、MQXQH、MQCIH 和 MQIIH。  
  
-   启用使用相关[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或 MQSeries 服务器创建的相关标识符。  
  
-   请求事务性和非事务性消息送达，以便进行发送和接收。  
  
> [!NOTE]
>  当使用诸如 MQSeries 这样对服务器调用分布式组件对象模型 (DCOM) 的功能时，请确保未启用基于网络地址转换 (NAT) 的防火墙。 客户端必须能够通过其实际 IP 地址访问该服务器，并且基于 NAT 的防火墙将此地址翻译为客户端不能识别的地址。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [MQSeries 适配器的组件](../core/components-of-the-mqseries-adapter.md)  
  
-   [MQSeries 适配器体系结构](../core/mqseries-adapter-architecture.md)  
  
-   [使用 MQSeries 适配器](../core/using-the-mqseries-adapter.md)  
  
-   [MQSeries 适配器安全](../core/mqseries-adapter-security.md)