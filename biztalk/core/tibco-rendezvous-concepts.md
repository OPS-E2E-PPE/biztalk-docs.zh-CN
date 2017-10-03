---
title: "TIBCO 集合概念 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certified message delivery
- subjects
- messages, defined
- transports, defined
- events
- virtual circuits
- direct communication
- batch mode
- queue group
- TIBCO Rendezvous, concepts
- distributed queue daemons
ms.assetid: 36060091-57dc-4125-8dca-23058d813deb
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 129fc0a864ac485919090476e153600adf5b4080
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-rendezvous-concepts"></a>TIBCO Rendezvous 概念
下表介绍 TIBCO Rendezvous 中的某些功能和概念。  
  
|概念|定义|  
|-------------|----------------|  
|**消息**|在程序进程或线程之间传递数据。 消息包含自描述数据字段。 程序可以操作消息字段、发送消息和接收消息。|  
|**事件**|创建事件对象以在明确的条件下有意向注册。 例如，调度侦听器事件将通知程序消息已经到达，调度计时器事件将通知程序已经过设置的时间间隔。<br /><br /> 程序定义事件回调函数来处理事件。|  
|**使用者**|消息与逻辑名称（主题）相关联。 程序侦听某个特定主题，或在特定主题下发布消息。|  
|**传输**|定义传递作用域、机制和协议的对象。|  
|**批处理模式**|TIBCO Rendezvous 传输对象支持使用批处理模式发布消息。 <br />默认模式是： 将消息发送越早越好。 计时器批处理模式是： 累积消息并发送缓冲区已满或计时器时间间隔到期时。|  
|**队列**|程序创建事件队列来组织事件。 队列保留准备进行处理的事件对象的序列。|  
|**队列组**|通过合并队列（使用不同的优先级）来自定义事件处理。|  
|**认证的消息传递**|确认将每个消息传递给每个已注册的收件人。 即时进程终止仍然发送消息，并使用基于文件的分类帐重新启动。<br /><br /> 认证的传递可向程序确保使每个认证的消息到达每个目标收件人（按发送顺序）。 无法实现传递时，发送和侦听程序将收到有关每个未传递消息的显式信息。<br /><br /> 程序确定每个消息的显式时间限制。<br /><br /> 在程序发送已认证的消息之后，TIBCO Rendezvous 软件会继续进行传递尝试，直到传递成功，或消息的时间限制过期为止。<br /><br /> TIBCO Rendezvous 认证的传递软件显示提示消息，以通知程序与传递相关的每个重要事件。<br /><br /> TIBCO Rendezvous 认证的传递软件将每个消息的状态都记录在分类帐中。 仅针对程序进程持续时间要求认证的程序应该使用基于进程的分类帐。 要求认证超越进程终止和程序重新启动的程序应该使用基于文件的分类帐。<br /><br /> 不允许认证的传递时，传递条件将下降至标准的 TIBCO Rendezvous 可靠传递语义。|  
|**分布式的队列守护程序**|通过多个进程分发服务。<br /><br /> TIBCO Rendezvous 后台程序完成整个网络中 TIBCO Rendezvous 程序进程间的信息路径。 程序尝试连接到 TIBCO Rendezvous 后台程序进程。 如果本地后台程序进程尚未运行，则程序将自动启动一个进程，并与其相连接。 TIBCO Rendezvous 后台程序将排列数据传输、数据包排序、确认回执、重新传输请求以及将信息调度到正确程序进程中的详细信息。 后台程序将从 TIBCO Rendezvous 程序中隐藏所有这些详细信息。 TIBCO Rendezvous 后台程序对于依赖它的程序几乎是不可见的。 程序使用 TIBCO Rendezvous 通信调用发送和接收信息，并且 TIBCO Rendezvous 后台程序会将信息放在合适位置。<br /><br /> 后台程序执行以下操作：<br /><br /> -传输来自程序进程到网络的出站消息。<br />-提供入站消息从网络到程序进程。<br />-筛选器使用者发送消息。<br />-可保护从操作系统特性，例如低级别的套接字的程序。|  
|**安全性**|TIBCO Rendezvous 支持基于证书或（用户，密码）的身份验证。|  
|**虚拟线路**|让 Rendezvous 通过独占和连续的监视连接在两个终端之间进行通信。|  
|**直接通信**|无中间 Rendezvous 后台程序进程的点对点通信。|  
  
## <a name="see-also"></a>另请参阅  
 [用于 TIBCO 会合的 BizTalk Adapter 中的消息](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md)   
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)