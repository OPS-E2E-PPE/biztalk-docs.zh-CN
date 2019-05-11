---
title: TIBCO Rendezvous 概念 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 36060091-57dc-4125-8dca-23058d813deb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fad646b84cf904481a181b0ef9c6870b655bee3f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314125"
---
# <a name="tibco-rendezvous-concepts"></a>TIBCO Rendezvous 概念

## <a name="concepts-explained"></a>所述概念
下表介绍的一些功能和 TIBCO Rendezvous 中的概念。  
  
|概念|定义|  
|-------------|----------------|  
|**消息**|执行程序进程或线程之间的数据。 消息包含自描述数据字段。 程序可以操作消息字段、 将消息，发送和接收消息。|  
|**事件**|创建用于注册重要条件感兴趣的 event 对象。 例如，调度侦听器事件通知的程序的已接收到消息;调度计时器事件通知其时间间隔已过的程序。<br /><br /> 程序定义事件回调函数来处理事件。|  
|**Subjects**|消息相关联的逻辑名称 （主题）。 程序侦听某个特定主题，或特定主题下发布消息。|  
|**传输**|定义传递作用域、 机制和协议的对象。|  
|**批处理模式**|TIBCO Rendezvous 传输对象支持批处理模式发布的消息。 <br />默认模式是：尽快发送消息。 计时器批处理模式是：积累消息并发送缓冲区已满或计时器间隔过期时。|  
|**Queue**|程序创建事件队列来组织事件。 队列保留准备就绪待处理的事件对象的序列。|  
|**队列组**|通过合并队列 （使用不同的优先级） 来自定义事件处理。|  
|**认证的消息传递**|确认每个消息传递给每个已注册的收件人。 尽管进程终止，并通过使用基于文件的分类帐重新启动消息传递。<br /><br /> 认证的传递可确保程序每个认证的消息到达每个目标的收件人-发送的顺序。 不可能传递时，发送和侦听程序将收到有关每个未传递消息的显式信息。<br /><br /> 程序确定明确的时间限制为每个消息。<br /><br /> 在程序发送已认证的消息之后，TIBCO Rendezvous 软件将继续多次传送尝试，直到传递成功，或超过消息的时间限制。<br /><br /> TIBCO Rendezvous 认证的传递软件显示提示消息，以通知程序与传递相关的每个重要事件。<br /><br /> TIBCO Rendezvous 认证的传递软件记录在分类帐的每个消息状态。 仅针对程序进程的持续时间要求认证的程序应使用基于进程的分类帐。 要求认证超越进程终止和程序重新启动的程序使用基于文件的分类帐。<br /><br /> 如果不允许认证的传递，传递条件将下降至标准的 TIBCO Rendezvous 可靠传递语义。|  
|**分布式的队列守护程序**|通过多个进程分发服务。<br /><br /> TIBCO Rendezvous 后台程序完成整个网络的 TIBCO Rendezvous 程序进程之间的信息路径。 程序尝试连接到 TIBCO Rendezvous 后台程序进程。 如果本地后台程序进程尚未运行，该程序将自动启动一个，并连接到它。 TIBCO Rendezvous 后台程序排列数据传输、 数据包排序、 确认回执、 重新传输请求和调度到正确程序进程的信息的详细的信息。 守护程序将隐藏从 TIBCO Rendezvous 程序的所有这些详细信息。 TIBCO Rendezvous 后台程序几乎是不可见的程序依赖于它。 程序发送和接收信息使用 TIBCO Rendezvous 通信调用和 TIBCO Rendezvous 后台程序会将适当的位置信息。<br /><br /> 守护程序执行以下任务：<br /><br /> -将传输到网络的出站消息从程序进程。<br />-提供入站消息从网络到程序进程。<br />-筛选主题寻址消息。<br />-保护程序从操作系统特性，例如低级别套接字。|  
|**安全性**|TIBCO Rendezvous 支持基于证书或 （用户、 密码） 身份验证。|  
|**虚拟线路**|功能 Rendezvous 通过独占和连续监视连接的两个终端之间的通信。|  
|**直接通信**|点到点通信，而无需中间 Rendezvous 后台程序进程。|  
  
## <a name="see-also"></a>请参阅  
 [用于 TIBCO Rendezvous 的 BizTalk 适配器中的消息](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md)   
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)