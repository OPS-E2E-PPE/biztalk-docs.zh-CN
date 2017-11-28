---
title: "教程： 使用消息上下文属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, changing priority
- message context properties, tutorial
ms.assetid: 6e52593b-5001-4740-89fb-e003e12d8e69
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f122215baa5660294e159e4f1d6967a2df5ba9b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-using-message-context-properties"></a><span data-ttu-id="205ef-102">教程： 使用消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="205ef-102">Tutorial: Using Message Context Properties</span></span>
<span data-ttu-id="205ef-103">本教程演示了如何使用 BizTalk Server 上下文属性在业务流程中设置 TIBCO Enterprise Message Service (EMS) 消息描述符字段。</span><span class="sxs-lookup"><span data-stu-id="205ef-103">This tutorial demonstrates how to use BizTalk Server context properties to set TIBCO Enterprise Message Service (EMS) message descriptor fields in your orchestration.</span></span> <span data-ttu-id="205ef-104">该教程假定您已具备一个可执行如下操作的业务流程：从接收端口接收消息并将该消息发送到与用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器绑定的发送端口。</span><span class="sxs-lookup"><span data-stu-id="205ef-104">The tutorial assumes that you have an orchestration that receives a message from a receive port and sends the message to a send port bound to Microsoft BizTalk Adapter for TIBCO Enterprise Message Service.</span></span>  
  
 <span data-ttu-id="205ef-105">下面的过程演示了如何通过更改 TibcoEMS.Priority 上下文属性的值来更改 TIBCO EMS 消息的优先级。</span><span class="sxs-lookup"><span data-stu-id="205ef-105">The following procedure demonstrates how to change the priority of the TIBCO EMS message by changing the value of the TibcoEMS.Priority context property.</span></span> <span data-ttu-id="205ef-106">在 BizTalk Server 中，消息是不可改变的。</span><span class="sxs-lookup"><span data-stu-id="205ef-106">In BizTalk Server, messages are immutable.</span></span> <span data-ttu-id="205ef-107">因此，若要更改属性值，必须创建和修改新的消息。</span><span class="sxs-lookup"><span data-stu-id="205ef-107">Therefore, to change a property value, you must create and modify a new message.</span></span> <span data-ttu-id="205ef-108">通过在接收形状和发送形状之间插入消息赋值形状可以创建和修改新消息。</span><span class="sxs-lookup"><span data-stu-id="205ef-108">You create and modify the new message by inserting a message assignment shape between the Receive and Send shapes.</span></span> <span data-ttu-id="205ef-109">但是，必须首先引用架构 DLL 才能访问 TIBCO EMS 属性。</span><span class="sxs-lookup"><span data-stu-id="205ef-109">First, however, you must reference the schema DLL to gain access to the TIBCO EMS properties.</span></span>  
  
### <a name="to-reference-the-schema-dll"></a><span data-ttu-id="205ef-110">若要引用 DLL 的架构</span><span class="sxs-lookup"><span data-stu-id="205ef-110">To reference the schema DLL</span></span>  
  
1.  <span data-ttu-id="205ef-111">打开**解决方案资源管理器**Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="205ef-111">Open **Solution Explorer** in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="205ef-112">右键单击**引用**，然后选择**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="205ef-112">Right-click **References**, and select **Add Reference**.</span></span>  
  
     <span data-ttu-id="205ef-113">此时将显示“添加引用”对话框。</span><span class="sxs-lookup"><span data-stu-id="205ef-113">The **Add Reference** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="205ef-114">单击**浏览**选项卡。</span><span class="sxs-lookup"><span data-stu-id="205ef-114">Click the **Browse** tab.</span></span>  
  
     <span data-ttu-id="205ef-115">**选择组件**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="205ef-115">The **Select Component** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="205ef-116">找到 **\<TIBCO EMS_Adapter_installation_directory > \bin**，然后选择**Microsoft.Adapters.TibcoEMSProperties.dll**。</span><span class="sxs-lookup"><span data-stu-id="205ef-116">Locate **\<TIBCO EMS_Adapter_installation_directory>\bin**, and then select **Microsoft.Adapters.TibcoEMSProperties.dll**.</span></span>  
  
5.  <span data-ttu-id="205ef-117">单击 **“打开”**。</span><span class="sxs-lookup"><span data-stu-id="205ef-117">Click **Open**.</span></span>  
  
     <span data-ttu-id="205ef-118">DLL 将出现在**选定的组件**中**添加引用**对话框。</span><span class="sxs-lookup"><span data-stu-id="205ef-118">The DLL appears in the **Selected Components** in the **Add Reference** dialog box.</span></span>  
  
6.  <span data-ttu-id="205ef-119">单击**确定**然后双击您的业务流程，以访问业务流程设计器。</span><span class="sxs-lookup"><span data-stu-id="205ef-119">Click **OK** and then double-click your orchestration to access the Orchestration Designer.</span></span>  
  
7.  <span data-ttu-id="205ef-120">上**视图**菜单上，指向**其他窗口**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="205ef-120">On the **View** menu, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
8.  <span data-ttu-id="205ef-121">在业务流程视图中，右键单击**消息**和选择**新消息**。</span><span class="sxs-lookup"><span data-stu-id="205ef-121">In the Orchestration view, right-click **Messages** and select **New Message**.</span></span>  
  
