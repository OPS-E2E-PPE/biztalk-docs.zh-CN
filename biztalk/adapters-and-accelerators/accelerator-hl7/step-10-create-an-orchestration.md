---
title: 步骤 10： 创建业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, creating
- creating, orchestrations
- message enrichment tutorial, orchestrations
ms.assetid: 10f5cf3d-4a34-4c80-89d1-c390552cfc09
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfc554a6f3c94a077b34ae79a36b8e484eadcd5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206565"
---
# <a name="step-10-create-an-orchestration"></a><span data-ttu-id="08958-102">步骤 10： 创建业务流程</span><span class="sxs-lookup"><span data-stu-id="08958-102">Step 10: Create an Orchestration</span></span>
<span data-ttu-id="08958-103">在此步骤中，你可以使用 Orchestration 设计器创建业务流程来表示检索其他患者的详细信息，以完全填充 ADT_A04 消息的业务流程。</span><span class="sxs-lookup"><span data-stu-id="08958-103">In this step, you use Orchestration Designer to create an orchestration to represent the business process for retrieving additional patient details to fully populate an ADT_A04 message.</span></span> <span data-ttu-id="08958-104">使用业务流程设计器，选择表示此业务流程的操作所需的业务流程形状。</span><span class="sxs-lookup"><span data-stu-id="08958-104">Using Orchestration Designer, you select the orchestration shapes required to represent actions for this business process.</span></span> <span data-ttu-id="08958-105">在更高版本的练习中，你提供其他信息以配置形状，以便它们可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="08958-105">In later exercises, you provide additional information to configure the shapes so that they can function properly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08958-106">在以下步骤中创建业务流程只能在本教程的上下文中。</span><span class="sxs-lookup"><span data-stu-id="08958-106">The orchestration created in the following steps only works in the context of this tutorial.</span></span> <span data-ttu-id="08958-107">为了使业务流程能够正常工作，它需要的程序集引用、 映射和其他使用本教程时创建的项目。</span><span class="sxs-lookup"><span data-stu-id="08958-107">In order for the orchestration to work correctly, it needs the assembly references, maps, and the other artifacts that you create while using this tutorial.</span></span>  
  
### <a name="to-create-an-orchestration"></a><span data-ttu-id="08958-108">若要创建业务流程</span><span class="sxs-lookup"><span data-stu-id="08958-108">To create an orchestration</span></span>  
  
1.  <span data-ttu-id="08958-109">在解决方案资源管理器，右键单击**BTAHL7 项目**，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="08958-109">In Solution Explorer, right-click **BTAHL7 Project**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="08958-110">在**添加新项**对话框中，在**类别**窗格中，单击**Orchestration 文件**。</span><span class="sxs-lookup"><span data-stu-id="08958-110">In the **Add New Item** dialog box, in the **Categories** pane, click **Orchestration Files**.</span></span>  
  
3.  <span data-ttu-id="08958-111">在**模板**窗格中，单击**BizTalk 业务流程**。</span><span class="sxs-lookup"><span data-stu-id="08958-111">In the **Templates** pane, click **BizTalk Orchestration**.</span></span>  
  
4.  <span data-ttu-id="08958-112">在**名称**字段中，键入**门铃 Orchestration.odx** (请注意，单词之间没有空格**门铃**和**Orchestration**) 作为业务流程的名称，然后单击**添加**若要创建新的业务流程文件。</span><span class="sxs-lookup"><span data-stu-id="08958-112">In the **Name** field, type **Doorbell Orchestration.odx** (note that there is a space between the word **Doorbell** and **Orchestration**) as the orchestration name, and then click **Add** to create a new orchestration file.</span></span>  
  
5.  <span data-ttu-id="08958-113">在**视图**菜单上，单击**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="08958-113">In the **View** menu, click **Toolbox**.</span></span>  
  
