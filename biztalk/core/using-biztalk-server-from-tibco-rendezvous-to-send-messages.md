---
title: "使用从 TIBCO 会合的 BizTalk Server 发送消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, sending
- sending messages
- BizTalk Server, using from TIBCO Rendezvous
ms.assetid: 72057d42-32b5-4748-81e4-5ffb89630f5a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4556ce5ca90b3c62f779d2df55e78c4506458d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-biztalk-server-from-tibco-rendezvous-to-send-messages"></a>使用来自 TIBCO Rendezvous 的 BizTalk Server 以发送消息
用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器使用异步 API (Transport.Send)。 您可以指定适配器使用消息上下文属性发送的消息类型：  
  
-   **结构化**： 适配器生成 TIBRVMSG_MSG 结构化，根据消息从 BizTalk Server 接收的 XML 数据。 (*)  
  
 如果 BizTalk Server 发送字段名称长于 127 个字符的消息，则用于 TIBCO Rendezvous 的 BizTalk 适配器会将名称截断到 TIBCO Rendezvous 的最大字段名称大小（即 127）。  
  
 如果提供 `reply subject name` 属性，则该属性用于在 TIBCO Rendezvous 消息上设置答复主题。 假设将接收端口设置为侦听回复或将其转发到 BizTalk Server，或者一些其他的 TIBCO Rendezvous 程序负责回复。  
  
 三联（服务、后台程序、网络）组成传输配置。 空（默认）传输配置导致通过默认传输对象发送消息。  
  
 如果未指定代码页，则适配器使用 UTF-8 编码（代码页 65001）。 发送器端不支持经过认证的消息。  
  
## <a name="see-also"></a>另请参阅  
 [TIBCO 会合概念](../core/tibco-rendezvous-concepts.md)   
 [创建 TIBCO 会合发送处理程序](../core/creating-tibco-rendezvous-send-handlers.md)