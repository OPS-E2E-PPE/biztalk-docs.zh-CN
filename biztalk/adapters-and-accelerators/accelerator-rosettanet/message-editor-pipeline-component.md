---
title: 消息编辑器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, Message Editor Pipeline Component
- Message Editor Pipeline Component
- messages, editing
- pipelines, Message Editor Pipeline Component
ms.assetid: f2b22dea-54e8-410b-868f-2978139f438b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f0ac419e64b8a1a949fb2e3044be9de670b387a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975422"
---
# <a name="message-editor-pipeline-component"></a><span data-ttu-id="c5c03-102">消息编辑器管道组件</span><span class="sxs-lookup"><span data-stu-id="c5c03-102">Message Editor Pipeline Component</span></span>
<span data-ttu-id="c5c03-103">此组件可用于在发送或接收管道内自动编辑多部分消息的任何部分。</span><span class="sxs-lookup"><span data-stu-id="c5c03-103">This component lets you edit automatically any part of a multipart message within a send or receive pipeline.</span></span> <span data-ttu-id="c5c03-104">向现有管道添加此组件可以在典型处理中设置替换部分。</span><span class="sxs-lookup"><span data-stu-id="c5c03-104">You add this component to an existing pipeline to set up the replacement as part of typical processing.</span></span>  
  
## <a name="building-the-message-editor-pipeline-component-into-an-existing-pipeline"></a><span data-ttu-id="c5c03-105">在现有管道中构建消息编辑器管道组件</span><span class="sxs-lookup"><span data-stu-id="c5c03-105">Building the Message Editor Pipeline Component into an Existing Pipeline</span></span>  
 <span data-ttu-id="c5c03-106">要使用消息编辑器管道组件，必须向现有管道添加该组件。</span><span class="sxs-lookup"><span data-stu-id="c5c03-106">To use the Message Editor Pipeline Component, you have to add the component to an existing pipeline.</span></span> <span data-ttu-id="c5c03-107">有关详细信息，请参阅"创建管道使用管道设计器"中 BizTalk Server 帮助。</span><span class="sxs-lookup"><span data-stu-id="c5c03-107">For more information, see "Creating Pipelines with Pipeline Designer" in BizTalk Server Help.</span></span>  
  
#### <a name="to-add-the-message-editor-pipeline-component-to-an-existing-pipeline"></a><span data-ttu-id="c5c03-108">向现有管道添加消息编辑器管道组件</span><span class="sxs-lookup"><span data-stu-id="c5c03-108">To add the Message Editor Pipeline Component to an existing pipeline</span></span>  
  
1. <span data-ttu-id="c5c03-109">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="c5c03-109">Start Visual Studio.</span></span>  
  
2. <span data-ttu-id="c5c03-110">上**文件**菜单，依次指向**打开**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="c5c03-110">On the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="c5c03-111">将移到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Message Editor Pipeline Component，选择**MessageEditor.csproj**，然后单击**打开**.</span><span class="sxs-lookup"><span data-stu-id="c5c03-111">Move to C:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Message Editor Pipeline Component, select **MessageEditor.csproj**, and then click **Open**.</span></span>  
  
4. <span data-ttu-id="c5c03-112">启动 Visual Studio 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="c5c03-112">Start Visual Studio command prompt.</span></span>  
  
5. <span data-ttu-id="c5c03-113">在命令提示符处，转到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Message Editor Pipeline Component\obj\debug。</span><span class="sxs-lookup"><span data-stu-id="c5c03-113">At the command prompt, move to C:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Message Editor Pipeline Component\obj\debug.</span></span>  
  
6. <span data-ttu-id="c5c03-114">在命令提示符处，键入**sn-k MessageEditor.snk**创建密钥，，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="c5c03-114">At the command prompt, type **sn -k MessageEditor.snk** to create a key, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="c5c03-115">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器中右键单击**MessageEditor**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="c5c03-115">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click **MessageEditor**, and then click **Properties**.</span></span>  
  
8. <span data-ttu-id="c5c03-116">在中**MessageEditor 属性**页上，单击**签名**选项卡，然后依次**程序集签名**复选框。</span><span class="sxs-lookup"><span data-stu-id="c5c03-116">In the **MessageEditor Property** page, click **Signing** tab, and then click **Sign the assembly** checkbox.</span></span>  
  
