---
title: 教程：使用 TIBCO EMS 消息上下文属性 |Microsoft Docs
description: 使用 TIBCO Enterprise Message Service 消息描述符字段在业务流程中的对 BizTalk Server 使用的分步指南
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e52593b-5001-4740-89fb-e003e12d8e69
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef7ce23a38c528b3dc7e3d0a3d98c39412e9c175
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393844"
---
# <a name="tutorial-use-tibco-ems-message-descriptors"></a><span data-ttu-id="e9043-103">教程：使用 TIBCO EMS 消息描述符</span><span class="sxs-lookup"><span data-stu-id="e9043-103">Tutorial: Use TIBCO EMS message descriptors</span></span>

## <a name="overview"></a><span data-ttu-id="e9043-104">概述</span><span class="sxs-lookup"><span data-stu-id="e9043-104">Overview</span></span>
<span data-ttu-id="e9043-105">本教程演示如何使用 BizTalk Server 上下文属性在您的业务流程中设置 TIBCO Enterprise Message Service (EMS) 消息描述符字段。</span><span class="sxs-lookup"><span data-stu-id="e9043-105">This tutorial demonstrates how to use BizTalk Server context properties to set TIBCO Enterprise Message Service (EMS) message descriptor fields in your orchestration.</span></span> <span data-ttu-id="e9043-106">本教程假定你具有一个业务流程从接收端口接收消息并将消息发送到 TIBCO Enterprise Message Service 的绑定到的 Microsoft BizTalk 适配器的发送端口。</span><span class="sxs-lookup"><span data-stu-id="e9043-106">The tutorial assumes that you have an orchestration that receives a message from a receive port and sends the message to a send port bound to Microsoft BizTalk Adapter for TIBCO Enterprise Message Service.</span></span>  
  
 <span data-ttu-id="e9043-107">以下过程演示如何通过更改 TibcoEMS.Priority 上下文属性的值来更改 TIBCO EMS 消息的优先级。</span><span class="sxs-lookup"><span data-stu-id="e9043-107">The following procedure demonstrates how to change the priority of the TIBCO EMS message by changing the value of the TibcoEMS.Priority context property.</span></span> <span data-ttu-id="e9043-108">在 BizTalk Server 中，消息是不可变的。</span><span class="sxs-lookup"><span data-stu-id="e9043-108">In BizTalk Server, messages are immutable.</span></span> <span data-ttu-id="e9043-109">因此，若要更改属性值，必须创建和修改新消息。</span><span class="sxs-lookup"><span data-stu-id="e9043-109">Therefore, to change a property value, you must create and modify a new message.</span></span> <span data-ttu-id="e9043-110">创建和修改新消息的方法是插入消息赋值形状在接收和发送形状之间。</span><span class="sxs-lookup"><span data-stu-id="e9043-110">You create and modify the new message by inserting a message assignment shape between the Receive and Send shapes.</span></span> <span data-ttu-id="e9043-111">但是，您必须首先引用架构 DLL 才能访问 TIBCO EMS 属性。</span><span class="sxs-lookup"><span data-stu-id="e9043-111">First, however, you must reference the schema DLL to gain access to the TIBCO EMS properties.</span></span>  
  
## <a name="reference-the-schema-dll"></a><span data-ttu-id="e9043-112">引用架构 DLL</span><span class="sxs-lookup"><span data-stu-id="e9043-112">Reference the schema DLL</span></span>  
  
1.  <span data-ttu-id="e9043-113">在 Visual Studio 中，打开 BizTalk Server 项目，并打开**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="e9043-113">In Visual Studio, open your BizTalk Server project, and open **Solution Explorer** .</span></span>  
  
2.  <span data-ttu-id="e9043-114">右键单击**引用**，然后选择**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="e9043-114">Right-click **References**, and select **Add Reference**.</span></span>  
  
     <span data-ttu-id="e9043-115">此时将显示“添加引用”对话框。</span><span class="sxs-lookup"><span data-stu-id="e9043-115">The **Add Reference** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="e9043-116">单击**浏览**选项卡。</span><span class="sxs-lookup"><span data-stu-id="e9043-116">Click the **Browse** tab.</span></span>  
  
     <span data-ttu-id="e9043-117">**选择组件**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="e9043-117">The **Select Component** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="e9043-118">找到 **\<TIBCO EMS_Adapter_installation_directory\>\bin**，然后选择**Microsoft.Adapters.TibcoEMSProperties.dll**。</span><span class="sxs-lookup"><span data-stu-id="e9043-118">Locate **\<TIBCO EMS_Adapter_installation_directory\>\bin**, and then select **Microsoft.Adapters.TibcoEMSProperties.dll**.</span></span>  
  
5.  <span data-ttu-id="e9043-119">单击 **“打开”**。</span><span class="sxs-lookup"><span data-stu-id="e9043-119">Click **Open**.</span></span>  
  
     <span data-ttu-id="e9043-120">中将显示该 DLL**选定的组件**中**添加引用**对话框。</span><span class="sxs-lookup"><span data-stu-id="e9043-120">The DLL appears in the **Selected Components** in the **Add Reference** dialog box.</span></span>  
  
6.  <span data-ttu-id="e9043-121">单击**确定**然后双击您的业务流程访问业务流程设计器。</span><span class="sxs-lookup"><span data-stu-id="e9043-121">Click **OK** and then double-click your orchestration to access the Orchestration Designer.</span></span>  
  
