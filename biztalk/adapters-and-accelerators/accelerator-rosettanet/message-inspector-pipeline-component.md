---
title: 消息检查器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipelines, custom pipelines
- pipelines, Message Inspector Pipeline Component
- Message Inspector Pipeline Component
- pipelines, creating
ms.assetid: d9c00718-c8cd-4289-8f58-e4edc61b9a05
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b7b0a20e584771a41c6732bccbdf017efe29517
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966862"
---
# <a name="message-inspector-pipeline-component"></a><span data-ttu-id="0590a-102">消息检查器管道组件</span><span class="sxs-lookup"><span data-stu-id="0590a-102">Message Inspector Pipeline Component</span></span>
<span data-ttu-id="0590a-103">使用此管道组件，你可以检查由多个部分组成的消息的所有部分和消息上下文，以便确定消息是否存在问题。</span><span class="sxs-lookup"><span data-stu-id="0590a-103">This pipeline component lets you examine all the parts of a multi-part message, and the message context, to determine whether there is a problem with the message.</span></span> <span data-ttu-id="0590a-104">你可以用此组件来排除故障。</span><span class="sxs-lookup"><span data-stu-id="0590a-104">You use this component for troubleshooting purposes.</span></span>  
  
 <span data-ttu-id="0590a-105">该管道组件将 XML 文件放入你指定的目录中。</span><span class="sxs-lookup"><span data-stu-id="0590a-105">The pipeline component drops XML files into a directory that you designate.</span></span> <span data-ttu-id="0590a-106">这些文件中的每一个都包含 RNIFv2.0 消息的四个部分（前导头、传递头、服务头和服务内容）中的一个或 RNIFv1.1 消息的三个部分（前导头、服务头和服务内容）中的一个。</span><span class="sxs-lookup"><span data-stu-id="0590a-106">Each of these files contains one of the four parts of an RNIFv2.0 message (Preamble Header, Delivery Header, Service Header, and Service Content) or the three parts of an RNIFv1.1 message (Preamble Header, Service Header, and Service Content).</span></span> <span data-ttu-id="0590a-107">另一个 XML 文件中包含消息上下文。</span><span class="sxs-lookup"><span data-stu-id="0590a-107">Another XML file contains the message context.</span></span>  
  
 <span data-ttu-id="0590a-108">你可以将此组件构建到自定义管道中，然后将其附加到发送端口。</span><span class="sxs-lookup"><span data-stu-id="0590a-108">You build this component into a custom pipeline and attach it to a send port.</span></span> <span data-ttu-id="0590a-109">你可以在发送端口中创建一个筛选器，用于订阅要监视的消息。</span><span class="sxs-lookup"><span data-stu-id="0590a-109">You create a filter in the send port to subscribe to the messages that you want to monitor.</span></span> <span data-ttu-id="0590a-110">此故障排除操作除了处理该 Microsoft® 标准[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]已执行。</span><span class="sxs-lookup"><span data-stu-id="0590a-110">This troubleshooting occurs in addition to the standard processing that Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] already performs.</span></span>  
  
## <a name="building-a-custom-pipeline-using-the-message-inspector-pipeline-component"></a><span data-ttu-id="0590a-111">使用消息检查器管道组件构建自定义管道</span><span class="sxs-lookup"><span data-stu-id="0590a-111">Building a Custom Pipeline Using the Message Inspector Pipeline Component</span></span>  
 <span data-ttu-id="0590a-112">若要使用消息检查器管道组件，你必须构建并部署一个包含该组件的自定义管道。</span><span class="sxs-lookup"><span data-stu-id="0590a-112">To use the Message Inspector Pipeline Component, you have to build and deploy a custom pipeline that includes the component.</span></span> <span data-ttu-id="0590a-113">有关详细信息，请参阅"创建管道使用管道设计器"中 BizTalk Server 帮助。</span><span class="sxs-lookup"><span data-stu-id="0590a-113">For more information, see "Creating Pipelines with Pipeline Designer" in BizTalk Server Help.</span></span>  
  
#### <a name="to-deploy-the-message-inspector-pipeline-component"></a><span data-ttu-id="0590a-114">部署消息检查器管道组件</span><span class="sxs-lookup"><span data-stu-id="0590a-114">To deploy the Message Inspector Pipeline Component</span></span>  
  
1. <span data-ttu-id="0590a-115">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="0590a-115">Start Visual Studio.</span></span>  
  
