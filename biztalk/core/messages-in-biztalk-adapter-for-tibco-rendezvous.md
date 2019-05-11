---
title: TIBCO Rendezvous 适配器中的消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12699550-22e7-4a11-a024-2302570970af
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 686b8f5764c0d4832770f777cdf65b5287bd848e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394511"
---
# <a name="messages-in-biztalk-adapter-for-tibco-rendezvous"></a>用于 TIBCO Rendezvous 的 BizTalk 适配器中的消息
用于 TIBCO Rendezvous 的 BizTalk 适配器提供之间的双向连接[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 TIBCO Rendezvous。 此适配器使用 TIBCO Rendezvous API 和 BizTalk 适配器框架 API 来提供紧密集成。  
  
## <a name="about-tibco-rendezvous"></a>有关 TIBCO Rendezvous  
 TIBCO Rendezvous 是为企业应用程序集成 (EAI) 提供消息总线的程序。 TIBCO 提供消息传送 Api 在 C 中， C++、 Java、 Visual Basic 和 Microsoft.NET framework，若要接收 Microsoft Office Excel 工作表和所选的其他应用程序上的数据源。 有关详细信息，请参阅[TIBCO Rendezvous 概念](../core/tibco-rendezvous-concepts.md)。  
  
## <a name="message-passing"></a>消息传递  
 消息传递的基本概念是相当简单：  
  
- 消息具有单个主题，其中用句点分隔的元素组成。 一条消息发送到单个的 Rendezvous 后台程序，尽管可能最终需要广播其他守护程序。  
  
- 侦听器宣布其感兴趣的后台程序 （使用基本的通配符工具） 的主题。 如果两个守护程序连接到对方，或者它们实际上是同一个守护程序拥有匹配主题的消息传递到它。  
  
  重要"的企业"功能分层到此，如果所需-，容错/可靠或 Certified 选项可能进行-所有已通过基础的基本消息实现。  
  
  消息本身可看作是键入的名称-值字段或数字-值字段 （在消息中的两个标识机制可以混合和匹配的某些限制）。 消息本身可包含子消息，可以包含子消息。  
  
  使用者名称包含一个或多个由圆点字符 （句点） 分隔的元素。 元素实现的信息的结构反映在应用程序系统中的主题名称层次结构。 以下字符串是有效的主题名称的示例：  
  
- 运行。主页  
  
- RUN.for.Elected_Office  
  
  用于 TIBCO Rendezvous 的 BizTalk 适配器使用 TIBCO Rendezvous SDK 将消息发布到 TIBCO Rendezvous 主题并注册 TIBCO Rendezvous 事件。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的相关的类托管在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。 单独的进程 （运行时代理） 启动，并且可作为 Rendezvous 程序，.NET Framework 远程处理用于这两个之间交换消息。  
  
- 信息级警告级别和错误级别的消息发送到 Windows 事件日志。  
  
- 所有级别，包括调试级别消息被都发送到 Windows 跟踪日志。  
  
## <a name="transmitter"></a>发送器  
 用于 TIBCO Rendezvous 的 BizTalk 适配器将启动一个运行时代理，每个发送端口。 TIBCO Rendezvous.NET Framework API 只允许设置字符编码在全局范围内。 因此，一个端口配置选项是一个代码页编号。 通过启动的每个代码页不同的进程，适配器可以提供更好地支持全球化。  
  
## <a name="receiver"></a>接收方  
 用于 TIBCO Rendezvous 启动一个运行时代理，每个 BizTalk 适配器接收位置。  
  
## <a name="transactions"></a>事务  
 TIBCO Rendezvous 产品不是事务性的。 需要一个单独的产品，TIBCO Rendezvous TX。 用于 TIBCO Rendezvous 的 BizTalk 适配器不在此版本中支持事务。  
  
## <a name="security"></a>安全性  
 TIBCO Rendezvous 仅支持 TIBCO Rendezvous 程序和守护程序之间的身份验证。 它不会执行授权或加密。 需要一个单独的产品，TIBCO Rendezvous DataSecurity。  
  
## <a name="see-also"></a>请参阅  
 [TIBCO Rendezvous 概念](../core/tibco-rendezvous-concepts.md)   
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)