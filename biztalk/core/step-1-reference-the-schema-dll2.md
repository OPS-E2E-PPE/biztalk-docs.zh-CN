---
title: 步骤 1： 引用架构 DLL2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1db92227-6164-42b9-b60c-12dd2cae46e2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c58156c64ae9954115ff214518879c4cd17e7417
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984326"
---
# <a name="step-1-reference-the-schema-dll"></a><span data-ttu-id="819de-102">步骤 1： 引用架构 DLL</span><span class="sxs-lookup"><span data-stu-id="819de-102">Step 1: Reference the Schema DLL</span></span>
<span data-ttu-id="819de-103">在 BizTalk 中，消息是不可改变的。</span><span class="sxs-lookup"><span data-stu-id="819de-103">In BizTalk, messages are immutable.</span></span> <span data-ttu-id="819de-104">因此，若要更改属性值，必须创建和修改新消息。</span><span class="sxs-lookup"><span data-stu-id="819de-104">Therefore, to change a property value you must create and modify a new message.</span></span> <span data-ttu-id="819de-105">通过在接收形状和发送形状之间插入消息赋值形状可以创建和修改新消息。</span><span class="sxs-lookup"><span data-stu-id="819de-105">You create and modify the new message by inserting a message assignment shape between the Receive and Send shapes.</span></span>  
  
 <span data-ttu-id="819de-106">但是，必须首先引用架构 DLL 才能访问 J.D.</span><span class="sxs-lookup"><span data-stu-id="819de-106">First, however, you must reference the schema DLL to gain access to the J.D.</span></span> <span data-ttu-id="819de-107">Edwards 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="819de-107">Edwards context properties.</span></span>  
  
### <a name="to-reference-the-schema-dll"></a><span data-ttu-id="819de-108">若要引用架构 DLL</span><span class="sxs-lookup"><span data-stu-id="819de-108">To reference the schema DLL</span></span>  
  
1. <span data-ttu-id="819de-109">为项目创建工作文件夹，例如 c:\class\JDE\BeginDoc，并创建用于放置测试 XML 的文件夹，例如 c:\class\JDE\input。</span><span class="sxs-lookup"><span data-stu-id="819de-109">Create a working folder, for example, c:\class\JDE\BeginDoc, for your project and a folder in which you will put the test XML, for example, c:\class\JDE\input.</span></span>  
  
2. <span data-ttu-id="819de-110">创建静态要求响应发送端口将请求发送到 J.D.</span><span class="sxs-lookup"><span data-stu-id="819de-110">Create a Static Solicit-Response Send Port to send the request to J.D.</span></span> <span data-ttu-id="819de-111">Edwards OneWorld。</span><span class="sxs-lookup"><span data-stu-id="819de-111">Edwards OneWorld.</span></span>  
  
    <span data-ttu-id="819de-112">![](../core/media/jde-example-2waysendport-ow.gif "JDE_example_2waysendport_OW")</span><span class="sxs-lookup"><span data-stu-id="819de-112">![](../core/media/jde-example-2waysendport-ow.gif "JDE_example_2waysendport_OW")</span></span>  
  
3. <span data-ttu-id="819de-113">在解决方案编辑器中，右键单击项目。</span><span class="sxs-lookup"><span data-stu-id="819de-113">In the Solution Editor, right-click your project.</span></span>  
  
   1. <span data-ttu-id="819de-114">选择**外**，选择**添加生成的项**，然后单击**添加适配器**。</span><span class="sxs-lookup"><span data-stu-id="819de-114">Select **Add**, select **Add Generated Items**, and then click **Add Adapter**.</span></span>  
  
   2. <span data-ttu-id="819de-115">选择用于 J.D.的 Microsoft BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="819de-115">Select the Microsoft BizTalk Adapter for J.D.</span></span> <span data-ttu-id="819de-116">Edwards OneWorld 和刚创建的端口。</span><span class="sxs-lookup"><span data-stu-id="819de-116">Edwards OneWorld and the port you just created.</span></span>  
  
   3. <span data-ttu-id="819de-117">在中**添加适配器向导**，选择**CSALES\B4200310**。</span><span class="sxs-lookup"><span data-stu-id="819de-117">In the **Add Adapter Wizard**, select **CSALES\B4200310**.</span></span>  
  
   4. <span data-ttu-id="819de-118">单击**完成**生成包含格式的消息的架构。</span><span class="sxs-lookup"><span data-stu-id="819de-118">Click **Finish** to generate the schema containing the format for the Message.</span></span>  
  
      <span data-ttu-id="819de-119">![](../core/media/jde-add-adapter-wizard.gif "JDE_add_adapter_wizard")</span><span class="sxs-lookup"><span data-stu-id="819de-119">![](../core/media/jde-add-adapter-wizard.gif "JDE_add_adapter_wizard")</span></span>  
  
