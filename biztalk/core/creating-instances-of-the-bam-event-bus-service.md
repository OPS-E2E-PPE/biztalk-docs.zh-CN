---
title: 创建的 BAM 事件总线服务实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 454bdde7-45a6-41ab-9196-f662273f0f2b
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: daf847afc8f5c1d284a8266d70006a0f43508ed9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983998"
---
# <a name="creating-instances-of-the-bam-event-bus-service"></a><span data-ttu-id="ad865-102">创建 BAM 事件总线服务的实例</span><span class="sxs-lookup"><span data-stu-id="ad865-102">Creating Instances of the BAM Event Bus Service</span></span>
<span data-ttu-id="ad865-103">BAM 事件总线服务运行于 BizTalk 应用程序主机内。</span><span class="sxs-lookup"><span data-stu-id="ad865-103">The BAM Event Bus Service runs inside a BizTalk application host.</span></span> <span data-ttu-id="ad865-104">您可以使用默认主机作为 BAM 事件总线服务的宿主，也可以创建一个新主机。</span><span class="sxs-lookup"><span data-stu-id="ad865-104">You can use the default host to host the BAM Event Bus Service, or you can create a new host.</span></span> <span data-ttu-id="ad865-105">如果某个主机作为 BAM 事件总线服务的宿主，则为该主机创建的任何新实例也将作为此服务的宿主。</span><span class="sxs-lookup"><span data-stu-id="ad865-105">If a host hosts the BAM Event Bus service, any new instances you create for that host also hosts the service.</span></span>  
  
 <span data-ttu-id="ad865-106">有关默认主机的信息，请参阅[主机](../core/hosts.md)。</span><span class="sxs-lookup"><span data-stu-id="ad865-106">For information about the default host, see [Hosts](../core/hosts.md).</span></span>  
  
 <span data-ttu-id="ad865-107">有关创建主机的信息，请参阅[如何创建新的主机](../core/how-to-create-a-new-host.md)。</span><span class="sxs-lookup"><span data-stu-id="ad865-107">For information about creating hosts, see [How to Create a New Host](../core/how-to-create-a-new-host.md).</span></span>  
  
 <span data-ttu-id="ad865-108">有关创建主机实例的信息，请参阅[如何将主机实例添加](../core/how-to-add-a-host-instance.md)。</span><span class="sxs-lookup"><span data-stu-id="ad865-108">For information about creating host instances, see [How to Add a Host Instance](../core/how-to-add-a-host-instance.md).</span></span>  
  
 <span data-ttu-id="ad865-109">有关创建和配置主机和主机实例的信息，请参阅[管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)。</span><span class="sxs-lookup"><span data-stu-id="ad865-109">For information about creating and configuring hosts and host instances, see [Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md).</span></span>  
  
### <a name="to-create-the-host-that-hosts-the-bam-event-bus-service"></a><span data-ttu-id="ad865-110">创建 BAM 事件总线服务的宿主主机</span><span class="sxs-lookup"><span data-stu-id="ad865-110">To create the host that hosts the BAM Event Bus Service</span></span>  
  
1. <span data-ttu-id="ad865-111">单击**启动**，依次指向**所有程序**，单击**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="ad865-111">Click **Start**, point to **All Programs**, click **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="ad865-112">在 BizTalk 管理控制台窗口中，展开**BizTalk Server 管理**节点，展开**Biztalk 组**节点，展开**平台设置**节点用鼠标右键单击**主机**节点中，选择**新建**，然后单击**主机**。</span><span class="sxs-lookup"><span data-stu-id="ad865-112">In the BizTalk Administration Console window, expand the **BizTalk Server Administration** node, expand the **Biztalk Group** node and expand the **Platform Settings** node, right-click the **Hosts** node, select **New**, and then click **Host**.</span></span>  
  
3. <span data-ttu-id="ad865-113">在中**主机属性**对话框中**名称**框中，键入主机的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="ad865-113">In the **Host Properties** dialog box, in the **Name** box, type a descriptive name for the host.</span></span>  
  
