---
title: "自定义以使用特定 PIP 私有过程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private processes, PIPs
- private processes, customizing
- developing, private processes
- PIPs, private processes
- customizing private processes
ms.assetid: 88494e87-25a0-4c94-9396-61a0e07964aa
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec579716f9ab02389ce9f2d5ae5ec02ef0b30730
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="customizing-a-private-process-to-work-with-a-specific-pip"></a><span data-ttu-id="9dab4-102">自定义以使用特定 PIP 私有过程</span><span class="sxs-lookup"><span data-stu-id="9dab4-102">Customizing a Private Process to Work with a Specific PIP</span></span>
<span data-ttu-id="9dab4-103">你可以创建特定的筛选器表达式，使响应方专用业务流程处理或不处理特定合作伙伴接口流程 (PIP) 的实例。</span><span class="sxs-lookup"><span data-stu-id="9dab4-103">You can create a filter expression that will cause a responder private-process orchestration to process or not process instances of a specific Partner Interface Process (PIP).</span></span> <span data-ttu-id="9dab4-104">这样你就可以灵活地创建自定义专用流程来接收和处理某些 PIP 实例，而使用默认的专用流程来处理所有其他 PIP 实例。</span><span class="sxs-lookup"><span data-stu-id="9dab4-104">This gives you the flexibility of creating a custom private process to receive and process some PIP instances, and using the default private process to process all other PIP instances.</span></span>  
  
 <span data-ttu-id="9dab4-105">若要创建自定义专用流程以处理一个或多个特定 PIP，可为专用业务流程的接收形状创建筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="9dab4-105">To create a custom private process to work with a specific PIP or multiple specific PIPs, you create a filter expression for the receive shape of the private-process orchestration.</span></span> <span data-ttu-id="9dab4-106">[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK 中提供了一个示例：PIP3A4PrivateResponder.odx 业务流程。</span><span class="sxs-lookup"><span data-stu-id="9dab4-106">An example is the PIP3A4PrivateResponder.odx orchestration in the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK.</span></span> <span data-ttu-id="9dab4-107">它位于\<*驱动器*>: \Program Files\BizTalk\<版本 > RosettaNet\SDK\PIP3A4Process 使用业务 Rules\PIP3A4PrivateResponder 快捷键。</span><span class="sxs-lookup"><span data-stu-id="9dab4-107">It is located at \<*drive*>:\Program Files\BizTalk \<version> Accelerator for RosettaNet\SDK\PIP3A4Process Using Business Rules\PIP3A4PrivateResponder.</span></span>  
  
 <span data-ttu-id="9dab4-108">除创建只处理特定 PIP 实例的专用流程外，还必须自定义默认的 BTARN 专用流程，使其不处理该 PIP 的实例。</span><span class="sxs-lookup"><span data-stu-id="9dab4-108">Besides creating a private process that process only instances of a specific PIP, you must customize the default BTARN private process so that it will not process instances for that PIP.</span></span>  
  
### <a name="to-customize-a-responder-private-process-to-work-with-a-specific-pip"></a><span data-ttu-id="9dab4-109">自定义处理特定 PIP 的响应方专用流程</span><span class="sxs-lookup"><span data-stu-id="9dab4-109">To customize a responder private process to work with a specific PIP</span></span>  
  
1.  <span data-ttu-id="9dab4-110">在 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 中，创建处理特定 PIP 的自定义响应方专用业务流程。</span><span class="sxs-lookup"><span data-stu-id="9dab4-110">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], create a custom responder private-process orchestration for working with a specific PIP.</span></span> <span data-ttu-id="9dab4-111">可以基于默认的 BTARN 响应方专用业务流程来创建该业务流程。</span><span class="sxs-lookup"><span data-stu-id="9dab4-111">You can base the orchestration on the default BTARN responder private-process orchestration.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9dab4-112">你可以在 BTARN SDK 中查找默认的响应方专用业务流程，其名称为 PrivateResponder.odx。</span><span class="sxs-lookup"><span data-stu-id="9dab4-112">You can find the default responder private-process orchestration, named PrivateResponder.odx, in the BTARN SDK.</span></span> <span data-ttu-id="9dab4-113">它位于*\<驱动器 >*: \Program Files\BizTalk\<版本 > RosettaNet\SDK\PrivateResponder 快捷键。</span><span class="sxs-lookup"><span data-stu-id="9dab4-113">It is located at *\<drive>*:\Program Files\BizTalk \<version> Accelerator for RosettaNet\SDK\PrivateResponder.</span></span>  
  
2.  <span data-ttu-id="9dab4-114">将该自定义业务流程添加到 BizTalk 项目中。</span><span class="sxs-lookup"><span data-stu-id="9dab4-114">Add the custom orchestration to your BizTalk project.</span></span> <span data-ttu-id="9dab4-115">确保该项目中具有对 Microsoft.Solutions.BTARN.GlobalSchemas.dll 文件的引用。</span><span class="sxs-lookup"><span data-stu-id="9dab4-115">Make sure that your project has a reference to the Microsoft.Solutions.BTARN.GlobalSchemas.dll file.</span></span>  
  
3.  <span data-ttu-id="9dab4-116">在业务流程设计器中打开该自定义业务流程。</span><span class="sxs-lookup"><span data-stu-id="9dab4-116">Open the custom orchestration in Orchestration Designer.</span></span>  
  
