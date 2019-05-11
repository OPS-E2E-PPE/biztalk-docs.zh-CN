---
title: 自定义处理特定 PIP 的专用流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private processes, PIPs
- private processes, customizing
- developing, private processes
- PIPs, private processes
- customizing private processes
ms.assetid: 88494e87-25a0-4c94-9396-61a0e07964aa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2a9bac75fd3cb71210fdfff99978d973f28c142
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284070"
---
# <a name="customizing-a-private-process-to-work-with-a-specific-pip"></a><span data-ttu-id="90e0d-102">自定义处理特定 PIP 的专用流程</span><span class="sxs-lookup"><span data-stu-id="90e0d-102">Customizing a Private Process to Work with a Specific PIP</span></span>
<span data-ttu-id="90e0d-103">可以创建一个筛选表达式，将使响应方专用业务流程来处理或不进程实例的特定合作伙伴接口流程 (PIP)。</span><span class="sxs-lookup"><span data-stu-id="90e0d-103">You can create a filter expression that will cause a responder private-process orchestration to process or not process instances of a specific Partner Interface Process (PIP).</span></span> <span data-ttu-id="90e0d-104">这使你能够灵活创建自定义专用流程来接收和处理某些 PIP 实例，并使用默认的专用流程来处理所有其他 PIP 实例。</span><span class="sxs-lookup"><span data-stu-id="90e0d-104">This gives you the flexibility of creating a custom private process to receive and process some PIP instances, and using the default private process to process all other PIP instances.</span></span>  
  
 <span data-ttu-id="90e0d-105">若要创建自定义的专用流程来处理特定 PIP 或多个特定 Pip，你创建专用业务流程接收形状的筛选的表达式。</span><span class="sxs-lookup"><span data-stu-id="90e0d-105">To create a custom private process to work with a specific PIP or multiple specific PIPs, you create a filter expression for the receive shape of the private-process orchestration.</span></span> <span data-ttu-id="90e0d-106">例如，在 PIP3A4PrivateResponder.odx 业务流程中 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK。</span><span class="sxs-lookup"><span data-stu-id="90e0d-106">An example is the PIP3A4PrivateResponder.odx orchestration in the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK.</span></span> <span data-ttu-id="90e0d-107">它位于\<*驱动器*\>: \Program Files\BizTalk\<版本\>Accelerator for RosettaNet\SDK\PIP3A4Process Using Business rules\pip3a4privateresponder。</span><span class="sxs-lookup"><span data-stu-id="90e0d-107">It is located at \<*drive*\>:\Program Files\BizTalk \<version\> Accelerator for RosettaNet\SDK\PIP3A4Process Using Business Rules\PIP3A4PrivateResponder.</span></span>  
  
 <span data-ttu-id="90e0d-108">除了创建处理实例特定 PIP 的专用流程，您必须自定义默认的 BTARN 专用流程以便它将处理该 pip 的实例。</span><span class="sxs-lookup"><span data-stu-id="90e0d-108">Besides creating a private process that process only instances of a specific PIP, you must customize the default BTARN private process so that it will not process instances for that PIP.</span></span>  
  
### <a name="to-customize-a-responder-private-process-to-work-with-a-specific-pip"></a><span data-ttu-id="90e0d-109">若要自定义响应方专用流程来处理特定 PIP</span><span class="sxs-lookup"><span data-stu-id="90e0d-109">To customize a responder private process to work with a specific PIP</span></span>  
  
1. <span data-ttu-id="90e0d-110">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，创建用于处理特定 PIP 的自定义响应方专用流程的业务流程。</span><span class="sxs-lookup"><span data-stu-id="90e0d-110">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], create a custom responder private-process orchestration for working with a specific PIP.</span></span> <span data-ttu-id="90e0d-111">您可以基于默认 BTARN 响应方专用流程业务流程上的业务流程。</span><span class="sxs-lookup"><span data-stu-id="90e0d-111">You can base the orchestration on the default BTARN responder private-process orchestration.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="90e0d-112">您可以找到默认响应方专用业务流程的业务流程，名称为 PrivateResponder.odx，BTARN SDK 中的。</span><span class="sxs-lookup"><span data-stu-id="90e0d-112">You can find the default responder private-process orchestration, named PrivateResponder.odx, in the BTARN SDK.</span></span> <span data-ttu-id="90e0d-113">它位于*\<驱动器\>*: \Program Files\BizTalk\<版本\>Accelerator for RosettaNet\SDK\PrivateResponder。</span><span class="sxs-lookup"><span data-stu-id="90e0d-113">It is located at *\<drive\>*:\Program Files\BizTalk \<version\> Accelerator for RosettaNet\SDK\PrivateResponder.</span></span>  
  
2. <span data-ttu-id="90e0d-114">向 BizTalk 项目中添加自定义业务流程。</span><span class="sxs-lookup"><span data-stu-id="90e0d-114">Add the custom orchestration to your BizTalk project.</span></span> <span data-ttu-id="90e0d-115">请确保你的项目具有对 Microsoft.Solutions.BTARN.GlobalSchemas.dll 文件的引用。</span><span class="sxs-lookup"><span data-stu-id="90e0d-115">Make sure that your project has a reference to the Microsoft.Solutions.BTARN.GlobalSchemas.dll file.</span></span>  
  
3. <span data-ttu-id="90e0d-116">在业务流程设计器中打开自定义业务流程。</span><span class="sxs-lookup"><span data-stu-id="90e0d-116">Open the custom orchestration in Orchestration Designer.</span></span>  
  