2. <span data-ttu-id="0590a-116">上**文件**菜单，依次指向**打开**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="0590a-116">On the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="0590a-117">将移到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Message Inspector Pipeline Component，选择**MessageInspector.csproj**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="0590a-117">Move to C:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Message Inspector Pipeline Component, select **MessageInspector.csproj**, and then click **Open**.</span></span>  
  
4. <span data-ttu-id="0590a-118">打开 Visual Studio 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="0590a-118">Open the Visual Studio command prompt.</span></span>  
  
5. <span data-ttu-id="0590a-119">在命令提示符处，转到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Message Inspector Pipeline Component\obj\debug。</span><span class="sxs-lookup"><span data-stu-id="0590a-119">At the command prompt, move to C:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Message Inspector Pipeline Component\obj\debug.</span></span>  
  
6. <span data-ttu-id="0590a-120">在命令提示符处，键入**sn-k MessageInspector.snk"** 创建密钥，，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="0590a-120">At the command prompt, type **"sn -k MessageInspector.snk"** to create a key, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="0590a-121">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器中右键单击**MessageInspector**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="0590a-121">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click **MessageInspector**, and then click **Properties**.</span></span>  
  
8. <span data-ttu-id="0590a-122">在中**MessageInspector 属性**页上，单击**签名**选项卡，然后依次**程序集签名**复选框。</span><span class="sxs-lookup"><span data-stu-id="0590a-122">In the **MessageInspector Property**  page, click **Signing** tab, and then click **Sign the assembly** checkbox.</span></span>  
  
9. <span data-ttu-id="0590a-123">在中**选择强名称密钥文件**下拉列表中，浏览到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Message Inspector Pipeline Component\obj\debug 选择**MessageInspector.snk** ，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="0590a-123">In **Choose a strong name key file** drop-down, browse to C:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Message Inspector Pipeline Component\obj\debug and select **MessageInspector.snk** and then click **Open**.</span></span>  
  
10. <span data-ttu-id="0590a-124">在解决方案资源管理器中右键单击**MessageInspector**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="0590a-124">In Solutions Explorer, right-click **MessageInspector**, and then click **Build**.</span></span> <span data-ttu-id="0590a-125">在输出窗格中检验该生成操作是否成功。</span><span class="sxs-lookup"><span data-stu-id="0590a-125">Verify in the Output pane that the build succeeded.</span></span>  
  
