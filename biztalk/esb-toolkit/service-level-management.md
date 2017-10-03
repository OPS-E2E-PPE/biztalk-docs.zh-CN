---
title: "服务级别管理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: add50343-5470-4db3-a029-c827523e2f2c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86b7ba1672660af2a68a5d193729a0a9009173d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="service-level-management"></a>服务级别管理
AmberPoint SMS 服务级别管理器提供了到特定的性能和企业级 SOA 基于系统内的可用性问题的可见性。 它会检测并为每个 Microsoft BizTalk Server 接收位置和发送端口跟踪度量值。 这可实时运行状况和状态指示，除了这些组件的正在进行的性能特征描述。 图 1 显示与接收位置相关联的度量值的显示。  
  
 ![AmberPoint 接收位置](../esb-toolkit/media/ch9-amberpointreceivelocation.gif "Ch9 AmberPointReceiveLocation")  
  
 **图 1**  
  
 **接收位置与关联的度量值**  
  
 AmberPoint 实时运行分析允许用户设置阈值和系统跨越严重事件阈值，包括符合性警告事件、 符合性冲突事件和后续返回到符合性时发送警报。 图 2 显示的显示，其中用户配置服务级别协议和查看针对此服务级别协议生成的警报。  
  
 ![AmberPoint SLA](../esb-toolkit/media/ch9-amberpointsla.gif "Ch9 AmberPointSLA")  
  
 **图 2**  
  
 **屏幕以配置服务级别协议和查看警报**  
  
 你可以建立服务级别管理器中的性能目标。 软件然后跟踪各个消息、 来自特定用户的消息从组的用户，来衡量针对这些目标的性能。  
  
 你还可以配置日志记录策略，以指导 AmberPoint SMS 动态收集并检查消息上下文和 BizTalk Server 中，通过传递数据，如图 3 中所示。 你可以然后使用这些日志进行故障排除"即时上"、 技术分析问题，以及进行存档符合特定于行业的法规。  
  
 ![BizTalk 服务消息](../esb-toolkit/media/ch9-biztalkservicemessages.jpg "Ch9 BizTalkServiceMessages")  
  
 **图 3**  
  
 **BizTalk Server 服务消息日志文件**