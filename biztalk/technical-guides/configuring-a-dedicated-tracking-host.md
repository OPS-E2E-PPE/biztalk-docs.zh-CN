---
title: "配置专用的跟踪主机 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f997bcc2-08fd-4e9a-ba44-542ec8460d6d
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3651d91f9c4b28fae30182ed6ddd18cde1bb3f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-a-dedicated-tracking-host"></a>配置专用的跟踪主机
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]针对吞吐量优化，因此主要业务流程和消息传送引擎执行不实际事件或消息直接转至 BizTalk 跟踪 (DTA) 或业务活动监视 (BAM) 数据库，因为这将会从其主这些引擎将转换执行业务流程的作业。 相反，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使 MessageBox 数据库中的事件和消息并将其标记为需要迁移到 BizTalk 跟踪或 BAM 数据库。 后台进程 （跟踪主机），然后移动到 BizTalk 跟踪和 BAM 数据库，SQL Server 代理作业副本跟踪的消息到 BizTalk 跟踪数据库时的事件。  
  
## <a name="advantages-of-using-a-dedicated-tracking-host"></a>使用专用的跟踪主机的优点  
 可承载跟踪 BizTalk 主机负责移动 DTA 和 BAM 到 BizTalk 跟踪 (DTA) 和 BAM 主导入数据库从 MessageBox 数据库跟踪数据。 这种跟踪数据移动的其他 BizTalk 项目，在承载跟踪的同一主机中运行的性能产生影响。 因此，应使用不执行任何操作，但跟踪的主机的专用的主机。  
  
 使用专用的跟踪主机还使你可以停止而不会干扰其他 BizTalk 主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]跟踪。 跟踪从 MessageBox 的数据库的数据的移动至关重要的正常[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。 如果停止 BizTalk 主机负责将跟踪数据移动 BizTalk 组中，跟踪数据解码服务将不会运行。 此方法的影响是，如下所示：  
  
-   HAT 跟踪数据不会从 MessageBox 数据库移至 BizTalk 跟踪数据库。  
  
-   BAM 跟踪数据不会从 MessageBox 数据库移至 BAM 主导入数据库。  
  
-   因为不移动数据时，它不能从 MessageBox 数据库中删除。  
  
-   当停止跟踪数据解码服务时，跟踪拦截器仍将运行并将跟踪数据写入到 MessageBox 数据库。 如果不移动数据时，这会将会影响性能随着时间的推移导致 MessageBox 数据库变得臃肿。 即使自定义属性不会跟踪或 BAM 配置文件未设置，默认情况下的某些数据跟踪 （如管道接收 / 发送事件和业务流程事件）。 如果您不想要运行的跟踪数据解码的服务，请关闭所有跟踪，以便不拦截器将数据保存到数据库。 若要禁用全局跟踪，请参阅[如何打开关闭全局跟踪](http://go.microsoft.com/fwlink/?LinkId=154193)(http://go.microsoft.com/fwlink/?LinkId=154193) 使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，可有选择性地禁用跟踪事件。  
  
## <a name="optimizing-performance-for-a-dedicated-tracking-host"></a>优化的专用的跟踪主机的性能  
 应运行的在至少两台计算机上运行此主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]（用例中的冗余来说一个失败）。 为了获得最佳性能，应具有至少一个跟踪每个 MessageBox 数据库的主机实例。 跟踪主机实例的实际数应为 N + 1，其中 N = MessageBox 数据库的数目。 "+ 1"是以实现冗余。 没有没有好处。 添加多个，因为只有一个跟踪主机实例可以将特定的 MessageBox 数据库的数据移动。 因此，锁定不应是问题。 其他的一个跟踪主机实例将添加容错功能;如果跟踪之一承载实例失败，其他实例将假定的失败实例的职责。  
  
 跟踪主机实例移动特定的 MessageBox 数据库的跟踪数据，但将永远不会有多个跟踪主机实例特定的 MessageBox 数据库的数据移动。 例如，如果你有三个 MessageBox 数据库，并只有两个跟踪主机实例，然后其中一个主机实例需要 MessageBox 数据库中的两个移动数据。 添加第三个跟踪主机实例将分发跟踪主机到另一台计算机运行的工作[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 在此方案中，程序将添加第四个跟踪主机实例将不会将任何详细的跟踪主机的分发工作，但将提供一个额外跟踪容错能力的主机实例。  
  
 有关 BAM 事件总线服务的详细信息，请参阅中的以下主题[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]帮助：  
  
-   [管理 BAM 事件总线服务](http://go.microsoft.com/fwlink/?LinkId=154194)(http://go.microsoft.com/fwlink/?LinkId=154194)  
  
-   [创建 BAM 事件总线服务的实例](http://go.microsoft.com/fwlink/?LinkId=154195)(http://go.microsoft.com/fwlink/?LinkId=154195)  
  
## <a name="configuring-a-dedicated-tracking-host"></a>配置专用的跟踪主机  
 若要在本部分中执行该过程，必须具有的以下用户权限修改主机属性，它使跟踪的主机：  
  
-   您必须是属于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。  
  
-   必须在 SQL Server 中具有以下权限：  
  
    -   你必须是 SQL Server 管理员或的成员*db_owner*或*db_securityadmin* BizTalk 跟踪数据库中 (BizTalk DTADb) MessageBox 数据库 （SQL Server 数据库角色BizTalkMsgBoxDb)，和 BAM 主导入数据库 (BAMPrimaryImport)。  
  
    -   必须是在所有计算机上的 sysadmin SQL Server 角色的成员，其中有 MessageBox 数据库，或成员*db_owner*或*db_ddladmin* MessageBox 的所有数据库的 SQL Server 角色。  
  
#### <a name="to-enable-host-tracking"></a>若要启用跟踪的主机  
  
1.  单击**启动**，单击**程序**，单击**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开 BizTalk 组，单击**平台设置**，然后单击**主机**。  
  
3.  在详细信息窗格中，右键单击你想要修改，，然后单击主机**属性**。  
  
4.  在**主机属性**对话框中，在**常规**选项卡上，选中或清除**选项-允许主机跟踪**，然后单击**确定**。  
  
     选中此复选框可指示主机加载 BizTalk 跟踪组件以处理运行状况监视数据和业务数据。 如果选中此复选框，当前主机需要跟踪数据库中的表的 MessageBox，以及到跟踪数据库的读/写访问。 因此，运行在此主机中的任何对象也具有对这些数据库的读/写权限。  
  
     如果清除此复选框，该主机将仅对 MessageBox 数据库中的跟踪表具有写权限并且无权访问跟踪数据库。  
  
## <a name="see-also"></a>另请参阅  
 [清单： 配置 BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)