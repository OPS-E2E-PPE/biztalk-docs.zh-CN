---
title: "步骤 11： 创建业务流程变量 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
- message enrichment tutorial, orchestrations
ms.assetid: 3d1f792d-fe74-4373-86fa-3debda55e732
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c12a437371c5412cfafa4140e74733655962fd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-11-create-orchestration-variables"></a><span data-ttu-id="a811a-102">步骤 11： 创建业务流程变量</span><span class="sxs-lookup"><span data-stu-id="a811a-102">Step 11: Create Orchestration Variables</span></span>
<span data-ttu-id="a811a-103">在此步骤中，你可以创建消息实例发送和接收的业务流程的业务流程变量。</span><span class="sxs-lookup"><span data-stu-id="a811a-103">In this step, you create the orchestration variables for the message instances sent and received by the orchestration.</span></span>  
  
 <span data-ttu-id="a811a-104">HL7 BizTalk 快捷键 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 序列化程序要求以下部件名称。</span><span class="sxs-lookup"><span data-stu-id="a811a-104">The BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) serializer expects the following part names.</span></span> <span data-ttu-id="a811a-105">如果使用任何其他部分的名称创建多部分消息，序列化程序将拒绝该消息。</span><span class="sxs-lookup"><span data-stu-id="a811a-105">If you create a multipart message with any other part names, the serializer rejects the message.</span></span> <span data-ttu-id="a811a-106">消息部分名称为：</span><span class="sxs-lookup"><span data-stu-id="a811a-106">The message part names are:</span></span>  
  
-   <span data-ttu-id="a811a-107">MSHSegment</span><span class="sxs-lookup"><span data-stu-id="a811a-107">MSHSegment</span></span>  
  
-   <span data-ttu-id="a811a-108">BodySegments</span><span class="sxs-lookup"><span data-stu-id="a811a-108">BodySegments</span></span>  
  
-   <span data-ttu-id="a811a-109">Z 段</span><span class="sxs-lookup"><span data-stu-id="a811a-109">Z segments</span></span>  
  
 <span data-ttu-id="a811a-110">下面是有关 Z 段部件的重要信息：</span><span class="sxs-lookup"><span data-stu-id="a811a-110">The following is important information about Z segment parts:</span></span>  
  
-   <span data-ttu-id="a811a-111">所有消息上文所述，无论 Z 段是否存在或不都包含三个部分。</span><span class="sxs-lookup"><span data-stu-id="a811a-111">All messages contain three parts as described above, regardless of whether a Z segment is present or not.</span></span>  
  
-   <span data-ttu-id="a811a-112">你可以使用 Z 段一部分来包含从消息实例，即尾随和未定义架构 （这也意味着它未声明） 中的数据。</span><span class="sxs-lookup"><span data-stu-id="a811a-112">You use a Z segment part to contain data from the message instance, which is trailing and not defined in the schema (which also means that it is undeclared).</span></span>  
  
-   <span data-ttu-id="a811a-113">如果没有未声明的数据，Z 段部分为空。</span><span class="sxs-lookup"><span data-stu-id="a811a-113">If there is no undeclared data, the Z segment part is blank.</span></span> <span data-ttu-id="a811a-114">查看 BizTalk 映射程序; 中的中间 XML 时，看不到 Z 段部分但是，在 BizTalk 运行状况和活动跟踪 (HAT) 工具中，你看到到每条消息的三个部分。</span><span class="sxs-lookup"><span data-stu-id="a811a-114">You do not see the Z segment parts when viewing the intermediate XML within BizTalk Mapper; however, in the BizTalk Health and Activity Tracking (HAT) tool, you see three parts to each message.</span></span>  
  
### <a name="to-create-orchestration-variables"></a><span data-ttu-id="a811a-115">若要创建业务流程变量</span><span class="sxs-lookup"><span data-stu-id="a811a-115">To create orchestration variables</span></span>  
  
1.  <span data-ttu-id="a811a-116">单击**业务流程视图**选项卡旁边**解决方案资源管理器**解决方案资源管理器下的选项卡。</span><span class="sxs-lookup"><span data-stu-id="a811a-116">Click the **Orchestration View** tab next to the **Solution Explorer** tab beneath the Solutions Explorer.</span></span>  
  
2.  <span data-ttu-id="a811a-117">在**业务流程视图**窗格中，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="a811a-117">In the **Orchestration View** pane, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="a811a-118">更改**标识符**中的属性**属性**窗格**DoorbellInputMessage**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="a811a-118">Change the **Identifier** property in the **Properties** pane to **DoorbellInputMessage**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="a811a-119">在**属性**窗格的下拉列表中**消息类型**，展开**架构**，然后单击**BTAHL7_Project.Doorbell**。</span><span class="sxs-lookup"><span data-stu-id="a811a-119">In the **Properties** pane, in the drop-down list for **Message Type**, expand **Schemas**, and then click **BTAHL7_Project.Doorbell**.</span></span>  
  
