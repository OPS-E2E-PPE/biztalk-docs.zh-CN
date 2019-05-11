---
title: 维护可靠性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 09cdce13-a75b-44d7-8388-7a868bb51c69
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7569b0abf5745a7809f371486492de2d880ad3d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396280"
---
# <a name="maintaining-reliability"></a>维护可靠性
本部分提供有关如何解决可靠性问题的信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。 这些问题可能会发现通过在中执行的日常维护检查[例程维护清单](../technical-guides/routine-maintenance-checklists.md)本文档的部分。  

 除了此部分中的主题，本文档中的其他主题解决可靠性问题。 这些主题中列出[相关章节](../technical-guides/maintaining-reliability.md#BKMK_Related)下面。  

## <a name="testing-group-failover"></a>测试故障转移组  
 在本部分中执行过程，应该在每月的可靠性检查的一部分。 这些过程包括测试组故障转移策略，以及测试是否可以进行故障转移组资源。  

> [!NOTE]  
>  如果将计算机加入到域中，Domain Admins 组的成员应能够执行此过程。  

> [!NOTE]  
>  若要在本部分中执行的过程，您必须登录本地计算机上 Administrators 组的成员，或者您必须被委派了适当的权限。  

 执行以下步骤来测试运行 Windows Server 2008 的计算机上的组故障转移。  

#### <a name="to-test-a-group-failover-policy"></a>若要测试组的故障转移策略  

1.  请确保已安装**故障转移群集**功能在至少两台计算机上运行 Windows Server 2008，以便创建两个节点 Windows 故障转移群集。 有关如何安装此功能的说明，请参阅[安装故障转移群集功能](http://go.microsoft.com/fwlink/?LinkId=157259)(http://go.microsoft.com/fwlink/?LinkId=157259)。  

2.  通过单击打开故障转移群集管理**启动**，再单击**管理工具**，然后单击**故障转移群集管理**。  

3.  在控制台树中，展开群集节点，展开**服务和应用程序**节点，右键单击群集的实例的应用程序以进行故障转移，然后单击**属性**。  

4.  上**故障转移**选项卡上，设置**中指定的时间段的最大故障数**为 0，然后单击**确定**。  

5.  在控制台树中，展开**服务和应用程序**节点。  

6.  在详细信息窗格中，右键单击资源，然后依次**属性**。  

7.  上**策略**选项卡上，设置**中指定的时间段的最大启动次数**为 0，然后单击**确定**。  

8.  右键单击该资源中，单击**更多操作**，然后单击**该资源的模拟故障**。 验证是否在组的反应基于你在上一步中指定的策略。  

9. 右键单击应用程序以进行故障转移，然后单击该群集的实例**属性**。  

10. 上**故障转移**选项卡上，设置**中指定的时间段的最大故障数**为 1，然后单击**确定**。  

11. 右键单击资源，然后选择**将此资源联机**。  

#### <a name="to-test-whether-group-resources-can-fail-over"></a>若要测试是否可以进行故障转移组资源  

1.  请确保已安装**故障转移群集**运行 Windows Server 2008 的计算机上的功能。 有关如何安装此功能的说明，请参阅[安装故障转移群集功能](http://go.microsoft.com/fwlink/?LinkId=157259)(http://go.microsoft.com/fwlink/?LinkId=157259)。  

2.  通过单击打开故障转移群集管理**启动**，再单击**管理工具**，然后单击**故障转移群集管理**。  

3.  在控制台树中，展开群集节点，展开**服务和应用程序**节点，然后单击应用程序以进行故障转移群集的实例。  

4.  上**操作**菜单上，单击**将此服务或应用程序到另一个节点移动**，然后单击向其应用程序将故障转移节点。  

5.  在中**请确认操作**对话框框中，选择要移动到所选节点的应用程序。  

6.  请确保为应用程序移动到的节点列出针对**当前所有者**在应用程序的详细信息窗格中。  

##  <a name="BKMK_BTSGrp"></a> 确保多个服务器是 BizTalk 组的一部分  
 若要确保系统的可靠性，至少两个物理 BizTalk server 应是 BizTalk 组的一部分。  如果需要将服务器添加到 BizTalk 组，请记住以下：  

- 一台服务器只能与一个 BizTalk 组相关联。 如果服务器已属于另一个组，则必须首先删除该服务器从其当前组之前可以将其添加到新的组。 有关从 BizTalk 组中删除服务器的详细信息，请参阅"如何删除服务器从将组"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkId=155577 ](http://go.microsoft.com/fwlink/?LinkId=155577)。  

- 与 BizTalk Server 环境中的不同服务器相关联的 BizTalk 组除交换消息不进行交互。  

- 必须在你想要添加到 BizTalk 组的计算机上安装 BizTalk Server 运行时。  

> [!NOTE]  
>  若要执行本主题中的过程，必须为 SSO Administrators 组的成员和 Windows Administrators 组的成员身份登录。  

#### <a name="to-determine-whether-at-least-two-physical-biztalk-servers-are-part-of-the-biztalk-group"></a>若要确定是否在至少两台物理 BizTalk server 是 BizTalk 组的一部分  

1. 打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过单击管理控制台**启动**，依次指向**所有程序**，指向**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** ，然后单击**BizTalk Server 管理**。  

2. 展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]节点，展开**BizTalk 组**节点，然后展开**平台设置**节点。  

3. 单击**服务器**节点。 验证多个服务器列在**服务器**窗格。  

   > [!NOTE]  
   >  若要查看有关服务器的信息，请右键单击服务器，指向**视图**，然后单击**组中心页**。  

#### <a name="to-add-a-server-to-a-biztalk-group"></a>若要将服务器添加到 BizTalk 组  

1. 在你想要添加到 BizTalk 组的计算机，单击**启动**，单击**所有程序**，单击**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** ，然后单击**BizTalk Server 配置**。  

2. 在中**Microsoft BizTalk Server 2010 配置**，选择**自定义配置**。  

3. 在中**数据库服务器名称**，键入服务器要加入的 BizTalk 组的 SQL server 的名称。  

4. 在中**服务凭据**，键入相应的用户名和密码，服务将使用，然后单击**配置**。  

5. 在屏幕左侧导航树中，单击**企业 SSO**。  

6. 上**企业单一登录**页上，单击**加入现有 SSO 系统**。  

   > [!NOTE]  
   >  请确保服务器名称和数据库名称指向该服务器将加入的 BizTalk 组的主 SSO 数据库服务器。  

7. 在屏幕左侧导航树中，单击**组**。  

8. 上**组**页上，单击**加入现有 BizTalk 组**。  

   > [!NOTE]  
   >  请确保服务器名称和数据库名称指向该服务器加入 BizTalk 组的数据库。  

9. 在菜单栏上，单击**应用配置**若要在此计算机上配置企业单一登录和组。  

##  <a name="BKMK_Related"></a> 相关章节  

- 有关检查故障磁盘硬件 RAID 中的信息，请参阅"查看磁盘属性"Windows Server 2003 产品帮助中在[ http://go.microsoft.com/fwlink/?linkid=104161 ](http://go.microsoft.com/fwlink/?linkid=104161)。  

- 有关手动检查挂起的消息的信息，请参阅"调查业务流程、 端口和消息故障"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkID=154512 ](http://go.microsoft.com/fwlink/?LinkID=154512)。  

- 确保每个主机具有至少两个物理 BizTalk 服务器上运行的实例有关的信息，请参阅[BizTalk 主机的高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)。  

- 确保每个主机具有至少两个物理 BizTalk 服务器上运行的实例有关的信息，请参阅[缩放扩展接收主机](../technical-guides/scaling-out-receiving-hosts.md)。  

- 有关如何确保所有群集服务，故障转移的信息已经过测试，请参阅[聚类分析主密钥服务器](../technical-guides/clustering-the-master-secret-server.md)。  

- 有关确保 BizTalk 数据库群集化 SQL 服务下的信息，请参阅[聚类分析 BizTalk Server 数据库 2](../technical-guides/clustering-the-biztalk-server-databases2.md)。  

- 有关确定是否 （需要单独的主机） 正在使用任何不稳定的代码的信息，请参阅[BizTalk 主机的高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)。  

- 有关执行的所有新的 BizTalk 应用程序功能测试的信息，请参阅[测试的应用程序](../technical-guides/testing-an-application.md)
