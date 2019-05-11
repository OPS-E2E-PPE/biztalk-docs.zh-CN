---
title: MQSeries 适配器是什么？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, about MQSeries adapters
- MQSeries adapters
ms.assetid: fd3dfa9a-344a-46e5-a342-bc56da7c1c50
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10157d2e29b9ab3b23f1f938cdc55a2c1b7d7f5b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243056"
---
# <a name="what-is-the-mqseries-adapter"></a>MQSeries 适配器是什么？
可以使用 MQSeries 适配器发送和接收消息与 MQSeries 系统 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 对于 Windows，该适配器依赖 MQSeries 服务器。 此设计可确保可靠消息传送，因为 MQSeries Server for Windows 支持 Microsoft 分布式事务处理协调器 (MSDTC)。  
  
 该适配器支持群集的 MQSeries 服务器和群集的 MQSeries 队列管理器，以及群集的 BizTalk server。  
  
 您可以执行以下操作使用 MQSeries 适配器：  
  
- 将消息发送到 MQSeries 远程定义队列、 本地队列、 传输队列和别名队列中，从 BizTalk Server。  
  
- 从 MQSeries 传输队列、 本地队列和别名队列接收消息。  
  
- 从发送和接收消息 MQSeries Server for Windows （MQSeries 服务器可以运行 BizTalk Server 所在的计算机或远程安装）。 只需部署一份 MQSAgent （的 COM + 组件的适配器） 来支持所有 BizTalk Server 安装。  
  
- 等待间隔来轮询 MQSeries Server。  
  
- 使用动态发送端口来控制适配器。  
  
- 在运行时动态创建队列。  
  
- 从根据 MQSeries MatchOptions 队列动态接收消息。  
  
- 将上下文属性映射到用于传输和接收消息的标头属性。 可以获取和设置 MQSeries 标头属性 （包括 MQMD、 MQXQH、 MQCIH 和 MQIIH） 通过 BizTalk Server 上下文属性。  
  
- 启用与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或 MQSeries 服务器可以创建相关标识符。  
  
- 请求事务性和非事务性传递的消息的发送和接收。  
  
> [!NOTE]
>  使用 MQSeries 这样对服务器的分布式组件对象模型 (DCOM) 调用如功能时，请确保你没有启用了-基于网络地址转换 (NAT） 防火墙。 客户端必须能够访问服务器的实际 IP 地址，并基于 NAT 的防火墙将此地址为客户端将无法识别的内容。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [MQSeries 适配器的组件](../core/components-of-the-mqseries-adapter.md)  
  
-   [MQSeries 适配器的体系结构](../core/mqseries-adapter-architecture.md)  
  
-   [使用 MQSeries 适配器](../core/using-the-mqseries-adapter.md)  
  
-   [MQSeries 适配器安全性](../core/mqseries-adapter-security.md)