---
title: 监视应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4be98ba2-6acd-4dee-b6ea-db71bbd368f0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67c937ae0edb1698991ad111622a582ebfc64d76
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008974"
---
# <a name="monitoring-applications"></a>监视应用程序
设置 Microsoft System Center Operations Manager 来监视 BizTalk 应用程序通常可以分为渐进式四个步骤，如下所示：  
  
1.  **修改现有规则和/或复制到自定义管理包以监视自定义的 BizTalk 应用程序的规则**  
  
     你需要将许多这些规则复制多次。 如果监视大量的文件共享，例如，这是这种情况。 在此方案中，将在说明字段中添加上的文件共享地址复制一次每个文件共享的基本规则**条件**规则选项卡。 通过添加地址，Operations Manager 将引发警报的每个单独的文件共享。 复制现有规则时，确保选择**启用**规则禁用重写此规则，或者你将收到重复的警报。  
  
     你应该添加到每个规则，你创建的另一项位于知识库信息**知识库**选项卡的规则属性。 此数据会附加到 Operations Manager 会发出警报时，会引发通知。 包括可帮助解决该错误的步骤时，此功能的电源就变得清楚。  
  
2.  **创建每个定义的规则的操作**  
  
     创建或复制规则实际上是过程的第一步。 下一步是采取某项措施基于该规则。 如果没有任何操作根据规则则实际上并不重要事件不断监视。 最常执行的操作是警报的运算符或出现错误的管理员。 Operations Manager 还提供了多个触发事件时，可以使用其他操作。 这些操作包括：  
  
    -   启动脚本  
  
    -   发送的简单网络管理协议 (SNMP) 陷阱 （在 SNMP 代理监视的网络和网络控制台工作站的报表中的各种设备中的活动）  
  
    -   向通知组发送通知  
  
    -   执行的命令或批处理文件  
  
    -   更新状态变量  
  
    -   将文件传输  
  
    -   在托管的代码程序集上调用的方法  
  
3.  **创建迭代进程来自动执行手动任务**  
  
     下一步是一个迭代过程，并将移动超出基本警报机制。 借助 Operations Manager 能够调用脚本和.NET 代码，自动执行基于引发的事件的手动任务的过程是一种功能强大和时间的保存功能。 此示例是运行一个脚本来自动启动一个端口，如果记录已禁用 / 停止事件消息。 由于可以自动执行的许多过程，此过程是迭代。  
  
4.  **阈值规则用于自动执行手动任务**  
  
     处理的下一步是超越反应警报并可以使用阈值规则。 默认情况下，BizTalk Server 管理包不包含任何阈值规则。 这是因为此类规则通常特定于自定义应用程序，并且对于每个应用程序都有所不同。 阈值它包含有关自定义应用程序的业务规则，并提供一种监视系统的主动方法。 你可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供使用性能分析的日志 (PAL) 工具来定义规则的阈值模板。  
  
     此类阈值规则的示例是度量值在服务器上的 Cpu 一致地运行时 75%以上指定的时间段。 这可能表明需要横向扩展系统。 还有另一个示例是在其中创建监视一组唯一的计数器的阈值规则。 然后，此规则就会调用代码以在需求较高的时间段期间初始化以前配置的备份服务器上的 BizTalk 主机实例。  
  
## <a name="see-also"></a>另请参阅  
 [使用 System Center Operations Manager 2007 监视 BizTalk Server](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)