4. <span data-ttu-id="819de-120">在 Visual Studio 中，打开解决方案资源管理器。</span><span class="sxs-lookup"><span data-stu-id="819de-120">In Visual Studio, open the Solution Explorer.</span></span>  
  
5. <span data-ttu-id="819de-121">右键单击**引用**，然后选择**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="819de-121">Right-click **References**, and then select **Add Reference**.</span></span>  
  
6. <span data-ttu-id="819de-122">上**添加引用**屏幕上，单击**浏览**按钮。</span><span class="sxs-lookup"><span data-stu-id="819de-122">On the **Add Reference** screen, click the **Browse** button.</span></span>  
  
    <span data-ttu-id="819de-123">![](../core/media/jde-add-reference-dll.gif "JDE_add_reference_dll")</span><span class="sxs-lookup"><span data-stu-id="819de-123">![](../core/media/jde-add-reference-dll.gif "JDE_add_reference_dll")</span></span>  
  
7. <span data-ttu-id="819de-124">上**选择组件**屏幕上，导航到 %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin。</span><span class="sxs-lookup"><span data-stu-id="819de-124">On the **Select Component** screen, navigate to %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin.</span></span>  
  
8. <span data-ttu-id="819de-125">选择**Microsoft.Adapters.JDEProperties.dll**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="819de-125">Select **Microsoft.Adapters.JDEProperties.dll**, and then click **Open**.</span></span>  
  
9. <span data-ttu-id="819de-126">上**添加引用**屏幕上，该 DLL 中将显示**选定的组件**部分。</span><span class="sxs-lookup"><span data-stu-id="819de-126">On the **Add Reference** screen, the DLL appears in the **Selected Components** section.</span></span>  
  
     <span data-ttu-id="819de-127">![](../core/media/jde-properties-selection.gif "JDE_properties_selection")</span><span class="sxs-lookup"><span data-stu-id="819de-127">![](../core/media/jde-properties-selection.gif "JDE_properties_selection")</span></span>  
  
10. <span data-ttu-id="819de-128">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="819de-128">Click **OK**.</span></span>  
  
11. <span data-ttu-id="819de-129">双击业务流程可访问业务流程设计器。</span><span class="sxs-lookup"><span data-stu-id="819de-129">Double-click your orchestration to access the Orchestration Designer.</span></span>  
  
     <span data-ttu-id="819de-130">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="819de-130">\- OR -</span></span>  
  
     <span data-ttu-id="819de-131">选择**视图**，选择**其他 Windows**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="819de-131">Select **View**, select **Other Windows**, and then click **Orchestration View**.</span></span>  
  
     <span data-ttu-id="819de-132">随即将显示业务流程视图。</span><span class="sxs-lookup"><span data-stu-id="819de-132">The Orchestration View appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="819de-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="819de-133">See Also</span></span>  
 <span data-ttu-id="819de-134">[步骤 2： 创建业务流程](../core/step-2-create-the-orchestration1.md) </span><span class="sxs-lookup"><span data-stu-id="819de-134">[Step 2: Create the Orchestration](../core/step-2-create-the-orchestration1.md) </span></span>  
 <span data-ttu-id="819de-135">[步骤 3： 完成并运行项目](../core/step-3-complete-and-run-the-project2.md) </span><span class="sxs-lookup"><span data-stu-id="819de-135">[Step 3: Complete and Run the Project](../core/step-3-complete-and-run-the-project2.md) </span></span>  
 [<span data-ttu-id="819de-136">步骤 4：创建示例 XML BeginDoc</span><span class="sxs-lookup"><span data-stu-id="819de-136">Step 4: Create a Sample XML BeginDoc</span></span>](../core/step-4-create-a-sample-xml-begindoc1.md)