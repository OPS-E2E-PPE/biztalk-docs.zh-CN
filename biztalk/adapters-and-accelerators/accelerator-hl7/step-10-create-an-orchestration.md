---
title: 步骤 10:创建一个业务流程 |Microsoft Docs
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
ms.openlocfilehash: da424576feb01762b703f43e796956e2dbb25228
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289001"
---
# <a name="step-10-create-an-orchestration"></a><span data-ttu-id="c66be-102">步骤 10:创建一个业务流程</span><span class="sxs-lookup"><span data-stu-id="c66be-102">Step 10: Create an Orchestration</span></span>
<span data-ttu-id="c66be-103">在此步骤中，使用业务流程设计器来创建用于表示检索其他患者的详细信息，以完全填充 ADT_A04 消息的业务流程的业务流程。</span><span class="sxs-lookup"><span data-stu-id="c66be-103">In this step, you use Orchestration Designer to create an orchestration to represent the business process for retrieving additional patient details to fully populate an ADT_A04 message.</span></span> <span data-ttu-id="c66be-104">使用业务流程设计器，则选择表示此业务流程的操作所需的业务流程形状。</span><span class="sxs-lookup"><span data-stu-id="c66be-104">Using Orchestration Designer, you select the orchestration shapes required to represent actions for this business process.</span></span> <span data-ttu-id="c66be-105">在更高版本的练习中，您提供其他信息以配置的形状，以便它们可以正常运行。</span><span class="sxs-lookup"><span data-stu-id="c66be-105">In later exercises, you provide additional information to configure the shapes so that they can function properly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c66be-106">以下步骤中创建的业务流程仅适用于本教程的上下文。</span><span class="sxs-lookup"><span data-stu-id="c66be-106">The orchestration created in the following steps only works in the context of this tutorial.</span></span> <span data-ttu-id="c66be-107">为了使业务流程才能正常工作，它需要的程序集引用、 映射和使用本教程时创建的其他项目。</span><span class="sxs-lookup"><span data-stu-id="c66be-107">In order for the orchestration to work correctly, it needs the assembly references, maps, and the other artifacts that you create while using this tutorial.</span></span>  
  
### <a name="to-create-an-orchestration"></a><span data-ttu-id="c66be-108">若要创建一个业务流程</span><span class="sxs-lookup"><span data-stu-id="c66be-108">To create an orchestration</span></span>  
  
1. <span data-ttu-id="c66be-109">在解决方案资源管理器中右键单击**BTAHL7 项目**，依次指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="c66be-109">In Solution Explorer, right-click **BTAHL7 Project**, point to **Add**, and then click **New Item**.</span></span>  
  
2. <span data-ttu-id="c66be-110">在中**添加新项**对话框中**类别**窗格中，单击**业务流程文件**。</span><span class="sxs-lookup"><span data-stu-id="c66be-110">In the **Add New Item** dialog box, in the **Categories** pane, click **Orchestration Files**.</span></span>  
  
3. <span data-ttu-id="c66be-111">在中**模板**窗格中，单击**BizTalk 业务流程**。</span><span class="sxs-lookup"><span data-stu-id="c66be-111">In the **Templates** pane, click **BizTalk Orchestration**.</span></span>  
  
4. <span data-ttu-id="c66be-112">在中**名称**字段中，键入**门铃 Orchestration.odx** (请注意，单词之间没有空格**门铃**并**业务流程**) 作为业务流程名称，然后单击**添加**创建新的业务流程文件。</span><span class="sxs-lookup"><span data-stu-id="c66be-112">In the **Name** field, type **Doorbell Orchestration.odx** (note that there is a space between the word **Doorbell** and **Orchestration**) as the orchestration name, and then click **Add** to create a new orchestration file.</span></span>  
  
5. <span data-ttu-id="c66be-113">在中**视图**菜单上，单击**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="c66be-113">In the **View** menu, click **Toolbox**.</span></span>  
  