4.  <span data-ttu-id="9dab4-117">右键单击第一个**接收**形状，激活业务流程，然后单击**编辑筛选器表达式**。</span><span class="sxs-lookup"><span data-stu-id="9dab4-117">Right-click the first **Receive** shape that activates the orchestration, and then click **Edit Filter Expression**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9dab4-118">默认 BTARN 响应方私有进程业务流程的接收形状具有两个筛选器条件： Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory = ="AsyncAction"或 Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory = ="SyncAction"。</span><span class="sxs-lookup"><span data-stu-id="9dab4-118">The receive shape for the default BTARN responder private-process orchestration has two filter conditions: Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory == "AsyncAction" or Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory == "SyncAction".</span></span> <span data-ttu-id="9dab4-119">此表达式确保该业务流程处理 RosettaNet 消息。</span><span class="sxs-lookup"><span data-stu-id="9dab4-119">This expression makes sure that the orchestration processes RosettaNet messages.</span></span> <span data-ttu-id="9dab4-120">请在自定义业务流程中保留此筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="9dab4-120">Retain this filter expression in your custom orchestration.</span></span>  
  
5.  <span data-ttu-id="9dab4-121">在**筛选器表达式**对话框中，在第一个打开行中，属性列中的选择**Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode**从下拉列表中，在运算符列中，选择 **==** 从下拉列表中，在值列中，键入的三个数字 PIP 代码，例如，键入**3A4**。</span><span class="sxs-lookup"><span data-stu-id="9dab4-121">In the **Filter Expression** dialog box, in the Property column in the first open row, select **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** from the drop-down list, in the Operator column, select **==** from the drop-down list, in the Value column, type the three-digit PIP code, for example, type **3A4**.</span></span>  
  
6.  <span data-ttu-id="9dab4-122">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="9dab4-122">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="9dab4-123">在业务流程设计器中打开默认的响应方专用业务流程项目 (PrivateResponder.btproj)。</span><span class="sxs-lookup"><span data-stu-id="9dab4-123">Open the default responder private-process orchestration project (PrivateResponder.btproj) in Orchestration Designer.</span></span> <span data-ttu-id="9dab4-124">确保在该项目中具有对 Microsoft.Solutions.BTARN.GlobalSchemas.dll 文件的有效引用。</span><span class="sxs-lookup"><span data-stu-id="9dab4-124">Make sure that the project has a working reference to the Microsoft.Solutions.BTARN.GlobalSchemas.dll file.</span></span>  
  
8.  <span data-ttu-id="9dab4-125">双击**PrivateResponder.odx**。</span><span class="sxs-lookup"><span data-stu-id="9dab4-125">Double-click **PrivateResponder.odx**.</span></span>  
  
9. <span data-ttu-id="9dab4-126">右键单击**ReceiveFromPublicProcessResponder**接收形状，并依次**编辑筛选器表达式**。</span><span class="sxs-lookup"><span data-stu-id="9dab4-126">Right-click the **ReceiveFromPublicProcessResponder** receive shape, and then click **Edit Filter Expression**.</span></span>  
  
10. <span data-ttu-id="9dab4-127">在**筛选器表达式**对话框中，在第一个打开行中，属性列中的选择**Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="9dab4-127">In the **Filter Expression** dialog box, in the Property column in the first open row, select **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** from the drop-down list.</span></span> <span data-ttu-id="9dab4-128">在运算符列中，选择**！ =**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="9dab4-128">In the Operator column, select **!=** from the drop-down list.</span></span> <span data-ttu-id="9dab4-129">在值列中，键入三位数 PIP 代码，例如，键入"**3A4"**。</span><span class="sxs-lookup"><span data-stu-id="9dab4-129">In the Value column, type the three-digit PIP code, for example, type "**3A4"**.</span></span>  
  
11. <span data-ttu-id="9dab4-130">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="9dab4-130">Click **OK**.</span></span>  
  
12. <span data-ttu-id="9dab4-131">在解决方案资源管理器，右键单击包含业务流程的项目，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="9dab4-131">In Solution Explorer, right-click the project that contains the orchestration and then click **Build**.</span></span>  
  
13. <span data-ttu-id="9dab4-132">已成功生成项目后，右键单击该项目，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="9dab4-132">After the project has been successfully built, right-click the project, and then click **Deploy**.</span></span>  
  
14. <span data-ttu-id="9dab4-133">上**文件**菜单上，指向**打开**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="9dab4-133">On the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
15. <span data-ttu-id="9dab4-134">将移动到\<*驱动器*>: \Program Files\BizTalk\<版本 > Accelerator for RosettaNet\SDK\PrivateResponder，选择**PrivateResponder.odx**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9dab4-134">Move to \<*drive*>:\Program Files\BizTalk \<version> Accelerator for RosettaNet\SDK\PrivateResponder, select **PrivateResponder.odx**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="9dab4-135">在解决方案资源管理器中，右键单击该项目，再单击“生成”。</span><span class="sxs-lookup"><span data-stu-id="9dab4-135">In Solution Explorer, right-click the project, and then click **Build**.</span></span>  
  
17. <span data-ttu-id="9dab4-136">已成功生成项目后，右键单击该项目，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="9dab4-136">After the project has been successfully built, right-click the project, and then click **Deploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dab4-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9dab4-137">See Also</span></span>  
 [<span data-ttu-id="9dab4-138">编程指南</span><span class="sxs-lookup"><span data-stu-id="9dab4-138">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)