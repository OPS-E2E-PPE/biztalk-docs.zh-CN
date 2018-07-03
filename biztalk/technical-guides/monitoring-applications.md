---
title: 监视应用程序 |Microsoft Docs
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
ms.openlocfilehash: 0d1a7e4e0d4cb0f4e6899159da6c6c06a83e9165
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010288"
---
# <a name="monitoring-applications"></a>监视应用程序
设置 Microsoft System Center Operations Manager 来监视 BizTalk 应用程序通常可以分解为渐进式的四步过程，如下所示：  
  
1. **修改现有规则和/或复制到一个自定义管理包，用于监视自定义的 BizTalk 应用程序的规则**  
  
    您需要将这些规则的许多复制多次。 如果监视大量的文件共享，例如，这是这种情况。 在此方案中，将在说明字段中添加的文件共享地址复制一次每个文件共享的基本规则**条件**规则的选项卡。 通过添加地址，Operations Manager 将引发一个警报，以便每个单独的文件共享。 当您复制现有规则时，确保选择**启用**规则禁用此规则将覆盖，否则会收到重复警报。  
  
    您应将其添加到你创建的每个规则的另一个项上是知识信息**知识库**规则属性的选项卡。 此数据附加到 Operations Manager 会发出警报时引发的通知。 包括可帮助解决此错误的步骤时，此功能的强大功能就变得显而易见。  
  
2. **创建针对每个定义的规则的操作**  
  
    在创建或复制规则实际上是在过程中的第一步。 下一步是执行某些操作根据此规则。 如果没有执行任何操作不基于规则无关紧要，则该事件已不断监视。 最常执行的操作是为提醒操作员或管理员出现错误。 Operations Manager 还提供多项时触发某个事件时，可以使用其他操作。 这些操作包括：  
  
   -   启动脚本  
  
   -   发送简单网络管理协议 (SNMP) 陷阱 （在 SNMP 代理监视的网络和报表向网络控制台工作站上的各种设备中的活动）  
  
   -   将通知发送到通知组  
  
   -   执行命令或批处理文件  
  
   -   更新状态变量  
  
   -   传输文件  
  
   -   在托管的代码程序集上调用方法  
  
3. **创建迭代的进程来自动执行手动任务**  
  
    下一步是一个迭代过程和功能超出了基本的警报机制。 使用 Operations Manager 能够调用脚本和.NET 代码，自动根据引发的事件的手动任务的过程是一个功能强大且时间保存功能。 此示例是运行一个脚本来自动启动一个端口，如果已禁用 / 停止事件消息记录。 此过程是迭代的因为可以自动执行许多过程。  
  
4. **使用阈值规则来自动执行手动任务**  
  
    处理的下一步是超越反应警报限制，使用阈值规则。 默认情况下，BizTalk Server 管理包不包含任何阈值规则。 这是因为此类规则通常特定于自定义应用程序和每个应用程序不同。 阈值包含有关自定义应用程序的业务规则，并提供主动的监视系统。 可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供使用性能分析日志 (PAL) 的工具来定义规则的阈值模板。  
  
    此类阈值规则的示例是度量值时服务器上 Cpu 持续运行高于 75%在特定时间段内。 这可能表明您需要向外扩展系统。 尚未另一个示例是在其中创建阈值规则，用于监视一组唯一的计数器。 此规则然后可以调用代码的高需求期间初始化以前配置的备份服务器上的 BizTalk 主机实例。  
  
## <a name="see-also"></a>请参阅  
 [使用 System Center Operations Manager 2007 监视 BizTalk Server](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)