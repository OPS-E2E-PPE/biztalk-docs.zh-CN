---
title: 监视带宽限制 |Microsoft Docs
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
ms.openlocfilehash: 6c175c2668a3d2f8bdf0d4088d51bfd76d43ca8d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305541"
---
# <a name="monitoring-for-throttling"></a>监视带宽限制
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包监视性能计数器指示的阻止状态[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 下面列出了关于限制需要了解一些关键因素。  
  
- 基于速率的限制是每个主机和基于消息的速率入站和出站消息。  
  
- 有关送达阻止功能 (**MsgBox-> 发送端口或业务流程**)，入站的率是从消息框中接收消息的速率。 出站速率是在该消息成功传递通过适配器的速率。  
  
- 为发布阻止功能 (**接收适配器**或**业务流程-> MsgBox)，** 入站的率是从适配器接收消息的速率，出站速率速率消息插入到 MsgBox。  
  
- 数据库中的总消息以外的主机之间不存在任何阻止机制。  
  
  有关更多背景信息，请参阅主题[如何 BizTalk Server 实现主机阻止](http://go.microsoft.com/fwlink/?LinkID=155286)(<http://go.microsoft.com/fwlink/?LinkID=155286>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 集成了自阻止功能，这有助于防止服务器基于各种参数的重载。 由临时重载引发的阻止不是严重问题。 持久性阻止，但是，不应出现在稳定的环境，可能表示底层基础结构级别的问题。 管理包提供了性能阈值规则与此类持久性阻止条件进行主动监视。  
  
  四个使用率/性能跟踪规则监视的扩展限制下表中所示，由四个不同的条件导致的时间段。  
  
|                                                     条件                                                     |                                        规则                                         |
|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|
|     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务进程内存     |     警告：BizTalk 上长时间的高进程内存限制      |
|                                        正在处理的消息数                                         | 警告：BizTalk 限制上高进程内消息计数相当长一段 |
| 中的线程数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]过程 |      警告：BizTalk 限制在相当长一段的高的线程计数       |
|  大小[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库队列   |      警告：BizTalk 在相当长一段高数据库大小限制      |
  
 这些阈值规则使用基于阻止状态指示器性能计数器的数据提供程序。 有关这些性能计数器的详细信息，请参阅部分[性能计数器](http://go.microsoft.com/fwlink/?LinkId=157269)(<http://go.microsoft.com/fwlink/?LinkId=157269>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
 这些规则配置为超过某个数目的样本的平均值超出特定阈值时引发警报 （默认值为 30）。 例如，"警告：BizTalk 受到限制高数据库大小进行相当长一段"是规则用来监视所有的阻止状态[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]给定计算机中的进程。 该规则使用基于阻止状态指示器性能计数器"Agent-high 数据库大小。"的数据提供程序 如果此性能计数器的值为 1，然后由于数据库规模过大而阻止关联的进程。  
  
 前面的规则配置为需要 30 个样本的平均并发出警报，如果样本的平均值超过 0.6。 由于每个采样的时间间隔为一分钟，这意味着在过去的 30 分钟，该计算机中的至少一个或多个 BizTalk Server 进程已由于数据库规模过大，60%的时间限制。  
  
 此启发式方法可能并不适合特定应用程序方案。 根据您的环境中的历史行为，如之前所述，应配置正确的值与这些规则通过以下任一方法：  
  
-   调整这些示例。  
  
-   调整阈值的值。  
  
-   如有必要，修改的提供程序的采样时间间隔。