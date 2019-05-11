---
title: 为 BizTalk Server 规划环境 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e9ef0b4-eccb-47e2-bbb5-e859ffa0468c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a05640ac656bbd6ead6206b2c787829b19badcf8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397003"
---
# <a name="planning-the-environment-for-biztalk-server"></a>为 BizTalk Server 规划环境
操作指南的规划部分介绍了角色和职责与关联[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。 它包括规划的应用程序和数据层的建议[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，并提供规划建议的版本管理的 BizTalk 解决方案的各个阶段。  
  
 如大家出现，"如果您不能计划，计划失败。" 虽然肯定有此的明智建议的例外情况，成功实施的生产型 BizTalk 解决方案的不是其中之一。 规划部分到本介绍性主题概述了在规划 BizTalk 解决方案时应做的决策。  
  
## <a name="deciding-whether-biztalk-server-is-the-right-tool-for-the-job"></a>确定 BizTalk Server 是否为作业合适的工具  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可视为"企业集成引擎"。 就其核心而言，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]旨在集成完全不同的业务系统、 流程和消息。 例如，交换遵循 EDI 标准的消息的业务系统可能需要将与交换符合 RosettaNet 标准的消息的业务系统相集成。 或内部业务使用的系统的 SAP 可能需要与另一个在 Microsoft SQL Server 数据库中存储数据的内部业务系统进行通信。 或者，也许只能发送或接收消息使用 FTP 协议的业务系统需要与只能使用 HTTP 协议的业务系统的消息交换。  
  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 通过充当两个系统之间的消息传送中转站，适合于此类不同的系统的集成。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 支持范围广泛的行业标准传送协议、 文档交换格式和业务线应用程序。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 此外提供了 BizTalk 业务流程引擎中的功能强大的业务流程自动化功能。 BizTalk 业务流程设计器用于创建可以为 BizTalk 业务流程引擎中运行的可执行代码生成的业务流程的可视表示形式。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 此外包括多种其他功能，便于业务集成，为信息工作人员例如业务活动监视 (BAM) 包括一个消息工作流引擎、 业务规则引擎 (BRE) 和技术。  
  
 有关使用详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务流程管理功能，请参阅[白皮书：Microsoft 和 BPM-技术概述](http://go.microsoft.com/fwlink/?LinkId=106015)(<http://go.microsoft.com/fwlink/?LinkId=106015>)。 若要了解有关 Microsoft 和优点而不是另一个具有所提供的不同的集成技术的详细信息，请参阅[Understanding Microsoft Integration Technologies](http://go.microsoft.com/fwlink/?LinkId=158452) (<http://go.microsoft.com/fwlink/?LinkId=158452>)。  
  
 某些集成方案并更好地适合于其他 Microsoft 产品。 如果你的主要任务是在下列任一情况时，请考虑使用这些 Microsoft 产品而不是[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
|**应用场景**|**若要使用的产品**|  
|------------------|------------------------|  
|用户预配|**Microsoft Identity Lifecycle Manager 2010**<br /><br /> 有关 Microsoft Identity Lifecycle Manager 2010 的详细信息，请参阅[Microsoft Identity Lifecycle Manager 2010 FP1](http://go.microsoft.com/fwlink/?LinkId=204577) (http://go.microsoft.com/fwlink/?LinkId=204577)。|  
|系统之间的数据复制|**SQL Server 复制**<br /><br /> 有关 SQL Server 复制的详细信息，请参阅[SQL Server 2008 R2 复制](http://go.microsoft.com/fwlink/?LinkID=69978)(http://go.microsoft.com/fwlink/?LinkID=69978)。|  
|数据提取、 转换和加载 (ETL)|**SQL Server Integration Services (SSIS)**<br /><br /> 有关 SQL Server Integration Services 的详细信息，请参阅[SQL Server 2008 R2 Integration Services](http://go.microsoft.com/fwlink/?LinkId=152044) (http://go.microsoft.com/fwlink/?LinkId=152044)。|  
  
## <a name="deciding-which-edition-of-biztalk-server-is-right-for-the-job"></a>确定哪个版本的 BizTalk Server 最适合作业  
 有四个不同版本的 BizTalk Server，其中每个为目标的特定方案。 四个版本的 BizTalk Server 包括：  
  
- **企业**-针对客户企业级高容量、 可靠性和可用性的要求而设计。  
  
- **标准**-具有中等卷和部署规模要求的企业而设计。  
  
- **分支**-专业版[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署方案包括 RFID 设计为中心辐射型。  
  
- **开发人员**-提供所有企业版的功能用于开发和测试目的，可用作 BizTalk Server 评估版用于评估目的免费。 安装为评估版，BizTalk Server 将正常 120 天。  
  
- **RFID 企业**-而设计，以便提供一个可缩放、 可扩展的平台的开发、 部署和管理多种 RFID 和传感器解决方案，包括 BizTalk RFID Server 和 BizTalk RFID Mobile。  
  
  有关不同版本的 BizTalk Server 的详细信息，请参阅[Microsoft BizTalk Server 版本](http://go.microsoft.com/fwlink/?LinkId=108051)(http://go.microsoft.com/fwlink/?LinkId=108051)。  
  
## <a name="planning-for-message-load"></a>规划消息负载  
 一旦您已确定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]符合你业务的集成需求，您应该确定将 BizTalk 解决方案的消息负载应处理下一件事情。 这是一项重要决策，因为不同版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]具有不同的纵向扩展和横向扩展功能。  
  
 确定消息负载的关键是要执行负载测试，以确定最大可承受吞吐量 (MST) 和最大可承受跟踪吞吐量 (MSTT) 的 BizTalk 解决方案。 测量最大可承受吞吐量，并在常规的性能最佳实践的详细信息，请参阅[BizTalk Server 2009 性能指南](http://go.microsoft.com/fwlink/?LinkID=150492)(http://go.microsoft.com/fwlink/?LinkID=150492)。  
  
## <a name="planning-for-expansion"></a>规划扩展  
 请考虑实现 BizTalk 解决方案使用的企业版[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]如果您将添加大量的贸易合作伙伴，将需要使用主机群集，或将需要向外扩展到多台计算机运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中BizTalk 组。 标准版和 Branch 版[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不适应多台计算机运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组或主机群集中。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [BizTalk Server 角色和职责](../technical-guides/biztalk-server-roles-and-responsibilities.md)  
  
-   [规划 BizTalk Server 层](../technical-guides/planning-the-biztalk-server-tier.md)  
  
-   [规划数据库层](../technical-guides/planning-the-database-tier.md)  
  
-   [规划开发、测试、暂存和生产环境](../technical-guides/planning-the-development-testing-staging-and-production-environments.md)