---
title: 配置专用的跟踪主机 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f997bcc2-08fd-4e9a-ba44-542ec8460d6d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: defed64020300ebe6843e8e06bb15a51af2c4ec3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986710"
---
# <a name="configuring-a-dedicated-tracking-host"></a>配置专用的跟踪主机
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 优化吞吐量，因此，主业务流程和消息传递引擎不实际移动的事件或消息直接向 BizTalk 跟踪 (DTA) 或业务活动监视 (BAM) 数据库，因为这会将转移这些引擎从其主执行业务流程的作业。 相反，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 MessageBox 数据库中留出的事件和消息并将其标记为需要迁移到 BizTalk 跟踪或 BAM 数据库。 后台进程 （跟踪主机），然后移动到的 BizTalk 跟踪数据库和 BAM 数据库，到 BizTalk 跟踪数据库的 SQL Server 代理作业将跟踪消息时的事件。  
  
## <a name="advantages-of-using-a-dedicated-tracking-host"></a>使用专用的跟踪主机的优点  
 托管跟踪的 BizTalk 主机负责移动 DTA 和 BAM 跟踪从 MessageBox 数据库的数据，对 BizTalk 跟踪 (DTA) 和 BAM 主导入数据库。 跟踪数据的此移动在托管跟踪的同一主机中运行的其他 BizTalk 项目的性能产生影响。 因此，应使用不执行任何操作，但主机跟踪的专用的主机。  
  
 使用专用的跟踪主机还允许您停止其他 BizTalk 主机而不会干扰[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]跟踪。 跟踪数据从 MessageBox 数据库的移动是正常的关键[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。 如果停止 BizTalk 主机负责将跟踪数据移 BizTalk 组中，将不运行的跟踪数据解码服务。 这种影响是，如下所示：  
  
- HAT 跟踪数据不会从 MessageBox 数据库移至 BizTalk 跟踪数据库。  
  
- BAM 跟踪数据不会从 MessageBox 数据库移至 BAM 主导入数据库。  
  
- 不移动数据，因为它不能从 MessageBox 数据库中删除。  
  
- 跟踪数据解码服务停止时，跟踪侦听器仍将运行并将跟踪数据写入到 MessageBox 数据库。 如果不移动数据时，这会 MessageBox 数据库变得臃肿，这将影响一段时间内的性能。 即使不会跟踪自定义属性或 BAM 配置文件未设置，默认情况下的某些数据被跟踪 （如管道接收 / 发送事件和业务流程事件）。 如果您不想要运行的跟踪数据解码服务，请关闭所有跟踪，以便没有侦听器将数据保存到数据库。 若要禁用全局跟踪，请参阅[如何禁用全局跟踪](http://go.microsoft.com/fwlink/?LinkId=154193)(<http://go.microsoft.com/fwlink/?LinkId=154193>) 使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来有选择性地禁用跟踪事件。  
  
## <a name="optimizing-performance-for-a-dedicated-tracking-host"></a>优化专用的跟踪主机的性能  
 应在至少两台运行的计算机上运行此主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]（用例中的冗余一个失败）。 为了获得最佳性能，应具有至少一个跟踪主机实例，每个 MessageBox 数据库。 跟踪主机实例的实际数应为 N + 1，其中 N = MessageBox 数据库的数量。 "+ 1"是以实现冗余。 没有添加更多，因为只有一个跟踪主机实例并无好处可以将特定的 MessageBox 数据库的数据移动。 因此，锁定不应是一个问题。 其他的一个跟踪主机实例将添加容错功能;如果其中一个跟踪主机实例失败，其他实例将假定在执行任务的失败实例。  
  
 一个跟踪主机实例将跟踪数据的特定 MessageBox 数据库，但永远不会有多个跟踪主机实例特定的 MessageBox 数据库移动数据。 例如，如果您有三个 MessageBox 数据库，并且只有两个跟踪主机实例，然后其中一个主机实例需要将数据移动 MessageBox 数据库中的两个。 添加第三个跟踪主机实例分配跟踪主机到另一台计算机运行的工作[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 在此方案中，添加第四个跟踪主机实例将不分发任何详细的跟踪主机，但会提供一个额外跟踪主机实例的容错能力。  
  
 有关 BAM 事件总线服务的详细信息，请参阅 BizTalk Server 帮助中的以下主题：  
  
-   [管理 BAM 事件总线服务](http://go.microsoft.com/fwlink/?LinkId=154194)(http://go.microsoft.com/fwlink/?LinkId=154194)  
  
-   [创建的 BAM 事件总线服务实例](http://go.microsoft.com/fwlink/?LinkId=154195)(http://go.microsoft.com/fwlink/?LinkId=154195)  
  
## <a name="configuring-a-dedicated-tracking-host"></a>配置专用的跟踪主机  
 若要在本部分中执行该过程，必须具有以下用户权限来修改主机属性以允许主机跟踪：  
  
- 您必须是属于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
- 必须在 SQL Server 中具有以下权限：  
  
  -   您必须是 SQL Server 管理员或的成员*db_owner*或*db_securityadmin*中 BizTalk 跟踪数据库 (BizTalk DTADb) MessageBox 数据库 （SQL Server 数据库角色BizTalkMsgBoxDb) 和 BAM 主导入数据库 (BAMPrimaryImport)。  
  
  -   必须是所有计算机上的 sysadmin SQL Server 角色的成员，其中有 MessageBox 数据库或隶属*db_owner*或*db_ddladmin*所有 MessageBox 数据库的 SQL Server 角色。  
  
#### <a name="to-enable-host-tracking"></a>若要启用主机跟踪  
  
1. 单击**启动**，单击**程序**，单击**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开 BizTalk 组，单击**平台设置**，然后单击**主机**。  
  
3. 在详细信息窗格中，右键单击你想要修改，然后单击主机**属性**。  
  
4. 在中**主机属性**对话框中，在**常规**选项卡上，选中或清除**选项-允许主机跟踪**，然后单击**确定**。  
  
    选中此复选框可指示主机加载 BizTalk 跟踪组件以处理运行状况监视数据和业务数据。 如果选中此复选框，当前主机将具有读/写访问 MessageBox 数据库中的跟踪表以及跟踪数据库。 因此，运行在此主机中的任何对象也具有对这些数据库的读/写权限。  
  
    如果清除此复选框，该主机将仅对 MessageBox 数据库中的跟踪表具有写权限并且无权访问跟踪数据库。  
  
## <a name="see-also"></a>请参阅  
 [清单：配置 BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)