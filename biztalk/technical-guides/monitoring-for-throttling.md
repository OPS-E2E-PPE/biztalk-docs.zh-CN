---
title: 监视限制 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d1d4c72-6942-4572-b27f-c58d37c94062
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d60b9f3deb77df927eb055b4504b809b421ae663
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299757"
---
# <a name="monitoring-for-throttling"></a>监视的限制
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包监视性能计数器指示限制状态的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 下面列出了几个关键因素了解限制。  
  
-   基于速率限制是每个主机和基于消息的速率入站和出站消息。  
  
-   传递限制 (**MsgBox-> 发送端口或业务流程**)，入站的速率是从消息框中接收消息的速率。 出站率是从该处消息成功传递通过适配器的速率。  
  
-   发布限制 (**接收适配器**或**业务流程-> MsgBox)，** 入站的速率是从适配器接收消息的速率和出站率是速率消息插入到 MsgBox。  
  
-   非数据库中的总消息的主机之间不存在任何限制的机制。  
  
 有关其他背景信息，请参阅主题[如何 BizTalk Server 实现主机限制](http://go.microsoft.com/fwlink/?LinkID=155286)(http://go.microsoft.com/fwlink/?LinkID=155286) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包含自限制，这有助于防止服务器基于各种参数的重载。 从操作方面而言，由临时重载引发的阻止并不是严重问题。 不过，在稳定的环境中不应发生持久性阻止，它说明在基础结构级可能出现问题。 管理包可使用性能阈值规则对此类持久性阻止条件进行主动监视。  
  
 四个规则的监视器的使用率/性能跟踪长时间内限制由四个不同的条件，按下表中所示。  
  
|条件|规则|  
|---------------|----------|  
|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务进程内存|警告： BizTalk Throttled 上经过很长的高进程内存|  
|正在处理的消息数|警告： BizTalk Throttled 上高进程内消息计数经过很长|  
|中的线程数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]过程|Warning: BizTalk Throttled on High Thread Count for a significant period（警告：由于线程数过多导致 BizTalk 长时间被阻止）|  
|大小[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库队列|Warning: BizTalk Throttled on High Database Size for a significant period（警告：由于数据库较大导致 BizTalk 长时间被阻止）|  
  
 这些阈值规则使用基于限制状态指示器性能计数器的数据提供程序。 有关这些性能计数器的详细信息，请参阅部分[性能计数器](http://go.microsoft.com/fwlink/?LinkId=157269)(http://go.microsoft.com/fwlink/?LinkId=157269) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
 这些规则被配置为一定数量的样本的平均值超过特定阈值时引发警报 （默认值为 30）。 例如，"警告： 上经过很长的高数据库大小的 BizTalk Throttled"是一种规则监视的所有限制状态[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]给定计算机中的进程。 此规则使用数据提供程序基于限制状态指示器性能计数器"BizTalk:Message 代理-高数据库大小。" 如果此性能计数器的值为 1，则相关进程将由于数据库规模过大而被阻止。  
  
 前面的规则配置为需要 30 样本的平均值和样本的平均值大于 0.6 时引发警报。 由于每个示例均为一分钟的时间间隔，这意味着在过去 30 分钟内，，该计算机中的至少一个或多个 BizTalk 服务器进程已由于高数据库大小、 60%的时间限制。  
  
 此试探性方法可能不适用于您的特定应用程序方案。 根据你的环境中的历史行为，如之前所述，你应配置这些规则使用正确的值通过以下任一方法：  
  
-   调整这些示例。  
  
-   调整阈值的值。  
  
-   如有必要，修改提供程序的采样的间隔。