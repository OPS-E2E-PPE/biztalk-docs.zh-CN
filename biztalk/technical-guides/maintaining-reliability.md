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
# <a name="maintaining-reliability"></a><span data-ttu-id="bb232-102">维护可靠性</span><span class="sxs-lookup"><span data-stu-id="bb232-102">Maintaining Reliability</span></span>
<span data-ttu-id="bb232-103">本部分提供有关如何解决可靠性问题的信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。</span><span class="sxs-lookup"><span data-stu-id="bb232-103">This section provides information about how you can resolve reliability issues with a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span> <span data-ttu-id="bb232-104">这些问题可能会发现通过在中执行的日常维护检查[例程维护清单](../technical-guides/routine-maintenance-checklists.md)本文档的部分。</span><span class="sxs-lookup"><span data-stu-id="bb232-104">These issues may be discovered by the routine maintenance checks that are performed in the [Routine Maintenance Checklists](../technical-guides/routine-maintenance-checklists.md) section of this document.</span></span>  

 <span data-ttu-id="bb232-105">除了此部分中的主题，本文档中的其他主题解决可靠性问题。</span><span class="sxs-lookup"><span data-stu-id="bb232-105">In addition to the topics in this section, other topics in this document address reliability issues.</span></span> <span data-ttu-id="bb232-106">这些主题中列出[相关章节](../technical-guides/maintaining-reliability.md#BKMK_Related)下面。</span><span class="sxs-lookup"><span data-stu-id="bb232-106">These topics are listed in [Related Sections](../technical-guides/maintaining-reliability.md#BKMK_Related) below.</span></span>  

## <a name="testing-group-failover"></a><span data-ttu-id="bb232-107">测试故障转移组</span><span class="sxs-lookup"><span data-stu-id="bb232-107">Testing Group Failover</span></span>  
 <span data-ttu-id="bb232-108">在本部分中执行过程，应该在每月的可靠性检查的一部分。</span><span class="sxs-lookup"><span data-stu-id="bb232-108">Perform the procedures in this section as part of the reliability checks that should be performed monthly.</span></span> <span data-ttu-id="bb232-109">这些过程包括测试组故障转移策略，以及测试是否可以进行故障转移组资源。</span><span class="sxs-lookup"><span data-stu-id="bb232-109">These procedures include testing the group failover policy, and testing whether the group resources can fail over.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="bb232-110">如果将计算机加入到域中，Domain Admins 组的成员应能够执行此过程。</span><span class="sxs-lookup"><span data-stu-id="bb232-110">If the computer is joined to a domain, members of the Domain Admins group should be able to perform this procedure.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="bb232-111">若要在本部分中执行的过程，您必须登录本地计算机上 Administrators 组的成员，或者您必须被委派了适当的权限。</span><span class="sxs-lookup"><span data-stu-id="bb232-111">To perform the procedures in this section, you must be logged on as a member of the Administrators group on the local computer, or you must have been delegated the appropriate authority.</span></span>  

 <span data-ttu-id="bb232-112">执行以下步骤来测试运行 Windows Server 2008 的计算机上的组故障转移。</span><span class="sxs-lookup"><span data-stu-id="bb232-112">Perform the following steps to test group failover on computers running Windows Server 2008.</span></span>  

#### <a name="to-test-a-group-failover-policy"></a><span data-ttu-id="bb232-113">若要测试组的故障转移策略</span><span class="sxs-lookup"><span data-stu-id="bb232-113">To test a group failover policy</span></span>  

1.  <span data-ttu-id="bb232-114">请确保已安装**故障转移群集**功能在至少两台计算机上运行 Windows Server 2008，以便创建两个节点 Windows 故障转移群集。</span><span class="sxs-lookup"><span data-stu-id="bb232-114">Make sure you have installed the **Failover Clustering** feature on at least two computer running Windows Server 2008 so as to create a two node Windows Failover Cluster.</span></span> <span data-ttu-id="bb232-115">有关如何安装此功能的说明，请参阅[安装故障转移群集功能](http://go.microsoft.com/fwlink/?LinkId=157259)(http://go.microsoft.com/fwlink/?LinkId=157259)。</span><span class="sxs-lookup"><span data-stu-id="bb232-115">For instructions on how to install this feature, see [Install the Failover Clustering Feature](http://go.microsoft.com/fwlink/?LinkId=157259) (http://go.microsoft.com/fwlink/?LinkId=157259).</span></span>  

2.  <span data-ttu-id="bb232-116">通过单击打开故障转移群集管理**启动**，再单击**管理工具**，然后单击**故障转移群集管理**。</span><span class="sxs-lookup"><span data-stu-id="bb232-116">Open Failover Cluster Management by clicking **Start**, clicking **Administrative Tools**, and then clicking **Failover Cluster Management**.</span></span>  

3.  <span data-ttu-id="bb232-117">在控制台树中，展开群集节点，展开**服务和应用程序**节点，右键单击群集的实例的应用程序以进行故障转移，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="bb232-117">In the console tree, expand the cluster node, expand the **Services and Applications** node, right-click the clustered instance of the application to be failed over, and then click **Properties**.</span></span>  

4.  <span data-ttu-id="bb232-118">上**故障转移**选项卡上，设置**中指定的时间段的最大故障数**为 0，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="bb232-118">On the **Failover** tab, set **Maximum failures in the specified period** to 0, and then click **OK**.</span></span>  

5.  <span data-ttu-id="bb232-119">在控制台树中，展开**服务和应用程序**节点。</span><span class="sxs-lookup"><span data-stu-id="bb232-119">In the console tree, expand the **Services and Applications** node.</span></span>  

6.  <span data-ttu-id="bb232-120">在详细信息窗格中，右键单击资源，然后依次**属性**。</span><span class="sxs-lookup"><span data-stu-id="bb232-120">In the details pane, right-click a resource, and then click **Properties**.</span></span>  

7.  <span data-ttu-id="bb232-121">上**策略**选项卡上，设置**中指定的时间段的最大启动次数**为 0，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="bb232-121">On the **Policies** tab, set **Maximum restarts in the specified period** to 0, and then click **OK**.</span></span>  

8.  <span data-ttu-id="bb232-122">右键单击该资源中，单击**更多操作**，然后单击**该资源的模拟故障**。</span><span class="sxs-lookup"><span data-stu-id="bb232-122">Right-click the resource, click **More Actions**, and then click **Simulate Failure of this resource**.</span></span> <span data-ttu-id="bb232-123">验证是否在组的反应基于你在上一步中指定的策略。</span><span class="sxs-lookup"><span data-stu-id="bb232-123">Verify whether the group reacts based on the policy you specified in the previous step.</span></span>  

9. <span data-ttu-id="bb232-124">右键单击应用程序以进行故障转移，然后单击该群集的实例**属性**。</span><span class="sxs-lookup"><span data-stu-id="bb232-124">Right-click the clustered instance of the application to be failed over, and then click **Properties**.</span></span>  

10. <span data-ttu-id="bb232-125">上**故障转移**选项卡上，设置**中指定的时间段的最大故障数**为 1，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="bb232-125">On the **Failover** tab, set **Maximum failures in the specified period** to 1, and then click **OK**.</span></span>  

11. <span data-ttu-id="bb232-126">右键单击资源，然后选择**将此资源联机**。</span><span class="sxs-lookup"><span data-stu-id="bb232-126">Right-click the resource and select **Bring this resource online**.</span></span>  

#### <a name="to-test-whether-group-resources-can-fail-over"></a><span data-ttu-id="bb232-127">若要测试是否可以进行故障转移组资源</span><span class="sxs-lookup"><span data-stu-id="bb232-127">To test whether group resources can fail over</span></span>  

1.  <span data-ttu-id="bb232-128">请确保已安装**故障转移群集**运行 Windows Server 2008 的计算机上的功能。</span><span class="sxs-lookup"><span data-stu-id="bb232-128">Make sure you have installed the **Failover Clustering** feature on the computer running Windows Server 2008.</span></span> <span data-ttu-id="bb232-129">有关如何安装此功能的说明，请参阅[安装故障转移群集功能](http://go.microsoft.com/fwlink/?LinkId=157259)(http://go.microsoft.com/fwlink/?LinkId=157259)。</span><span class="sxs-lookup"><span data-stu-id="bb232-129">For instructions on how to install this feature, see [Install the Failover Clustering Feature](http://go.microsoft.com/fwlink/?LinkId=157259) (http://go.microsoft.com/fwlink/?LinkId=157259).</span></span>  

2.  <span data-ttu-id="bb232-130">通过单击打开故障转移群集管理**启动**，再单击**管理工具**，然后单击**故障转移群集管理**。</span><span class="sxs-lookup"><span data-stu-id="bb232-130">Open Failover Cluster Management by clicking **Start**, clicking **Administrative Tools**, and then clicking **Failover Cluster Management**.</span></span>  

3.  <span data-ttu-id="bb232-131">在控制台树中，展开群集节点，展开**服务和应用程序**节点，然后单击应用程序以进行故障转移群集的实例。</span><span class="sxs-lookup"><span data-stu-id="bb232-131">In the console tree, expand the cluster node, expand the **Services and Applications** node, and then click the clustered instance of the application to be failed over.</span></span>  

4.  <span data-ttu-id="bb232-132">上**操作**菜单上，单击**将此服务或应用程序到另一个节点移动**，然后单击向其应用程序将故障转移节点。</span><span class="sxs-lookup"><span data-stu-id="bb232-132">On the **Action** menu, click **Move this service or application to another node**, and then click the node to which the application will be failed over.</span></span>  

5.  <span data-ttu-id="bb232-133">在中**请确认操作**对话框框中，选择要移动到所选节点的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bb232-133">In the **Please confirm action** dialog box, choose to move the application to selected node.</span></span>  

6.  <span data-ttu-id="bb232-134">请确保为应用程序移动到的节点列出针对**当前所有者**在应用程序的详细信息窗格中。</span><span class="sxs-lookup"><span data-stu-id="bb232-134">Make sure that the node to which you moved the application to is listed against the **Current Owner** in the details pane of the application.</span></span>  

##  <a name="BKMK_BTSGrp"></a> <span data-ttu-id="bb232-135">确保多个服务器是 BizTalk 组的一部分</span><span class="sxs-lookup"><span data-stu-id="bb232-135">Ensuring Multiple Servers Are Part of a BizTalk Group</span></span>  
 <span data-ttu-id="bb232-136">若要确保系统的可靠性，至少两个物理 BizTalk server 应是 BizTalk 组的一部分。</span><span class="sxs-lookup"><span data-stu-id="bb232-136">To ensure the reliability of a system, at least two physical BizTalk servers should be part of the BizTalk group.</span></span>  <span data-ttu-id="bb232-137">如果需要将服务器添加到 BizTalk 组，请记住以下：</span><span class="sxs-lookup"><span data-stu-id="bb232-137">If you need to add a server to a BizTalk group, keep the following in mind:</span></span>  

- <span data-ttu-id="bb232-138">一台服务器只能与一个 BizTalk 组相关联。</span><span class="sxs-lookup"><span data-stu-id="bb232-138">A server can only be associated with one BizTalk group.</span></span> <span data-ttu-id="bb232-139">如果服务器已属于另一个组，则必须首先删除该服务器从其当前组之前可以将其添加到新的组。</span><span class="sxs-lookup"><span data-stu-id="bb232-139">If a server already belongs to another group, you must first remove that server from its current group before you can add it to a new group.</span></span> <span data-ttu-id="bb232-140">有关从 BizTalk 组中删除服务器的详细信息，请参阅"如何删除服务器从将组"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkId=155577 ](http://go.microsoft.com/fwlink/?LinkId=155577)。</span><span class="sxs-lookup"><span data-stu-id="bb232-140">For more information about removing a server from a BizTalk group, see "How to Remove a Server from a Group" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkId=155577](http://go.microsoft.com/fwlink/?LinkId=155577).</span></span>  

- <span data-ttu-id="bb232-141">与 BizTalk Server 环境中的不同服务器相关联的 BizTalk 组除交换消息不进行交互。</span><span class="sxs-lookup"><span data-stu-id="bb232-141">BizTalk groups associated with different servers in a BizTalk Server environment do not interact except to exchange messages.</span></span>  

- <span data-ttu-id="bb232-142">必须在你想要添加到 BizTalk 组的计算机上安装 BizTalk Server 运行时。</span><span class="sxs-lookup"><span data-stu-id="bb232-142">The BizTalk Server runtime must be installed on the computer you want to add to the BizTalk group.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="bb232-143">若要执行本主题中的过程，必须为 SSO Administrators 组的成员和 Windows Administrators 组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="bb232-143">To perform the procedures in this topic, you must be logged on as a member of the SSO Administrators group and as a member of the Windows Administrators group.</span></span>  

#### <a name="to-determine-whether-at-least-two-physical-biztalk-servers-are-part-of-the-biztalk-group"></a><span data-ttu-id="bb232-144">若要确定是否在至少两台物理 BizTalk server 是 BizTalk 组的一部分</span><span class="sxs-lookup"><span data-stu-id="bb232-144">To determine whether at least two physical BizTalk servers are part of the BizTalk group</span></span>  

1. <span data-ttu-id="bb232-145">打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过单击管理控制台**启动**，依次指向**所有程序**，指向**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** ，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="bb232-145">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console by clicking **Start**, pointing to **All Programs**, pointing to **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and then clicking **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="bb232-146">展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]节点，展开**BizTalk 组**节点，然后展开**平台设置**节点。</span><span class="sxs-lookup"><span data-stu-id="bb232-146">Expand the [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] node, expand the **BizTalk Group** node, and then expand the **Platform Settings** node.</span></span>  

3. <span data-ttu-id="bb232-147">单击**服务器**节点。</span><span class="sxs-lookup"><span data-stu-id="bb232-147">Click the **Servers** node.</span></span> <span data-ttu-id="bb232-148">验证多个服务器列在**服务器**窗格。</span><span class="sxs-lookup"><span data-stu-id="bb232-148">Verify that more than one server is listed in the **Servers** pane.</span></span>  

   > [!NOTE]  
   >  <span data-ttu-id="bb232-149">若要查看有关服务器的信息，请右键单击服务器，指向**视图**，然后单击**组中心页**。</span><span class="sxs-lookup"><span data-stu-id="bb232-149">To view information about the server, right-click the server, point to **View**, and then click **Group Hub Page**.</span></span>  

#### <a name="to-add-a-server-to-a-biztalk-group"></a><span data-ttu-id="bb232-150">若要将服务器添加到 BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="bb232-150">To add a server to a BizTalk group</span></span>  

1. <span data-ttu-id="bb232-151">在你想要添加到 BizTalk 组的计算机，单击**启动**，单击**所有程序**，单击**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** ，然后单击**BizTalk Server 配置**。</span><span class="sxs-lookup"><span data-stu-id="bb232-151">On the computer that you want to add to a BizTalk group, click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and then click **BizTalk Server Configuration**.</span></span>  

2. <span data-ttu-id="bb232-152">在中**Microsoft BizTalk Server 2010 配置**，选择**自定义配置**。</span><span class="sxs-lookup"><span data-stu-id="bb232-152">In **Microsoft BizTalk Server 2010 Configuration**, select **Custom configuration**.</span></span>  

3. <span data-ttu-id="bb232-153">在中**数据库服务器名称**，键入服务器要加入的 BizTalk 组的 SQL server 的名称。</span><span class="sxs-lookup"><span data-stu-id="bb232-153">In **Database server name**, type the name of the SQL server for the BizTalk group that the server is joining.</span></span>  

4. <span data-ttu-id="bb232-154">在中**服务凭据**，键入相应的用户名和密码，服务将使用，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="bb232-154">In **Service credential**, type the appropriate user name and password that the services will use, and then click **Configure**.</span></span>  

5. <span data-ttu-id="bb232-155">在屏幕左侧导航树中，单击**企业 SSO**。</span><span class="sxs-lookup"><span data-stu-id="bb232-155">In the navigation tree on the left side of the screen, click **Enterprise SSO**.</span></span>  

6. <span data-ttu-id="bb232-156">上**企业单一登录**页上，单击**加入现有 SSO 系统**。</span><span class="sxs-lookup"><span data-stu-id="bb232-156">On the **Enterprise Single Sign-On** page, click **Join an existing SSO system**.</span></span>  

   > [!NOTE]  
   >  <span data-ttu-id="bb232-157">请确保服务器名称和数据库名称指向该服务器将加入的 BizTalk 组的主 SSO 数据库服务器。</span><span class="sxs-lookup"><span data-stu-id="bb232-157">Ensure that the server name and database name point to the master SSO database server for the BizTalk group that the server is joining.</span></span>  

7. <span data-ttu-id="bb232-158">在屏幕左侧导航树中，单击**组**。</span><span class="sxs-lookup"><span data-stu-id="bb232-158">In the navigation tree on the left side of the screen, click **Group**.</span></span>  

8. <span data-ttu-id="bb232-159">上**组**页上，单击**加入现有 BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="bb232-159">On the **Group** page, click **Join an existing BizTalk Group**.</span></span>  

   > [!NOTE]  
   >  <span data-ttu-id="bb232-160">请确保服务器名称和数据库名称指向该服务器加入 BizTalk 组的数据库。</span><span class="sxs-lookup"><span data-stu-id="bb232-160">Ensure that the server name and database name point to the databases for the BizTalk group that the server is joining.</span></span>  

9. <span data-ttu-id="bb232-161">在菜单栏上，单击**应用配置**若要在此计算机上配置企业单一登录和组。</span><span class="sxs-lookup"><span data-stu-id="bb232-161">On the menu bar, click **Apply Configuration** to configure both Enterprise Single Sign-On and the group on this computer.</span></span>  

##  <a name="BKMK_Related"></a> <span data-ttu-id="bb232-162">相关章节</span><span class="sxs-lookup"><span data-stu-id="bb232-162">Related Sections</span></span>  

- <span data-ttu-id="bb232-163">有关检查故障磁盘硬件 RAID 中的信息，请参阅"查看磁盘属性"Windows Server 2003 产品帮助中在[ http://go.microsoft.com/fwlink/?linkid=104161 ](http://go.microsoft.com/fwlink/?linkid=104161)。</span><span class="sxs-lookup"><span data-stu-id="bb232-163">For information about checking for failed disks in the hardware RAID, see "View Disk Properties" in the Windows Server 2003 product Help at [http://go.microsoft.com/fwlink/?linkid=104161](http://go.microsoft.com/fwlink/?linkid=104161).</span></span>  

- <span data-ttu-id="bb232-164">有关手动检查挂起的消息的信息，请参阅"调查业务流程、 端口和消息故障"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkID=154512 ](http://go.microsoft.com/fwlink/?LinkID=154512)。</span><span class="sxs-lookup"><span data-stu-id="bb232-164">For information about manually checking for suspended messages, see "Investigating Orchestration, Port, and Message Failures" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkID=154512](http://go.microsoft.com/fwlink/?LinkID=154512).</span></span>  

- <span data-ttu-id="bb232-165">确保每个主机具有至少两个物理 BizTalk 服务器上运行的实例有关的信息，请参阅[BizTalk 主机的高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)。</span><span class="sxs-lookup"><span data-stu-id="bb232-165">For information about ensuring that each host has an instance running on at least two physical BizTalk servers, see [High Availability for BizTalk Hosts](../technical-guides/high-availability-for-biztalk-hosts.md).</span></span>  

- <span data-ttu-id="bb232-166">确保每个主机具有至少两个物理 BizTalk 服务器上运行的实例有关的信息，请参阅[缩放扩展接收主机](../technical-guides/scaling-out-receiving-hosts.md)。</span><span class="sxs-lookup"><span data-stu-id="bb232-166">For information about ensuring that each host has an instance running on at least two physical BizTalk servers, see [Scaling Out Receiving Hosts](../technical-guides/scaling-out-receiving-hosts.md).</span></span>  

- <span data-ttu-id="bb232-167">有关如何确保所有群集服务，故障转移的信息已经过测试，请参阅[聚类分析主密钥服务器](../technical-guides/clustering-the-master-secret-server.md)。</span><span class="sxs-lookup"><span data-stu-id="bb232-167">For information about ensuring that failover for all clustered services has been tested, see [Clustering the Master Secret Server](../technical-guides/clustering-the-master-secret-server.md).</span></span>  

- <span data-ttu-id="bb232-168">有关确保 BizTalk 数据库群集化 SQL 服务下的信息，请参阅[聚类分析 BizTalk Server 数据库 2](../technical-guides/clustering-the-biztalk-server-databases2.md)。</span><span class="sxs-lookup"><span data-stu-id="bb232-168">For information about ensuring that the BizTalk databases are clustered under SQL Services, see [Clustering the BizTalk Server Databases2](../technical-guides/clustering-the-biztalk-server-databases2.md).</span></span>  

- <span data-ttu-id="bb232-169">有关确定是否 （需要单独的主机） 正在使用任何不稳定的代码的信息，请参阅[BizTalk 主机的高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)。</span><span class="sxs-lookup"><span data-stu-id="bb232-169">For information about determining whether any unstable code is being used (requiring separate hosts), see [High Availability for BizTalk Hosts](../technical-guides/high-availability-for-biztalk-hosts.md).</span></span>  

- <span data-ttu-id="bb232-170">有关执行的所有新的 BizTalk 应用程序功能测试的信息，请参阅[测试的应用程序](../technical-guides/testing-an-application.md)</span><span class="sxs-lookup"><span data-stu-id="bb232-170">For information about performing functional testing of all new BizTalk applications, see [Testing an Application](../technical-guides/testing-an-application.md)</span></span>