9. <span data-ttu-id="205ef-122">编辑新的消息属性和分配**消息类型**。</span><span class="sxs-lookup"><span data-stu-id="205ef-122">Edit your new message properties and assign a **Message Type**.</span></span>  
  
     <span data-ttu-id="205ef-123">您会将 Message_1 分配给 Message_2。</span><span class="sxs-lookup"><span data-stu-id="205ef-123">You will assign Message_1 to Message_2.</span></span> <span data-ttu-id="205ef-124">因此，您必须为这两个消息分配相同的消息类型。</span><span class="sxs-lookup"><span data-stu-id="205ef-124">Therefore, you must assign the same message type to both messages.</span></span>  
  
10. <span data-ttu-id="205ef-125">在“视图”菜单上，单击“工具箱”。</span><span class="sxs-lookup"><span data-stu-id="205ef-125">On the **View** menu, click **Toolbox**.</span></span>  
  
11. <span data-ttu-id="205ef-126">拖动**消息分配**形状拖到您想要创建一封新邮件的业务流程。</span><span class="sxs-lookup"><span data-stu-id="205ef-126">Drag a **Message Assignment** shape onto your orchestration where you want to create a new message.</span></span>  
  
12. <span data-ttu-id="205ef-127">编辑外部 ConstructMessage_1 形状，并在选择新消息，Message_2，**构造消息**属性。</span><span class="sxs-lookup"><span data-stu-id="205ef-127">Edit the outer ConstructMessage_1 shape and select your new message, Message_2, in the **Constructed Messages** property.</span></span>  
  
13. <span data-ttu-id="205ef-128">双击内部 MessageAssignment_1 形状。</span><span class="sxs-lookup"><span data-stu-id="205ef-128">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
     <span data-ttu-id="205ef-129">随即将显示 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="205ef-129">The BizTalk Expression Editor appears.</span></span>  
  
14. <span data-ttu-id="205ef-130">在 BizTalk 表达式编辑器中，键入代码。</span><span class="sxs-lookup"><span data-stu-id="205ef-130">In the BizTalk Expression Editor, type your code.</span></span>  
  
15. <span data-ttu-id="205ef-131">首先复制现有的消息，然后对消息上下文属性赋值。</span><span class="sxs-lookup"><span data-stu-id="205ef-131">First copy an existing message and then assign values to message context properties.</span></span>  
  
     <span data-ttu-id="205ef-132">语法为 `Message(property) = value;`。</span><span class="sxs-lookup"><span data-stu-id="205ef-132">The syntax is `Message(property) = value;`.</span></span> <span data-ttu-id="205ef-133">例如：</span><span class="sxs-lookup"><span data-stu-id="205ef-133">For example:</span></span>  
  
    ```  
    Message_2 = Message_1;  
    Message_2( TibcoEMS.Priority) = 6;  
    ```  
  
     <span data-ttu-id="205ef-134">有关可在自定义消息中使用的受支持属性的列表，请参阅 TIBCO EMS。</span><span class="sxs-lookup"><span data-stu-id="205ef-134">See TIBCO EMS for a list of supported properties that you can use in your custom message.</span></span>  
  
16. <span data-ttu-id="205ef-135">单击**确定**关闭 BizTalk 表达式编辑器并保存你的代码。</span><span class="sxs-lookup"><span data-stu-id="205ef-135">Click **OK** to close the BizTalk Expression Editor and save your code.</span></span>  
  
17. <span data-ttu-id="205ef-136">单击发送形状并将分配**消息**要**Message_2**。</span><span class="sxs-lookup"><span data-stu-id="205ef-136">Click the Send shape and assign the **Message** to be **Message_2**.</span></span>  
  
18. <span data-ttu-id="205ef-137">请确保其余消息流中的形状对适当的消息执行了操作。</span><span class="sxs-lookup"><span data-stu-id="205ef-137">Verify that the shapes in the rest of the message flow operate on the appropriate message.</span></span>  
  
19. <span data-ttu-id="205ef-138">右键单击你的项目在解决方案资源管理器，然后选择**生成**。</span><span class="sxs-lookup"><span data-stu-id="205ef-138">Right-click your project in Solution Explorer, and select **Build**.</span></span>  
  
20. <span data-ttu-id="205ef-139">右键单击你的项目并选择**部署**。</span><span class="sxs-lookup"><span data-stu-id="205ef-139">Right-click your project and select **Deploy**.</span></span>  
  
21. <span data-ttu-id="205ef-140">选择**绑定**， **Enlist**，和**启动**BizTalk 资源管理器来测试您的业务流程。</span><span class="sxs-lookup"><span data-stu-id="205ef-140">Select **Bind**, **Enlist**, and **Start** in the BizTalk Explorer to test your orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="205ef-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="205ef-141">See Also</span></span>  
 [<span data-ttu-id="205ef-142">消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="205ef-142">Message Context Properties</span></span>](../core/message-context-properties2.md)