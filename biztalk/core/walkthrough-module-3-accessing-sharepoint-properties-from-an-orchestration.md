---
title: "演练： 模块 3-从业务流程访问 SharePoint 属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, Windows SharePoint Services adapters
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, orchestrations
- Windows SharePoint Services adapter tutorials, accessing SharePoint properties
ms.assetid: 310c4002-3416-44c6-b409-1d5467063e28
caps.latest.revision: "45"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a44fd7e30bf511ee77cc1f3e79f6ba63908259ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-module-3---accessing-sharepoint-properties-from-an-orchestration"></a><span data-ttu-id="f86aa-102">演练： 模块 3-从业务流程访问 SharePoint 属性</span><span class="sxs-lookup"><span data-stu-id="f86aa-102">Walkthrough: Module 3 - Accessing SharePoint Properties from an Orchestration</span></span>
<span data-ttu-id="f86aa-103">本演练是的延续[演练： 模块 2-将与 Windows SharePoint Services Adapter 集成 Office](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)并演示如何访问在传入消息的 Windows SharePoint Services 上下文属性运行时间，并确定使用动态端口业务流程中的属性上基于该消息的目标。</span><span class="sxs-lookup"><span data-stu-id="f86aa-103">This walkthrough is a continuation of [Walkthrough: Module 2 - Integrating Office with the Windows SharePoint Services Adapter](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md) and shows you how to access the Windows SharePoint Services context properties of an incoming message at run time and then determine the destination of that message based on a property using dynamic ports in an orchestration.</span></span> <span data-ttu-id="f86aa-104">有关 Windows SharePoint Services 适配器的简介，请参阅[什么是 Windows SharePoint Services Adapter？](../core/what-is-the-windows-sharepoint-services-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="f86aa-104">For an introduction to the Windows SharePoint Services adapter see [What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f86aa-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="f86aa-105">Prerequisites</span></span>  
 <span data-ttu-id="f86aa-106">以下为执行本主题中步骤的前提条件：</span><span class="sxs-lookup"><span data-stu-id="f86aa-106">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
-   <span data-ttu-id="f86aa-107">必须具有在 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 上运行的、完整安装的 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 的单服务器部署。</span><span class="sxs-lookup"><span data-stu-id="f86aa-107">You must have a single server deployment with a complete installation of [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] running on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)].</span></span>  
  