4. <span data-ttu-id="90e0d-117">右键单击第一个**接收**形状，激活该业务流程，然后单击**编辑筛选器表达式**。</span><span class="sxs-lookup"><span data-stu-id="90e0d-117">Right-click the first **Receive** shape that activates the orchestration, and then click **Edit Filter Expression**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="90e0d-118">默认 BTARN 响应方专用流程业务流程的接收形状具有两个筛选条件：Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory = ="AsyncAction"或 Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory = ="SyncAction"。</span><span class="sxs-lookup"><span data-stu-id="90e0d-118">The receive shape for the default BTARN responder private-process orchestration has two filter conditions: Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory == "AsyncAction" or Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory == "SyncAction".</span></span> <span data-ttu-id="90e0d-119">此表达式可确保该业务流程处理 RosettaNet 消息。</span><span class="sxs-lookup"><span data-stu-id="90e0d-119">This expression makes sure that the orchestration processes RosettaNet messages.</span></span> <span data-ttu-id="90e0d-120">保留在自定义业务流程中的此筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="90e0d-120">Retain this filter expression in your custom orchestration.</span></span>  
  
5. <span data-ttu-id="90e0d-121">在中**筛选器表达式**对话框中的属性列中第一个打开的行中，选择**Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode**从下拉列表中，在运算符列选择**==** 从下拉列表中，在值列中，键入三位 PIP 代码，例如，键入**3A4**。</span><span class="sxs-lookup"><span data-stu-id="90e0d-121">In the **Filter Expression** dialog box, in the Property column in the first open row, select **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** from the drop-down list, in the Operator column, select **==** from the drop-down list, in the Value column, type the three-digit PIP code, for example, type **3A4**.</span></span>  
  
6. <span data-ttu-id="90e0d-122">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="90e0d-122">Click **OK**.</span></span>  
  
7. <span data-ttu-id="90e0d-123">在业务流程设计器中打开默认响应方专用业务流程项目 (PrivateResponder.btproj)。</span><span class="sxs-lookup"><span data-stu-id="90e0d-123">Open the default responder private-process orchestration project (PrivateResponder.btproj) in Orchestration Designer.</span></span> <span data-ttu-id="90e0d-124">请确保项目具有对 Microsoft.Solutions.BTARN.GlobalSchemas.dll 文件的有效引用。</span><span class="sxs-lookup"><span data-stu-id="90e0d-124">Make sure that the project has a working reference to the Microsoft.Solutions.BTARN.GlobalSchemas.dll file.</span></span>  
  
8. <span data-ttu-id="90e0d-125">双击**PrivateResponder.odx**。</span><span class="sxs-lookup"><span data-stu-id="90e0d-125">Double-click **PrivateResponder.odx**.</span></span>  
  
9. <span data-ttu-id="90e0d-126">右键单击**ReceiveFromPublicProcessResponder**接收形状，然后依次**编辑筛选器表达式**。</span><span class="sxs-lookup"><span data-stu-id="90e0d-126">Right-click the **ReceiveFromPublicProcessResponder** receive shape, and then click **Edit Filter Expression**.</span></span>  
  
10. <span data-ttu-id="90e0d-127">在中**筛选器表达式**对话框中的属性列中第一个打开的行中，选择**Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="90e0d-127">In the **Filter Expression** dialog box, in the Property column in the first open row, select **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** from the drop-down list.</span></span> <span data-ttu-id="90e0d-128">在运算符列中，选择 **！ =** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="90e0d-128">In the Operator column, select **!=** from the drop-down list.</span></span> <span data-ttu-id="90e0d-129">在值列中，键入三位 PIP 代码，例如，类型"**3A4"**。</span><span class="sxs-lookup"><span data-stu-id="90e0d-129">In the Value column, type the three-digit PIP code, for example, type "**3A4"**.</span></span>  
  
11. <span data-ttu-id="90e0d-130">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="90e0d-130">Click **OK**.</span></span>  
  
12. <span data-ttu-id="90e0d-131">在解决方案资源管理器，右键单击包含业务流程的项目，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="90e0d-131">In Solution Explorer, right-click the project that contains the orchestration and then click **Build**.</span></span>  
  
13. <span data-ttu-id="90e0d-132">已成功生成项目后，右键单击项目，然后依次**部署**。</span><span class="sxs-lookup"><span data-stu-id="90e0d-132">After the project has been successfully built, right-click the project, and then click **Deploy**.</span></span>  
  
14. <span data-ttu-id="90e0d-133">上**文件**菜单，依次指向**打开**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="90e0d-133">On the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
15. <span data-ttu-id="90e0d-134">将移动到\<*驱动器*\>: \Program Files\BizTalk\<版本\>Accelerator for RosettaNet\SDK\PrivateResponder，选择**PrivateResponder.odx**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="90e0d-134">Move to \<*drive*\>:\Program Files\BizTalk \<version\> Accelerator for RosettaNet\SDK\PrivateResponder, select **PrivateResponder.odx**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="90e0d-135">在解决方案资源管理器中，右键单击该项目，再单击“生成”。</span><span class="sxs-lookup"><span data-stu-id="90e0d-135">In Solution Explorer, right-click the project, and then click **Build**.</span></span>  
  
17. <span data-ttu-id="90e0d-136">已成功生成项目后，右键单击项目，然后依次**部署**。</span><span class="sxs-lookup"><span data-stu-id="90e0d-136">After the project has been successfully built, right-click the project, and then click **Deploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90e0d-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="90e0d-137">See Also</span></span>  
 [<span data-ttu-id="90e0d-138">编程指南</span><span class="sxs-lookup"><span data-stu-id="90e0d-138">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)