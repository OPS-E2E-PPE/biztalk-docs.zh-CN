---
title: "运行 Orchestrations2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47496b875297e6c16141780979fda933f3968c6b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="running-orchestrations"></a><span data-ttu-id="426d4-102">运行业务流程</span><span class="sxs-lookup"><span data-stu-id="426d4-102">Running Orchestrations</span></span>
<span data-ttu-id="426d4-103">以下过程介绍如何生成、部署、绑定和启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="426d4-103">The following procedures describe how to build, deploy, bind, and start an orchestration.</span></span>  
  
## <a name="creating-a-strong-name-key"></a><span data-ttu-id="426d4-104">创建强名称密钥</span><span class="sxs-lookup"><span data-stu-id="426d4-104">Creating a Strong Name Key</span></span>  
  
#### <a name="to-create-a-strong-name-key"></a><span data-ttu-id="426d4-105">若要创建强名称密钥</span><span class="sxs-lookup"><span data-stu-id="426d4-105">To create a strong name key</span></span>  
  
1.  <span data-ttu-id="426d4-106">打开[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符。</span><span class="sxs-lookup"><span data-stu-id="426d4-106">Open a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command Prompt.</span></span>  
  
2.  <span data-ttu-id="426d4-107">将目录更改为指向现有的项目，然后按 ENTER 键。</span><span class="sxs-lookup"><span data-stu-id="426d4-107">Change directories to an existing project and press ENTER.</span></span>  
  
     <span data-ttu-id="426d4-108">例如：</span><span class="sxs-lookup"><span data-stu-id="426d4-108">For example:</span></span>  
  
     <span data-ttu-id="426d4-109">**\<驱动器\>: \Adapter_Install\biztalk\my_project**</span><span class="sxs-lookup"><span data-stu-id="426d4-109">**\<drive\>:\Adapter_Install\biztalk\my_project**</span></span>  
  
3.  <span data-ttu-id="426d4-110">在命令提示符下键入以下命令并按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="426d4-110">Type the following at the command prompt and press ENTER:</span></span>  
  
     `sn -k SSOSchedule.snk`  
  
## <a name="compiling-and-deploying-an-orchestration"></a><span data-ttu-id="426d4-111">编译和部署业务流程</span><span class="sxs-lookup"><span data-stu-id="426d4-111">Compiling and Deploying an Orchestration</span></span>  
  
#### <a name="to-compile-and-deploy-an-orchestration"></a><span data-ttu-id="426d4-112">若要编译并部署业务流程</span><span class="sxs-lookup"><span data-stu-id="426d4-112">To compile and deploy an orchestration</span></span>  
  
1.  <span data-ttu-id="426d4-113">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击**SSOSchedule**项目，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="426d4-113">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, right-click the **SSOSchedule** project, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="426d4-114">单击**通用属性**，然后展开**程序集**节点。</span><span class="sxs-lookup"><span data-stu-id="426d4-114">Click **Common Properties**, and expand the **Assembly** node.</span></span>  
  
3.  <span data-ttu-id="426d4-115">输入的路径中的 SSOSchedule.snk**程序集密钥文件**文本框。</span><span class="sxs-lookup"><span data-stu-id="426d4-115">Enter the path to SSOSchedule.snk in the **Assembly Key File** text box.</span></span>  
  
4.  <span data-ttu-id="426d4-116">验证配置 Properties\Deployment\Server 是句点 （.） 或您的计算机名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="426d4-116">Verify that Configuration Properties\Deployment\Server is a dot (.) or your computer name, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="426d4-117">在解决方案资源管理器，右键单击**SSOSchedule**，然后单击**重新生成**。</span><span class="sxs-lookup"><span data-stu-id="426d4-117">In Solution Explorer, right-click **SSOSchedule**, and then click **Rebuild**.</span></span>  
  
6.  <span data-ttu-id="426d4-118">右键单击**SSOSchedule**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="426d4-118">Right-click **SSOSchedule**, and then click **Deploy**.</span></span>  
  
## <a name="starting-the-orchestration"></a><span data-ttu-id="426d4-119">启动业务流程</span><span class="sxs-lookup"><span data-stu-id="426d4-119">Starting the Orchestration</span></span>  
  
#### <a name="to-start-the-orchestration"></a><span data-ttu-id="426d4-120">若要启动业务流程</span><span class="sxs-lookup"><span data-stu-id="426d4-120">To start the orchestration</span></span>  
  
1.  <span data-ttu-id="426d4-121">单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理。**</span><span class="sxs-lookup"><span data-stu-id="426d4-121">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration.**</span></span>  
  
2.  <span data-ttu-id="426d4-122">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开所需应用程序，，然后单击**业务流程**。</span><span class="sxs-lookup"><span data-stu-id="426d4-122">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand the desired application, and then click **Orchestrations**.</span></span>  
  
3.  <span data-ttu-id="426d4-123">在详细信息窗格中，右键单击业务流程，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="426d4-123">In the details pane, right-click the orchestration and click **Start**.</span></span>  
  
## <a name="stopping-and-restarting-a-host-instance"></a><span data-ttu-id="426d4-124">停止并重新启动主机实例</span><span class="sxs-lookup"><span data-stu-id="426d4-124">Stopping and Restarting a Host Instance</span></span>  
 <span data-ttu-id="426d4-125">部署示例后，你必须重新启动主机实例。</span><span class="sxs-lookup"><span data-stu-id="426d4-125">After you deploy the sample, you must restart the host instance.</span></span>  
  
#### <a name="to-stop-and-restart-a-host-instance"></a><span data-ttu-id="426d4-126">若要停止并重新启动主机实例</span><span class="sxs-lookup"><span data-stu-id="426d4-126">To stop and restart a host instance</span></span>  
  
1.  <span data-ttu-id="426d4-127">单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理。**</span><span class="sxs-lookup"><span data-stu-id="426d4-127">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration.**</span></span>  
  
2.  <span data-ttu-id="426d4-128">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**托管实例**。</span><span class="sxs-lookup"><span data-stu-id="426d4-128">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Host Instances**.</span></span>  
  
3.  <span data-ttu-id="426d4-129">在右窗格中，右键单击主机实例 （例如，计算机名称），然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="426d4-129">In the right pane, right-click the host instance (for example, the computer name), and click **Stop**.</span></span>  
  
     <span data-ttu-id="426d4-130">主机实例的状态更改为**已停止**。</span><span class="sxs-lookup"><span data-stu-id="426d4-130">The status of the host instance changes to **Stopped**.</span></span>  
  
4.  <span data-ttu-id="426d4-131">在右窗格中，右键单击主机实例，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="426d4-131">In the right pane, right-click the host instance and click **Start**.</span></span>  
  
     <span data-ttu-id="426d4-132">主机实例的状态更改为**启动挂起**。</span><span class="sxs-lookup"><span data-stu-id="426d4-132">The status of the host instance changes to **Start pending**.</span></span>  
  
     <span data-ttu-id="426d4-133">若要将状态更改为**运行**单击**刷新**，或右键单击主机实例，然后单击**刷新**。</span><span class="sxs-lookup"><span data-stu-id="426d4-133">To change the status to **Running** and click **Refresh**, or right-click the host instance and then click **Refresh**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="426d4-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="426d4-134">See Also</span></span>  
 [<span data-ttu-id="426d4-135">保护适配器</span><span class="sxs-lookup"><span data-stu-id="426d4-135">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)