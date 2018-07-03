---
title: 步骤 5： 执行分级负载模式测试以确定最大可承受吞吐量 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8056ced6-1f04-4be2-878a-48a427a93dad
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 223d8e444bbfc05960f2266e0c23eb0f1a90d9ee
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987566"
---
# <a name="step-5-perform-step-load-pattern-tests-to-determine-maximum-sustainable-throughput"></a>步骤 5： 执行分级负载模式测试以确定最大可承受吞吐量
确定 BizTalk Server 解决方案具有 Visual Studio 负载测试的最大可承受吞吐量 (MST) 的最简单方法是执行分级负载模式并比较每秒总文档每秒处理接收的文档总数. 只要每秒处理的平均总文档是大于或等于每秒的测试的持续时间接收到的平均总文档，则被视为负载可承受。 如果每个接收的文档总数的平均第二个是大于每秒的测试的持续时间处理的平均总文档则负载不会被视为可承受，并且这将出现的相应增长的值Biztalk: Message Box: General Counters\Spool Size 计数器。 随着时间推移，当 BizTalk Server 应用程序接收多于其处理的更多文档，未处理的文档将会累积在 MessageBox 数据库，这将最终引入的阻止条件，并大大降低的性能BizTalk Server 应用程序。  
  
## <a name="configure-the-load-test-with-a-step-load-pattern-appropriate-for-your-application"></a>使用分级负载模式适用于你的应用程序中配置负载测试  
 按照本主题中的步骤[第 3 步： 创建负载测试对执行多个单元测试同时](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md)若要创建的负载测试使用分级负载模式。 影响 BizTalk Server 应用程序能够及时处理文档的能力的因素包括：  
  
- **在组中的 BizTalk Server 计算机的数量**-其他 BizTalk 服务器提供额外的处理功能。  
  
- **正在处理的消息大小**-更大的消息需要额外的处理资源。  
  
- **文档映射的量执行**-映射需要额外的处理资源。  
  
- **接收或发送管道的应用程序所需**。 -复杂的管道需要额外的处理资源。  
  
- **适配器和/或 BizTalk Server 应用程序使用的加速器**– 某些适配器和/或加速器需要比其他更多处理资源。  
  
- **消息跟踪所需的量**– 消息跟踪是需要消耗大量资源。  
  
- **数和在 BizTalk Server 应用程序中运行的业务流程的复杂性**– 业务流程可以是消耗大量的资源。  
  
  在配置步骤负载模式测试时，修改为指定的值**开始用户计数**并**最大用户计数**以确保能轻松地开始用户计数为指定的消息数由 BizTalk Server 处理对时间和同样，为最大用户计数指定的消息数的应用程序是多个 BizTalk Server 应用程序可以处理随着时间的推移。 请参阅[添加负载测试和配置负载测试方案、 计数器集和运行设置](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_StepLoadTest)有关编辑负载测试的负载模式设置信息。  
  
## <a name="ensure-that-the-correct-test-settings-are-used-for-the-step-pattern-load-test"></a>确保使用正确的测试设置为步骤模式负载测试  
 配置要使用的负载测试**测试设置**中创建[添加到运行测试并远程收集数据的解决方案测试设置文件](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_TestSettings)。  
  
## <a name="configure-the-load-test-with-the-appropriate-performance-counters-and-run-the-step-pattern-load-test"></a>为负载测试配置与相应的性能计数器和运行步骤模式的负载测试  
 按照中的步骤[自定义计数器集添加到度量值 BizTalk Server 关键性能指标 (KPI)](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_BTSCounters)添加必要的 BizTalk Server 性能计数器用于测量的 BizTalk Server 性能应用程序，并确定在哪个点 BizTalk Server 应用程序不再是可以维护创建的负载测试代理的消息负载。 这将通过 biztalk: Message Box: General Counters\Spool Size 计数器增加的值可以看到在 Spool 表中的消息积压的应计出现。 如果此计数器的值开始显著增加然后你可能已超过 MST 的 BizTalk Server 应用程序。 当您确定的 BizTalk Server 应用程序不再能够处理多条消息因为它接收到，记下的文档的 received/Sec 时出现这种情况的消息数。 请务必记下此值，因为主题[第 6 步： 执行常量负载模式测试验证最大可承受吞吐量](../technical-guides/step-6-complete-load-pattern-tests-to-verify-maximum-sustainable-throughput.md)将介绍如何使用"常数用户计数"值运行常量模式负载测试这就是某种程度上小于最大可承受文档秒接收的值。 这样做是为了验证 BizTalk Server 应用程序能够随着时间的推移处理这个数量的消息。 若要查看的计数器集的值，请首先通过右键单击测试名称 (例如 BTS_Messaging_Step) 启动负载测试，然后单击**运行测试**菜单选项。 性能计数器被初始化并在负载测试开始后，Visual Studio 会自动切换到图形窗口，这样即可同时显示从 1 到 4 个关系图的焦点。 如果你主要想要仅查看关键性能指标，如中所定义[自定义计数器集添加到度量值 BizTalk Server 关键性能指标 (KPI)](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_BTSCounters)，单击**面板**下拉列表从负载测试菜单，然后选择的选项**一个面板**。 然后单击该图表并选择顶部的下拉列表**关键指标**中实时显示关键性能指标的值。  
  
> [!NOTE]  
>  因为某些默认计数器值将显示在**关键指标**关系图，因为您可能希望显示添加到你的自定义计数器集的计数器值，你可能想要首先手动删除每个中显示的计数器**关键指标**关系图，然后手动从自定义计数器集添加计数器。 例如，至少，你会想要至少计数器下表中向图形添加以确定 BizTalk Server 环境如何处理负载，以及任何瓶颈可能发生的位置：  
  
|计数器类别|计数器|实例|Computer|  
|----------------------|-------------|--------------|--------------|  
|BizTalk:Message Box:General Counters |后台处理大小|*BizTalk Server Messagebox 数据库*:*存储 BizTalk Server Messagebox 数据库的 SQL Server 实例*|使用 BizTalk Server 管理控制台在组中任何 BizTalk Server 安装。|  
|BizTalk:Messaging|Documents received/Sec|RxHost （或接收主机的名称）|*BizTalk Server 组中的 BizTalk Server 计算机 #1*|  
|BizTalk:Messaging|Documents received/Sec|RxHost （或接收主机的名称）|*BizTalk Server 组中的 BizTalk Server 计算机 #2*|  
|BizTalk:Messaging|Documents received/Sec|RxHost （或接收主机的名称）|*BizTalk Server 组中的 BizTalk Server 计算机 #n*|  
|BizTalk:Messaging|处理的文档数/秒|TxHost （或发送主机的名称）|*BizTalk Server 组中的 BizTalk Server 计算机 #1*|  
|BizTalk:Messaging|处理的文档数/秒|TxHost （或发送主机的名称）|*BizTalk Server 组中的 BizTalk Server 计算机 #2*|  
|BizTalk:Messaging|处理的文档数/秒|TxHost （或发送主机的名称）|*BizTalk Server 组中的 BizTalk Server 计算机 #n*|  
|处理器|% Processor Time|_Total|*BizTalk Server 组中的 BizTalk Server 计算机 #1*|  
|处理器|% Processor Time|_Total|*BizTalk Server 组中的 BizTalk Server 计算机 #2*|  
|处理器|% Processor Time|_Total|*BizTalk Server 组中的 BizTalk Server 计算机 #n*|  
|处理器|% Processor Time|_Total|*包含 BizTalk Server 数据库的 SQL Server 实例*|