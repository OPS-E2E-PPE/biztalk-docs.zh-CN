---
title: 运行 Orchestrations2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- strong name keys, creating
- orchestrations
- creating strong name keys
- compiling orchestrations
- host instances, stopping and restarting
- deployment, orchestrations
- orchestrations, compiling
- orchestrations, deploying
- stopping host instances
- restarting host instances
ms.assetid: a098d552-d302-44f6-9af9-d77d16549fd3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c299486c8ca43b34ba93ce434245b52b30e567aa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981046"
---
# <a name="running-orchestrations"></a><span data-ttu-id="3a40e-102">运行业务流程</span><span class="sxs-lookup"><span data-stu-id="3a40e-102">Running Orchestrations</span></span>
<span data-ttu-id="3a40e-103">以下过程介绍如何生成、部署、绑定和启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="3a40e-103">The following procedures describe how to build, deploy, bind, and start an orchestration.</span></span>  
  
## <a name="creating-a-strong-name-key"></a><span data-ttu-id="3a40e-104">创建强名称密钥</span><span class="sxs-lookup"><span data-stu-id="3a40e-104">Creating a Strong Name Key</span></span>  
  
#### <a name="to-create-a-strong-name-key"></a><span data-ttu-id="3a40e-105">若要创建一个强名称密钥</span><span class="sxs-lookup"><span data-stu-id="3a40e-105">To create a strong name key</span></span>  
  
