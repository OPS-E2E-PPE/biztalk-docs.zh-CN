---
title: 服务级别管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: add50343-5470-4db3-a029-c827523e2f2c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c67b66bf5a353b22193037d7112de8233982834b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394010"
---
# <a name="service-level-management"></a>服务级别管理
AmberPoint SMS 服务级别管理器提供了到特定的性能和可用性问题中企业级基于 SOA 的系统的可见性。 它将检测并跟踪指标，每个 Microsoft BizTalk Server 接收位置和发送端口。 这提供了实时的运行状况和状态指示，除了这些组件的正在进行的性能特征描述。 图 1 显示了与接收位置关联的度量值的显示。  
  
 ![AmberPoint 接收位置](../esb-toolkit/media/ch9-amberpointreceivelocation.gif "Ch9-AmberPointReceiveLocation")  
  
 **图 1**  
  
 **与接收位置关联的指标**  
  
 AmberPoint 实时运行分析允许用户设置阈值和系统超过关键事件的阈值，包括法规遵从性警告事件、 符合性冲突事件和后续返回到符合性时发送警报。 图 2 显示了的显示用户在其中配置服务级别协议并查看针对此服务级别协议生成的警报。  
  
 ![AmberPoint SLA](../esb-toolkit/media/ch9-amberpointsla.gif "Ch9-AmberPointSLA")  
  
 **图 2**  
  
 **若要配置服务级别协议和查看警报屏幕**  
  
 您可以建立服务级别管理器中的性能目标。 该软件然后跟踪各个消息、 来自特定用户的消息从组的用户，针对这些目标的性能进行测量。  
  
 此外可以配置日志记录策略，以指导 AmberPoint SMS 动态收集，以查看消息上下文和 BizTalk Server 中，通过传递的数据，如图 3 中所示。 你可以然后使用这些日志进行"动态上"故障排除、 技术分析的问题，以及存档遵守特定于行业的法规。  
  
 ![BizTalk Service Messages](../esb-toolkit/media/ch9-biztalkservicemessages.jpg "Ch9-BizTalkServiceMessages")  
  
 **图 3**  
  
 **BizTalk Server 服务消息日志文件**