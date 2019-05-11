---
title: 字符编码 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a0c21c8-3318-4533-9734-89302527cb67
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7418a6e6d1321450e0156fedc38fb5cb69a260e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357472"
---
# <a name="character-encoding"></a>字符编码
TIBCO Enterprise Message Service (EMS) 支持不同的字符编码中传输到 EMS 的 BizTalk 适配器用于 TIBCO EMS 的消息。 使用默认的 utf-8 编码进行编码的消息。 适配器接收消息时，确定消息的编码，并提供到消息前将相应的字符串转换为 utf-8 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 所有字符转换中都使用 Microsoft.NET Framework 类;因此，适配器支持通过此相同框架提供的字符转换。  
  
## <a name="running-in-a-clustered-environment"></a>在群集环境中运行  
 发布到队列的消息使用者以预先确定的 EMS 服务器的顺序使用 — 在群集中的只有一个适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中接收的消息。 队列可以配置为*独占*。 这意味着只有注册自身以使用该队列消息的第一个适配器接收的消息。 EMS 服务器仅将消息发送到其他使用者如果独占使用者未确认已接收到消息。 独占队列配置在 EMS 配置中执行，而不是可配置的客户端。  
  
> [!NOTE]
>  关于订阅主题： 因为中的所有适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组的配置都相同，它们都订阅的消息和每个主题订阅接收消息。  
  
## <a name="transaction-support"></a>事务支持  
 适配器提供支持的事务时所需的业务流程发送端口。 不没有 EMS 服务器不支持任何事务时该适配器侦听消息;但是，适配器将确认接收到所有消息从 EMS 消息成功提交到后的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 EMS 重新未确认的消息发送到适配器。  
  
## <a name="see-also"></a>请参阅  
 [用于 TIBCO EMS 的 BizTalk 适配器中的安全性](../core/security-in-biztalk-adapter-for-tibco-ems.md)   
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)