7.  <span data-ttu-id="e9043-122">上**视图**菜单，依次指向**其他 Windows**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="e9043-122">On the **View** menu, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
8.  <span data-ttu-id="e9043-123">在业务流程视图中，右键单击**消息**，然后选择**新消息**。</span><span class="sxs-lookup"><span data-stu-id="e9043-123">In the Orchestration view, right-click **Messages** and select **New Message**.</span></span>  
  
9. <span data-ttu-id="e9043-124">编辑新的消息属性和分配**消息类型**。</span><span class="sxs-lookup"><span data-stu-id="e9043-124">Edit your new message properties and assign a **Message Type**.</span></span>  
  
     <span data-ttu-id="e9043-125">会将 Message_1 分配给 Message_2。</span><span class="sxs-lookup"><span data-stu-id="e9043-125">You will assign Message_1 to Message_2.</span></span> <span data-ttu-id="e9043-126">因此，您必须为这两个消息分配相同的消息类型。</span><span class="sxs-lookup"><span data-stu-id="e9043-126">Therefore, you must assign the same message type to both messages.</span></span>  
  
10. <span data-ttu-id="e9043-127">在“视图”菜单上，单击“工具箱”。</span><span class="sxs-lookup"><span data-stu-id="e9043-127">On the **View** menu, click **Toolbox**.</span></span>  
  
11. <span data-ttu-id="e9043-128">拖动**消息赋值**形状拖到您想要创建新的消息的业务流程。</span><span class="sxs-lookup"><span data-stu-id="e9043-128">Drag a **Message Assignment** shape onto your orchestration where you want to create a new message.</span></span>  
  
12. <span data-ttu-id="e9043-129">编辑外部 ConstructMessage_1 形状和中选择新消息，Message_2**构造消息**属性。</span><span class="sxs-lookup"><span data-stu-id="e9043-129">Edit the outer ConstructMessage_1 shape and select your new message, Message_2, in the **Constructed Messages** property.</span></span>  
  
13. <span data-ttu-id="e9043-130">双击内部 MessageAssignment_1 形状。</span><span class="sxs-lookup"><span data-stu-id="e9043-130">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
     <span data-ttu-id="e9043-131">将显示 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="e9043-131">The BizTalk Expression Editor appears.</span></span>  
  
14. <span data-ttu-id="e9043-132">在 BizTalk 表达式编辑器中，键入你的代码。</span><span class="sxs-lookup"><span data-stu-id="e9043-132">In the BizTalk Expression Editor, type your code.</span></span>  
  
15. <span data-ttu-id="e9043-133">首先复制现有的消息，然后将值分配给消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="e9043-133">First copy an existing message and then assign values to message context properties.</span></span>  
  
     <span data-ttu-id="e9043-134">语法是`Message(property) = value;`。</span><span class="sxs-lookup"><span data-stu-id="e9043-134">The syntax is `Message(property) = value;`.</span></span> <span data-ttu-id="e9043-135">例如：</span><span class="sxs-lookup"><span data-stu-id="e9043-135">For example:</span></span>  
  
    ```  
    Message_2 = Message_1;  
    Message_2( TibcoEMS.Priority) = 6;  
    ```  
  
     <span data-ttu-id="e9043-136">可以使用自定义消息中的受支持属性的列表，请参阅 TIBCO EMS。</span><span class="sxs-lookup"><span data-stu-id="e9043-136">See TIBCO EMS for a list of supported properties that you can use in your custom message.</span></span>  
  
16. <span data-ttu-id="e9043-137">单击**确定**关闭 BizTalk 表达式编辑器并保存您的代码。</span><span class="sxs-lookup"><span data-stu-id="e9043-137">Click **OK** to close the BizTalk Expression Editor and save your code.</span></span>  
  
17. <span data-ttu-id="e9043-138">单击发送形状并将分配**消息**要**Message_2**。</span><span class="sxs-lookup"><span data-stu-id="e9043-138">Click the Send shape and assign the **Message** to be **Message_2**.</span></span>  
  
18. <span data-ttu-id="e9043-139">验证消息流的其余部分中的形状对适当的消息。</span><span class="sxs-lookup"><span data-stu-id="e9043-139">Verify that the shapes in the rest of the message flow operate on the appropriate message.</span></span>  
  
19. <span data-ttu-id="e9043-140">右键单击你的项目在解决方案资源管理器，然后选择**生成**。</span><span class="sxs-lookup"><span data-stu-id="e9043-140">Right-click your project in Solution Explorer, and select **Build**.</span></span>  
  
20. <span data-ttu-id="e9043-141">右键单击你的项目并选择**部署**。</span><span class="sxs-lookup"><span data-stu-id="e9043-141">Right-click your project and select **Deploy**.</span></span>  
  
21. <span data-ttu-id="e9043-142">选择**绑定**，**登记**，并**启动**BizTalk 资源管理器来测试业务流程中。</span><span class="sxs-lookup"><span data-stu-id="e9043-142">Select **Bind**, **Enlist**, and **Start** in the BizTalk Explorer to test your orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9043-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9043-143">See Also</span></span>  
[<span data-ttu-id="e9043-144">TIBCO EMS 消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="e9043-144">TIBCO EMS message context properties</span></span>](../core/message-context-properties-in-biztalk-server.md)