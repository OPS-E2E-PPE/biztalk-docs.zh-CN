---
title: 业务活动监视 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83b3c92f-3062-413e-8d89-797f1c7ea7ab
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87dfcfdf647a9cdb434512774b320eeaefbeea83
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357706"
---
# <a name="business-activity-monitoring"></a>业务活动监视
信息工作者需要灵活地查看和评估业务流程。 采购经理可能需要查看批准和拒绝每一天，例如，尽管销售经理可能需要每小时更新当前所订购的哪些产品的多少 POs。 满足这些不同需求需要一个通用框架，用于跟踪与特定的业务流程正在运行的内容。 这是完全哪些业务活动监视 (BAM) 中的组件 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供。  
  
 ![BAM 关系图](../core/media/bam-diagram.gif "bam_diagram")  
  
 如图所示，使用 BAM 组件可监视事件和生成的 BizTalk 应用程序数据。 此信息可供访问使用 SOAP 可调用的 Web 服务和它将可在多种不同的方式，按如下所示：  
  
- 通过 Microsoft Excel 或其他桌面客户端，例如自定义仪表板应用程序。  
  
- 使用 BAM 门户，使业务用户可以检查和配置 BAM 信息的 BizTalk Server 中的组件。 使用 BAM 门户，信息工作者可以选择某个业务流程，一个特定实例，然后选择到过程中的特定 BAM 视图。 每个视图提供了不同的角度看，如每个产品的销售趋势或当前库存水平或其他关键性能指标的图形形式表示。 这些视图中的信息可能会更新每一天，每个小时或更频繁。 使用 BAM 门户，信息工作者还可以定义数据的聚合，如订单数填写、 取消或正在进行中的过去 1 小时。 作为一组 ASP.NET 页实现的 BAM 门户可还作为承载 Windows SharePoint Services 的一个 Web 部件。  
  
- 通过 SQL Server Notification Services，可将 BAM 信息以作为通知进行传送。 尽管前两个选项允许信息工作检查 BAM 信息，此第三个选项将一些有趣的事情发生时创建的通知。 使用 BAM 门户的警报管理器，信息工作者可以定义将指定的事件发生时发送的警报。 例如，BAM 用户可能选择时的一天中取消的订单数超过 10，向特定经理发送一封电子邮件，或可能是从其最大客户的订单到达的时通知某个销售关联。  
  
  事实上，每个 BAM 视图依赖于一个或多个 BAM 活动。 BAM 活动代表特定业务流程，例如处理采购订单或发运产品和每个具有一组定义的里程碑和业务数据。 例如，采购订单活动可能具有 Approved、 Denied 和 Delivered 等里程碑以及客户姓名和产品等业务数据。  
  
  通过 Excel 访问 BAM 的信息工作者，BAM 活动和 BAM 视图可以使用创建的 Excel 外接程序。 用于该外接程序的 BAM 活动向导允许定义活动，而 BAM 视图向导允许基于这些活动的视图的定义。 实际上，BAM 视图向导只是帮助信息工作者生成标准 Excel 数据透视表使用一个或多个 BAM 活动中的信息。 下图所示，然后可以直接在 Excel 中显示此视图提供的信息。  
  
  ![](../core/media/understandingbts-12-bam2.gif "UnderstandingBTS_12_BAM2")  
  
  在此简单示例中，两个 Excel 图表显示有关订单进度和销售信息。 BAM 视图可能会更复杂，并且其创建者可以指定允许哪些用户要查看它公开的数据。 也许采购经理可以访问某些内容到采购订单流程，例如，视图中隐藏的采购职员。  
  
  尽管信息工作者可以自行创建 BAM 视图和 BAM 活动，这些视图和活动依赖于信息提供它们监视的业务流程。 相应地，开发人员仍然可以扮演的角色。 使用工具调用跟踪配置文件编辑器 (TPE)，开发人员必须配置业务流程，以使它提供了所需的特定 BAM 活动，从而确定依赖于此活动的 BAM 视图的信息。 此工具允许开发人员能够以图形方式相关联的相应事件和消息在业务流程中的字段对应的里程碑和 BAM 活动中的业务数据。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]引擎随后将发送这些事件和消息字段值到跟踪数据库，如上图中所示然后就可以访问 BAM 组件。 尽管开发人员必须完成其相应，BAM 活动和 BAM 视图并不是其关注的问题。 这些面向业务的服务创建、 维护和使用仅由信息工作者。  
  
  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，还可以使用 TPE 来指定管道生成事件的方式。 更重要的是，BAM 可接受，并显示由任何用户代码，生成的事件，指示生成为业务流程。 使用.NET Framework 构建任何应用程序可能使用的 BAM 组件来监视[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="see-also"></a>请参阅  
 [信息工作者技术](../core/information-worker-technologies.md)