6. <span data-ttu-id="c66be-114">在**工具箱**窗格中，拖动**接收**到设计视图图面上形状并将其放在标记为区域**从工具箱中删除形状**。</span><span class="sxs-lookup"><span data-stu-id="c66be-114">In the **Toolbox** pane, drag the **Receive** shape to the Design view surface and drop it on the area labeled **Drop a shape from the toolbox here**.</span></span>  
  
7. <span data-ttu-id="c66be-115">在属性窗口 （在屏幕的底部） 中，单击**名称**属性，然后键入**DoorbellReceive**的名称作为**接收**形状，，然后按**输入**。</span><span class="sxs-lookup"><span data-stu-id="c66be-115">In the Properties window (on the bottom right of your screen), click the **Name** property and type **DoorbellReceive** as the name of the **Receive** shape, and then press **Enter**.</span></span>  
  
8. <span data-ttu-id="c66be-116">在属性窗口中更改**激活**属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="c66be-116">In the Properties window, change the **Activate** property to **True**.</span></span>  
  
9. <span data-ttu-id="c66be-117">拖动**转换**形状从工具箱拖放直接**DoorbellReceive**形状。</span><span class="sxs-lookup"><span data-stu-id="c66be-117">Drag the **Transform** shape from the Toolbox and drop it directly below the **DoorbellReceive** shape.</span></span>  
  
10. <span data-ttu-id="c66be-118">在属性窗口 （在屏幕的底部） 中，单击**名称**要更改的名称属性**转换**形状变为**DoorbellTransform**，然后按**输入**。</span><span class="sxs-lookup"><span data-stu-id="c66be-118">In the Properties window (on the bottom right of your screen), click the **Name** property to change the name of the **Transform** shape to **DoorbellTransform**, and then press **Enter**.</span></span>  
  
11. <span data-ttu-id="c66be-119">在中**工具箱**窗格中，拖动**消息赋值**到设计视图图面上形状并将其放在下方的区域上**ConstructMessage_1**形状。</span><span class="sxs-lookup"><span data-stu-id="c66be-119">In the **Toolbox** pane, drag the **Message Assignment** shape to the Design view surface and drop it on the area directly below the **ConstructMessage_1** shape.</span></span>  
  
12. <span data-ttu-id="c66be-120">在业务流程设计视图图面上，单击**MessageAssignment_1**形状，然后在**属性**窗格中，单击**名称**并键入新名称**DoorbellFinalTransform**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="c66be-120">In the orchestration Design view surface, click the **MessageAssignment_1** shape, and in the **Properties** pane, click **Name** and type the new name **DoorbellFinalTransform**, and then press **Enter**.</span></span>  
  
13. <span data-ttu-id="c66be-121">拖动**发送**从工具箱形状，然后将其放在下方的连接线上**DoorbellFinalTransform**形状。</span><span class="sxs-lookup"><span data-stu-id="c66be-121">Drag the **Send** shape from the Toolbox and drop it on the connecting line directly below the **DoorbellFinalTransform** shape.</span></span>  
  
14. <span data-ttu-id="c66be-122">在属性窗口 （在屏幕的底部） 中，单击**名称**要更改的名称属性**发送**形状变为**DoorbellSend**，然后按**输入**。</span><span class="sxs-lookup"><span data-stu-id="c66be-122">In the Properties window (on the bottom right of your screen), click the **Name** property to change the name of the **Send** shape to **DoorbellSend**, and then press **Enter**.</span></span>  
  
    <span data-ttu-id="c66be-123">请继续执行[步骤 11:创建业务流程变量](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md)。</span><span class="sxs-lookup"><span data-stu-id="c66be-123">Proceed to [Step 11: Create Orchestration Variables](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c66be-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="c66be-124">See Also</span></span>  
 [<span data-ttu-id="c66be-125">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="c66be-125">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)