4. <span data-ttu-id="ad865-114">上**常规**选项卡上，选择**允许主机跟踪**复选框。</span><span class="sxs-lookup"><span data-stu-id="ad865-114">On the **General** tab, select the **Allow Host Tracking** check box.</span></span>  
  
    <span data-ttu-id="ad865-115">新的子节点下显示**主机**与新主机的名称的节点。</span><span class="sxs-lookup"><span data-stu-id="ad865-115">A new child node appears under the **Hosts** node with the name of the new host.</span></span>  
  
5. <span data-ttu-id="ad865-116">在中**Windows 组**框中，键入要分配此主机，然后单击 Windows 组的名称**确定**。</span><span class="sxs-lookup"><span data-stu-id="ad865-116">In the **Windows group** box, type the name of the Windows group to assign this host, and then click **OK**.</span></span>  
  
    <span data-ttu-id="ad865-117">新的子节点下显示**主机**与新主机的名称的节点。</span><span class="sxs-lookup"><span data-stu-id="ad865-117">A new child node appears under the **Hosts** node with the name of the new host.</span></span>  
  
### <a name="to-create-a-new-host-instance-of-the-host"></a><span data-ttu-id="ad865-118">为主机创建新的主机实例</span><span class="sxs-lookup"><span data-stu-id="ad865-118">To create a new host instance of the host</span></span>  
  
1.  <span data-ttu-id="ad865-119">右键单击**主机实例**节点中，选择**新建**，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="ad865-119">Right-click the **Host Instance** node, select **New**, and then click **Host Instance**.</span></span>  
  
2.  <span data-ttu-id="ad865-120">选择的服务器位置的主机实例将运行，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="ad865-120">Select a server where the host instance will run, and then click **OK**.</span></span>  
  
### <a name="to-add-hosting-tracking-to-the-host"></a><span data-ttu-id="ad865-121">为主机添加主机跟踪</span><span class="sxs-lookup"><span data-stu-id="ad865-121">To add hosting tracking to the host</span></span>  
  
1.  <span data-ttu-id="ad865-122">右键单击你想要重新配置，然后单击的主机**属性**。</span><span class="sxs-lookup"><span data-stu-id="ad865-122">Right-click the host you want to reconfigure, and then click **Properties** .</span></span>  
  
2.  <span data-ttu-id="ad865-123">上**常规**选项卡上，选择**允许主机跟踪**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ad865-123">On the **General** tab, select **Allow Host Tracking**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="ad865-124">重新启动该主机的所有实例。</span><span class="sxs-lookup"><span data-stu-id="ad865-124">Restart all instances of that host.</span></span>  
  
### <a name="to-remove-hosting-tracking-from-the-host"></a><span data-ttu-id="ad865-125">从主机删除主机跟踪</span><span class="sxs-lookup"><span data-stu-id="ad865-125">To remove hosting tracking from the host</span></span>  
  
1.  <span data-ttu-id="ad865-126">右键单击你想要删除主机跟踪，的主机，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ad865-126">Right-click the host from which you want to remove host tracking, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ad865-127">清除**允许主机跟踪**复选框，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="ad865-127">Clear the **Allow Host tracking** check box, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="ad865-128">重新启动该主机的实例。</span><span class="sxs-lookup"><span data-stu-id="ad865-128">Restart instances of that host.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad865-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad865-129">See Also</span></span>  
 <span data-ttu-id="ad865-130">[管理 BAM 事件总线服务](../core/managing-the-bam-event-bus-service.md) </span><span class="sxs-lookup"><span data-stu-id="ad865-130">[Managing the BAM Event Bus Service](../core/managing-the-bam-event-bus-service.md) </span></span>  
 <span data-ttu-id="ad865-131">[BAM 安全建议](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="ad865-131">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="ad865-132">业务活动监视 (BAM)</span><span class="sxs-lookup"><span data-stu-id="ad865-132">Business Activity Monitoring (BAM)</span></span>](../core/business-activity-monitoring-bam.md)