5.  <span data-ttu-id="a811a-120">重复步骤 2 和 3 以创建名为的另一条消息**DoorbellOutputMessage**。</span><span class="sxs-lookup"><span data-stu-id="a811a-120">Repeat steps 2 and 3 to create another message named **DoorbellOutputMessage**.</span></span>  
  
6.  <span data-ttu-id="a811a-121">在**属性**窗格的下拉列表中**消息类型**，展开**架构**，然后单击**BTAHL7Schemas.ADT_A04_22_GLO_DEF**.</span><span class="sxs-lookup"><span data-stu-id="a811a-121">In the **Properties** pane, in the drop-down list for **Message Type**, expand **Schemas**, and then click **BTAHL7Schemas.ADT_A04_22_GLO_DEF**.</span></span>  
  
7.  <span data-ttu-id="a811a-122">在**业务流程视图**窗格中，展开**类型**节点。</span><span class="sxs-lookup"><span data-stu-id="a811a-122">In the **Orchestration View** pane, expand the **Types** node.</span></span> <span data-ttu-id="a811a-123">右键单击**多部分消息类型**，然后单击**新多部分消息类型**。</span><span class="sxs-lookup"><span data-stu-id="a811a-123">Right-click **Multi-part Message Types**, and then click **New Multi-part Message Type**.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]<span data-ttu-id="a811a-124">创建名为的新消息类型**MultipartType_1**与名为新消息一起**MessagePart_1**。</span><span class="sxs-lookup"><span data-stu-id="a811a-124"> creates a new message type named **MultipartType_1** along with a new message named **MessagePart_1**.</span></span>  
  
8.  <span data-ttu-id="a811a-125">单击**MultipartType_1**，然后在**属性**窗口中，单击**标识符**，然后键入新名称**DoorbellFinalMessageType**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="a811a-125">Click **MultipartType_1**, and in the **Properties** window, click **Identifier** and type the new name **DoorbellFinalMessageType**, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a811a-126">在步骤 9 到 15，你将创建多部分消息的组成部分。</span><span class="sxs-lookup"><span data-stu-id="a811a-126">In steps 9 through 15, you will create the parts of the multipart message.</span></span> <span data-ttu-id="a811a-127">在其中创建的多部分消息部分的顺序非常重要。</span><span class="sxs-lookup"><span data-stu-id="a811a-127">The order in which you create the parts of a multipart message is important.</span></span> <span data-ttu-id="a811a-128">始终会创建标头，然后正文，然后 Z 段。</span><span class="sxs-lookup"><span data-stu-id="a811a-128">Always create the header, then the body, then the Z segment.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a811a-129">一次你已创建，并且名为消息部分中，不要重命名它们。</span><span class="sxs-lookup"><span data-stu-id="a811a-129">Once you have created and named the message parts, do not rename them.</span></span> <span data-ttu-id="a811a-130">如有必要，删除旧的正文部分，并使用新名称创建新的正文部分。</span><span class="sxs-lookup"><span data-stu-id="a811a-130">If necessary, delete the old body part, and create a new body part with a new name.</span></span>  
  
9. <span data-ttu-id="a811a-131">在**类型**窗口下**多部分消息类型**，展开**DoorbellFinalMessageType**，然后单击**MessagePart_1**。</span><span class="sxs-lookup"><span data-stu-id="a811a-131">In the **Types** window, under **Multi-part Message Types**, expand **DoorbellFinalMessageType**, and then click **MessagePart_1**.</span></span> <span data-ttu-id="a811a-132">在**属性**窗格中，输入**MSHSegment**为**标识符**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="a811a-132">In the **Properties** pane, enter **MSHSegment** for **Identifier**, and then press **Enter**.</span></span> <span data-ttu-id="a811a-133">中的下拉列表**类型**，展开**.NET 类**，然后单击\<**选择从引用的程序集 >**。</span><span class="sxs-lookup"><span data-stu-id="a811a-133">In the drop-down list for **Type**, expand **.NET Classes**, and then click \<**Select from referenced assemblies>**.</span></span>  
  
10. <span data-ttu-id="a811a-134">在**选择项目类型**对话框中，在左窗格中，单击**System.Xml**。</span><span class="sxs-lookup"><span data-stu-id="a811a-134">In the **Select Artifact Type** dialog box, in the left pane, click **System.Xml**.</span></span> <span data-ttu-id="a811a-135">在右窗格中，单击**XmlDocument**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a811a-135">In the right pane, click **XmlDocument**, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="a811a-136">在业务流程视图窗口中，右键单击**DoorbellFinalMessageType**，然后单击**新消息部分**创建 MessagePart_1。</span><span class="sxs-lookup"><span data-stu-id="a811a-136">In the Orchestration View window, right-click **DoorbellFinalMessageType**, and then click **New Message Part** to create MessagePart_1.</span></span>  
  
