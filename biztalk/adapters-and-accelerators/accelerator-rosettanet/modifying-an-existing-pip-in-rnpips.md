---
title: 修改 Rnpip 中的现有 PIP |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RNPIPs
- modifying, PIPs
- PIPs, modifying
- assemblies, RNPIPs
ms.assetid: f2ed25c4-1979-4691-9315-e7568e7cca8b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e3867c50e73c1747ed6e800f624b674e2ee737c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004862"
---
# <a name="modifying-an-existing-pip-in-rnpips"></a><span data-ttu-id="38056-102">修改 Rnpip 中的现有 PIP</span><span class="sxs-lookup"><span data-stu-id="38056-102">Modifying an Existing PIP in RNPIPs</span></span>
<span data-ttu-id="38056-103">本主题介绍如何更改和重新部署安装的 Microsoft 合作伙伴接口流程 (PIP) 架构中的一个[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="38056-103">This topic describes how to change and re-deploy one of the Partner Interface Process (PIP) schemas installed by Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] setup.</span></span> <span data-ttu-id="38056-104">该架构部署为 RNPIP 程序集的组成部分。</span><span class="sxs-lookup"><span data-stu-id="38056-104">You deploy the schema as part of the RNPIPs assembly.</span></span>  
  
### <a name="to-modify-an-existing-pip-in-rnpips"></a><span data-ttu-id="38056-105">修改 RNPIP 中的现有 PIP</span><span class="sxs-lookup"><span data-stu-id="38056-105">To modify an existing PIP in RNPIPs</span></span>  
  
1. <span data-ttu-id="38056-106">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="38056-106">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="38056-107">找到\<*驱动器*\>\Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Utilities\Schema Generator 文件夹。</span><span class="sxs-lookup"><span data-stu-id="38056-107">Locate the \<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Utilities\Schema Generator folder.</span></span>  
  
3. <span data-ttu-id="38056-108">在命令提示符处，键入**CScript InstallDTD.vbs**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="38056-108">At the command prompt, type **CScript InstallDTD.vbs**, and then press ENTER.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="38056-109">只需执行步骤 1 和 2 一次安装 BizTalk Server 之后。</span><span class="sxs-lookup"><span data-stu-id="38056-109">You only have to do steps 1 and 2 one time after you install BizTalk Server.</span></span>  
  
4. <span data-ttu-id="38056-110">启动**Microsoft Visual Studio 2012**。</span><span class="sxs-lookup"><span data-stu-id="38056-110">Start **Microsoft Visual Studio 2012**.</span></span>  
  
5. <span data-ttu-id="38056-111">在中**文件**菜单，依次指向**打开**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="38056-111">In the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
6. <span data-ttu-id="38056-112">在中**打开项目**对话框中，转到\<*驱动器*\>\Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\架构，并选择**RNPIPs.btproj**。</span><span class="sxs-lookup"><span data-stu-id="38056-112">In the **Open Project** dialog box, move to \<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas, and then select **RNPIPs.btproj**.</span></span>  
  
7. <span data-ttu-id="38056-113">在中**视图**菜单上，单击**BizTalk 浏览器**。</span><span class="sxs-lookup"><span data-stu-id="38056-113">In the **View** menu, click **BizTalk Explorer**.</span></span> <span data-ttu-id="38056-114">展开**程序集**，然后右键单击**microsoft.solutions.btarn.schemas.rnpips （3.3.0.0)**。</span><span class="sxs-lookup"><span data-stu-id="38056-114">Expand **Assemblies**, and then right-click **Microsoft.Solutions.BTARN.Schemas.RNPIPs(3.3.0.0)**.</span></span> <span data-ttu-id="38056-115">单击**取消部署**。</span><span class="sxs-lookup"><span data-stu-id="38056-115">Click **Undeploy**.</span></span>  
  
8. <span data-ttu-id="38056-116">启动**Visual Studio 2012 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="38056-116">Start **Visual Studio 2012 Command Prompt**.</span></span>  
  
9. <span data-ttu-id="38056-117">转到步骤 6，在命令提示符下，键入中输入的位置**sn-k RNPIPs.snk**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="38056-117">Move to the location entered in step 6, at the command prompt, type **sn -k RNPIPs.snk**, and then press **Enter**.</span></span>  
  
10. <span data-ttu-id="38056-118">在解决方案资源管理器中右键单击**Rnpip**，单击**属性**，单击**通用属性**，然后单击**程序集。**</span><span class="sxs-lookup"><span data-stu-id="38056-118">In Solution Explorer, right-click **RNPIPs**, click **Properties**, click **Common Properties**, and then click **Assembly.**</span></span>  
  
11. <span data-ttu-id="38056-119">在右窗格中，向下滚动到**强名称**，在**程序集密钥文件**部分中，单击省略号按钮 （...） 按钮，转到步骤 6，在命令提示符下，键入中输入的位置**RNPIPs.snk**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="38056-119">In the right pane, scroll down to **Strong Name**, in the **Assembly Key File** section, click the ellipsis button (...) button, go to the location entered in step 6, at the command prompt, type **RNPIPs.snk**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="38056-120">在中**属性页**对话框中，单击**配置属性**，单击**部署**，单击**重新部署**，选择`True`，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="38056-120">In the **Property Pages** dialog box, click **Configuration Properties**, click **Deployment**, click **Redeploy**, select `True`, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="38056-121">根据需要编辑 RNPIP 中的任何现有架构。</span><span class="sxs-lookup"><span data-stu-id="38056-121">Edit any of the existing schemas in RNPIPs, as required.</span></span>  
  
14. <span data-ttu-id="38056-122">单击**文件**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="38056-122">Click **File**, and then click **Save**.</span></span>  
  
15. <span data-ttu-id="38056-123">右键单击项目名称，然后依次**生成**。</span><span class="sxs-lookup"><span data-stu-id="38056-123">Right-click the project name, and then click **Build**.</span></span>  
  
16. <span data-ttu-id="38056-124">右键单击项目名称，然后依次**部署**。</span><span class="sxs-lookup"><span data-stu-id="38056-124">Right-click the project name, and then click **Deploy**.</span></span>  
  
17. <span data-ttu-id="38056-125">单击**启动**，依次指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="38056-125">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
18. <span data-ttu-id="38056-126">在 BizTalk 管理控制台中，展开**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**，然后展开**主机**。</span><span class="sxs-lookup"><span data-stu-id="38056-126">In BizTalk Administration Console, expand **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**, and then expand **Hosts**.</span></span>  
  
19. <span data-ttu-id="38056-127">在右窗格中，右键单击该主机的名称，然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="38056-127">In the right pane, right-click the name of the host, and then click **Stop**.</span></span> <span data-ttu-id="38056-128">服务停止后，右键单击主机的名称，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="38056-128">After the service has stopped, right-click the name of the host, and then click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38056-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="38056-129">See Also</span></span>  
 <span data-ttu-id="38056-130">[编程指南](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md) </span><span class="sxs-lookup"><span data-stu-id="38056-130">[Programming Guide](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md) </span></span>  
 [<span data-ttu-id="38056-131">并入新的合作伙伴接口流程</span><span class="sxs-lookup"><span data-stu-id="38056-131">Incorporating a New Partner Interface Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)