9. <span data-ttu-id="c5c03-117">在中**选择强名称密钥文件**下拉列表中，浏览到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for Rosettanet\sdk\message Editor Pipeline Component\obj\debug 选择**MessageEditor.snk** ，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="c5c03-117">In **Choose a strong name key file** drop-down, browse to C:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\ SDK\Message Editor Pipeline Component\obj\debug and select **MessageEditor.snk** and then click **Open**.</span></span>  
  
10. <span data-ttu-id="c5c03-118">在解决方案资源管理器中右键单击**MessageEditor**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="c5c03-118">In Solution Explorer, right-click **MessageEditor**, and then click **Build**.</span></span> <span data-ttu-id="c5c03-119">在输出窗格中检验该生成操作是否成功。</span><span class="sxs-lookup"><span data-stu-id="c5c03-119">Verify in the Output pane that the build succeeded.</span></span>  
  
11. <span data-ttu-id="c5c03-120">单击**启动**，依次指向**所有程序**，指向**附件**，然后单击**Windows 资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="c5c03-120">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
12. <span data-ttu-id="c5c03-121">在中[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，转到 C:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\Message Editor Pipeline Component\obj\debug，右键单击**Microsoft.Solutions.BTARN.SDK.MessageEditor.dll**，然后单击**复制**。</span><span class="sxs-lookup"><span data-stu-id="c5c03-121">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to C:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\Message Editor Pipeline Component\obj\debug, right-click **Microsoft.Solutions.BTARN.SDK.MessageEditor.dll**, and then click **Copy**.</span></span>  
  
13. <span data-ttu-id="c5c03-122">转到 C:\Program Files\Microsoft BizTalk Server 2013\Pipeline Components，右键单击**管道组件**，然后单击**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="c5c03-122">Move to C:\Program Files\Microsoft BizTalk Server 2013\Pipeline Components, right-click **Pipeline Components**, and then click **Paste**.</span></span>  
  
14. <span data-ttu-id="c5c03-123">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**打开**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="c5c03-123">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
15. <span data-ttu-id="c5c03-124">打开包含要添加编辑器的管道的项目。</span><span class="sxs-lookup"><span data-stu-id="c5c03-124">Open the project that contains the pipeline to which you want to add the editor.</span></span>  
  
16. <span data-ttu-id="c5c03-125">在解决方案资源管理器中，双击管道名称，在“管道设计器”中打开该管道。</span><span class="sxs-lookup"><span data-stu-id="c5c03-125">In Solution Explorer, double-click the pipeline name to open the pipeline in Pipeline Designer.</span></span>  
  
17. <span data-ttu-id="c5c03-126">在工具箱窗格中，BizTalk 管道组件窗格中右键单击，然后单击**添加/删除项**。</span><span class="sxs-lookup"><span data-stu-id="c5c03-126">Right-click in the BizTalk Pipeline Components pane of the Toolbox pane, and then click **Add/Remove Items**.</span></span>  
  
18. <span data-ttu-id="c5c03-127">在**自定义工具箱**对话框中，在**BizTalk 管道组件**选项卡上，选择**BTARN 消息编辑器组件**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="c5c03-127">In the **Customize Toolbox** dialog box, on the **BizTalk Pipeline Components** tab, select **BTARN Message Editor Component**, and then click **OK**.</span></span>  
  
19. <span data-ttu-id="c5c03-128">在工具箱窗格的 BizTalk 管道组件窗格中，单击并按住**BTARN 消息编辑器组件**，然后将该组件拖动到要在管道中的位置。</span><span class="sxs-lookup"><span data-stu-id="c5c03-128">In the BizTalk Pipeline Components pane of the Toolbox pane, click and hold **BTARN Message Editor Component**, and then drag the component to the position that you want in the pipeline.</span></span>  
  
20. <span data-ttu-id="c5c03-129">在工具箱窗格的 BizTalk 管道组件窗格中，单击并按住**BTARN 消息编辑器组件**，然后将该组件拖动到要在管道中的位置。</span><span class="sxs-lookup"><span data-stu-id="c5c03-129">In the BizTalk Pipeline Components pane of the Toolbox pane, click and hold **BTARN Message Editor Component**, and then drag the component to the position that you want in the pipeline.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c5c03-130">建议你在接收管道组件的“拆装”阶段后或在发送管道组件的“预组装”阶段中，添加消息编辑器管道组件。</span><span class="sxs-lookup"><span data-stu-id="c5c03-130">It is recommended that you add the Message Editor Pipeline Component after the Disassemble stage in the receive pipeline component or in the Pre-Assemble stage of the send pipeline component.</span></span>  
  
21. <span data-ttu-id="c5c03-131">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，在管道设计器中，选择**BTARN 消息编辑器组件**形状。</span><span class="sxs-lookup"><span data-stu-id="c5c03-131">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in Pipeline Designer, select the **BTARN Message Editor Component** shape.</span></span>  
  
22. <span data-ttu-id="c5c03-132">在属性窗格中，在文本框中与相关联**XPath 查询**，键入你想要更改的值的 XPath 元素的名称。</span><span class="sxs-lookup"><span data-stu-id="c5c03-132">In the Properties pane, in the text box associated with **XPath Query**, type the name of the XPath element for which you want to change the value.</span></span>  
  
23. <span data-ttu-id="c5c03-133">在文本框中与相关联**XPath 值**，键入你想要设置的 XPath 元素的值。</span><span class="sxs-lookup"><span data-stu-id="c5c03-133">In the text box associated with **XPath Value**, type the value to which you want to set the XPath element.</span></span>  
  
24. <span data-ttu-id="c5c03-134">在解决方案资源管理器中，右键单击项目名称，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="c5c03-134">In Solutions Explorer, right-click the project name, and then click **Build**.</span></span> <span data-ttu-id="c5c03-135">检验该生成操作是否成功。</span><span class="sxs-lookup"><span data-stu-id="c5c03-135">Verify that the build succeeds.</span></span>  
  
25. <span data-ttu-id="c5c03-136">在解决方案资源管理器中，右键单击项目名称，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="c5c03-136">In Solutions Explorer, right-click the project name, and then click **Deploy**.</span></span> <span data-ttu-id="c5c03-137">检验该部署操作是否成功。</span><span class="sxs-lookup"><span data-stu-id="c5c03-137">Verify that the deployment succeeds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5c03-138">示例</span><span class="sxs-lookup"><span data-stu-id="c5c03-138">Example</span></span>  
 <span data-ttu-id="c5c03-139">要更改 0C1 PIP 架构中元素 `ProprietaryDocumentIdentifier` 的值，请将以下代码段中给出的 XPath 查询添加到消息编辑器管道组件的“XPath 查询”属性中：</span><span class="sxs-lookup"><span data-stu-id="c5c03-139">To change the value of the element `ProprietaryDocumentIdentifier` in the 0C1 PIP Schema, add the XPath Query shown in the following Code section to the XPath Query property of the Message Editor Pipeline Component.</span></span>  
  
```  
/*[local-name()='Pip0C1AsynchronousTestNotification' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']/*[local-name()='thisDocumentIdentifier' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']/*[local-name()='ProprietaryDocumentIdentifier' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']  
```  
  
 <span data-ttu-id="c5c03-140">若要获取完整的 XPath 查询，请在 BizTalk 编辑器中打开该架构，然后从“属性”窗口下的 `Instance XPath` 属性中复制 Xpath。</span><span class="sxs-lookup"><span data-stu-id="c5c03-140">To obtain a complete XPath Query, open the schema in BizTalk Editor, and then copy the Xpath from the `Instance XPath` property under the Properties window.</span></span> <span data-ttu-id="c5c03-141">你提供的 XPath 查询应在其中具有所有命名空间引用。</span><span class="sxs-lookup"><span data-stu-id="c5c03-141">The XPath Query that you provide should have all the namespace references in it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5c03-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5c03-142">See Also</span></span>  
 [<span data-ttu-id="c5c03-143">实用工具</span><span class="sxs-lookup"><span data-stu-id="c5c03-143">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
