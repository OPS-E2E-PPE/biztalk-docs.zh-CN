---
title: TIBCO Enterprise Message Service 适配器功能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ede748ce-3f28-4942-b2bd-e38e5f1b0f54
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d923f439598f9eaa924924b6c7a628caf62d32e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361551"
---
# <a name="tibco-ems-adapter-features"></a>TIBCO EMS 适配器功能
用于 TIBCO Enterprise Message Service (EMS) 的 Microsoft BizTalk 适配器可以发布和订阅队列和主题由 TIBCO EMS，使用 BizTalk Server 和 TIBCO SDK。 该适配器以快速、 简单和可靠的方式集成 TIBCO EMS 消息。 交换 XML TIBCO EMS 服务器与 Microsoft 之间的数据格式[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供一个高度整合并且可靠的应用程序基础结构。 它提供了传输和接收适配器集成操作提供了端到端业务流程管理使用 XML 架构。  
  
## <a name="data-validation"></a>数据验证  
 用于 TIBCO EMS 以进程形式运行与作为本机 BizTalk Server 主机的 BizTalk 适配器紧密集成适配器，并验证时配置的端口配置。 它会验证数据尽可能多地-例如，有效的名称、 有效的数字，范围内有效。 它不会尝试建立连接。 因此，主机、 端口目标、 用户和密码不会验证直到运行时调用，在其中记录错误情况。  
  
## <a name="message-delivery"></a>消息传递  
 用于 TIBCO EMS 的 BizTalk 适配器可保证的一次性送达消息。 未达到 EMS 的消息被标记为挂起时，可重试。 时可能存在一些例外情况，例如，在执行时存在一个无效的端口配置。  
  
 适配器接受 EMS 消息类型的文本。  适配器支持转到 EMS 的消息的事务和由控制的事务支持[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
> [!NOTE]
>  用于 TIBCO EMS 的 BizTalk 适配器和 EMS 服务器之间的连接不安全。 不受提供的 TIBCO EMS SDK。  
  
 适配器支持所有标准的 JMS 属性和 EMS 扩展名。 这些属性放在可供业务流程的 BizTalk 消息上下文中。  
  
## <a name="general-adapter-features"></a>常规适配器功能  
 用于 TIBCO EMS 的 BizTalk 适配器提供了一种方法来交换 TIBCO EMS 系统和 BizTalk Server 之间的实时业务数据。 适配器允许 XML 应用程序与 TIBCO EMS 之间的交互。 这样，XML 用于与 TIBCO EMS 的入站和出站处理的应用程序。  
  
 适配器接受 XML 消息，以使 BizTalk Server 应用程序与 TIBCO EMS 使用以下方法之一进行通信：  
  
-   传输适配器，使用静态单向发送端口将消息发送到 TIBCO EMS。  
  
-   接收适配器使用静态单向接收端口接收来自 TIBCO EMS 的消息。  
  
### <a name="transmit-adapter-architecture-send--static-one-way"></a>传输适配器体系结构：发送 – 静态单向  
 在单向发送方案中，发送端口配置为将消息发送到队列/主题。 用于 TIBCO Enterprise Message Service 的 BizTalk 适配器将请求转发到指定队列/主题上的 TIBCO EMS 服务器。 该适配器将消息发送到 TIBCO EMS 系统使用 TIBCO EMS 通信协议。 TIBCO EMS 系统接收请求并执行业务逻辑。 若要呼叫 TIBCO EMS，必须以访问 TIBCO EMS 服务器的配置信息提供适配器。  
  
 下图显示了适配器的单向发送操作。  
  
 ![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")  
  
### <a name="receive-adapter-architecture-receive--static-one-way"></a>接收适配器体系结构：接收 – 静态单向  
 在单向接收方案中，接收位置配置为接收 EMS 队列/主题上的消息。 用于 TIBCO EMS 的 BizTalk 适配器侦听指定队列/主题上的消息，并将提交到 BizTalk Server 接收的消息。  
  
 下图显示了适配器的单向接收操作。  
  
 ![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")  
  
## <a name="see-also"></a>请参阅  
 [开发应用程序](../core/developing-applications5.md)   
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)