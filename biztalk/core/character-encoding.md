---
title: "字符编码 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transaction support
- character encoding
- encoding characters
- messages, character encoding
ms.assetid: 0a0c21c8-3318-4533-9734-89302527cb67
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19d3204cae7b82e9d18325b223e5c3b7a2d40808
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="character-encoding"></a>字符编码
TIBCO Enterprise Message Service (EMS) 支持在由 TIBCO EMS 的 BizTalk 适配器传输到 EMS 的消息中使用不同的字符编码。 消息是使用默认的 UTF-8 进行编码的。 当接收消息，适配器确定消息编码，以及提供到的消息之前将相应的字符串转换为 utf-8 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 所有字符转换都使用 Microsoft .NET Framework 类；因此，适配器支持通过此相同框架转换字符。  
  
## <a name="running-in-a-clustered-environment"></a>在群集环境中运行  
 发布到队列消息由 EMS 服务器预先确定的顺序的使用者 — 在群集中的只有一个适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中接收的消息。 队列可以配置为*独占*。 这意味着只有注册自身以使用该队列中的消息的第一个适配器接收消息。 仅当独占使用者未确认接收到消息时，EMS 服务器才将消息发送给其他使用者。 独占队列配置是在 EMS 配置中执行的，不能在客户端对其进行配置。  
  
> [!NOTE]
>  有关主题的订阅： 因为中的所有适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组配置相同，它们所有订阅的消息，以及每个主题订阅接收消息。  
  
## <a name="transaction-support"></a>事务支持  
 当业务流程发送端口需要时，适配器将为事务提供支持。 当适配器侦听消息时，EMS 服务器并不支持任何事务；但是，将消息成功提交到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 后，适配器将确认从 EMS 接收到所有消息。 EMS 将未经确认的消息重新发送到适配器。  
  
## <a name="see-also"></a>另请参阅  
 [用于 TIBCO EMS 的 BizTalk Adapter 中的安全性](../core/security-in-biztalk-adapter-for-tibco-ems.md)   
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)