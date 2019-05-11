---
title: BizTalk Server 2010 操作指南 |Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4dc0d8e9-9ad6-4ce1-8ca7-399b67cb360e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b2dcbc8dcd8602828e8a2a04986de2a88d545cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399344"
---
# <a name="biztalk-server-2010-operations-guide"></a>BizTalk Server 2010 操作指南
欢迎使用 Microsoft® BizTalk® Server 2010 操作指南。 我们创建了本指南是相关的实现和管理 BizTalk 解决方案，尤其是 IT 专业人员的所有人的宝贵资源。  
  
 若要下载本指南中 chm、 pdf 或 docx 窗体的副本，请转到[Microsoft BizTalk Server 2010 操作指南](http://go.microsoft.com/fwlink/?LinkId=212652)(http://go.microsoft.com/fwlink/?LinkId=212652)。  
  
## <a name="which-versions-of-biztalk-server-does-the-guide-cover"></a>本指南涵盖哪些版本的 BizTalk Server？  
 本指南适用于 BizTalk Server，并提供操作准备情况信息以帮助您快速开始使用你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序。  
  
> [!NOTE]
>  若要查看有关操作指南[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]或[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]，请参阅[ http://go.microsoft.com/fwlink/?LinkID=130458 ](http://go.microsoft.com/fwlink/?LinkID=130458)。  
  
## <a name="where-do-i-start"></a>如何开始？  
 我们组织规划、 部署和管理的功能方面根据指南[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。 因此可以根据这些功能的特性来读取它。 但是，意识到，清单将会最查找 BizTalk Server 操作指南 》 中的信息后，我们已分类的可访问性，以便下表中的文档中的所有清单。  
  
|||  
|-|-|  
|**设置 BizTalk 环境**|**设置高可用性和灾难恢复环境**|  
|-   [清单：BizTalk Server 入门](http://msdn.microsoft.com/library/37d265cd-c393-46ac-ac21-129a1511359b)<br />-   [清单：配置 Windows Server](~/technical-guides/checklist-configuring-windows-server.md)<br />-   [清单：配置 Internet Information Services](~/technical-guides/checklist-configuring-internet-information-services.md)<br />-   [清单：配置 SQL Server](../technical-guides/checklist-configuring-sql-server.md)<br />-   [清单：配置 BizTalk Server](~/technical-guides/checklist-configuring-biztalk-server.md)|-   [清单：提供高可用性容错或负载平衡](~/technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)<br />-   [清单：提供高可用性灾难恢复](~/technical-guides/checklist-increasing-availability-with-disaster-recovery.md)|  
|**监视、 测试和故障排除**|**性能和维护**|  
|-   [清单：监视操作准备情况](~/technical-guides/checklist-monitoring-operational-readiness.md)<br />-   [清单：维护和故障排除 BizTalk Server 数据库](../technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)<br />-   [清单：测试操作准备情况](~/technical-guides/checklist-testing-operational-readiness.md)<br />-   [清单：监视 BizTalk Server 使用 Operations Manager 2007](~/technical-guides/checklist-monitoring-biztalk-server-with-operations-manager-2007.md)<br />-   [清单：监视 SQL Server](~/technical-guides/checklist-monitoring-sql-servers.md)|维护相关的检查表：<br /><br /> -   [清单：执行每日维护检查](~/technical-guides/checklist-performing-daily-maintenance-checks.md)<br />-   [清单：执行每周维护检查](~/technical-guides/checklist-performing-weekly-maintenance-checks.md)<br />-   [清单：执行每月维护检查](~/technical-guides/checklist-performing-monthly-maintenance-checks.md)<br /><br /> 与性能相关的检查表：<br /><br /> -   [清单：执行每周性能检查](~/technical-guides/checklist-performing-weekly-performance-checks.md)<br />-   [清单：执行每月性能检查](~/technical-guides/checklist-performing-monthly-performance-checks.md)|  
|**其他重要任务清单**||  
|-   [清单：将应用程序部署](~/technical-guides/checklist-deploying-an-application.md)<br />-   [清单：将绑定导出到另一个应用程序](~/technical-guides/checklist-exporting-bindings-from-one-application-to-another.md)<br />-   [清单：更新的程序集](~/technical-guides/checklist-updating-an-assembly.md)<br />-   [清单：更新 BizTalk 应用程序中的项目](~/technical-guides/checklist-updating-artifacts-in-a-biztalk-application.md)|-   [清单：更新使用的并行版本控制的应用程序](~/technical-guides/checklist-updating-an-application-using-side-by-side-versioning.md)<br />-   [清单：正在更新业务流程使用的并行版本控制](~/technical-guides/checklist-updating-an-orchestration-using-side-by-side-versioning.md)<br />-   [清单：安装和配置证书](../technical-guides/checklist-installing-and-configuring-certificates.md)<br />-   [清单：规划在安全环境中的操作](../technical-guides/checklist-planning-for-operations-in-a-secure-environment.md)|  
  
 如果正在执行以下任务，你可以开始的相关部分：  
  
- **评估操作就绪性**:如果您侧重于评估和评估的程序操作就绪性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署，则先阅读[操作查检表](~/technical-guides/operations-checklists.md)和[增加可用性为 BizTalk Server](~/technical-guides/increasing-availability-for-biztalk-server.md)部分。  
  
- **成为做好运行准备**:若要确保你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]基础结构和应用程序变得在操作上准备就绪后，请参阅[为 BizTalk Server 规划环境](~/technical-guides/planning-the-environment-for-biztalk-server.md)部分。  
  
- **维护操作环境**:大部分操作指南 》 中的主题可帮助您维护一个可供[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。 您将找到用于维护以下各节中的操作环境的最佳实践、 关键概念和过程：[BizTalk Server 提供高可用性](~/technical-guides/increasing-availability-for-biztalk-server.md)，[监视 BizTalk Server](~/technical-guides/monitoring-biztalk-server2.md)，和[维护 BizTalk Server2](~/technical-guides/maintaining-biztalk-server2.md)。  
  
## <a name="whats-in-it"></a>什么是它？  
 根据实际经验的指南。 发起与 Microsoft 字段代表，合作伙伴组织和计划，客户的指南了解部署和维护 BizTalk Server 安装。 此组的 IT 专业人员已累积大量不同的 BizTalk 解决方案的亲身体验。 因为它们获得了体验创建这些清单、 最佳实践和演示文稿来指导将来[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]操作。 我们收集和组织此信息来创建参考线。  
  
 本指南的关键部分是新;但是，相当大一部分是指[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助、 白皮书、 知识库文章和其他源。 它经过仔细审阅并由来自社区的专家审查，所以[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]IT 专业人员和产品开发团队，其我们有幸确认本主题末尾处的成员。 我们相信，此处提供的信息有助于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用户解决问题，并最重要的是，避免部署和维护时，会发生的常见问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。  
  
## <a name="acknowledgments"></a>确认  
 在我们[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用户培训团队有幸确认用于提供技术反馈以及大量的内容的以下个人的杰出贡献[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]操作指南：  
  
-   Paolo Salvatori、 Tim Wieman