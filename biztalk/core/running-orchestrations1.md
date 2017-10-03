---
title: "运行 Orchestrations1 |Microsoft 文档"
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
- host instances, stopping and restarting
- orchestrations, compiling
- orchestrations, deploying
ms.assetid: b992bdba-630d-4f28-aca8-c568f3c27968
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3bc4326d5821dd9fb672d8dabf9751a3fa2d816
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="running-orchestrations"></a><span data-ttu-id="2950b-102">运行业务流程</span><span class="sxs-lookup"><span data-stu-id="2950b-102">Running Orchestrations</span></span>
<span data-ttu-id="2950b-103">以下过程介绍如何生成、部署、绑定和启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="2950b-103">The following procedures describe how to build, deploy, bind, and start an orchestration.</span></span>  
  
## <a name="creating-a-strong-name-key"></a><span data-ttu-id="2950b-104">创建强名称密钥</span><span class="sxs-lookup"><span data-stu-id="2950b-104">Creating a Strong Name Key</span></span>  
  
#### <a name="to-create-a-strong-name-key"></a><span data-ttu-id="2950b-105">若要创建强名称密钥</span><span class="sxs-lookup"><span data-stu-id="2950b-105">To create a strong name key</span></span>  
  
1.  <span data-ttu-id="2950b-106">启动 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="2950b-106">Start a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command Prompt.</span></span>  
  
2.  <span data-ttu-id="2950b-107">例如，将目录更改为现有项目中，\<驱动器 >: \Adapter_Install\biztalk2010\my_project。</span><span class="sxs-lookup"><span data-stu-id="2950b-107">Change directories to an existing project, for example, \<drive>:\Adapter_Install\biztalk2010\my_project.</span></span>  
  
3.  <span data-ttu-id="2950b-108">在命令提示符中键入以下内容并按 Enter：</span><span class="sxs-lookup"><span data-stu-id="2950b-108">Type the following in the command prompt and press ENTER:</span></span>  
  
     `sn -k SSOSchedule.snk`  
  
## <a name="compiling-and-deploying-an-orchestration"></a><span data-ttu-id="2950b-109">编译和部署业务流程</span><span class="sxs-lookup"><span data-stu-id="2950b-109">Compiling and Deploying an Orchestration</span></span>  
  
#### <a name="to-compile-and-deploy-an-orchestration"></a><span data-ttu-id="2950b-110">若要编译并部署业务流程</span><span class="sxs-lookup"><span data-stu-id="2950b-110">To compile and deploy an orchestration</span></span>  
  
1.  <span data-ttu-id="2950b-111">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击 SSOSchedule 项目，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="2950b-111">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, right-click the SSOSchedule project, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="2950b-112">单击**通用属性**，然后展开**程序集**节点。</span><span class="sxs-lookup"><span data-stu-id="2950b-112">Click **Common Properties**, and expand the **Assembly** node.</span></span>  
  
3.  <span data-ttu-id="2950b-113">输入的路径中的 SSOSchedule.snk**程序集密钥文件**文本框。</span><span class="sxs-lookup"><span data-stu-id="2950b-113">Enter the path to SSOSchedule.snk in the **Assembly Key File** text box.</span></span>  
  
4.  <span data-ttu-id="2950b-114">验证配置 Properties\Deployment\Server 包含句点 （.） 或你计算机的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2950b-114">Verify that Configuration Properties\Deployment\Server contains a dot (.) or your computer name, and click **OK**.</span></span>  
  
5.  <span data-ttu-id="2950b-115">在解决方案资源管理器，右键单击**SSOSchedule**，然后单击**重新生成**。</span><span class="sxs-lookup"><span data-stu-id="2950b-115">In Solution Explorer, right-click **SSOSchedule**, and click **Rebuild**.</span></span>  
  
6.  <span data-ttu-id="2950b-116">右键单击**SSOSchedule**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="2950b-116">Right-click the **SSOSchedule**, and click **Deploy**.</span></span>  
  
## <a name="starting-the-orchestration"></a><span data-ttu-id="2950b-117">启动业务流程</span><span class="sxs-lookup"><span data-stu-id="2950b-117">Starting the Orchestration</span></span>  
  
#### <a name="to-start-the-orchestration"></a><span data-ttu-id="2950b-118">若要启动业务流程</span><span class="sxs-lookup"><span data-stu-id="2950b-118">To start the orchestration</span></span>  
  
1.  <span data-ttu-id="2950b-119">在 BizTalk 管理控制台中，选择要启动的业务流程。</span><span class="sxs-lookup"><span data-stu-id="2950b-119">In the BizTalk Administration console, select the orchestration you want to start.</span></span>  
  
2.  <span data-ttu-id="2950b-120">右键单击业务流程和单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="2950b-120">Right-click the orchestration and click **Start**.</span></span>  
  
## <a name="stopping-and-restarting-a-host-instance"></a><span data-ttu-id="2950b-121">停止并重新启动主机实例</span><span class="sxs-lookup"><span data-stu-id="2950b-121">Stopping and Restarting a Host Instance</span></span>  
 <span data-ttu-id="2950b-122">部署示例后，必须重新启动主机实例。</span><span class="sxs-lookup"><span data-stu-id="2950b-122">After deploying the sample, you must restart the host instance.</span></span>  
  
#### <a name="to-stop-and-restart-a-host-instance"></a><span data-ttu-id="2950b-123">若要停止并重新启动主机实例</span><span class="sxs-lookup"><span data-stu-id="2950b-123">To stop and restart a host instance</span></span>  
  
1.  <span data-ttu-id="2950b-124">单击**启动**，指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后选择**BizTalk Server 管理。**</span><span class="sxs-lookup"><span data-stu-id="2950b-124">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and select **BizTalk Server Administration.**</span></span>  
  
2.  <span data-ttu-id="2950b-125">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，双击**Microsoft BizTalk Server （本地）**节点，然后展开**主机**。</span><span class="sxs-lookup"><span data-stu-id="2950b-125">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, double-click the **Microsoft BizTalk Server (local)** node, and expand **Hosts**.</span></span>  
  
3.  <span data-ttu-id="2950b-126">在左窗格中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="2950b-126">In the left pane, select the **BizTalkServerApplication**.</span></span>  
  
4.  <span data-ttu-id="2950b-127">在右窗格中，右键单击主机实例 （例如，计算机名称），然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="2950b-127">In the right pane, right-click the host instance (for example, the computer name), and click **Stop**.</span></span>  
  
     <span data-ttu-id="2950b-128">主机实例的状态更改为**已停止**。</span><span class="sxs-lookup"><span data-stu-id="2950b-128">The status of the host instance changes to **Stopped**.</span></span>  
  
5.  <span data-ttu-id="2950b-129">在右窗格中，右键单击主机实例，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="2950b-129">In the right pane, right-click the host instance and click **Start**.</span></span>  
  
     <span data-ttu-id="2950b-130">主机实例的状态更改为**启动挂起**。</span><span class="sxs-lookup"><span data-stu-id="2950b-130">The status of the host instance changes to **Start pending**.</span></span>  
  
     <span data-ttu-id="2950b-131">若要将状态更改为**运行**，单击**刷新**，或右键单击主机实例，然后单击**刷新**。</span><span class="sxs-lookup"><span data-stu-id="2950b-131">To change the status to **Running**, click **Refresh**, or right-click the host instance and then click **Refresh**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2950b-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2950b-132">See Also</span></span>  
 [<span data-ttu-id="2950b-133">使用单一登录</span><span class="sxs-lookup"><span data-stu-id="2950b-133">Using Single Sign-On</span></span>](../core/using-single-sign-on3.md)