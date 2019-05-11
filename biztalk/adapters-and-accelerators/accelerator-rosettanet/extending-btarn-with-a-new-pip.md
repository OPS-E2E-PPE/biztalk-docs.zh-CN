---
title: 使用新 PIP 扩展 BTARN |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTARN, extending functionality
- PIPs, extending BTARN
- BTARN, PIPs
ms.assetid: 3db5cd5c-031f-4451-9be5-4b5d6163c3b1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3aa99d4bbf131587a48b5b0f417c4c08c142107
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283707"
---
# <a name="extending-btarn-with-a-new-pip"></a><span data-ttu-id="86ae8-102">使用新 PIP 扩展 BTARN</span><span class="sxs-lookup"><span data-stu-id="86ae8-102">Extending BTARN with a New PIP</span></span>
<span data-ttu-id="86ae8-103">本主题介绍如何扩展 Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]使用新的合作伙伴接口流程 (PIP) 架构。</span><span class="sxs-lookup"><span data-stu-id="86ae8-103">This topic describes how to extend Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] with a new Partner Interface Process (PIP) schema.</span></span> <span data-ttu-id="86ae8-104">这允许您添加的架构时该 PIP 不相关联的任何情况下安装架构基于 RosettaNet PIP[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="86ae8-104">This lets you add a schema based on a RosettaNet PIP when that PIP is not associated with any of the schemas installed by the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program.</span></span>  

 <span data-ttu-id="86ae8-105">当扩展[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]使用新的 PIP，你部署中它自己的程序集的新架构。</span><span class="sxs-lookup"><span data-stu-id="86ae8-105">When you extend [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] with a new PIP, you deploy the new schema in its own assembly.</span></span> <span data-ttu-id="86ae8-106">此外可以修改部署中的现有架构[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Rnpip 程序集。</span><span class="sxs-lookup"><span data-stu-id="86ae8-106">You can also modify an existing schema that is deployed within the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RNPIPs assembly.</span></span> <span data-ttu-id="86ae8-107">有关详细信息，请参阅[修改 Rnpip 中的现有 PIP](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)。</span><span class="sxs-lookup"><span data-stu-id="86ae8-107">For more information, see [Modifying an Existing PIP in RNPIPs](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md).</span></span>  

### <a name="to-extend-btarn-with-a-new-pip"></a><span data-ttu-id="86ae8-108">扩展 BTARN 使用新 PIP</span><span class="sxs-lookup"><span data-stu-id="86ae8-108">To extend BTARN with a new PIP</span></span>  

1. <span data-ttu-id="86ae8-109">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-109">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  

2. <span data-ttu-id="86ae8-110">在命令提示符处，转到\<*驱动器*\>: \Program Files\\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\Utilities\Schema Generator。</span><span class="sxs-lookup"><span data-stu-id="86ae8-110">At the command prompt, move to \<*drive*\>:\Program Files\\Microsoft  BizTalk 2013 Accelerator for RosettaNet\SDK\Utilities\Schema Generator.</span></span>  

3. <span data-ttu-id="86ae8-111">在命令提示符处，键入**CScript InstallDTD.vbs**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-111">At the command prompt, type **CScript InstallDTD.vbs**, and then press **Enter**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="86ae8-112">您只需在安装 BizTalk Server 之后一次执行步骤 1 到 3。</span><span class="sxs-lookup"><span data-stu-id="86ae8-112">You will only have to perform steps 1 through 3 once after you install BizTalk Server.</span></span>  

4. <span data-ttu-id="86ae8-113">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="86ae8-113">Start Visual Studio.</span></span>  

5. <span data-ttu-id="86ae8-114">在 **“文件”** 菜单上，指向 **“新建”**，再单击 **“项目”**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-114">On the **File** menu, point to **New**, and then click **Project**.</span></span>  

6. <span data-ttu-id="86ae8-115">在新建项目对话框中，选择**BizTalk 项目**在左窗格中，然后单击**空的 BizTalk Server 项目**右窗格中。</span><span class="sxs-lookup"><span data-stu-id="86ae8-115">In the New Project dialog box, select **BizTalk Projects** in the left pane, and then click **Empty BizTalk Server Project** in the right pane.</span></span>  

7. <span data-ttu-id="86ae8-116">单击**浏览**和指向要保存你的项目的目录。</span><span class="sxs-lookup"><span data-stu-id="86ae8-116">Click **Browse** and point to the directory where you want to save your project.</span></span>  

8. <span data-ttu-id="86ae8-117">在中**名称**框中，键入项目名称，如**MyCustomPIP**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-117">In the **Name** box, type a project name, such as **MyCustomPIP**, and then click **OK**.</span></span>  

9. <span data-ttu-id="86ae8-118">启动 Visual Studio 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="86ae8-118">Start Visual Studio command prompt.</span></span>  

10. <span data-ttu-id="86ae8-119">在命令提示符处，转到步骤 7 中，类型中输入的位置**sn-k\<项目 name.snk\>**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-119">At the command prompt, move to the location entered in step 7, type **sn -k \<project name.snk\>**, and then press **Enter**.</span></span>  

11. <span data-ttu-id="86ae8-120">在解决方案资源管理器中，右键单击项目名称，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-120">In Solutions Explorer, right-click the project name, and then click **Properties**.</span></span>  

12. <span data-ttu-id="86ae8-121">在中**属性页**对话框中，单击**程序集**下**通用属性**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="86ae8-121">In the **Property Pages** dialog box, click **Assembly** under **Common Properties** in the left pane.</span></span>  

13. <span data-ttu-id="86ae8-122">在右窗格中，向下滚动到**强名称**，单击**程序集密钥文件**，然后单击右窗格中的省略号按钮 （...）。</span><span class="sxs-lookup"><span data-stu-id="86ae8-122">In the right pane, scroll down to **Strong Name**, click **Assembly Key File**, and then click the ellipsis button (...) in the right pane.</span></span> <span data-ttu-id="86ae8-123">转到步骤 7 中输入的位置并选择在步骤 10 中创建的.snk 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="86ae8-123">Move to the location entered in step 7, and select the name of the .snk file created in step 10.</span></span>  

14. <span data-ttu-id="86ae8-124">在属性页对话框中，展开**配置属性**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-124">In the Property Pages dialog box, expand **Configuration Properties**, and then click **Deployment**.</span></span> <span data-ttu-id="86ae8-125">在右窗格中，单击**重新部署**，选择`True`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-125">In the right pane, click **Redeploy**, select `True`, and then click **OK**.</span></span>  

15. <span data-ttu-id="86ae8-126">在解决方案资源管理器中右键单击项目名称，指向**外**，然后单击**现有项**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-126">In Solution Explorer, right-click the project name, point to **Add**, and then click **Existing Item**.</span></span>  

16. <span data-ttu-id="86ae8-127">在中**添加现有项**对话框中，转到\<*驱动器*\>: \Program Files\\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\Schemas，选择**xml.xsd**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-127">In the **Add Existing Item** dialog box, move to \<*drive*\>:\Program Files\\Microsoft  BizTalk 2013 Accelerator for RosettaNet\SDK\Schemas, select **xml.xsd**, then click **Add**.</span></span>  

17. <span data-ttu-id="86ae8-128">下载要用 RosettaNet.org 扩展 Rnpip 的 PIP。有关详细信息，请参阅[并入新的合作伙伴接口流程](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)。</span><span class="sxs-lookup"><span data-stu-id="86ae8-128">Download the PIP that you are going to extend RNPIPs with RosettaNet.org. For more information, see [Incorporating a New Partner Interface Process](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md).</span></span>  

18. <span data-ttu-id="86ae8-129">在解决方案资源管理器，展开项目名称，右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-129">In Solution Explorer, expand the project name, right-click **Reference**, and then click **Add Reference**.</span></span>  

19. <span data-ttu-id="86ae8-130">在中**添加引用**对话框中，单击**浏览**，然后将移到\<*驱动器*\>: \Program Files\\Microsoft BizTalk 2013Accelerator for RosettaNet\Bin，然后选择**Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-130">In the **Add Reference** dialog box, click **Browse**, and move to \<*drive*\>:\Program Files\\Microsoft  BizTalk 2013 Accelerator for RosettaNet\Bin, and then select **Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll**.</span></span> <span data-ttu-id="86ae8-131">单击**开放**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-131">Click **Open**, and then click **OK**.</span></span>  

20. <span data-ttu-id="86ae8-132">在解决方案资源管理器中右键单击项目名称，指向**外**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-132">In Solution Explorer, right-click the project name, point to **Add**, and then click **Add Generated Items**.</span></span>  

21. <span data-ttu-id="86ae8-133">在中**添加生成的项**对话框中**类别**窗格中，单击**生成架构**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-133">In the **Add Generated Items** dialog box, in the **Categories** pane, click **Generate Schemas**.</span></span> <span data-ttu-id="86ae8-134">在中**模板**窗格中，单击**生成架构**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-134">In the **Templates** pane, click **Generate Schemas**, and then click **Add**.</span></span>  

22. <span data-ttu-id="86ae8-135">在生成架构对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="86ae8-135">In the Generate Schemas dialog box, do the following:</span></span>  


    |     <span data-ttu-id="86ae8-136">使用此选项</span><span class="sxs-lookup"><span data-stu-id="86ae8-136">Use this</span></span>      |                                                                    <span data-ttu-id="86ae8-137">执行的操作</span><span class="sxs-lookup"><span data-stu-id="86ae8-137">To do this</span></span>                                                                    |
    |-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
    | <span data-ttu-id="86ae8-138">**文档类型**</span><span class="sxs-lookup"><span data-stu-id="86ae8-138">**Document type**</span></span> |                                                              <span data-ttu-id="86ae8-139">选择**DTD 架构**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-139">Select **DTD Schema**.</span></span>                                                              |
    |  <span data-ttu-id="86ae8-140">**输入的文件**</span><span class="sxs-lookup"><span data-stu-id="86ae8-140">**Input File**</span></span>   | <span data-ttu-id="86ae8-141">单击**浏览**，转到包含从 rosettanet.org 下载得到的 DTD 文件的文件夹，选择的 DTD 文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-141">Click **Browse**, move to the folder that contains the DTD file from RosettaNet.org, select the DTD file that you want, and then click **Open**.</span></span> |


23. <span data-ttu-id="86ae8-142">在生成架构对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-142">In the Generate Schemas dialog box, click **OK**.</span></span>  

24. <span data-ttu-id="86ae8-143">在解决方案资源管理器，双击您刚导入的.xsd 文件。</span><span class="sxs-lookup"><span data-stu-id="86ae8-143">In Solution Explorer, double-click the .xsd file that you just imported.</span></span>  

25. <span data-ttu-id="86ae8-144">在 BizTalk 编辑器中，选择\<*架构*\>节点。</span><span class="sxs-lookup"><span data-stu-id="86ae8-144">In BizTalk Editor, select the \<*Schema*\> node.</span></span>  

26. <span data-ttu-id="86ae8-145">在属性窗口中向下滚动到**文档类型**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-145">In the Properties window, scroll down to **Document Type**.</span></span> <span data-ttu-id="86ae8-146">在中**文档类型**框中， **PIP**\<*三位代码*\>，例如**PIP3A2**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-146">In the **Document Type** box, **PIP**\<*three-digit code*\>, for example, **PIP3A2**.</span></span> <span data-ttu-id="86ae8-147">在中**文档版本**框中，键入**v**\<*xx.xx* \>或**R** \< *xx.xx*\>，例如**R01.02**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-147">In the **Document Version** box, type **v**\<*xx.xx*\> or **R**\<*xx.xx*\>, for example, **R01.02**.</span></span> <span data-ttu-id="86ae8-148">此版本应为 RosettaNet PIP 规范中所述。</span><span class="sxs-lookup"><span data-stu-id="86ae8-148">This version should be as documented in the RosettaNet PIP specification.</span></span>  

27. <span data-ttu-id="86ae8-149">在属性窗口中向下滚动到**根引用**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-149">In the Properties window, scroll down to **Root Reference**.</span></span> <span data-ttu-id="86ae8-150">单击**根引用**，然后从下拉列表中，选择根节点的架构，例如，选择**Pip3C5BillingStatementNotification**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-150">Click **Root Reference**, and from the drop-down list, select the root node of the schema, for example, select **Pip3C5BillingStatementNotification**.</span></span>  

28. <span data-ttu-id="86ae8-151">在属性窗口中，向上滚动到**目标 Namespace**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-151">In the Properties window, scroll up to **Target Namespace**.</span></span> <span data-ttu-id="86ae8-152">有关**目标 Namespace**，类型<strong>http://schemas.microsoft.com/biztalk/btarn/2004/\<DTD文件名\>.dtd</strong>，其中 DTD 文件名为，例如， **3C5_MS_R01_00_BillingStatementNotification.dtd**.</span><span class="sxs-lookup"><span data-stu-id="86ae8-152">For **Target Namespace**, type <strong>http://schemas.microsoft.com/biztalk/btarn/2004/\<DTD file name\>.dtd</strong>, where the DTD file name is, for example, **3C5_MS_R01_00_BillingStatementNotification.dtd**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="86ae8-153">对于 BTARN，要求此命名约定为的目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="86ae8-153">This naming convention for the target namespace is required for BTARN.</span></span> <span data-ttu-id="86ae8-154">如果使用另一个命名空间约定，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不会处理 PIP 文档进行架构验证。</span><span class="sxs-lookup"><span data-stu-id="86ae8-154">If you use another namespace convention, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] will not process PIP documents for schema validation.</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="86ae8-155">在目标命名空间属性中的 DTD 文件名包括 PIP 的版本号。</span><span class="sxs-lookup"><span data-stu-id="86ae8-155">The DTD file name in the target namespace property includes the version number of the PIP.</span></span> <span data-ttu-id="86ae8-156">这允许您使用同一 PIP 代码的多个版本。</span><span class="sxs-lookup"><span data-stu-id="86ae8-156">This lets you use multiple versions of the same PIP code.</span></span>  

29. <span data-ttu-id="86ae8-157">在属性窗口中，向上滚动到**导入**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-157">In the Properties window, scroll up to **Imports**.</span></span> <span data-ttu-id="86ae8-158">单击省略号按钮 （...） 下一步**导入**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-158">Click the ellipsis button (...) next to **Imports**, and then click **Add**.</span></span>  

30. <span data-ttu-id="86ae8-159">在中**BizTalk 类型选取器**对话框框中，展开\<*项目名称*\>，展开**引用**，依次展开**Microsoft.Solutions.BTARN.Schemas.RNPIPs**，展开**架构**，选择**Microsoft.Solutions.BTARN.Schemas.RNPIPs.BaseDataTypes**，单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="86ae8-159">In the **BizTalk Type Picker** dialog box, expand \<*Project Name*\>, expand **References**, expand **Microsoft.Solutions.BTARN.Schemas.RNPIPs**, expand **Schemas**, select **Microsoft.Solutions.BTARN.Schemas.RNPIPs.BaseDataTypes**, click **OK**, and then click **OK** again.</span></span>  

31. <span data-ttu-id="86ae8-160">右键单击项目名称，然后依次**部署**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-160">Right-click the project name, and then click **Deploy**.</span></span>  

32. <span data-ttu-id="86ae8-161">单击**启动**，依次指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-161">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

33. <span data-ttu-id="86ae8-162">在 BizTalk 管理控制台中，展开**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**，然后展开**主机**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-162">In BizTalk Administration Console, expand **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**, and then expand **Hosts**.</span></span> <span data-ttu-id="86ae8-163">下**主机**，单击**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-163">Under **Host**, click **BizTalkServerApplication**.</span></span>  

34. <span data-ttu-id="86ae8-164">在右窗格中，右键单击该主机的名称，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="86ae8-164">In the right pane, right-click the name of the host, and then click **Restart**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="86ae8-165">扩展 Rnpip 使用新导入的 PIP 之后, 您必须创建正确的 PIP 配置和协议中使用该 PIP[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="86ae8-165">After extending RNPIPs with a newly imported PIP, you must create the correct PIP configuration, and an agreement using that PIP, in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console.</span></span>  

## <a name="see-also"></a><span data-ttu-id="86ae8-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="86ae8-166">See Also</span></span>  
 <span data-ttu-id="86ae8-167">[并入新的合作伙伴接口流程](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md) </span><span class="sxs-lookup"><span data-stu-id="86ae8-167">[Incorporating a New Partner Interface Process](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md) </span></span>  
 <span data-ttu-id="86ae8-168">[使用 Pip](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md) </span><span class="sxs-lookup"><span data-stu-id="86ae8-168">[Working with PIPs](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md) </span></span>  
 [<span data-ttu-id="86ae8-169">修改 RNPIP 中的现有 PIP</span><span class="sxs-lookup"><span data-stu-id="86ae8-169">Modifying an Existing PIP in RNPIPs</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)