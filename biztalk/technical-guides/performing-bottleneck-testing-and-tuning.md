---
title: 执行测试和优化的瓶颈 |Microsoft 文档
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
ms.openlocfilehash: 27d2e0ed3c8298287471b60d87b199fcfc800e61
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008910"
---
# <a name="performing-bottleneck-testing-and-tuning"></a>执行测试和优化的瓶颈
应完成性能测试来确定在系统中的瓶颈和相应地调整系统。  
  
## <a name="testing-a-subsystem"></a>测试子系统  
 确定系统瓶颈的最佳做法是例如在整个系统的子集上运行性能测试：  
  
-   建立的外部系统的将消息发送到或从收到消息的基线性能参数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
-   登记业务流程，但不是会开始使用它们。 放到入站的队列/文件位置的消息，并允许入站接收队列/文件位置的适配器漏和将消息发布到 MessageBox 数据库。 这样，你可以隔离你接收端口以确定其最大持续输入的速率。  
  
-   消息会拉取到 MessageBox 数据库后, 停止接收适配器、 启用业务流程和/或发送适配器，然后测量的业务流程的速度和/或发送适配器所处理的消息。  
  
## <a name="testing-the-end-to-end-system"></a>测试端到端系统  
 中前面部分所述测试的输入和输出速率是一种有效来隔离性能的应用程序子系统，尽管它未介绍端到端性能。 你还应该测试端到端性能，因为无法识别某些瓶颈，直至多个资源开始争用同一共享资源 （例如，MessageBox 数据库）。  
  
 若要生成针对负载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境，请考虑使用 Microsoft BizTalk LoadGen 2007 工具。 下载[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)。  
  
 若要生成和分析的性能报表[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境，请考虑使用性能分析的日志 (PAL) 工具。 有关 PAL 工具的详细信息，请参阅[使用性能分析的日志 (PAL) 工具](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)。  
  
## <a name="what-developers-operators-and-administrators-should-know"></a>应该知道哪些开发人员、 运算符和管理员  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发人员应也熟悉如何在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能特征和优化。 操作员和管理员应了解 MessageBox 数据库向外扩展方面，SAN 优化、 网络优化和 SQL Server 数据库优化 (例如，请参阅[SQL Server 设置，不应更改](../technical-guides/sql-server-settings-that-should-not-be-changed.md))。 开发人员、 运算符和管理员应了解如何优化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]高吞吐量和低延迟。