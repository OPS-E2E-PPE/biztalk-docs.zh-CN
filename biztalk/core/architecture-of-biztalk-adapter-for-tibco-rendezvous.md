---
title: "用于 TIBCO 会合的 BizTalk Adapter 的体系结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passing messages
- architecture
- message passing
- messages, passing
ms.assetid: 174d6ceb-8e1d-4c93-827d-8155cfe47836
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 801f92453ffc85d83d57c1caa5c89ec618b96ed0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-of-biztalk-adapter-for-tibco-rendezvous"></a>TIBCO Rendezvous 的 BizTalk 适配器体系结构
用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器提供 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与 TIBCO Rendezvous 之间的双向连接。 此适配器同时使用 TIBCO Rendezvous API 和 BizTalk 适配器框架 API 来提供紧密集成。  
  
 TIBCO Rendezvous 是一种为企业应用程序集成 (EAI) 提供消息库的软件产品。 TIBCO 提供 C、C++、Java、Visual Basic 和 Microsoft .NET Framework 中的消息传递 API 来接收 Microsoft Office Excel 工作表和所选的其他应用程序中的数据源。  
  
## <a name="message-passing"></a>消息传递  
 消息传递的基本概念相当简单：  
  
-   消息具有单个主题，其中包含用句点分隔的元素。 它会发送给单个 Rendezvous 守护程序（尽管它最终可能会在其他守护程序中广播）。   
  
-   侦听器向守护程序公布其感兴趣的主题（使用基本的通配符工具），如果两个守护程序互相“连接”，或者实际是同一个守护程序，则系统会将具有匹配主题的消息传递给该侦听器。 有关详细信息，请参阅中的消息[TIBCO 会合的 BizTalk Adapter 中的消息](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md)。  
  
 下图显示了用于 TIBCO Rendezvous 的 BizTalk 适配器的体系结构。  
  
 ![](../core/media/tibcorend-arch.gif "TibcoRend_Arch")  
  
## <a name="see-also"></a>另请参阅  
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)   
 [规划和体系结构](../core/planning-and-architecture15.md)