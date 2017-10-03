---
title: "步骤 5： 执行步骤负载模式测试以确定最大可持续吞吐量 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8056ced6-1f04-4be2-878a-48a427a93dad
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f9794634b5a782ef6d9bce4e819e759fd47ba1a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-perform-step-load-pattern-tests-to-determine-maximum-sustainable-throughput"></a>步骤 5： 执行步骤负载模式测试以确定最大可持续吞吐量
确定 BizTalk Server 解决方案与 Visual Studio 负载测试的最大可持续吞吐量 (MST) 的最简单方法是执行分级负载模式并比较每秒到每秒处理的总文档接收的总文档. 只要每秒处理的平均总文档是大于或等于每秒的测试的持续时间接收的平均总文档，然后考虑负载可持续。 如果每个接收的总文档的平均值第二个是大于每秒的测试持续时间内处理的平均总文档则负载不会被视为可持续的并且这将出现的值中的相应增长BizTalk:Message Box: General Counters\Spool 大小计数器。 随着时间推移，当 BizTalk 服务器应用程序收到多个文档不是它可以处理，未处理的文档将累积在 MessageBox 数据库中，将最终引入限制条件，并大幅降低性能BizTalk Server 应用程序。  
  
## <a name="configure-the-load-test-with-a-step-load-pattern-appropriate-for-your-application"></a>使用分级负载模式适用于你的应用程序配置负载测试  
 按照本主题中的步骤[步骤 3： 创建负载测试对执行多个单元测试同时](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md)创建负载测试使用分级负载模式。 影响及时处理文档 BizTalk 服务器应用程序的能力的因素包括：  
  
-   **你的组中的 BizTalk Server 计算机的数量**-其他 BizTalk 服务器提供额外的处理能力。  
  
-   **正在处理的消息大小**-更大的消息需要额外的处理资源。  
  
-   **文档映射量执行**-映射都要求额外的处理资源。  
  
-   **接收或发送应用程序所需的管道**。 -复杂的管道需要额外的处理资源。  
  
-   **适配器和/或 BizTalk Server 应用程序使用的快捷键**– 某些适配器和/或快捷键需要比其他更多处理资源。  
  
-   **所需的消息跟踪量**– 消息跟踪，则占用大量资源。  
  
-   **在 BizTalk Server 应用程序中运行的业务流程的数量和复杂度**– 业务流程可以是消耗大量的资源。  
  
 在配置步骤负载模式测试时，修改为指定的值**开始用户计数**和**最大用户计数**以确保为开始用户计数可轻松地为指定的消息数由 BizTalk Server 应用程序这段时间和同样，最大用户计数为指定的消息数高于 BizTalk Server 应用程序可以处理随着时间的推移。 请参阅[添加负载测试和配置的负载测试方案、 计数器集和运行设置](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_StepLoadTest)有关编辑负载测试的负载模式设置信息。  
  
## <a name="ensure-that-the-correct-test-settings-are-used-for-the-step-pattern-load-test"></a>确保为步骤模式负载测试使用正确的测试设置  
 配置负载测试，以使用**测试设置**在中创建[将测试设置文件添加到解决方案来运行测试和远程收集数据](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_TestSettings)。  
  
## <a name="configure-the-load-test-with-the-appropriate-performance-counters-and-run-the-step-pattern-load-test"></a>为负载测试配置使用适当的性能计数器和运行步骤模式负载测试  
 按照中的步骤[添加自定义计数器集到度量值 BizTalk Server 关键绩效指标 (KPI)](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_BTSCounters)添加必要的 BizTalk Server 性能计数器用于测量 BizTalk Server 的性能应用程序，并确定在哪个点 BizTalk Server 应用程序是否不再能够维护创建负载测试代理的消息负载。 这将通过显示 BizTalk:Message Box: General Counters\Spool 大小计数器更多价值的假脱机表中的消息的积压工作的累算出现。 如果此计数器的值开始显著增加然后你可能已超过 MST BizTalk 服务器应用程序。 当您确定此时 BizTalk Server 应用程序不再能够处理多条消息为接收，记下文档 received/Sec 发生此情况时的消息数。 务必要记下此值，因为主题[步骤 6： 执行常量负载模式测试验证最大可持续吞吐量](../technical-guides/step-6-complete-load-pattern-tests-to-verify-maximum-sustainable-throughput.md)将介绍如何运行"常量用户计数"值常量模式负载测试这就是某种程度上小于最大可持续文档秒接收的值。 这样做是为了验证 BizTalk Server 应用程序能够随着时间的推移处理这个数量的消息。 若要查看的计数器集的值，首先通过右击测试名称 (例如 BTS_Messaging_Step) 启动负载测试，然后单击**运行测试**菜单选项。 性能计数器进行了初始化，在负载测试开始后，Visual Studio 会自动切换到窗口使你可以同时显示从 1 到 4 的关系图的关系图窗口的焦点。 如果你感兴趣只能查看为关键绩效指标的主要中定义[添加自定义计数器集到度量值 BizTalk Server 关键绩效指标 (KPI)](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_BTSCounters)，单击**面板**下拉列表中从负载测试菜单列表并选择的选项**一个面板**。 然后单击图表并选择顶部的下拉列表**关键指标**实时显示关键性能指标所指示的值。  
  
> [!NOTE]  
>  因为某些默认计数器值将显示在**关键指标**图形，并因为你可能希望显示添加到你的自定义计数器集的计数器值，你可能想要通过手动删除每个启动中显示的计数器**关键指标**图形，然后手动从自定义计数器集添加计数器。 例如，至少，你想要至少将计数器添加下表中到关系图中，以确定 BizTalk Server 环境如何很好地处理负载，并可能会出现任何瓶颈：  
  
|计数器类别|计数器|实例|Computer|  
|----------------------|-------------|--------------|--------------|  
|BizTalk:Message Box:General Counters |假脱机大小|*BizTalk Server 消息框数据库*:*保存 BizTalk Server 消息框数据库的 SQL Server 实例*|任何组中具有 BizTalk Server 管理控制台的 BizTalk 服务器安装。|  
|BizTalk:Messaging|Documents received/Sec|RxHost （或接收主机的名称）|*BizTalk Server 组中的 BizTalk Server 计算机 #1*|  
|BizTalk:Messaging|Documents received/Sec|RxHost （或接收主机的名称）|*BizTalk Server 组中的 BizTalk Server 计算机 #2*|  
|BizTalk:Messaging|Documents received/Sec|RxHost （或接收主机的名称）|*BizTalk Server 组中的 BizTalk Server 计算机 #n*|  
|BizTalk:Messaging|处理的文档数/秒|TxHost （或发送主机的名称）|*BizTalk Server 组中的 BizTalk Server 计算机 #1*|  
|BizTalk:Messaging|处理的文档数/秒|TxHost （或发送主机的名称）|*BizTalk Server 组中的 BizTalk Server 计算机 #2*|  
|BizTalk:Messaging|处理的文档数/秒|TxHost （或发送主机的名称）|*BizTalk Server 组中的 BizTalk Server 计算机 #n*|  
|处理器|% Processor Time|_Total|*BizTalk Server 组中的 BizTalk Server 计算机 #1*|  
|处理器|% Processor Time|_Total|*BizTalk Server 组中的 BizTalk Server 计算机 #2*|  
|处理器|% Processor Time|_Total|*BizTalk Server 组中的 BizTalk Server 计算机 #n*|  
|处理器|% Processor Time|_Total|*保存的 BizTalk Server 数据库的 SQL Server 实例*|