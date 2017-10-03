---
title: "使用从 BizTalk Server TIBCO 会合发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, handling
- message handling
- BizTalk Server, using send ports from
- send ports, using from BizTalk Server
- messages, generating
ms.assetid: 34e3edf7-cfc5-4c89-8069-63e8784bc9f9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04e11657e8e15ac0739124178e85f0c7c5c0a70e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-tibco-rendezvous-send-ports-from-biztalk-server"></a>使用 TIBCO Rendezvous 从 BizTalk Server 发送端口
传输端口可以发送任何种类的信息。 当 BizTalk Server 通过用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器发送消息时，适配器将基于消息上下文属性值生成消息，或者使用默认消息并将其发送到指定主题。  
  
> [!NOTE]
>  根据 TIBCO Rendezvous 文档，在传输主题名称中不支持通配符。  
  
## <a name="message-handling"></a>消息处理  
 适配器会保持某种状态，并相应地处理传入的 BizTalk Server 消息。  
  
-   如果因为传输失败而无法发送消息，则指示 BizTalk Server 稍后重新提交。  
  
-   如果因为适配器正在初始化而无法发送消息，则会将 BizTalk Server 消息排入队列。 如果初始化失败，则指示 BizTalk Server 稍后重新提交。  
  
## <a name="message-generation"></a>消息生成  
 使用传输适配器，用于 TIBCO Rendezvous 的 BizTalk 适配器会忽略消息目标命名空间和根元素。 如果适配器发送消息，则会原样发送负载。 如果适配器生成结构化 TIBCO Rendezvous 消息，则会忽略根元素的名称（消息没有名称）。 在每种情况下，适配器都将使用上下文属性来查找发布消息时使用的主题。  
  
 有关详细信息，请参阅[BizTalk Server 消息上下文属性 （发送处理程序）](../core/biztalk-server-message-context-properties-send-handlers.md)和[Data Type Mapping for 接收 TIBCO 集合中的处理程序](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)。  
  
## <a name="see-also"></a>另请参阅  
 [创建发送端口](../core/creating-send-ports2.md)   
 [创建 TIBCO 会合发送处理程序](../core/creating-tibco-rendezvous-send-handlers.md)