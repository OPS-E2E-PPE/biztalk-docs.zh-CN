---
title: "修改现有 PIP 在 RNPIPs |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RNPIPs
- modifying, PIPs
- PIPs, modifying
- assemblies, RNPIPs
ms.assetid: f2ed25c4-1979-4691-9315-e7568e7cca8b
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce7f87d9af24e6388199e76e9cbf0eba076ceacf
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="modifying-an-existing-pip-in-rnpips"></a><span data-ttu-id="7ea2a-102">修改在 RNPIPs 现有 PIP</span><span class="sxs-lookup"><span data-stu-id="7ea2a-102">Modifying an Existing PIP in RNPIPs</span></span>
<span data-ttu-id="7ea2a-103">本主题介绍如何更改和重新部署安装的合作伙伴接口过程 (PIP) 架构之一[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-103">This topic describes how to change and re-deploy one of the Partner Interface Process (PIP) schemas installed by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] setup.</span></span> <span data-ttu-id="7ea2a-104">该架构部署为 RNPIP 程序集的组成部分。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-104">You deploy the schema as part of the RNPIPs assembly.</span></span>  
  
### <a name="to-modify-an-existing-pip-in-rnpips"></a><span data-ttu-id="7ea2a-105">修改 RNPIP 中的现有 PIP</span><span class="sxs-lookup"><span data-stu-id="7ea2a-105">To modify an existing PIP in RNPIPs</span></span>  
  
1.  <span data-ttu-id="7ea2a-106">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-106">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="7ea2a-107">找到\<*驱动器*\>files\microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Utilities\Schema 生成器文件夹。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-107">Locate the \<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Utilities\Schema Generator folder.</span></span>  
  
3.  <span data-ttu-id="7ea2a-108">在命令提示符处，键入**CScript InstallDTD.vbs**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-108">At the command prompt, type **CScript InstallDTD.vbs**, and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7ea2a-109">只需执行步骤 1 和 2 一次后安装 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-109">You only have to do steps 1 and 2 one time after you install BizTalk Server.</span></span>  
  
4.  <span data-ttu-id="7ea2a-110">启动**Microsoft Visual Studio 2012**。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-110">Start **Microsoft Visual Studio 2012**.</span></span>  
  
5.  <span data-ttu-id="7ea2a-111">在**文件**菜单上，指向**打开**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-111">In the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
6.  <span data-ttu-id="7ea2a-112">在**打开项目**对话框中，移动到\<*驱动器*\>files\microsoft BizTalk\<版本\>RosettaNet\SDK\ 快捷键架构，，然后选择**RNPIPs.btproj**。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-112">In the **Open Project** dialog box, move to \<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas, and then select **RNPIPs.btproj**.</span></span>  
  
7.  <span data-ttu-id="7ea2a-113">在**视图**菜单上，单击**BizTalk 资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-113">In the **View** menu, click **BizTalk Explorer**.</span></span> <span data-ttu-id="7ea2a-114">展开**程序集**，然后右键单击**Microsoft.Solutions.BTARN.Schemas.RNPIPs(3.3.0.0)**。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-114">Expand **Assemblies**, and then right-click **Microsoft.Solutions.BTARN.Schemas.RNPIPs(3.3.0.0)**.</span></span> <span data-ttu-id="7ea2a-115">单击**取消部署**。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-115">Click **Undeploy**.</span></span>  
  
8.  <span data-ttu-id="7ea2a-116">启动**Visual Studio 2012 的命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-116">Start **Visual Studio 2012 Command Prompt**.</span></span>  
  
9. <span data-ttu-id="7ea2a-117">将移动到在步骤 6，在命令提示符下，键入中输入的位置**sn-k RNPIPs.snk**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-117">Move to the location entered in step 6, at the command prompt, type **sn -k RNPIPs.snk**, and then press **Enter**.</span></span>  
  
10. <span data-ttu-id="7ea2a-118">在解决方案资源管理器，右键单击**RNPIPs**，单击**属性**，单击**通用属性**，然后单击**程序集。**</span><span class="sxs-lookup"><span data-stu-id="7ea2a-118">In Solution Explorer, right-click **RNPIPs**, click **Properties**, click **Common Properties**, and then click **Assembly.**</span></span>  
  
11. <span data-ttu-id="7ea2a-119">在右窗格中，向下滚动到**强名称**中**程序集密钥文件**部分中，单击省略号按钮 （…） 按钮，转到在步骤 6，在命令提示符下，键入中输入的位置**RNPIPs.snk**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-119">In the right pane, scroll down to **Strong Name**, in the **Assembly Key File** section, click the ellipsis button (...) button, go to the location entered in step 6, at the command prompt, type **RNPIPs.snk**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="7ea2a-120">在**属性页**对话框中，单击**配置属性**，单击**部署**，单击**重新部署**，选择`True`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-120">In the **Property Pages** dialog box, click **Configuration Properties**, click **Deployment**, click **Redeploy**, select `True`, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="7ea2a-121">根据需要编辑 RNPIP 中的任何现有架构。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-121">Edit any of the existing schemas in RNPIPs, as required.</span></span>  
  
14. <span data-ttu-id="7ea2a-122">单击**文件**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-122">Click **File**, and then click **Save**.</span></span>  
  
15. <span data-ttu-id="7ea2a-123">右键单击项目名称，并依次**生成**。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-123">Right-click the project name, and then click **Build**.</span></span>  
  
16. <span data-ttu-id="7ea2a-124">右键单击项目名称，并依次**部署**。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-124">Right-click the project name, and then click **Deploy**.</span></span>  
  
17. <span data-ttu-id="7ea2a-125">单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-125">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
18. <span data-ttu-id="7ea2a-126">在 BizTalk 管理控制台中，展开**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **（本地）**，然后展开**主机**。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-126">In BizTalk Administration Console, expand **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**, and then expand **Hosts**.</span></span>  
  
19. <span data-ttu-id="7ea2a-127">在右窗格中，右键单击该主机的名称，然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-127">In the right pane, right-click the name of the host, and then click **Stop**.</span></span> <span data-ttu-id="7ea2a-128">服务已停止后，右键单击该主机的名称，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="7ea2a-128">After the service has stopped, right-click the name of the host, and then click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ea2a-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ea2a-129">See Also</span></span>  
 <span data-ttu-id="7ea2a-130">[编程指南](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md) </span><span class="sxs-lookup"><span data-stu-id="7ea2a-130">[Programming Guide](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md) </span></span>  
 [<span data-ttu-id="7ea2a-131">并入新的合作伙伴接口流程</span><span class="sxs-lookup"><span data-stu-id="7ea2a-131">Incorporating a New Partner Interface Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)