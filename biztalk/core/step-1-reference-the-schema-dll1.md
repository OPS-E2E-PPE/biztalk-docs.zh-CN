---
title: 步骤 1： 引用架构 DLL1 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47e4b773-e484-4931-9ab2-b8dd0080ea1c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9c2d5051c7dfd3c0f971b34922ca4e5747117c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279437"
---
# <a name="step-1-reference-the-schema-dll"></a><span data-ttu-id="77746-102">步骤 1： 引用 DLL 的架构</span><span class="sxs-lookup"><span data-stu-id="77746-102">Step 1: Reference the Schema DLL</span></span>
<span data-ttu-id="77746-103">在 BizTalk 中，消息是不可改变的。</span><span class="sxs-lookup"><span data-stu-id="77746-103">In BizTalk, messages are immutable.</span></span> <span data-ttu-id="77746-104">因此，若要更改属性值，必须创建和修改新消息。</span><span class="sxs-lookup"><span data-stu-id="77746-104">Therefore, to change a property value you must create and modify a new message.</span></span> <span data-ttu-id="77746-105">通过在接收形状和发送形状之间插入消息赋值形状可以创建和修改新消息。</span><span class="sxs-lookup"><span data-stu-id="77746-105">You create and modify the new message by inserting a message assignment shape between the Receive and Send shapes.</span></span>  
  
 <span data-ttu-id="77746-106">但是，必须首先引用架构 DLL 才能访问 J.D.</span><span class="sxs-lookup"><span data-stu-id="77746-106">First, however, you must reference the schema DLL to gain access to the J.D.</span></span> <span data-ttu-id="77746-107">Edwards EnterpriseOne 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="77746-107">Edwards EnterpriseOne context properties.</span></span>  
  
### <a name="to-reference-the-schema-dll"></a><span data-ttu-id="77746-108">若要引用 DLL 的架构</span><span class="sxs-lookup"><span data-stu-id="77746-108">To reference the schema DLL</span></span>  
  
1.  <span data-ttu-id="77746-109">为项目创建工作文件夹，例如 c:\class\JDE\BeginDoc，并创建用于放置测试 XML 的文件夹，例如 c:\class\JDE\input。</span><span class="sxs-lookup"><span data-stu-id="77746-109">Create a working folder, for example, c:\class\JDE\BeginDoc, for your project and a folder in which you will put the test XML, for example, c:\class\JDE\input.</span></span>  
  
2.  <span data-ttu-id="77746-110">创建静态请求-响应发送端口将请求发送到 J.D.</span><span class="sxs-lookup"><span data-stu-id="77746-110">Create a Static Solicit-Response Send Port to send the request to J.D.</span></span> <span data-ttu-id="77746-111">Edwards EnterpriseOne。</span><span class="sxs-lookup"><span data-stu-id="77746-111">Edwards EnterpriseOne.</span></span>  
  
     <span data-ttu-id="77746-112">![JDOneWorld 传输属性](../core/media/example-2waysendport-ow.gif "example_2waysendport_OW")</span><span class="sxs-lookup"><span data-stu-id="77746-112">![JDOneWorld Transport Properties](../core/media/example-2waysendport-ow.gif "example_2waysendport_OW")</span></span>  
  
3.  <span data-ttu-id="77746-113">在解决方案编辑器中，右键单击项目。</span><span class="sxs-lookup"><span data-stu-id="77746-113">In the Solution Editor, right-click your project.</span></span>  
  
    1.  <span data-ttu-id="77746-114">选择**添加**，选择**添加生成的项**，然后单击**添加适配器**。</span><span class="sxs-lookup"><span data-stu-id="77746-114">Select **Add**, select **Add Generated Items**, and then click **Add Adapter**.</span></span>  
  
    2.  <span data-ttu-id="77746-115">为 J.D.选择 Microsoft BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="77746-115">Select the Microsoft BizTalk Adapter for J.D.</span></span> <span data-ttu-id="77746-116">Edwards EnterpriseOne 和刚创建的端口。</span><span class="sxs-lookup"><span data-stu-id="77746-116">Edwards EnterpriseOne and the port you just created.</span></span>  
  
    3.  <span data-ttu-id="77746-117">在**添加适配器向导**，选择**CSALES\B4200310**。</span><span class="sxs-lookup"><span data-stu-id="77746-117">In the **Add Adapter Wizard**, select **CSALES\B4200310**.</span></span>  
  
    4.  <span data-ttu-id="77746-118">单击**完成**来生成包含格式的消息的架构。</span><span class="sxs-lookup"><span data-stu-id="77746-118">Click **Finish** to generate the schema containing the format for the Message.</span></span>  
  
     <span data-ttu-id="77746-119">![添加适配器向导](../core/media/add-adapter-wizard.gif "add_adapter_wizard")</span><span class="sxs-lookup"><span data-stu-id="77746-119">![Add Adapter Wizard](../core/media/add-adapter-wizard.gif "add_adapter_wizard")</span></span>  
  
