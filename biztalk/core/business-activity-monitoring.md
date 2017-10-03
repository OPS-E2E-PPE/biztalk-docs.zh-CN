---
title: "业务活动监视 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83b3c92f-3062-413e-8d89-797f1c7ea7ab
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9003c89f7e1e3491ff343078936a9f22e6a41ef1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="business-activity-monitoring"></a>业务活动监视
信息工作者在查看和评估业务流程时需要相应的灵活性。 例如，采购经理可能需要查看每天批准和拒绝的采购订单数，而销售经理可能需要每小时更新当前所订购的产品。 若要满足这些不同需要，则需要一个通用框架以跟踪特定业务流程的进展情况。 这是完全什么业务活动监视 (BAM) 中的组件 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供。  
  
 ![BAM 示意图](../core/media/bam-diagram.gif "bam_diagram")  
  
 如上图所示，使用 BAM 组件可监视 BizTalk 应用程序生成的事件和数据。 使用可调用 SOAP 的 Web Services 可访问此信息，并且可以通过以下多种方式来对其进行访问：  
  
-   通过 Microsoft Excel 或其他桌面客户端，例如自定义仪表板应用程序。  
  
-   使用 BAM 门户，通过 BizTalk Server 中的这一组件，业务用户可以检查和配置 BAM 信息。 使用 BAM 门户，信息工作者可以选择某个业务流程的特定实例，然后选择该流程中的特定 BAM 视图。 其中每个视图均反映不同的方面，例如以图形形式表示每个产品的销售趋势、当前库存水平或其他关键性能指标。 这些视图中的信息可能每天、每小时或更频繁地进行更新。 使用 BAM 门户，信息工作者还可以定义数据的聚合，例如过去一小时内填写、取消或正在进行中的订单数。 由于将 BAM 门户实现为一组 ASP.NET 页，因此在 Windows SharePoint Services 内也可将其作为 Web 部分承载。  
  
-   通过 SQL Server Notification Services，可将 BAM 信息作为通知进行传送。 尽管前两个选项允许信息工作检查 BAM 信息，但这第三个选项将在发生某些所关注事件时创建通知。 使用 BAM 门户的警报管理器，信息工作者可以定义发生指定事件时将要发送的警报。 例如，BAM 用户可能选择将一封电子邮件发送到特定的管理器中，只要一天中的已取消订单数超过 10 个，或从其最大客户的订单到达任何时间可能是通知某些销售相关联。  
  
 实际上，每个 BAM 视图都依赖一个或多个 BAM 活动。 BAM 活动代表特定的业务流程，例如处理采购订单或发运产品，并且每个业务流程都具有一组定义的里程碑和业务数据。 例如，采购订单活动可能包含 Approved、Denied 和 Delivered 等里程碑以及客户姓名和产品等业务数据。  
  
 为信息工作者通过 Excel 访问 BAM BAM 活动 BAM 视图可以创建和使用 Excel 外接程序。 BAM 活动向导为此外接程序允许定义活动，而 BAM 视图向导允许根据这些活动的视图的定义。 实际上，BAM 视图向导只是帮助信息工作者使用一个或多个 BAM 活动中的信息来生成标准的 Excel 数据透视表。 然后，如下图所示，此视图提供的信息即可直接显示在 Excel 中。  
  
 ![](../core/media/understandingbts-12-bam2.gif "UnderstandingBTS_12_BAM2")  
  
 在此简单示例中，两个 Excel 图表将显示有关订单进度和销售的信息。 BAM 视图可以更为复杂，并且其创建者可以指定允许哪些用户查看该视图显示的数据。 例如，采购经理可能可以访问采购订单流程中某视图的特定内容，而这些内容对于采购职员则是隐藏的。  
  
 尽管信息工作者可以自己创建 BAM 视图和 BAM 活动，但这些视图和活动仍依赖于其监视的业务流程所提供的信息。 因此，开发人员仍要负责相应任务。 使用名为跟踪配置文件编辑器 (TPE) 的工具，开发人员必须对业务流程进行配置，以便该业务流程可以为依赖于特定 BAM 活动的 BAM 视图提供该活动所需的信息。 开发人员可以使用此工具以图形方式将业务流程中的相应事件和消息字段与 BAM 活动中对应的里程碑和业务数据相关联。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 引擎随后将这些事件和消息字段值发送到跟踪数据库（如上图所示），BAM 组件可在该数据库中对其进行访问。 虽然开发人员必须完成其相应任务，但 BAM 活动和 BAM 视图不是其关注的问题。 这些面向业务的服务仅由信息工作者进行创建、维护和使用。  
  
 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，还可以使用 TPE 来指定管道生成事件的方式。 更为重要的是，BAM 现在可以接受并显示由任何用户代码生成的事件，无论其是否作为业务流程生成。 使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的 BAM 组件，可能能够对使用 .NET Framework 生成的任何应用程序进行监视。  
  
## <a name="see-also"></a>另请参阅  
 [信息工作者技术](../core/information-worker-technologies.md)