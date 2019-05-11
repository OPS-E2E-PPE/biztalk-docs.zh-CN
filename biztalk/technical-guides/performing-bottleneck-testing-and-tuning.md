---
title: 执行瓶颈测试并优化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95d41d95-3a76-4eb0-b07d-14c6b6dccdaa
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57d5d46bfa71fe6502b1831a8851e2ff448821d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291314"
---
# <a name="performing-bottleneck-testing-and-tuning"></a>执行瓶颈测试并优化
您应该完成性能测试来确定系统中的瓶颈和相应地调整系统。  
  
## <a name="testing-a-subsystem"></a>测试一个子系统  
 确定系统瓶颈的最佳做法是在整个系统的子集上运行性能测试例如：  
  
- 建立相互发送或接收来自消息的外部系统的基线性能参数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
- 登记业务流程，但没有启动它们。 放入站的队列/文件位置的消息，并允许入站接收适配器清空队列/文件位置和将消息发布到 MessageBox 数据库。 这样，您能够隔离在接收端口，以确定其最大持续输入的速率。  
  
- 消息拉取后到 MessageBox 数据库，停止接收适配器、 启用业务流程和/或发送适配器，然后测量在哪个业务流程的速率和/或发送适配器所处理的消息。  
  
## <a name="testing-the-end-to-end-system"></a>测试端到端系统  
 前面部分中所述测试的输入和输出费率是隔离应用程序子系统的性能的有效方法，尽管它没有描述的端到端性能。 此外应测试端到端性能，因为无法识别一些瓶颈，直到争用同一共享资源 （例如，MessageBox 数据库） 的多个资源开始。  
  
 若要生成针对负载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，请考虑使用 Microsoft BizTalk LoadGen 2007 工具。 下载[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)。  
  
 若要生成和分析的性能报告[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，请考虑使用性能分析日志 (PAL) 的工具。 有关 PAL 工具的详细信息，请参阅[使用性能分析的日志 (PAL) 工具](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)。  
  
## <a name="what-developers-operators-and-administrators-should-know"></a>哪些开发人员、 运算符和管理员应了解  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 开发人员应上也理解[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能特征和优化。 操作员和管理员应了解 MessageBox 数据库向外缩放方面，SAN 优化、 网络优化和 SQL Server 数据库优化 (有关示例，请参阅[SQL Server 设置，不应更改](../technical-guides/sql-server-settings-that-should-not-be-changed.md))。 开发人员、 运算符和管理员应了解如何优化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]高吞吐量和低延迟。