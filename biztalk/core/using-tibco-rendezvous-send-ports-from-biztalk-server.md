---
title: 使用 TIBCO Rendezvous 发送端口从 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 34e3edf7-cfc5-4c89-8069-63e8784bc9f9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bc98cc3136483a1481590fade44de2796562b2c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396768"
---
# <a name="using-tibco-rendezvous-send-ports"></a>使用 TIBCO Rendezvous 发送端口
传输端口可以发送任何种类的信息。 BizTalk Server 发送用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器通过一条消息，适配器生成基于消息上下文属性值，该消息或它使用默认值并将其发送到指定主题。  
  
> [!NOTE]
>  根据 TIBCO Rendezvous 文档，通配符字符不支持在传输主题名称。  
  
## <a name="message-handling"></a>消息处理  
 适配器会保持某种状态，并相应地处理传入的 BizTalk Server 消息。  
  
-   如果因为传输失败而无法发送一条消息，则指示 BizTalk Server 稍后重新提交。  
  
-   如果无法发送一条消息，因为仍在初始化适配器，BizTalk Server 消息排入队列。 如果初始化失败，则指示 BizTalk Server 稍后重新提交。  
  
## <a name="message-generation"></a>消息的生成  
 传输适配器，用于 TIBCO Rendezvous 的 BizTalk 适配器将忽略消息目标命名空间和根元素。 如果适配器发送消息，它将发送原样的有效负载。 如果适配器生成结构化的 TIBCO Rendezvous 消息，忽略根元素的名称 （一条消息不具有一个名称）。 在所有情况下，适配器使用的上下文属性以了解使用受发布消息时。  
  
 有关详细信息，请参阅[BizTalk Server 消息上下文属性 （发送处理程序）](../core/biztalk-server-message-context-properties-send-handlers.md)并[TIBCO Rendezvous 中的接收处理程序的数据类型映射](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)。  

## <a name="using-biztalk-to-send-messages"></a>使用 BizTalk 发送消息
用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器使用异步 API (Transport.Send)。 您可以指定适配器使用消息上下文属性发送的消息的类型：  
  
- **结构化**:适配器生成 TIBRVMSG_MSG 结构化的消息，根据从 BizTalk Server 收到的 XML 数据。 (*)  
  
  如果 BizTalk Server 发送字段名称长度超过 127 个字符的消息，用于 TIBCO Rendezvous 的 BizTalk 适配器会将名称截断到最大字段名称大小适用于 TIBCO Rendezvous 即 127。  
  
  如果`reply subject name`提供属性，它用于 TIBCO Rendezvous 消息上设置答复主题。 假定的接收端口设置为侦听回复，并将其转发到 BizTalk Server 中，或某些其他 TIBCO Rendezvous 程序负责回复。  
  
  三元数组 （服务、 守护程序、 网络） 组成传输配置。 一个空 （默认值） 传输配置导致通过默认传输对象发送一条消息。  
  
  如果代码页处于未指定，则适配器将使用 utf-8 编码 （代码页 65001）。 认证发送器端不支持消息。  
  
## <a name="see-also"></a>请参阅  
 [创建发送端口](../core/creating-send-ports2.md)   
 [创建 TIBCO Rendezvous 发送处理程序](../core/creating-tibco-rendezvous-send-handlers.md)