1. <span data-ttu-id="3a40e-106">打开[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符。</span><span class="sxs-lookup"><span data-stu-id="3a40e-106">Open a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command Prompt.</span></span>  
  
2. <span data-ttu-id="3a40e-107">将目录更改为指向现有的项目，然后按 ENTER 键。</span><span class="sxs-lookup"><span data-stu-id="3a40e-107">Change directories to an existing project and press ENTER.</span></span>  
  
    <span data-ttu-id="3a40e-108">例如：</span><span class="sxs-lookup"><span data-stu-id="3a40e-108">For example:</span></span>  
  
    <span data-ttu-id="3a40e-109">**\<驱动器\>: \Adapter_Install\biztalk\my_project**</span><span class="sxs-lookup"><span data-stu-id="3a40e-109">**\<drive\>:\Adapter_Install\biztalk\my_project**</span></span>  
  
3. <span data-ttu-id="3a40e-110">在命令提示符下键入以下命令并按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="3a40e-110">Type the following at the command prompt and press ENTER:</span></span>  
  
    `sn -k SSOSchedule.snk`  
  
## <a name="compiling-and-deploying-an-orchestration"></a><span data-ttu-id="3a40e-111">编译和部署业务流程</span><span class="sxs-lookup"><span data-stu-id="3a40e-111">Compiling and Deploying an Orchestration</span></span>  
  
#### <a name="to-compile-and-deploy-an-orchestration"></a><span data-ttu-id="3a40e-112">若要编译和部署业务流程</span><span class="sxs-lookup"><span data-stu-id="3a40e-112">To compile and deploy an orchestration</span></span>  
  
1. <span data-ttu-id="3a40e-113">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击**SSOSchedule**项目，并选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="3a40e-113">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, right-click the **SSOSchedule** project, and select **Properties**.</span></span>  
  
2. <span data-ttu-id="3a40e-114">单击**常见属性**，然后展开**程序集**节点。</span><span class="sxs-lookup"><span data-stu-id="3a40e-114">Click **Common Properties**, and expand the **Assembly** node.</span></span>  
  
3. <span data-ttu-id="3a40e-115">输入的路径中的 SSOSchedule.snk**程序集密钥文件**文本框。</span><span class="sxs-lookup"><span data-stu-id="3a40e-115">Enter the path to SSOSchedule.snk in the **Assembly Key File** text box.</span></span>  
  
4. <span data-ttu-id="3a40e-116">验证配置 properties\deployment\server 是否是圆点 （.） 或您的计算机名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3a40e-116">Verify that Configuration Properties\Deployment\Server is a dot (.) or your computer name, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="3a40e-117">在解决方案资源管理器中右键单击**SSOSchedule**，然后单击**重新生成**。</span><span class="sxs-lookup"><span data-stu-id="3a40e-117">In Solution Explorer, right-click **SSOSchedule**, and then click **Rebuild**.</span></span>  
  
6. <span data-ttu-id="3a40e-118">右键单击**SSOSchedule**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="3a40e-118">Right-click **SSOSchedule**, and then click **Deploy**.</span></span>  
  
## <a name="starting-the-orchestration"></a><span data-ttu-id="3a40e-119">启动业务流程</span><span class="sxs-lookup"><span data-stu-id="3a40e-119">Starting the Orchestration</span></span>  
  
#### <a name="to-start-the-orchestration"></a><span data-ttu-id="3a40e-120">若要启动的业务流程</span><span class="sxs-lookup"><span data-stu-id="3a40e-120">To start the orchestration</span></span>  
  
1. <span data-ttu-id="3a40e-121">单击**启动**，依次指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理。**</span><span class="sxs-lookup"><span data-stu-id="3a40e-121">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration.**</span></span>  
  
2. <span data-ttu-id="3a40e-122">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开所需应用程序，，然后单击**业务流程**。</span><span class="sxs-lookup"><span data-stu-id="3a40e-122">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand the desired application, and then click **Orchestrations**.</span></span>  
  
3. <span data-ttu-id="3a40e-123">在详细信息窗格中，右键单击该业务流程，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="3a40e-123">In the details pane, right-click the orchestration and click **Start**.</span></span>  
  
## <a name="stopping-and-restarting-a-host-instance"></a><span data-ttu-id="3a40e-124">停止并重新启动主机实例</span><span class="sxs-lookup"><span data-stu-id="3a40e-124">Stopping and Restarting a Host Instance</span></span>  
 <span data-ttu-id="3a40e-125">部署示例后，必须重新启动主机实例。</span><span class="sxs-lookup"><span data-stu-id="3a40e-125">After you deploy the sample, you must restart the host instance.</span></span>  
  
#### <a name="to-stop-and-restart-a-host-instance"></a><span data-ttu-id="3a40e-126">若要停止并重新启动主机实例</span><span class="sxs-lookup"><span data-stu-id="3a40e-126">To stop and restart a host instance</span></span>  
  
1. <span data-ttu-id="3a40e-127">单击**启动**，依次指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理。**</span><span class="sxs-lookup"><span data-stu-id="3a40e-127">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration.**</span></span>  
  
2. <span data-ttu-id="3a40e-128">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="3a40e-128">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Host Instances**.</span></span>  
  
3. <span data-ttu-id="3a40e-129">在右窗格中，右键单击主机实例 （例如，计算机名称），然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="3a40e-129">In the right pane, right-click the host instance (for example, the computer name), and click **Stop**.</span></span>  
  
    <span data-ttu-id="3a40e-130">主机实例的状态将变为**已停止**。</span><span class="sxs-lookup"><span data-stu-id="3a40e-130">The status of the host instance changes to **Stopped**.</span></span>  
  
4. <span data-ttu-id="3a40e-131">在右窗格中，右键单击主机实例，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="3a40e-131">In the right pane, right-click the host instance and click **Start**.</span></span>  
  
    <span data-ttu-id="3a40e-132">主机实例的状态将变为**启动挂起**。</span><span class="sxs-lookup"><span data-stu-id="3a40e-132">The status of the host instance changes to **Start pending**.</span></span>  
  
    <span data-ttu-id="3a40e-133">若要将状态更改为**运行**然后单击**刷新**，或右键单击主机实例，然后单击**刷新**。</span><span class="sxs-lookup"><span data-stu-id="3a40e-133">To change the status to **Running** and click **Refresh**, or right-click the host instance and then click **Refresh**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a40e-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a40e-134">See Also</span></span>  
 [<span data-ttu-id="3a40e-135">保护适配器</span><span class="sxs-lookup"><span data-stu-id="3a40e-135">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)