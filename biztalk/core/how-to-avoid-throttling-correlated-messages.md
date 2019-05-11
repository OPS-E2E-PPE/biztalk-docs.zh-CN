---
title: 如何避免阻止相关消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bfe47747-01e7-4e2f-bbd5-d5055cea001a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a8d093daa5b20e12ae2e6c56621180ede3d598a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387157"
---
# <a name="how-to-avoid-throttling-correlated-messages"></a>如何避免阻止相关的消息
可通过以下方式之一处理排队到 BizTalk Server 中，例如通过接收位置或业务流程的消息：  
  
- 它们可以激活订户 （即，业务流程或发送端口） 的新实例  
  
- 它们可以向现有订阅服务器实例通过相关路由。 有关相关的详细信息，请参阅[业务流程中使用相关性](../core/using-correlations-in-orchestrations.md)。  
  
  很多开发人员应考虑作为接收激活和相关的消息通过同一端口解决方案的解决方案的接收位置。 这是自然，这样可减少需要跟踪的消息的发件人的地址数。 但是，对于中的阻止行为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可能有利于激活消息流并且的流的相关消息分别在发生阻止时。  
  
  通过相同的消息激活和相关消息到达时接收位置，因为在主机级别应用阻止它们会处于同一阻止状态。 因此，所有到达的消息中的接收位置主机将被作为一个单元。 这不是问题对于许多方案，但有些情况下，限制相关与激活一起可能导致系统死锁的类型。  
  
## <a name="example"></a>示例  
 例如，假设您有一个包含业务流程的接收一次激活，并用它来初始化相关集，然后接收 10 沿用相关集的其他消息的保护方案。 此外，假定在负载下，积压累积了假脱机中激活的组合作为和相关消息到达时导致的限制可以接收的消息量。 遗憾的是，相关消息会受到限制以及激活，这将减慢业务流程，从而导致进一步的积压和额外的阻止的完成。 再进一步，这将导致系统的向下到接近零的吞吐量。  
  
 通过拆分单个接收位置为两个-一个用于激活，一个用于关联-和位置配置于不同的主机中的数据库大小阻止阈值可以保持在低于相关，将导致降低整体，积压而保持消息顺畅流动。  
  
 因此，您可能会问:"为什么不能只是提出数据库大小阈值单个接收位置来解决该问题？" 答案是，您可以但它不会始终生成所需的行为。 限制存在主要是为了防止系统过载。 如果引发阈值得过高，或将它们全都禁用，将消除上述保护。  
  
## <a name="recommendation"></a>建议  
 如上面所述的方案的最佳做法是对阻止相关消息敏感，是到单独的主机，它们可以单独执行阻止将接收位置。  
  
 当接收位置配置单独的主机时，设置数据库大小阻止阈值为较低值的数据库大小阻止阈值使用业务流程或相关的主机的接收位置使用的主机。  
  
 如果您知道您的负载将永远不会高于系统的最大可承受吞吐量 (MST) 或者吞吐量峰值在峰值事件之间可恢复，则升高阻止阈值也将行之有效，但可能不保持为高的吞吐量作为使用单独的主机用于激活和相关。