11. <span data-ttu-id="0590a-126">单击**启动**，依次指向**所有程序**，指向**附件**，然后单击**Windows 资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="0590a-126">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
12. <span data-ttu-id="0590a-127">在中[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，转到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Message Inspector Pipeline Component\obj\debug，右键单击**Microsoft.Solutions.BTARN.SDK.MessageInspector.dll**，然后单击**复制**。</span><span class="sxs-lookup"><span data-stu-id="0590a-127">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to C:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Message Inspector Pipeline Component\obj\debug, right-click **Microsoft.Solutions.BTARN.SDK.MessageInspector.dll**, and then click **Copy**.</span></span>  
  
13. <span data-ttu-id="0590a-128">将移到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\Pipeline Components，右键单击**管道组件**，然后单击**粘贴**.</span><span class="sxs-lookup"><span data-stu-id="0590a-128">Move to C:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\Pipeline Components, right-click **Pipeline Components**, and then click **Paste**.</span></span>  
  
14. <span data-ttu-id="0590a-129">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="0590a-129">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
15. <span data-ttu-id="0590a-130">在中**新的项目**对话框中，在模板窗格中，选择**空的 BizTalk Server 项目**，在**名称**框中，键入项目的名称。</span><span class="sxs-lookup"><span data-stu-id="0590a-130">In the **New Project** dialog box, in the Templates pane, select **Empty BizTalk Server Project**, in the **Name** box, type a name for the project.</span></span> <span data-ttu-id="0590a-131">在中**位置**框中，转到你想要保存在中，项目的文件夹，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0590a-131">In the **Location** box, move to the folder that you want to save the project in, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="0590a-132">在解决方案资源管理器中右键单击项目名称，指向**外**，然后单击**添加新项**。</span><span class="sxs-lookup"><span data-stu-id="0590a-132">In Solution Explorer, right-click the project name, point to **Add**, and then click **Add New Item**.</span></span>  
  
17. <span data-ttu-id="0590a-133">在中**添加新项**对话框中，选择**发送管道**，在**名称**框中，为自定义管道文件中，键入一个名称，然后单击**打开**.</span><span class="sxs-lookup"><span data-stu-id="0590a-133">In the **Add New Item** dialog box, select **Send Pipeline**, in the **Name** box, type a name for the custom pipeline file, and then click **Open**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0590a-134">请只将消息检查器管道组件添加到发送端口，而不要添加到接收端口。</span><span class="sxs-lookup"><span data-stu-id="0590a-134">Add the Message Inspector Pipeline Component only to send ports, not to receive ports.</span></span>  
  
18. <span data-ttu-id="0590a-135">在工具箱窗格中，在 BizTalk 管道组件窗格中右键单击，然后单击**添加/删除项**。</span><span class="sxs-lookup"><span data-stu-id="0590a-135">Right-click within the BizTalk Pipeline Components pane of the Toolbox pane, and then click **Add/Remove Items**.</span></span>  
  
19. <span data-ttu-id="0590a-136">在**自定义工具箱**对话框中，在**BizTalk 管道组件**选项卡上，选择**BTARN 消息检查器组件**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="0590a-136">In the **Customize Toolbox** dialog box, on the **BizTalk Pipeline Components** tab, select **BTARN Message Inspector Component**, and then click **OK**.</span></span>  
  
20. <span data-ttu-id="0590a-137">在工具箱窗格的 BizTalk 管道组件窗格中，单击并按住**BTARN 消息检查器组件**，然后将该组件拖动上**放到此处 ！**</span><span class="sxs-lookup"><span data-stu-id="0590a-137">In the BizTalk Pipeline Components pane of the Toolbox pane, click and hold **BTARN Message Inspector Component**, and then drag the component on a **Drop Here!**</span></span> <span data-ttu-id="0590a-138">框。</span><span class="sxs-lookup"><span data-stu-id="0590a-138">box.</span></span>  
  
21. <span data-ttu-id="0590a-139">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器，右键单击管道项目的名称，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="0590a-139">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click the name of the pipeline project, and then click **Properties**.</span></span>  
  
22. <span data-ttu-id="0590a-140">在中**属性页**对话框中，单击**通用属性**，然后单击**程序集**。</span><span class="sxs-lookup"><span data-stu-id="0590a-140">In the **Property Pages** dialog box, click **Common Properties**, and then click **Assembly**.</span></span>  
  
23. <span data-ttu-id="0590a-141">在右窗格中，在文本框中与相关联**程序集密钥文件**，单击省略号，转到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Message InspectorPipeline Component\obj\debug，选择**MessageInspector.snk**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0590a-141">In the right pane, in the text box associated with **Assembly Key File**, click the ellipses, move to C:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Message Inspector Pipeline Component\obj\debug, select **MessageInspector.snk**, and then click **OK**.</span></span>  
  
24. <span data-ttu-id="0590a-142">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]管道设计器中，选择**BTARN 消息检查器组件**形状。</span><span class="sxs-lookup"><span data-stu-id="0590a-142">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Pipeline Designer, select the **BTARN Message Inspector Component** shape.</span></span>  
  
25. <span data-ttu-id="0590a-143">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]属性窗口，请在**Directory**框中，键入你想要删除的 XML 文件的目录的名称。</span><span class="sxs-lookup"><span data-stu-id="0590a-143">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Properties window, in the **Directory** box, type the name of the directory to which you want to drop the XML files.</span></span>  
  
26. <span data-ttu-id="0590a-144">在解决方案资源管理器，右键单击项目名称，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="0590a-144">In Solution Explorer, right-click the project name, and then click **Build**.</span></span> <span data-ttu-id="0590a-145">检验该生成操作是否成功。</span><span class="sxs-lookup"><span data-stu-id="0590a-145">Verify that the build succeeds.</span></span>  
  
27. <span data-ttu-id="0590a-146">在解决方案资源管理器，右键单击项目名称，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="0590a-146">In Solution Explorer, right-click the project name, and then click **Deploy**.</span></span> <span data-ttu-id="0590a-147">检验该部署操作是否成功。</span><span class="sxs-lookup"><span data-stu-id="0590a-147">Verify that the deployment succeeds.</span></span>  
  
28. <span data-ttu-id="0590a-148">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后在**视图**菜单中，单击**BizTalk 浏览器**。</span><span class="sxs-lookup"><span data-stu-id="0590a-148">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **View** menu, click **BizTalk Explorer**.</span></span>  
  