6.  <span data-ttu-id="08958-114">在**工具箱**窗格中，拖动**接收**形状变为设计视图图面，然后将其放置在标记为的区域上**从工具箱中删除形状**。</span><span class="sxs-lookup"><span data-stu-id="08958-114">In the **Toolbox** pane, drag the **Receive** shape to the Design view surface and drop it on the area labeled **Drop a shape from the toolbox here**.</span></span>  
  
7.  <span data-ttu-id="08958-115">在 （在你的屏幕的右下方） 的属性窗口中，单击**名称**属性并键入**DoorbellReceive**作为名称的**接收**形状，，然后按**输入**。</span><span class="sxs-lookup"><span data-stu-id="08958-115">In the Properties window (on the bottom right of your screen), click the **Name** property and type **DoorbellReceive** as the name of the **Receive** shape, and then press **Enter**.</span></span>  
  
8.  <span data-ttu-id="08958-116">在属性窗口中，更改**激活**属性**True**。</span><span class="sxs-lookup"><span data-stu-id="08958-116">In the Properties window, change the **Activate** property to **True**.</span></span>  
  
9. <span data-ttu-id="08958-117">拖动**转换**从工具箱形状并将其放正下方**DoorbellReceive**形状。</span><span class="sxs-lookup"><span data-stu-id="08958-117">Drag the **Transform** shape from the Toolbox and drop it directly below the **DoorbellReceive** shape.</span></span>  
  
10. <span data-ttu-id="08958-118">在 （在你的屏幕的右下方） 的属性窗口中，单击**名称**属性可以更改的名称**转换**形状变为**DoorbellTransform**，然后按**输入**。</span><span class="sxs-lookup"><span data-stu-id="08958-118">In the Properties window (on the bottom right of your screen), click the **Name** property to change the name of the **Transform** shape to **DoorbellTransform**, and then press **Enter**.</span></span>  
  
11. <span data-ttu-id="08958-119">在**工具箱**窗格中，拖动**消息分配**形状变为设计视图图面，然后将其放置在直接下方区域上**ConstructMessage_1**形状。</span><span class="sxs-lookup"><span data-stu-id="08958-119">In the **Toolbox** pane, drag the **Message Assignment** shape to the Design view surface and drop it on the area directly below the **ConstructMessage_1** shape.</span></span>  
  
12. <span data-ttu-id="08958-120">在业务流程设计视图图面中，单击**MessageAssignment_1**形状，然后在**属性**窗格中，单击**名称**，然后键入新名称**DoorbellFinalTransform**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="08958-120">In the orchestration Design view surface, click the **MessageAssignment_1** shape, and in the **Properties** pane, click **Name** and type the new name **DoorbellFinalTransform**, and then press **Enter**.</span></span>  
  
13. <span data-ttu-id="08958-121">拖动**发送**从工具箱形状并将其放连接线正下方**DoorbellFinalTransform**形状。</span><span class="sxs-lookup"><span data-stu-id="08958-121">Drag the **Send** shape from the Toolbox and drop it on the connecting line directly below the **DoorbellFinalTransform** shape.</span></span>  
  
14. <span data-ttu-id="08958-122">在 （在你的屏幕的右下方） 的属性窗口中，单击**名称**属性可以更改的名称**发送**形状变为**DoorbellSend**，然后按**输入**。</span><span class="sxs-lookup"><span data-stu-id="08958-122">In the Properties window (on the bottom right of your screen), click the **Name** property to change the name of the **Send** shape to **DoorbellSend**, and then press **Enter**.</span></span>  
  
 <span data-ttu-id="08958-123">继续执行[步骤 11： 创建业务流程变量](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md)。</span><span class="sxs-lookup"><span data-stu-id="08958-123">Proceed to [Step 11: Create Orchestration Variables](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08958-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08958-124">See Also</span></span>  
 [<span data-ttu-id="08958-125">消息扩充教程</span><span class="sxs-lookup"><span data-stu-id="08958-125">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)