4.  <span data-ttu-id="77746-120">在 Visual Studio 中，打开解决方案资源管理器。</span><span class="sxs-lookup"><span data-stu-id="77746-120">In Visual Studio, open the Solution Explorer.</span></span>  
  
5.  <span data-ttu-id="77746-121">右键单击**引用**，然后选择**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="77746-121">Right-click **References**, and then select **Add Reference**.</span></span>  
  
6.  <span data-ttu-id="77746-122">上**添加引用**屏幕上，单击**浏览**按钮。</span><span class="sxs-lookup"><span data-stu-id="77746-122">On the **Add Reference** screen, click the **Browse** button.</span></span>  
  
7.  <span data-ttu-id="77746-123">上**选择组件**屏幕上，为企业 Applications\bin 导航到 %SystemDrive%\Program Files\Common Files\Microsoft BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="77746-123">On the **Select Component** screen, navigate to %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin.</span></span>  
  
8.  <span data-ttu-id="77746-124">选择**Microsoft.Adapters.JDEProperties.dll**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="77746-124">Select **Microsoft.Adapters.JDEProperties.dll**, and then click **Open**.</span></span>  
  
9. <span data-ttu-id="77746-125">上**添加引用**DLL 中出现的屏幕，**选定的组件**部分。</span><span class="sxs-lookup"><span data-stu-id="77746-125">On the **Add Reference** screen, the DLL appears in the **Selected Components** section.</span></span>  
  
     <span data-ttu-id="77746-126">![属性选择屏幕](../core/media/properties-selection.gif "properties_selection")</span><span class="sxs-lookup"><span data-stu-id="77746-126">![Properties Selection screen](../core/media/properties-selection.gif "properties_selection")</span></span>  
  
10. <span data-ttu-id="77746-127">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="77746-127">Click **OK**.</span></span>  
  
11. <span data-ttu-id="77746-128">双击业务流程可访问业务流程设计器。</span><span class="sxs-lookup"><span data-stu-id="77746-128">Double-click your orchestration to access the Orchestration Designer.</span></span>  
  
     <span data-ttu-id="77746-129">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="77746-129">\- OR -</span></span>  
  
     <span data-ttu-id="77746-130">选择**视图**，选择**其他窗口**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="77746-130">Select **View**, select **Other Windows**, and then click **Orchestration View**.</span></span>  
  
     <span data-ttu-id="77746-131">随即将显示业务流程视图。</span><span class="sxs-lookup"><span data-stu-id="77746-131">The Orchestration View appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77746-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77746-132">See Also</span></span>  
 <span data-ttu-id="77746-133">[步骤 2： 创建业务流程](../core/step-2-create-the-orchestration2.md) </span><span class="sxs-lookup"><span data-stu-id="77746-133">[Step 2: Create the Orchestration](../core/step-2-create-the-orchestration2.md) </span></span>  
 <span data-ttu-id="77746-134">[任务 4： 配置构造消息形状](../core/task-4-configure-the-construct-message-shape1.md) </span><span class="sxs-lookup"><span data-stu-id="77746-134">[Task 4: Configure the Construct Message Shape](../core/task-4-configure-the-construct-message-shape1.md) </span></span>  
 <span data-ttu-id="77746-135">[任务 5： 配置转换形状](../core/task-5-configure-the-transform-shape2.md) </span><span class="sxs-lookup"><span data-stu-id="77746-135">[Task 5: Configure the Transform Shape](../core/task-5-configure-the-transform-shape2.md) </span></span>  
 <span data-ttu-id="77746-136">[步骤 3： 完成并运行项目](../core/step-3-complete-and-run-the-project1.md) </span><span class="sxs-lookup"><span data-stu-id="77746-136">[Step 3: Complete and Run the Project](../core/step-3-complete-and-run-the-project1.md) </span></span>  
 [<span data-ttu-id="77746-137">步骤 4： 创建示例 XML BeginDoc</span><span class="sxs-lookup"><span data-stu-id="77746-137">Step 4: Create a Sample XML BeginDoc</span></span>](../core/step-4-create-a-sample-xml-begindoc2.md)