-   <span data-ttu-id="f86aa-108">你必须完成以下演练：[演练： 模块 1-发送和接收消息与 Windows SharePoint Services Adapter](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)和[演练： 模块 2-与 Windows 集成 OfficeSharePoint Services Adapter](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)</span><span class="sxs-lookup"><span data-stu-id="f86aa-108">You must complete the following walkthroughs: [Walkthrough: Module 1 - Sending and Receiving Messages with the Windows SharePoint Services Adapter](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md) and [Walkthrough: Module 2 - Integrating Office with the Windows SharePoint Services Adapter](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)</span></span>  
  
 <span data-ttu-id="f86aa-109">有关在多服务器部署中使用 Windows SharePoint Services 适配器的信息，请参阅[设置和部署 Windows SharePoint Services Adapter](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="f86aa-109">For information about using the Windows SharePoint Services Adapter in a multi server deployment, see [Setting Up and Deploying the Windows SharePoint Services Adapter](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md).</span></span>  
  
## <a name="modify-the-biztalk-project"></a><span data-ttu-id="f86aa-110">修改 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="f86aa-110">Modify the BizTalk project</span></span>  
 <span data-ttu-id="f86aa-111">在此过程中修改中的 PurchaseOrder 架构[演练： 模块 2-将与 Windows SharePoint Services Adapter 集成 Office](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="f86aa-111">In this procedure you modify the PurchaseOrder schema from [Walkthrough: Module 2 - Integrating Office with the Windows SharePoint Services Adapter](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md).</span></span> <span data-ttu-id="f86aa-112">此过程说明如何升级架构属性以方便在 BizTalk 业务流程中进行访问。</span><span class="sxs-lookup"><span data-stu-id="f86aa-112">This procedure illustrates how to promote a schema property for easy access in a BizTalk orchestration.</span></span>  
  
#### <a name="modify-the-purchaseorderxsd-schema"></a><span data-ttu-id="f86aa-113">修改 PurchaseOrder.xsd 架构</span><span class="sxs-lookup"><span data-stu-id="f86aa-113">Modify the PurchaseOrder.xsd schema</span></span>  
  
1.  <span data-ttu-id="f86aa-114">启动**Microsoft Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-114">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="f86aa-115">单击**文件**，单击**打开**，然后单击**项目/解决方案**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-115">Click **File**, click **Open**, and then click **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="f86aa-116">浏览到`OrderProcess.sln`文件，，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-116">Browse to the `OrderProcess.sln` file, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="f86aa-117">在**解决方案资源管理器**，右键单击`OrderProcessSchema.xsd`文件，，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-117">In **Solution Explorer**, right-click the `OrderProcessSchema.xsd` file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="f86aa-118">在**BizTalk 编辑器**，展开`PurchaseOrder`。</span><span class="sxs-lookup"><span data-stu-id="f86aa-118">In **BizTalk Editor**, expand `PurchaseOrder`.</span></span>  
  
6.  <span data-ttu-id="f86aa-119">右键单击`Amount`，单击**Promote**，然后单击**快速升级**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-119">Right-click `Amount`, click **Promote**, and then click **Quick Promotion**.</span></span>  
  
7.  <span data-ttu-id="f86aa-120">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-120">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="f86aa-121">当前项目中为此创建一个属性的架构。</span><span class="sxs-lookup"><span data-stu-id="f86aa-121"> creates a property schema for this in the current project.</span></span>  
  
8.  <span data-ttu-id="f86aa-122">保存 `PurchaseOrder.xsd`。</span><span class="sxs-lookup"><span data-stu-id="f86aa-122">Save `PurchaseOrder.xsd`.</span></span>  
  
## <a name="create-an-orchestration"></a><span data-ttu-id="f86aa-123">创建业务流程</span><span class="sxs-lookup"><span data-stu-id="f86aa-123">Create an orchestration</span></span>  
 <span data-ttu-id="f86aa-124">在此过程中将创建新的 BizTalk 业务流程。</span><span class="sxs-lookup"><span data-stu-id="f86aa-124">In this procedure you create a new BizTalk orchestration.</span></span> <span data-ttu-id="f86aa-125">此过程创建用于处理由 Windows Sharepoint Services 适配器所接收消息的业务流程。</span><span class="sxs-lookup"><span data-stu-id="f86aa-125">This procedure creates the orchestration that is used to process a message received by the Windows Sharepoint Services adapter.</span></span>  
  
#### <a name="add-a-biztalk-orchestration"></a><span data-ttu-id="f86aa-126">添加 BizTalk 业务流程</span><span class="sxs-lookup"><span data-stu-id="f86aa-126">Add a BizTalk orchestration</span></span>  
  
1.  <span data-ttu-id="f86aa-127">在**解决方案资源管理器**，右键单击`OrderProcess`项目中，单击**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-127">In **Solution Explorer**, right-click the `OrderProcess` project, click **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="f86aa-128">下**类别**，选择**Orchestration 文件**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-128">Under **Categories**, select **Orchestration Files**.</span></span>  
  
3.  <span data-ttu-id="f86aa-129">下**模板**，选择**BizTalk 业务流程**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-129">Under **Templates**, select **BizTalk Orchestration**.</span></span>  
  
4.  <span data-ttu-id="f86aa-130">类型`MyCompanyOrderProcessing`中**名称**字段，然后再单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-130">Type `MyCompanyOrderProcessing` in the **Name** field, and then click **Add**.</span></span>  
  
## <a name="create-receive-information"></a><span data-ttu-id="f86aa-131">创建接收信息</span><span class="sxs-lookup"><span data-stu-id="f86aa-131">Create receive information</span></span>  
 <span data-ttu-id="f86aa-132">在此过程中，将为业务流程创建新消息、接收端口和接收形状。</span><span class="sxs-lookup"><span data-stu-id="f86aa-132">In this procedure you create a new message, receive port, and receive shape for the orchestration.</span></span> <span data-ttu-id="f86aa-133">此过程说明如何配置用于接收来自 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的消息的业务流程。</span><span class="sxs-lookup"><span data-stu-id="f86aa-133">This procedure illustrates how to configure an orchestration to receive a message from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
#### <a name="create-a-new-message"></a><span data-ttu-id="f86aa-134">创建新消息的步骤</span><span class="sxs-lookup"><span data-stu-id="f86aa-134">Create a new message</span></span>  
  
1.  <span data-ttu-id="f86aa-135">在**业务流程视图**，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-135">In **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span> <span data-ttu-id="f86aa-136">此操作将生成一条名为 `Message_1` 的新消息。</span><span class="sxs-lookup"><span data-stu-id="f86aa-136">This will generate a new message with the name `Message_1`.</span></span>  
  
2.  <span data-ttu-id="f86aa-137">右键单击`Message_1`，单击**重命名**，然后键入`Message_PO`。</span><span class="sxs-lookup"><span data-stu-id="f86aa-137">Right-click `Message_1`, click **Rename**, and then type `Message_PO`.</span></span>  
  
3.  <span data-ttu-id="f86aa-138">右键单击`Message_PO`，然后单击**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-138">Right-click `Message_PO`, and then click **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="f86aa-139">在**消息类型**属性中，展开**架构**，然后选择`OrderProcess.OrderProcessSchema`架构。</span><span class="sxs-lookup"><span data-stu-id="f86aa-139">In the **Message Type** property, expand **Schemas**, and then select `OrderProcess.OrderProcessSchema` schema.</span></span>  
  
#### <a name="add-a-receive-port-to-the-orchestration"></a><span data-ttu-id="f86aa-140">向业务流程添加接收端口</span><span class="sxs-lookup"><span data-stu-id="f86aa-140">Add a receive port to the orchestration</span></span>  
  
1.  <span data-ttu-id="f86aa-141">下**BizTalk 业务流程**在工具箱中，拖动**端口**形状上的与端口图面。</span><span class="sxs-lookup"><span data-stu-id="f86aa-141">Under **BizTalk Orchestrations** in the Toolbox, drag a **Port** shape to the Port Surface.</span></span> <span data-ttu-id="f86aa-142">此时将启动端口配置向导。</span><span class="sxs-lookup"><span data-stu-id="f86aa-142">The Port Configuration Wizard will start.</span></span>  
  
2.  <span data-ttu-id="f86aa-143">在欢迎屏幕上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-143">On the Welcome screen, click **Next**.</span></span>  
  
3.  <span data-ttu-id="f86aa-144">类型`ReceivePurchaseOrder`中**名称**字段，然后再单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-144">Type `ReceivePurchaseOrder` in the **Name** field, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="f86aa-145">选择**创建新的端口类型**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-145">Select **Create a new Port Type**.</span></span>  
  
5.  <span data-ttu-id="f86aa-146">类型`PurchaseOrderPT`中**端口类型名称**字段，然后再单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-146">Type `PurchaseOrderPT` in the **Port Type Name** field, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="f86aa-147">上**端口绑定屏幕**，保留默认值，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-147">On the **Port Binding screen**, leave the default values, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="f86aa-148">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-148">Click **Finish**.</span></span>  
  
8.  <span data-ttu-id="f86aa-149">在**业务流程视图**下**端口类型**，展开`PurchaseOrderPT`端口类型。</span><span class="sxs-lookup"><span data-stu-id="f86aa-149">In **Orchestration View**, under **Port Types**, expand the `PurchaseOrderPT` port type.</span></span>  
  
9. <span data-ttu-id="f86aa-150">右键单击`Operation_1`，单击**重命名**，然后键入`PurchaseOrderOperation`。</span><span class="sxs-lookup"><span data-stu-id="f86aa-150">Right-click `Operation_1`, click **Rename**, and then type `PurchaseOrderOperation`.</span></span>  
  
#### <a name="add-a-receive-shape-to-the-orchestration"></a><span data-ttu-id="f86aa-151">向业务流程添加接收形状</span><span class="sxs-lookup"><span data-stu-id="f86aa-151">Add a Receive shape to the orchestration</span></span>  
  
1.  <span data-ttu-id="f86aa-152">下**BizTalk 业务流程**在工具箱中，拖动**接收**形状上的与业务流程。</span><span class="sxs-lookup"><span data-stu-id="f86aa-152">Under **BizTalk Orchestrations** in the Toolbox, drag a **Receive** shape to the Orchestration.</span></span>  
  
2.  <span data-ttu-id="f86aa-153">右键单击接收形状，并依次**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-153">Right-click the Receive shape, and then click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="f86aa-154">设置**激活**属性`True`。</span><span class="sxs-lookup"><span data-stu-id="f86aa-154">Set the **Activate** property to `True`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f86aa-155">如果激活属性设置为 false，则会出现以下错误:"错误 X2214： 必须指定至少一个已初始化的相关集非激活接收在非自相关端口上的"</span><span class="sxs-lookup"><span data-stu-id="f86aa-155">If the activate property is set to false, you will get the following error: "error X2214: you must specify at least one already-initialized correlation set for a non-activation receive that is on a non-selfcorrelating port"</span></span>  
  
4.  <span data-ttu-id="f86aa-156">类型`Receive_PO`中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="f86aa-156">Type `Receive_PO` in the **Name** field.</span></span>  
  
5.  <span data-ttu-id="f86aa-157">在**属性窗口**，选择`Message_PO`消息属性。</span><span class="sxs-lookup"><span data-stu-id="f86aa-157">In the **Properties Window**, select `Message_PO` for the Message property.</span></span>  
  
6.  <span data-ttu-id="f86aa-158">选择`ReceivePurchaseOrder.PurchaseOrderOperation.Request`为**操作**属性。</span><span class="sxs-lookup"><span data-stu-id="f86aa-158">Select `ReceivePurchaseOrder.PurchaseOrderOperation.Request` for the **Operation** property.</span></span> <span data-ttu-id="f86aa-159">此操作会将该端口与业务流程设计器中的接收形状关联在一起。</span><span class="sxs-lookup"><span data-stu-id="f86aa-159">This will tie the port to the Receive shape in the Orchestration Designer.</span></span>  
  
## <a name="create-send-information"></a><span data-ttu-id="f86aa-160">创建发送信息</span><span class="sxs-lookup"><span data-stu-id="f86aa-160">Create send information</span></span>  
 <span data-ttu-id="f86aa-161">在此过程中，将为业务流程创建新消息、发送端口和决策结构。</span><span class="sxs-lookup"><span data-stu-id="f86aa-161">In this procedure you create a new message, send ports, and decision structure to the orchestration.</span></span> <span data-ttu-id="f86aa-162">此过程说明如何配置包含决策逻辑的业务流程，以及如何配置向发送端口发送消息的业务流程。</span><span class="sxs-lookup"><span data-stu-id="f86aa-162">This procedure illustrates how to configure an orchestration with decision logic and how to configure an orchestration to send a message to a send port.</span></span>  
  
#### <a name="create-a-new-message"></a><span data-ttu-id="f86aa-163">创建新消息的步骤</span><span class="sxs-lookup"><span data-stu-id="f86aa-163">Create a new message</span></span>  
  
1.  <span data-ttu-id="f86aa-164">在**业务流程视图**，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-164">In **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span> <span data-ttu-id="f86aa-165">此操作将生成一条名为 `Message_1` 的新消息。</span><span class="sxs-lookup"><span data-stu-id="f86aa-165">This will generate a new message with the name `Message_1`.</span></span>  
  
2.  <span data-ttu-id="f86aa-166">右键单击`Message_1`，单击**重命名**，然后键入`Message_Task`。</span><span class="sxs-lookup"><span data-stu-id="f86aa-166">Right-click `Message_1`, click **Rename**, and then type `Message_Task`.</span></span>  
  
3.  <span data-ttu-id="f86aa-167">右键单击`Message_Task`，然后单击**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-167">Right-click `Message_Task`, and then click **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="f86aa-168">在**消息类型**属性中，展开**架构**，然后选择`OrderProcess.OrderProcessSchema`架构。</span><span class="sxs-lookup"><span data-stu-id="f86aa-168">In the **Message Type** property, expand **Schemas**, and then select `OrderProcess.OrderProcessSchema` schema.</span></span>  
  
#### <a name="add-a-send-port-to-the-orchestration"></a><span data-ttu-id="f86aa-169">向业务流程添加发送端口</span><span class="sxs-lookup"><span data-stu-id="f86aa-169">Add a send port to the orchestration</span></span>  
  
1.  <span data-ttu-id="f86aa-170">下**BizTalk 业务流程**在工具箱中，拖动**端口**形状上的与端口图面。</span><span class="sxs-lookup"><span data-stu-id="f86aa-170">Under **BizTalk Orchestrations** in the Toolbox, drag a **Port** shape to the Port Surface.</span></span> <span data-ttu-id="f86aa-171">此时将启动端口配置向导。</span><span class="sxs-lookup"><span data-stu-id="f86aa-171">The Port Configuration Wizard will start.</span></span>  
  
2.  <span data-ttu-id="f86aa-172">在欢迎屏幕上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-172">On the Welcome screen, click **Next**.</span></span>  
  
3.  <span data-ttu-id="f86aa-173">类型`SendPurchaseOrder`中**名称**字段，然后再单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-173">Type `SendPurchaseOrder` in the **Name** field, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="f86aa-174">选择**使用现有的端口类型**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-174">Select **Use an existing Port Type**.</span></span>  
  
5.  <span data-ttu-id="f86aa-175">下**可用端口类型**，选择`OrderProcess.PurchaseOrderPT`，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-175">Under **Available Port Types**, select `OrderProcess.PurchaseOrderPT`, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="f86aa-176">上**端口绑定屏幕**下**端口的通信的方向**，选择`I'll always be sending messages on this port`，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-176">On the **Port Binding screen**, under **Port direction of communication**, select `I'll always be sending messages on this port`, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="f86aa-177">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-177">Click **Finish**.</span></span>  
  
#### <a name="add-a-send-shape-to-the-orchestration"></a><span data-ttu-id="f86aa-178">向业务流程添加发送形状</span><span class="sxs-lookup"><span data-stu-id="f86aa-178">Add a Send shape to the orchestration</span></span>  
  
1.  <span data-ttu-id="f86aa-179">下**BizTalk 业务流程**在工具箱中，拖动**发送**到业务流程设计器形状。</span><span class="sxs-lookup"><span data-stu-id="f86aa-179">Under **BizTalk Orchestrations** in the Toolbox, drag a **Send** shape to the Orchestration Designer.</span></span> <span data-ttu-id="f86aa-180">将其放置在 `Receive_PO` 接收形状的下方。</span><span class="sxs-lookup"><span data-stu-id="f86aa-180">Place it below the `Receive_PO` Receive shape.</span></span>  
  
2.  <span data-ttu-id="f86aa-181">右键单击发送形状，并依次**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-181">Right-click the Send shape, and then click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="f86aa-182">类型`Send_PO`中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="f86aa-182">Type `Send_PO` in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="f86aa-183">选择`Message_PO`为**消息**属性。</span><span class="sxs-lookup"><span data-stu-id="f86aa-183">Select `Message_PO` for the **Message** property.</span></span>  
  
5.  <span data-ttu-id="f86aa-184">选择`SendPurchaseOrder.PurchaseOrderOperation.Request`为**操作**属性。</span><span class="sxs-lookup"><span data-stu-id="f86aa-184">Select `SendPurchaseOrder.PurchaseOrderOperation.Request` for the **Operation** property.</span></span> <span data-ttu-id="f86aa-185">此操作会将该端口与业务流程设计器中的发送形状关联在一起。</span><span class="sxs-lookup"><span data-stu-id="f86aa-185">This will tie the port to the Send shape in the Orchestration Designer.</span></span>  
  
#### <a name="add-a-decide-shape-to-the-orchestration"></a><span data-ttu-id="f86aa-186">将判定形状添加到业务流程</span><span class="sxs-lookup"><span data-stu-id="f86aa-186">Add a Decide shape to the orchestration</span></span>  
  
1.  <span data-ttu-id="f86aa-187">下**BizTalk 业务流程**在工具箱中，拖动**确定**到业务流程设计器形状。</span><span class="sxs-lookup"><span data-stu-id="f86aa-187">Under **BizTalk Orchestrations** in the Toolbox, drag a **Decide** shape to the Orchestration Designer.</span></span> <span data-ttu-id="f86aa-188">将其放置在 `Send_PO` 发送形状的下方。</span><span class="sxs-lookup"><span data-stu-id="f86aa-188">Place it below the `Send_PO` Send shape.</span></span>  
  
2.  <span data-ttu-id="f86aa-189">右键单击确定形状，并依次**属性窗口。**</span><span class="sxs-lookup"><span data-stu-id="f86aa-189">Right-click the Decide shape, and then click **Properties Window.**</span></span>  
  
3.  <span data-ttu-id="f86aa-190">类型`NeedsApproval`中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="f86aa-190">Type `NeedsApproval` in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="f86aa-191">在业务流程设计器中，单击**Rule_1**确定形状上。</span><span class="sxs-lookup"><span data-stu-id="f86aa-191">In Orchestration Designer, click **Rule_1** on the Decide shape.</span></span>  
  
5.  <span data-ttu-id="f86aa-192">在属性窗口中，键入`ApprovalRequired`为**名称**属性。</span><span class="sxs-lookup"><span data-stu-id="f86aa-192">In the Properties Windows, type `ApprovalRequired` for the **Name** property.</span></span>  
  
6.  <span data-ttu-id="f86aa-193">单击**表达式**属性字段，然后再单击省略号 (**...**) 按钮。</span><span class="sxs-lookup"><span data-stu-id="f86aa-193">Click the **Expression** property field, and then click the ellipsis (**…**) button.</span></span>  
  
7.  <span data-ttu-id="f86aa-194">在 BizTalk 表达式编辑器中，键入或复制以下内容：</span><span class="sxs-lookup"><span data-stu-id="f86aa-194">In the BizTalk Expression Editor, type or copy the following:</span></span>  
  
    ```  
    Message_PO(OrderProcess.PropertySchema.Amount) > 1000  
    ```  
  
8.  <span data-ttu-id="f86aa-195">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-195">Click **OK**.</span></span>  
  
#### <a name="add-another-send-port-to-the-orchestration"></a><span data-ttu-id="f86aa-196">向业务流程添加其他发送端口</span><span class="sxs-lookup"><span data-stu-id="f86aa-196">Add another send port to the orchestration</span></span>  
  
1.  <span data-ttu-id="f86aa-197">下**BizTalk 业务流程**在工具箱中，拖动**端口**形状上的与端口图面。</span><span class="sxs-lookup"><span data-stu-id="f86aa-197">Under **BizTalk Orchestrations** in the Toolbox, drag a **Port** shape to the Port Surface.</span></span> <span data-ttu-id="f86aa-198">此时将启动端口配置向导。</span><span class="sxs-lookup"><span data-stu-id="f86aa-198">The Port Configuration Wizard will start.</span></span>  
  
2.  <span data-ttu-id="f86aa-199">在欢迎屏幕上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-199">On the Welcome screen, click **Next**.</span></span>  
  
3.  <span data-ttu-id="f86aa-200">类型`SendToTasksList`中**名称**字段，然后再单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-200">Type `SendToTasksList` in the **Name** field, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="f86aa-201">选择**使用现有的端口类型**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-201">Select **Use an existing Port Type**.</span></span>  
  
5.  <span data-ttu-id="f86aa-202">下**可用端口类型**，选择`OrderProcess.PurchaseOrderPT`，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-202">Under **Available Port Types**, select `OrderProcess.PurchaseOrderPT`, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="f86aa-203">上**端口绑定屏幕**下**端口的通信的方向**，选择`I'll always be sending messages on this port`。</span><span class="sxs-lookup"><span data-stu-id="f86aa-203">On the **Port Binding screen**, under **Port direction of communication**, select `I'll always be sending messages on this port`.</span></span>  
  
7.  <span data-ttu-id="f86aa-204">下**端口绑定**，选择`Dynamic`，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-204">Under **Port binding**, select `Dynamic`, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="f86aa-205">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-205">Click **Finish**.</span></span>  
  
#### <a name="add-a-send-shape-to-the-decide-shape"></a><span data-ttu-id="f86aa-206">向判定形状添加发送形状</span><span class="sxs-lookup"><span data-stu-id="f86aa-206">Add a Send shape to the Decide shape</span></span>  
  
1.  <span data-ttu-id="f86aa-207">下**BizTalk 业务流程**在工具箱中，拖动**发送**到业务流程设计器形状。</span><span class="sxs-lookup"><span data-stu-id="f86aa-207">Under **BizTalk Orchestrations** in the Toolbox, drag a **Send** shape to the Orchestration Designer.</span></span> <span data-ttu-id="f86aa-208">将其放置在 `ApprovalRequired` 形状的下方。</span><span class="sxs-lookup"><span data-stu-id="f86aa-208">Place it below the `ApprovalRequired` shape.</span></span>  
  
2.  <span data-ttu-id="f86aa-209">右键单击发送形状，并依次**属性窗口**</span><span class="sxs-lookup"><span data-stu-id="f86aa-209">Right-click the Send shape, and then click **Properties Window**</span></span>  
  
3.  <span data-ttu-id="f86aa-210">类型`CreateApprovalTask`中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="f86aa-210">Type `CreateApprovalTask` in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="f86aa-211">选择`Message_Task`为**消息**属性。</span><span class="sxs-lookup"><span data-stu-id="f86aa-211">Select `Message_Task` for the **Message** property.</span></span>  
  
5.  <span data-ttu-id="f86aa-212">选择`SendToTasksList.PurchaseOrderOperation.Request`为**操作**属性。</span><span class="sxs-lookup"><span data-stu-id="f86aa-212">Select `SendToTasksList.PurchaseOrderOperation.Request` for the **Operation** property.</span></span> <span data-ttu-id="f86aa-213">此操作会将该端口与业务流程设计器中的发送形状关联在一起。</span><span class="sxs-lookup"><span data-stu-id="f86aa-213">This will tie the port to the Send shape in the Orchestration Designer.</span></span>  
  
## <a name="create-an-expression"></a><span data-ttu-id="f86aa-214">创建表达式</span><span class="sxs-lookup"><span data-stu-id="f86aa-214">Create an expression</span></span>  
 <span data-ttu-id="f86aa-215">在此过程中，将向解决方案中添加可将任务路径值赋予变量的表达式形状。</span><span class="sxs-lookup"><span data-stu-id="f86aa-215">In this procedure you add an Expression shape to your solution which assigns the Tasks path value to a variable.</span></span> <span data-ttu-id="f86aa-216">此过程说明如何向业务流程添加逻辑以修改动态发送端口的属性。</span><span class="sxs-lookup"><span data-stu-id="f86aa-216">This procedure illustrates how to add logic to an orchestration to modify the properties of a dynamic send port.</span></span>  
  
#### <a name="create-a-new-expression"></a><span data-ttu-id="f86aa-217">创建新的表达式</span><span class="sxs-lookup"><span data-stu-id="f86aa-217">Create a new expression</span></span>  
  
1.  <span data-ttu-id="f86aa-218">下**BizTalk 业务流程**在工具箱中，拖动**表达式**之前调整`CreateApprovalTask`发送形状。</span><span class="sxs-lookup"><span data-stu-id="f86aa-218">Under **BizTalk Orchestrations** in the Toolbox, drag an **Expression** shape before the `CreateApprovalTask` Send shape.</span></span>  
  
2.  <span data-ttu-id="f86aa-219">右键单击表达式形状，并依次**属性窗口。**</span><span class="sxs-lookup"><span data-stu-id="f86aa-219">Right-click the Expression shape, and then click **Properties Window.**</span></span>  
  
3.  <span data-ttu-id="f86aa-220">类型`SetPortDestination`中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="f86aa-220">Type `SetPortDestination` in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="f86aa-221">单击**表达式**属性字段，然后再单击省略号 (**...**) 按钮。</span><span class="sxs-lookup"><span data-stu-id="f86aa-221">Click the **Expression** property field, and then click the ellipsis (**…**) button.</span></span>  
  
5.  <span data-ttu-id="f86aa-222">在**BizTalk 表达式编辑器**，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="f86aa-222">In the **BizTalk Expression Editor**, type the following:</span></span>  
  
    ```  
    SendToTasksList(Microsoft.XLANGs.BaseTypes.Address) = "wss://localhost/sites/WSSAdapterWalkthrough/Lists/Tasks/";  
    ```  
  
6.  <span data-ttu-id="f86aa-223">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-223">Click **OK**.</span></span>  
  
## <a name="construct-a-new-message"></a><span data-ttu-id="f86aa-224">构造新消息</span><span class="sxs-lookup"><span data-stu-id="f86aa-224">Construct a new message</span></span>  
 <span data-ttu-id="f86aa-225">在此过程中，将向解决方案中添加构造形状，该形状将在业务流程内构造消息类型的新实例。</span><span class="sxs-lookup"><span data-stu-id="f86aa-225">In this procedure you add a Construct shape to the solution which will construct a new instance of a message type within the orchestration.</span></span> <span data-ttu-id="f86aa-226">此过程说明如何创建作为入站消息副本的新消息，以及接下来如何修改该新消息的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="f86aa-226">This procedure illustrates how to create a new message that is a copy of the inbound message and then modify the context properties of the new message.</span></span> <span data-ttu-id="f86aa-227">此步骤是必需的，因为消息在 BizTalk 中是不可改变的，也就是说，在你构造原始消息之后，就不能修改原始消息了。</span><span class="sxs-lookup"><span data-stu-id="f86aa-227">This step is required because messages are immutable in BizTalk; that is, once you have constructed it, you cannot modify the original.</span></span>  
  
#### <a name="add-a-construct-shape"></a><span data-ttu-id="f86aa-228">添加构造形状</span><span class="sxs-lookup"><span data-stu-id="f86aa-228">Add a Construct Shape</span></span>  
  
1.  <span data-ttu-id="f86aa-229">下**BizTalk 业务流程**在工具箱中，拖动**构造消息**之前调整`SetPortDestination`表达式形状。</span><span class="sxs-lookup"><span data-stu-id="f86aa-229">Under **BizTalk Orchestrations** in the Toolbox, drag a **Construct Message** shape before the `SetPortDestination` Expression shape.</span></span>  
  
2.  <span data-ttu-id="f86aa-230">右键单击构造消息形状，并依次**属性窗口。**</span><span class="sxs-lookup"><span data-stu-id="f86aa-230">Right-click the Construct Message shape, and then click **Properties Window.**</span></span>  
  
3.  <span data-ttu-id="f86aa-231">类型`ConstructTaskMessage`中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="f86aa-231">Type `ConstructTaskMessage`in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="f86aa-232">选择`Message_Task`为**消息构造**属性。</span><span class="sxs-lookup"><span data-stu-id="f86aa-232">Select `Message_Task` for the **Messages Constructed** property.</span></span>  
  
5.  <span data-ttu-id="f86aa-233">下**BizTalk 业务流程**在工具箱中，拖动**消息分配**调整`ConstructTaskMessage`**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="f86aa-233">Under **BizTalk Orchestrations** in the Toolbox, drag a **Message Assignment** shape into the `ConstructTaskMessage`**Construct Message** shape.</span></span>  
  
6.  <span data-ttu-id="f86aa-234">在**属性窗口**，类型`InitTaskMessage`中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="f86aa-234">In the **Properties Window**, type `InitTaskMessage` in the **Name** field.</span></span>  
  
7.  <span data-ttu-id="f86aa-235">单击**表达式**属性字段，然后再单击省略号 (**...**) 按钮。</span><span class="sxs-lookup"><span data-stu-id="f86aa-235">Click the **Expression** property field, and then click the ellipsis (**…**) button.</span></span>  
  
8.  <span data-ttu-id="f86aa-236">在**BizTalk 表达式编辑器**，键入或复制下列文本：</span><span class="sxs-lookup"><span data-stu-id="f86aa-236">In the **BizTalk Expression Editor**, type or copy the following:</span></span>  
  
    ```  
    Message_Task = Message_PO;  
    Message_Task(WSS.ConfigOverwrite) = "no";  
    Message_Task(WSS.ConfigNamespaceAliases)= "orchns='http://OrderProcess.PurchaseOrder'";  
    Message_Task(WSS.ConfigPropertiesXml) = "<ConfigPropertiesXml><PropertyName1>Title</PropertyName1><PropertySource1>Approve %XPATH=//orchns:PurchaseOrder/orchns:PurchaseOrderID%</PropertySource1><PropertyName3>Status</PropertyName3><PropertySource3>Not Started</PropertySource3><PropertyName4>Priority</PropertyName4><PropertySource4>(1) High</PropertySource4></ConfigPropertiesXml>";  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f86aa-237">为这些上下文属性提供的值都是区分大小写的。</span><span class="sxs-lookup"><span data-stu-id="f86aa-237">These values supplied for these context properties are case sensitive.</span></span> <span data-ttu-id="f86aa-238">在使用上下文属性设置动态端口的配置值时，必须确保使用正确的大小写格式，否则，如果 BizTalk 尝试将文档路由到指定的发送端口，将会出现错误。</span><span class="sxs-lookup"><span data-stu-id="f86aa-238">When setting configuration values for a dynamic port with context properties you must ensure that you use the proper case or an error will occur when BizTalk attempts to route the document to the designated send port.</span></span>  
  
9. <span data-ttu-id="f86aa-239">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-239">Click **OK**.</span></span>  
  
10. <span data-ttu-id="f86aa-240">单击**文件**，然后单击**保存所有**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-240">Click **File**, and then click **Save All**.</span></span>  
  
## <a name="build-the-biztalk-project"></a><span data-ttu-id="f86aa-241">生成 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="f86aa-241">Build the BizTalk project</span></span>  
 <span data-ttu-id="f86aa-242">在此过程中，将生成并部署 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="f86aa-242">In this procedure you build and deploy the BizTalk project.</span></span> <span data-ttu-id="f86aa-243">此步骤对于创建和部署 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在运行时使用的程序集来说是必需的。</span><span class="sxs-lookup"><span data-stu-id="f86aa-243">This step is required to create and deploy the assembly that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses at runtime.</span></span>  
  
#### <a name="build-and-deploy-the-solution"></a><span data-ttu-id="f86aa-244">生成并部署解决方案</span><span class="sxs-lookup"><span data-stu-id="f86aa-244">Build and deploy the solution</span></span>  
  
1.  <span data-ttu-id="f86aa-245">单击**生成**，然后单击**生成 OrderProcess**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-245">Click **Build**, and then click **Build OrderProcess**.</span></span>  
  
2.  <span data-ttu-id="f86aa-246">单击**生成**，然后单击**部署 OrderProcess**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-246">Click **Build**, and then click **Deploy OrderProcess**.</span></span>  
  
3.  <span data-ttu-id="f86aa-247">关闭 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f86aa-247">Close Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="modify-the-receive-location-and-send-port"></a><span data-ttu-id="f86aa-248">修改接收位置和发送端口</span><span class="sxs-lookup"><span data-stu-id="f86aa-248">Modify the receive location and send port</span></span>  
 <span data-ttu-id="f86aa-249">在此过程中，将修改现有的接收位置和发送端口，以便对管道使用 XML 处理。</span><span class="sxs-lookup"><span data-stu-id="f86aa-249">In this procedure you modify the existing receive location and send port to use XML processing for the pipelines.</span></span> <span data-ttu-id="f86aa-250">接收 XML 管道保持在业务流程处理过程中所使用的消息属性，发送 XML 管道保持在业务流程中应用的消息属性，这些消息属性随后将用于消息路由。</span><span class="sxs-lookup"><span data-stu-id="f86aa-250">The receive XML pipeline persists message properties used during orchestration processing and the send XML pipeline persists the message properties that were applied in the orchestration which are subsequently used for message routing.</span></span>  
  
#### <a name="modify-the-receive-location"></a><span data-ttu-id="f86aa-251">修改接收位置</span><span class="sxs-lookup"><span data-stu-id="f86aa-251">Modify the receive location</span></span>  
  
1.  <span data-ttu-id="f86aa-252">单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理。**</span><span class="sxs-lookup"><span data-stu-id="f86aa-252">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration.**</span></span>  
  
2.  <span data-ttu-id="f86aa-253">展开**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理管理单元**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**接收位置**节点。</span><span class="sxs-lookup"><span data-stu-id="f86aa-253">Expand **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration SnapIn**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and then click the **Receive Locations** node.</span></span>  
  
3.  <span data-ttu-id="f86aa-254">右键单击`SourceLocation`，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-254">Right-click `SourceLocation`, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="f86aa-255">在**接收位置属性**对话框中，在**常规**，选择`XMLReceive`为**接收管道**属性。</span><span class="sxs-lookup"><span data-stu-id="f86aa-255">In the **Receive Location Properties** dialog box, under **General**, select `XMLReceive` for the **Receive pipeline** property.</span></span>  
  
5.  <span data-ttu-id="f86aa-256">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-256">Click **OK**.</span></span>  
  
#### <a name="modify-the-send-port"></a><span data-ttu-id="f86aa-257">修改发送端口</span><span class="sxs-lookup"><span data-stu-id="f86aa-257">Modify the send port</span></span>  
  
1.  <span data-ttu-id="f86aa-258">单击**发送端口**节点。</span><span class="sxs-lookup"><span data-stu-id="f86aa-258">Click the **Send Ports** node.</span></span>  
  
2.  <span data-ttu-id="f86aa-259">右键单击`SendToDestination`，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-259">Right-click `SendToDestination`, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="f86aa-260">在**发送端口属性**对话框中，在**常规**，选择`XMLTransmit`为**发送管道**属性。</span><span class="sxs-lookup"><span data-stu-id="f86aa-260">In the **Send Port Properties** dialog box, under **General**, select `XMLTransmit` for the **Send pipeline** property.</span></span>  
  
4.  <span data-ttu-id="f86aa-261">选择**筛选器**选项卡。</span><span class="sxs-lookup"><span data-stu-id="f86aa-261">Select the **Filters** tab.</span></span>  
  
5.  <span data-ttu-id="f86aa-262">选择现有条件，按 DELETE 键，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-262">Select the existing condition, press DELETE, and then click **OK**.</span></span>  
  
#### <a name="start-a-new-send-port"></a><span data-ttu-id="f86aa-263">启动新的发送端口</span><span class="sxs-lookup"><span data-stu-id="f86aa-263">Start a new send port</span></span>  
  
1.  <span data-ttu-id="f86aa-264">单击**发送端口**节点。</span><span class="sxs-lookup"><span data-stu-id="f86aa-264">Click the **Send Ports** node.</span></span>  
  
2.  <span data-ttu-id="f86aa-265">右键单击`OrderProcess_1.0.0.0_OrderProcess.MyCompanyOrderProcess_SendToTasksList_<GUID>`，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-265">Right-click `OrderProcess_1.0.0.0_OrderProcess.MyCompanyOrderProcess_SendToTasksList_<GUID>`, and then click **Start**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f86aa-266">如果此项不可见，则可能必须刷新控制台。</span><span class="sxs-lookup"><span data-stu-id="f86aa-266">You may have to refresh the console if this is not visible.</span></span>  
  
## <a name="bind-the-orchestration"></a><span data-ttu-id="f86aa-267">绑定业务流程的步骤</span><span class="sxs-lookup"><span data-stu-id="f86aa-267">Bind the orchestration</span></span>  
 <span data-ttu-id="f86aa-268">在此过程中，将业务流程绑定到指定端口。</span><span class="sxs-lookup"><span data-stu-id="f86aa-268">In this procedure you bind the orchestration to the specified ports.</span></span> <span data-ttu-id="f86aa-269">此过程对于将物理端口绑定到你构建并部署的业务流程是必需的。</span><span class="sxs-lookup"><span data-stu-id="f86aa-269">This procedure is required to tie physical ports to the orchestration that you built and deployed.</span></span>  
  
#### <a name="bind-the-orchestration"></a><span data-ttu-id="f86aa-270">绑定业务流程的步骤</span><span class="sxs-lookup"><span data-stu-id="f86aa-270">Bind the orchestration</span></span>  
  
1.  <span data-ttu-id="f86aa-271">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**业务流程**节点。</span><span class="sxs-lookup"><span data-stu-id="f86aa-271">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click the **Orchestrations** node.</span></span>  
  
2.  <span data-ttu-id="f86aa-272">右键单击`OrderProcess.MyCompanyOrderProcessing`业务流程，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-272">Right-click the `OrderProcess.MyCompanyOrderProcessing` orchestration, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="f86aa-273">选择**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="f86aa-273">Select the **Bindings** tab.</span></span>  
  
4.  <span data-ttu-id="f86aa-274">下**主机**，选择`BizTalkServerApplication`中**主机**字段。</span><span class="sxs-lookup"><span data-stu-id="f86aa-274">Under **Host**, select `BizTalkServerApplication` in the **Host** field.</span></span>  
  
5.  <span data-ttu-id="f86aa-275">下**绑定**，选择`FromSource`为`ReceivePurchaseOrder`入站逻辑端口。</span><span class="sxs-lookup"><span data-stu-id="f86aa-275">Under **Bindings**, select `FromSource` for the `ReceivePurchaseOrder` Inbound Logical Port.</span></span>  
  
6.  <span data-ttu-id="f86aa-276">下**绑定**，选择`SendToDestination`为`SendPurchaseOrder`出站逻辑端口。</span><span class="sxs-lookup"><span data-stu-id="f86aa-276">Under **Bindings**, select `SendToDestination` for the `SendPurchaseOrder` Outbound Logical Port.</span></span>  
  
7.  <span data-ttu-id="f86aa-277">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-277">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="f86aa-278">右键单击`OrderProcess.MyCompanyOrderProcessing`业务流程，，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-278">Right click `OrderProcess.MyCompanyOrderProcessing` orchestration, and then click **Start**.</span></span>  
  
## <a name="send-a-message-through-the-system"></a><span data-ttu-id="f86aa-279">通过系统发送消息</span><span class="sxs-lookup"><span data-stu-id="f86aa-279">Send a message through the system</span></span>  
 <span data-ttu-id="f86aa-280">在此过程中，将创建 InfoPath 表单并将其上载到 Windows SharePoint Services 网站。</span><span class="sxs-lookup"><span data-stu-id="f86aa-280">In this procedure you create an InfoPath form and upload it to the Windows SharePoint Services Web site.</span></span> <span data-ttu-id="f86aa-281">Windows SharePoint Services 适配器将接受该消息并将其存档在存档文档库中，然后将其发送到目标文档库。</span><span class="sxs-lookup"><span data-stu-id="f86aa-281">The Windows SharePoint Services adapter will take that message, archive it in the Archive document library, and then send it to the Destination document library.</span></span> <span data-ttu-id="f86aa-282">在处理此消息的过程中，将访问有助于确定目标的 Windows SharePoint Services 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="f86aa-282">During the processing of this message, Windows SharePoint Services context properties will be accessed that help determine the destination.</span></span>  
  
#### <a name="create-an-infopath-form-to-send-through-the-system"></a><span data-ttu-id="f86aa-283">创建要通过系统发送的 InfoPath 表单</span><span class="sxs-lookup"><span data-stu-id="f86aa-283">Create an InfoPath form to send through the system</span></span>  
  
1.  <span data-ttu-id="f86aa-284">打开 Web 浏览器并导航到所创建站点的 URL。</span><span class="sxs-lookup"><span data-stu-id="f86aa-284">Open a Web browser and navigate to the URL of the site you created.</span></span> <span data-ttu-id="f86aa-285">例如， `http://<server_name>/sites/WSSAdapterWalkthrough`。</span><span class="sxs-lookup"><span data-stu-id="f86aa-285">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2.  <span data-ttu-id="f86aa-286">在“快速启动”菜单中，单击“`InfoPathSolutions`”。</span><span class="sxs-lookup"><span data-stu-id="f86aa-286">In the Quick Launch menu, click `InfoPathSolutions`.</span></span>  
  
3.  <span data-ttu-id="f86aa-287">单击`PurchaseOrder`文件以显示**文件下载**对话框中，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-287">Click the `PurchaseOrder` file to display the **File Download** dialog box, and then click **Open**.</span></span> <span data-ttu-id="f86aa-288">InfoPath 将加载该表单。</span><span class="sxs-lookup"><span data-stu-id="f86aa-288">InfoPath will load the form.</span></span>  
  
4.  <span data-ttu-id="f86aa-289">在**采购订单 ID**字段中，键入`1003`。</span><span class="sxs-lookup"><span data-stu-id="f86aa-289">In the **Purchase Order ID** field, type `1003`.</span></span>  
  
5.  <span data-ttu-id="f86aa-290">在**帐单到**字段中，键入`John Doe`。</span><span class="sxs-lookup"><span data-stu-id="f86aa-290">In the **Bill To** field, type `John Doe`.</span></span>  
  
6.  <span data-ttu-id="f86aa-291">在**量**字段中，键入`1750`。</span><span class="sxs-lookup"><span data-stu-id="f86aa-291">In the **Amount** field, type `1750`.</span></span>  
  
7.  <span data-ttu-id="f86aa-292">在**采购订单日期**字段中，键入`1/3/2005`。</span><span class="sxs-lookup"><span data-stu-id="f86aa-292">In the **Purchase Order Date** field, type `1/3/2005`.</span></span>  
  
8.  <span data-ttu-id="f86aa-293">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-293">Click **Save**.</span></span>  
  
9. <span data-ttu-id="f86aa-294">在**另存为**对话框中，键入`http://<server_name>/sites/WSSAdapterWalkthrough/Source`中**文件名**字段，，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="f86aa-294">In the **Save As** dialog box, type `http://<server_name>/sites/WSSAdapterWalkthrough/Source`in the **file name** field, and then press ENTER.</span></span>  
  
10. <span data-ttu-id="f86aa-295">类型`PurchaseOrder3.xml`中**文件名**字段，然后再单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-295">Type `PurchaseOrder3.xml` in the **file name** field, and then click **Save**.</span></span>  
  
11. <span data-ttu-id="f86aa-296">关闭 InfoPath。</span><span class="sxs-lookup"><span data-stu-id="f86aa-296">Close InfoPath.</span></span>  
  
12. <span data-ttu-id="f86aa-297">在 Web 浏览器中，单击**文档和列表**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-297">In the Web browser, click **Documents and Lists**.</span></span>  
  
13. <span data-ttu-id="f86aa-298">下**文档库**，单击**目标**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-298">Under **Document Libraries**, click **Destination**.</span></span>  
  
14. <span data-ttu-id="f86aa-299">在目标文档库中，你现在将看到你在此库中列出了消息。</span><span class="sxs-lookup"><span data-stu-id="f86aa-299">In the Destination document library, you will now see your message listed in this library.</span></span> <span data-ttu-id="f86aa-300">你还将在存档文档库中找到存档副本。</span><span class="sxs-lookup"><span data-stu-id="f86aa-300">You will also find a copy archived in the Archive document library.</span></span>  
  
15. <span data-ttu-id="f86aa-301">单击 **“主页”**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-301">Click **Home**.</span></span>  
  
16. <span data-ttu-id="f86aa-302">下**列出**，单击**任务**。</span><span class="sxs-lookup"><span data-stu-id="f86aa-302">Under **Lists**, click **Tasks**.</span></span>  
  
17. <span data-ttu-id="f86aa-303">在“任务”列表中，将看到新创建的批准任务。</span><span class="sxs-lookup"><span data-stu-id="f86aa-303">In the Tasks list you will see the newly created approval task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f86aa-304">由于采购订单金额超过了 1,000.00 美元，因此创建了该任务。</span><span class="sxs-lookup"><span data-stu-id="f86aa-304">Since the amount of the purchase order was over $1,000.00, the task was created.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="f86aa-305">摘要</span><span class="sxs-lookup"><span data-stu-id="f86aa-305">Summary</span></span>  
 <span data-ttu-id="f86aa-306">在本演练中，你学习了如何访问 Windows SharePoint Services 上下文属性，以及如何确定经过动态端口的消息的目标。</span><span class="sxs-lookup"><span data-stu-id="f86aa-306">In this walkthrough you have seen how to access the Windows SharePoint Services context properties and how to determine the destination of messages going through dynamic ports.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f86aa-307">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f86aa-307">Next Steps</span></span>  
 <span data-ttu-id="f86aa-308">接下来请学习 Windows SharePoint Services 适配器部分的其余内容。</span><span class="sxs-lookup"><span data-stu-id="f86aa-308">Continue to review the rest of the Windows SharePoint Services adapter section.</span></span> <span data-ttu-id="f86aa-309">有关详细信息，请参阅“另请参见”部分中的主题。</span><span class="sxs-lookup"><span data-stu-id="f86aa-309">For more information, see the topics in See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f86aa-310">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f86aa-310">See Also</span></span>  
 <span data-ttu-id="f86aa-311">[什么是 Windows SharePoint Services Adapter？](../core/what-is-the-windows-sharepoint-services-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="f86aa-311">[What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md) </span></span>  
 [<span data-ttu-id="f86aa-312">Windows SharePoint Services 适配器演练</span><span class="sxs-lookup"><span data-stu-id="f86aa-312">Windows SharePoint Services Adapter Walkthroughs</span></span>](../core/windows-sharepoint-services-adapter-walkthroughs.md)