12. <span data-ttu-id="a811a-137">在**属性**窗口中，输入**BodySegments**为**标识符**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="a811a-137">In the **Properties** window, enter **BodySegments** for **Identifier**, and then press **Enter**.</span></span> <span data-ttu-id="a811a-138">中的下拉列表**类型**，展开**架构**，然后选择**BTAHL7Schemas.ADT_A04_22_GLO_DEF**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="a811a-138">In the drop-down list for **Type**, expand **Schemas**, and then select **BTAHL7Schemas.ADT_A04_22_GLO_DEF** from the drop-down list.</span></span>  
  
13. <span data-ttu-id="a811a-139">设置**消息正文部分**属性**True**。</span><span class="sxs-lookup"><span data-stu-id="a811a-139">Set the **Message Body Part** property to **True**.</span></span>  
  
14. <span data-ttu-id="a811a-140">在**业务流程视图**窗口中，右键单击**DoorbellFinalMessageType**，然后单击**新消息部分**。</span><span class="sxs-lookup"><span data-stu-id="a811a-140">In the **Orchestration View** window, right-click **DoorbellFinalMessageType**, and then click **New Message Part**.</span></span>  
  
15. <span data-ttu-id="a811a-141">在**属性**窗格中，输入**ZSegments**为**标识符**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="a811a-141">In the **Properties** pane, enter **ZSegments** for **Identifier**, and then press **Enter**.</span></span> <span data-ttu-id="a811a-142">单击**类型**，展开**.NET 类**，然后单击**System.String**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="a811a-142">Click **Type**, expand **.NET Classes**, and then click **System.String** from the drop-down list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a811a-143">你使用**System.String**为 Z 段消息部分，因为 Z 段中包含不需要符合架构的字符串数据。</span><span class="sxs-lookup"><span data-stu-id="a811a-143">You use **System.String** for the Z segments message part, because a Z segment contains string data that does not need to conform to a schema.</span></span>  
  
16. <span data-ttu-id="a811a-144">在**业务流程视图**窗口中，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="a811a-144">In the **Orchestration View** window, right-click **Messages**, and then click **New Message**.</span></span>  
  
17. <span data-ttu-id="a811a-145">在**属性**窗口中，输入**DoorbellFinalMessage**为**标识符**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="a811a-145">In the **Properties** window, enter **DoorbellFinalMessage** for **Identifier**, and then press **Enter**.</span></span> <span data-ttu-id="a811a-146">中的下拉列表**消息类型**，展开**多部分消息类型**，然后单击**BTAHL7_Project.DoorbellFinalMessageType**。</span><span class="sxs-lookup"><span data-stu-id="a811a-146">In the drop-down list for **Message Type**, expand **Multi-part Message Types**, and then click **BTAHL7_Project.DoorbellFinalMessageType**.</span></span>  
  
18. <span data-ttu-id="a811a-147">在**业务流程视图**窗口中，右键单击**变量**，然后单击**新变量**。</span><span class="sxs-lookup"><span data-stu-id="a811a-147">In the **Orchestration View** window, right-click **Variables**, and then click **New Variable**.</span></span>  
  
19. <span data-ttu-id="a811a-148">在**属性**窗格中，输入**HeaderInfo**为**标识符**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="a811a-148">In the **Properties** pane, enter **HeaderInfo** for **Identifier**, then press **Enter**.</span></span> <span data-ttu-id="a811a-149">中的下拉列表**类型**，双击\< **.NET 类 >**。</span><span class="sxs-lookup"><span data-stu-id="a811a-149">In the drop-down list for **Type**, double-click \<**.NET Class>**.</span></span>  
  
20. <span data-ttu-id="a811a-150">在**选择项目类型**窗口中的，在左窗格中，单击**System.Xml**。</span><span class="sxs-lookup"><span data-stu-id="a811a-150">In the **Select Artifact Type** window, in the left pane, click **System.Xml**.</span></span> <span data-ttu-id="a811a-151">在右窗格中，单击**XmlDocument**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a811a-151">In the right pane, click **XmlDocument**, and then click **OK**.</span></span>  
  
21. <span data-ttu-id="a811a-152">在**文件**菜单上，单击**保存所有**。</span><span class="sxs-lookup"><span data-stu-id="a811a-152">In the **File** menu, click **Save All**.</span></span>  
  
 <span data-ttu-id="a811a-153">继续执行[步骤 12： 配置业务流程形状](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md)。</span><span class="sxs-lookup"><span data-stu-id="a811a-153">Proceed to [Step 12: Configure Orchestration Shapes](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a811a-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a811a-154">See Also</span></span>  
 [<span data-ttu-id="a811a-155">消息扩充教程</span><span class="sxs-lookup"><span data-stu-id="a811a-155">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)