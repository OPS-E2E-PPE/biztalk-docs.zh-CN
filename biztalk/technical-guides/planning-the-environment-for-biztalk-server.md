---
title: "BizTalk Server 规划环境 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e9ef0b4-eccb-47e2-bbb5-e859ffa0468c
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66cd358f3d8a4fbda2c4ed43432f1ad8b2f6979e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="planning-the-environment-for-biztalk-server"></a>BizTalk Server 规划环境
操作指南的规划节介绍了角色和职责与关联[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。 它包括规划对于的应用程序和数据层的建议[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境，并提供规划的建议的版本管理的 BizTalk 解决方案的各个阶段。  
  
 为启用说出出现时，"如果您不能计划，计划失败。" 尽管当然有此安全建议的例外情况，是不其中之一的生产型 BizTalk 解决方案的成功实施。 规划部分本介绍性主题提供在规划 BizTalk 解决方案时应做的决策的高级概述。  
  
## <a name="deciding-whether-biztalk-server-is-the-right-tool-for-the-job"></a>决定是否 BizTalk Server 作业的合适工具  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以将看作"业务集成引擎"。 就其核心而言，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]旨在集成不同的业务系统、 过程和消息。 例如，交换遵循 EDI 标准的消息的业务系统可能需要与交换符合 RosettaNet 标准的消息的业务系统集成。 或使用 SAP 内部业务系统可能需要与另一个在 Microsoft SQL Server 数据库中存储数据的内部业务系统进行通信。 否则可能只能发送或接收消息使用 FTP 协议的业务系统需要与一个业务系统，只能使用 HTTP 协议交换消息。  
  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]充当中间人的两个系统之间的消息传递，可以适应不断这种不同的系统的集成。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持范围广泛的行业标准传输协议、 文档 exchange 格式和业务线应用程序。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]此外提供了 BizTalk 业务流程引擎中的功能强大的业务流程自动化功能。 BizTalk 业务流程设计器用于创建的视觉表示形式可以为在 BizTalk 业务流程引擎中运行的可执行代码生成业务流程。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]此外包括了一些其他功能，促进业务集成，为信息工作者如业务活动监视 (BAM) 包括消息工作流引擎、 业务规则引擎 (BRE) 和技术。  
  
 有关使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务进程管理功能，请参阅[白皮书： Microsoft 和 BPM-技术概述](http://go.microsoft.com/fwlink/?LinkId=106015)(http://go.microsoft.com/fwlink/?LinkId=106015)。 若要了解有关 Microsoft 和通过另一个具有的优势所提供的不同的集成技术的详细信息，请参阅[了解 Microsoft 集成技术](http://go.microsoft.com/fwlink/?LinkId=158452)(http://go.microsoft.com/fwlink/?LinkId=158452)。  
  
 某些集成方案，可更好适合于其他 Microsoft 产品。 如果你主要关注的是在下列任一情况时，请考虑使用而不是这些 Microsoft 产品[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
|**应用场景**|**若要使用的产品**|  
|------------------|------------------------|  
|用户设置|**Microsoft Identity Lifecycle Manager 2010**<br /><br /> 有关 Microsoft Identity Lifecycle Manager 2010 的详细信息，请参阅[Microsoft Identity Lifecycle Manager 2010 FP1](http://go.microsoft.com/fwlink/?LinkId=204577) (http://go.microsoft.com/fwlink/?LinkId=204577)。|  
|系统之间的数据复制|**SQL Server 复制**<br /><br /> 有关 SQL Server 复制的详细信息，请参阅[SQL Server 2008 R2 复制](http://go.microsoft.com/fwlink/?LinkID=69978)(http://go.microsoft.com/fwlink/?LinkID=69978)。|  
|数据提取、 转换和加载 (ETL)|**SQL Server Integration Services (SSIS)**<br /><br /> 有关 SQL Server Integration Services 的详细信息，请参阅[SQL Server 2008 R2 Integration Services](http://go.microsoft.com/fwlink/?LinkId=152044) (http://go.microsoft.com/fwlink/?LinkId=152044)。|  
  
## <a name="deciding-which-edition-of-biztalk-server-is-right-for-the-job"></a>决定哪个版本的 BizTalk Server 适合作业  
 有四个不同版本的 BizTalk Server 中，其中每个为目标的特定方案。 四个版本的 BizTalk Server 包括：  
  
-   **企业**-适用于客户与企业级高容量、 可靠性和可用性的要求。  
  
-   **标准**-具有中等卷和部署缩放要求的企业设计。  
  
-   **分支**-专业版[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]专为中心设计并分支包括 RFID 的部署方案。  
  
-   **开发人员**-出于开发和测试目的提供的所有企业版功能，可用作 BizTalk Server Evaluation Edition 用于评估目的，不收费。 安装为评估版，BizTalk Server 将为 120 天正常工作。  
  
-   **RFID 企业**-设计用于提供一个可缩放、 可扩展的平台进行开发、 部署和管理的丰富 RFID 和传感器解决方案，包括 BizTalk RFID Server 和 BizTalk RFID 移动。  
  
 有关不同版本的 BizTalk Server 的详细信息，请参阅[Microsoft BizTalk Server 版本](http://go.microsoft.com/fwlink/?LinkId=108051)(http://go.microsoft.com/fwlink/?LinkId=108051)。  
  
## <a name="planning-for-message-load"></a>规划消息负载  
 一旦确定了，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]符合你业务的集成需要你应该确定消息负载 BizTalk 解决方案将需要处理的下一步操作。 这是一项重要决定，因为在不同版本[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]具有不同的纵向扩展和横向扩展功能。  
  
 要确定消息负载的键是执行负载测试以确定最大可持续吞吐量 (MST) 和最大可持续跟踪吞吐量 (MSTT) 的 BizTalk 解决方案。 有关测量最大可持续吞吐量和在常规的性能最佳实践的详细信息，请参阅[BizTalk Server 2009 性能指南](http://go.microsoft.com/fwlink/?LinkID=150492)(http://go.microsoft.com/fwlink/?LinkID=150492)。  
  
## <a name="planning-for-expansion"></a>规划扩展  
 请考虑实施使用企业版的 BizTalk 解决方案[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]如果你将添加大量的贸易合作伙伴，将需要使用主机群集，或将需要向外扩展到多台计算机运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中BizTalk 组。 标准和分支版本[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不适应多台计算机运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组或主机群集中。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [BizTalk Server 角色和职责](../technical-guides/biztalk-server-roles-and-responsibilities.md)  
  
-   [规划 BizTalk Server 层](../technical-guides/planning-the-biztalk-server-tier.md)  
  
-   [规划数据库层](../technical-guides/planning-the-database-tier.md)  
  
-   [规划开发、测试、暂存和生产环境](../technical-guides/planning-the-development-testing-staging-and-production-environments.md)