29. <span data-ttu-id="0590a-149">右键单击**发送端口**，然后单击**添加发送端口**。</span><span class="sxs-lookup"><span data-stu-id="0590a-149">Right-click **Send Ports**, and then click **Add Send Port**.</span></span>  
  
30. <span data-ttu-id="0590a-150">在中**创建新发送端口**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0590a-150">In the **Create New Send Port** dialog box, click **OK**.</span></span>  
  
31. <span data-ttu-id="0590a-151">在中**发送端口属性**对话框中**名称**框中，键入发送端口的名称与**主**选择左窗格中，单击**传输类型**右窗格中，然后选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="0590a-151">In the **Send Port Properties** dialog box, in the **Name** box, type a name for the send port, with **Primary** selected in the left pane, click **Transport Type** in the right pane, and select **FILE**.</span></span>  
  
32. <span data-ttu-id="0590a-152">在中**发送端口属性**对话框中**地址 (URI)** 框中，单击省略号按钮 (**...**).</span><span class="sxs-lookup"><span data-stu-id="0590a-152">In the **Send Port Properties** dialog box, in the **Address (URI)** box, click the ellipsis button (**...**).</span></span>  
  
33. <span data-ttu-id="0590a-153">在中**FILE 传输属性**对话框中，键入**目标**文件夹的名称，单击**发送**在左窗格中，然后为**发送管道**在右窗格中，选择刚创建的自定义管道。</span><span class="sxs-lookup"><span data-stu-id="0590a-153">In the **FILE Transport Properties** dialog box, type the **Destination** folder name, click **Send** in the left pane, and then for the **Send Pipeline** in the right pane, select the custom pipeline that you have just created.</span></span>  
  
34. <span data-ttu-id="0590a-154">单击**筛选器和映射**在左窗格中，然后单击**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="0590a-154">Click **Filters & Maps** in the left pane, and then click **Filters**.</span></span>  
  
35. <span data-ttu-id="0590a-155">在右窗格中输入筛选器表达式，指定希望该管道为哪种类型的文件放置 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="0590a-155">Enter a filter expression in the right pane, designating the type of files that you want the pipeline to drop XML files for.</span></span> <span data-ttu-id="0590a-156">例如，如果你想要删除的文件为所有 RNIF v1.1 消息**属性**应选择 Microsoft.Solutions.BTARN.Schemas.RNIFv11.GlobalBusinessAction，并为**运算符**像选择"Exists"，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0590a-156">For example, if you want to drop files for all RNIF v1.1 messages, for **Property** you would select Microsoft.Solutions.BTARN.Schemas.RNIFv11.GlobalBusinessAction, and for **Operator** you would select "Exists", and then click **OK**.</span></span>  
  
36. <span data-ttu-id="0590a-157">在 BizTalk 浏览器中，右键单击刚创建的发送端口，单击**登记**，同样，右键单击发送端口，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="0590a-157">In BizTalk Explorer, right-click the send port that you just created, click **Enlist**, right-click the send port again, and then click **Start**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0590a-158">Remarks</span><span class="sxs-lookup"><span data-stu-id="0590a-158">Remarks</span></span>  
 <span data-ttu-id="0590a-159">在常规的处理操作中，你一次只能检查消息的一部分，即已在业务流程中指定为消息正文的部分。</span><span class="sxs-lookup"><span data-stu-id="0590a-159">In typical processing, you can only examine one of the message parts at a time (the part that you have designated as the message body in the orchestration).</span></span> <span data-ttu-id="0590a-160">因此，你只能在 BizTalk 管理控制台中检查消息的各个部分中的一个，这样，排除故障的能力就受到限制。</span><span class="sxs-lookup"><span data-stu-id="0590a-160">Therefore, you can only examine one of the parts in the BizTalk Administration Console, and your ability to troubleshoot is limited.</span></span> <span data-ttu-id="0590a-161">消息检查器管道组件可以帮助你突破此限制。</span><span class="sxs-lookup"><span data-stu-id="0590a-161">The Message Inspector Pipeline Component helps you to overcome this limitation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0590a-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="0590a-162">See Also</span></span>  
 [<span data-ttu-id="0590a-163">实用工具</span><span class="sxs-lookup"><span data-stu-id="0590a-163">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
