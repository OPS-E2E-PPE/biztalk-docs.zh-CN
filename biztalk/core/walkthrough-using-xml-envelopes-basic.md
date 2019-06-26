---
title: 演练：使用 XML 信封 （基础） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- content-based routing, promoting properties
- promoting properties, routing messages
- promoting properties, content-based routing
- routing, messages
- routing, promoting properties
ms.assetid: 02d0c596-0cfe-4bae-9f1b-d7dbc17e18a9
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f614a1400631a1bae36a1f15dc4b1f6916b45916
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279641"
---
# <a name="walkthrough-using-xml-envelopes-basic"></a><span data-ttu-id="1d2a3-102">演练：使用 XML 信封 （基础）</span><span class="sxs-lookup"><span data-stu-id="1d2a3-102">Walkthrough: Using XML Envelopes (Basic)</span></span>
<span data-ttu-id="1d2a3-103">此示例演示通过实现部分虚构的错误跟踪系统的基本 XML 信封拆装。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-103">This example demonstrates basic XML envelope disassembly by implementing part of a fictitious error-tracking system.</span></span> <span data-ttu-id="1d2a3-104">该示例要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="1d2a3-104">The example meets the following requirements:</span></span>  
  
1.  <span data-ttu-id="1d2a3-105">错误消息记录在公司内的各种物理站点，并发送到中央位置进行到各种后端系统的处理。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-105">Error messages are logged at various physical sites within the company and sent to a central location for processing into various back-end systems.</span></span>  
  
2.  <span data-ttu-id="1d2a3-106">错误消息以 XML 格式编写。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-106">Error messages are written in XML format.</span></span>  
  
3.  <span data-ttu-id="1d2a3-107">不使用信封或作为批处理包含在一个信封可以成批发送一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-107">An error message can be sent singly without an envelope or as a batch contained within an envelope.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1d2a3-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="1d2a3-108">Prerequisites</span></span>  
 <span data-ttu-id="1d2a3-109">对于此示例，您需要熟悉创建 BizTalk 项目，为程序集签名并使用 BizTalk Server 管理控制台查看应用程序和端口。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-109">For this example you need to be comfortable with creating BizTalk projects, signing an assembly, and using the BizTalk Server Administration console to view applications and ports.</span></span> <span data-ttu-id="1d2a3-110">您还应熟悉中列出的观点与[演练：部署基本 BizTalk 应用程序](../core/walkthrough-deploying-a-basic-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-110">You should also be comfortable with the ideas presented in [Walkthrough: Deploying a Basic BizTalk Application](../core/walkthrough-deploying-a-basic-biztalk-application.md).</span></span>  
  
## <a name="what-this-example-does"></a><span data-ttu-id="1d2a3-111">此示例的用途</span><span class="sxs-lookup"><span data-stu-id="1d2a3-111">What This Example Does</span></span>  
 <span data-ttu-id="1d2a3-112">示例进程的入站通过定义信封架构并使用 XmlDisassembler 管道包含单个错误消息或一批错误消息的消息。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-112">The example processes inbound messages containing either a single error message or a batch of error messages by defining an envelope schema and using the XmlDisassembler pipeline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d2a3-113">示例</span><span class="sxs-lookup"><span data-stu-id="1d2a3-113">Example</span></span>  
 <span data-ttu-id="1d2a3-114">若要创建该示例，请执行以下各节中所述的步骤。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-114">To create the example, follow the steps outlined in the following sections.</span></span>  
  
### <a name="create-a-new-biztalk-project"></a><span data-ttu-id="1d2a3-115">创建新的 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="1d2a3-115">Create a New BizTalk Project</span></span>  
 <span data-ttu-id="1d2a3-116">在生成解决方案之前需要创建 BizTalk 项目，请确保它具有强名称，并将其分配应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-116">Before building a solution you need to create a BizTalk project, ensure that it is strongly named, and assign it an application name.</span></span> <span data-ttu-id="1d2a3-117">指定应用程序名可防止 BizTalk Server 将解决方案部署到默认 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-117">Assigning an application name prevents BizTalk Server from deploying the solution into the default BizTalk application.</span></span>  
  
##### <a name="to-create-and-configure-a-new-biztalk-project"></a><span data-ttu-id="1d2a3-118">若要创建和配置新的 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="1d2a3-118">To create and configure a new BizTalk project</span></span>  
  
1. <span data-ttu-id="1d2a3-119">使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]若要创建新的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-119">Use [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to create a new BizTalk project.</span></span> <span data-ttu-id="1d2a3-120">调用项目**BasicXMLEnvelope**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-120">Call the project **BasicXMLEnvelope**.</span></span>  
  
2. <span data-ttu-id="1d2a3-121">生成密钥文件并将其分配到项目。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-121">Generate a key file and assign it to the project.</span></span> <span data-ttu-id="1d2a3-122">有关此任务的详细信息，请参阅[如何配置强名称程序集密钥文件](../core/how-to-configure-a-strong-name-assembly-key-file.md)。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-122">For more information about this task, see [How to Configure a Strong Name Assembly Key File](../core/how-to-configure-a-strong-name-assembly-key-file.md).</span></span>  
  
3. <span data-ttu-id="1d2a3-123">在项目的部署配置属性，将分配**应用程序名称**并设置**重新启动主机实例**到`True`。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-123">In the deployment configuration properties for the project, assign an **Application Name** and set **Restart Host Instances** to `True`.</span></span> <span data-ttu-id="1d2a3-124">设置此标志指示要清除的程序集的所有缓存的实例的主机。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-124">Setting this flag tells the host to clear any cached instances of the assembly.</span></span>  
  
### <a name="create-the-error-schema"></a><span data-ttu-id="1d2a3-125">创建架构时出现错误</span><span class="sxs-lookup"><span data-stu-id="1d2a3-125">Create the Error Schema</span></span>  
 <span data-ttu-id="1d2a3-126">在此步骤中创建架构时出现错误。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-126">In this step you create the Error schema.</span></span> <span data-ttu-id="1d2a3-127">它定义系统的重要消息。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-127">It defines the key message for the system.</span></span>  
  
##### <a name="to-create-the-error-schema"></a><span data-ttu-id="1d2a3-128">若要创建错误架构</span><span class="sxs-lookup"><span data-stu-id="1d2a3-128">To create the Error schema</span></span>  
  
1. <span data-ttu-id="1d2a3-129">添加到项目名称为"Error"的新架构。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-129">Add a new schema named "Error" to the project.</span></span>  
  
2. <span data-ttu-id="1d2a3-130">更改到架构的目标命名空间 **http://BasicXMLEnvelope** 。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-130">Change the target namespace for the schema to **http://BasicXMLEnvelope**.</span></span>  
  
3. <span data-ttu-id="1d2a3-131">更改架构属性**Element FormDefault**下**高级**到类别**限定**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-131">Change the schema property **Element FormDefault** under the **Advanced** category to **Qualified**.</span></span> <span data-ttu-id="1d2a3-132">这表示必须在实例文档中的目标命名空间限定本地声明的元素。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-132">This indicates that locally declared elements must be qualified by the target namespace in an instance document.</span></span>  
  
4. <span data-ttu-id="1d2a3-133">重命名根节点"Error"，并与所指示的类型创建 5 个子元素：</span><span class="sxs-lookup"><span data-stu-id="1d2a3-133">Rename the root node "Error" and create five child elements with the types indicated:</span></span>  
  
   - <span data-ttu-id="1d2a3-134">ID、 xs: int</span><span class="sxs-lookup"><span data-stu-id="1d2a3-134">ID, xs:int</span></span>  
  
   - <span data-ttu-id="1d2a3-135">类型 xs: int</span><span class="sxs-lookup"><span data-stu-id="1d2a3-135">Type, xs:int</span></span>  
  
   - <span data-ttu-id="1d2a3-136">优先级，xs: string</span><span class="sxs-lookup"><span data-stu-id="1d2a3-136">Priority, xs:string</span></span>  
  
   - <span data-ttu-id="1d2a3-137">说明，xs: string</span><span class="sxs-lookup"><span data-stu-id="1d2a3-137">Description, xs:string</span></span>  
  
   - <span data-ttu-id="1d2a3-138">ErrorDateTime，xs: string</span><span class="sxs-lookup"><span data-stu-id="1d2a3-138">ErrorDateTime, xs:string</span></span>  
  
     <span data-ttu-id="1d2a3-139">您的架构应如以下所示：</span><span class="sxs-lookup"><span data-stu-id="1d2a3-139">Your schema should look like the following:</span></span>  
  
     <span data-ttu-id="1d2a3-140">![架构已完成时出现错误](../core/media/error-schema.gif "error_schema")</span><span class="sxs-lookup"><span data-stu-id="1d2a3-140">![Completed Error schema](../core/media/error-schema.gif "error_schema")</span></span>  
  
5. <span data-ttu-id="1d2a3-141">创建此架构的示例消息。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-141">Create a sample message for this schema.</span></span> <span data-ttu-id="1d2a3-142">这用于验证对信封外的单个消息处理正确。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-142">This is used to verify that single messages outside of an envelope are processed properly.</span></span> <span data-ttu-id="1d2a3-143">是一个示例消息：</span><span class="sxs-lookup"><span data-stu-id="1d2a3-143">An example sample message is:</span></span>  
  
   ```  
   <Error xmlns="http://BasicXMLEnvelope">  
     <ID>1</ID>  
     <Type>5</Type>  
     <Priority>Low</Priority>  
     <Description>Sprocket widget prints reports slowly.</Description>  
     <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
   </Error>  
   ```  
  
    <span data-ttu-id="1d2a3-144">将此消息保存在项目目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-144">Save this message in a file in the project directory.</span></span>  
  
### <a name="create-the-envelope-schema"></a><span data-ttu-id="1d2a3-145">创建信封架构</span><span class="sxs-lookup"><span data-stu-id="1d2a3-145">Create the Envelope Schema</span></span>  
 <span data-ttu-id="1d2a3-146">信封包含一个或多个错误消息。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-146">The envelope contains one or more error messages.</span></span> <span data-ttu-id="1d2a3-147">在此基本示例中，信封没有自己的属性和元素。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-147">In this basic example, the envelope does not have properties and elements of its own.</span></span>  
  
##### <a name="to-create-the-envelope-schema"></a><span data-ttu-id="1d2a3-148">若要创建信封架构</span><span class="sxs-lookup"><span data-stu-id="1d2a3-148">To create the envelope schema</span></span>  
  
1.  <span data-ttu-id="1d2a3-149">添加到 BasicXMLEnvelope 项目名称为"Envelope"的新架构。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-149">Add a new schema named "Envelope" to the BasicXMLEnvelope project.</span></span>  
  
2.  <span data-ttu-id="1d2a3-150">更改到的目标命名空间 **http://BasicXMLEnvelope** 。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-150">Change the target namespace to **http://BasicXMLEnvelope**.</span></span>  
  
3.  <span data-ttu-id="1d2a3-151">更改从"Root"改为"Envelope"的根节点名称。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-151">Change the name of the root node from "Root" to "Envelope".</span></span>  
  
4.  <span data-ttu-id="1d2a3-152">现在将此架构标记为信封架构。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-152">Now mark the schema as an envelope schema.</span></span> <span data-ttu-id="1d2a3-153">单击 **\<架构\>** 节点。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-153">Click the **\<Schema\>** node.</span></span> <span data-ttu-id="1d2a3-154">在属性窗格中，将架构引用属性设置**信封**到`OK`。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-154">In the Properties pane, set the schema reference property **Envelope** to `OK`.</span></span>  
  
5.  <span data-ttu-id="1d2a3-155">设置**正文 XPath**属性。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-155">Set the **Body XPath** property.</span></span> <span data-ttu-id="1d2a3-156">若要执行此操作，请单击**信封**节点。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-156">To do this, click the **Envelope** node.</span></span> <span data-ttu-id="1d2a3-157">在属性窗口中，单击省略号 ( **...** ) 按钮**正文 XPath**属性中，选择**信封**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-157">In the Properties window, click the ellipsis (**...**) button in the **Body XPath** property, select **Envelope**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="1d2a3-158">向 Envelope 节点中添加任何元素子级。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-158">Add an Any element child to the Envelope node.</span></span> <span data-ttu-id="1d2a3-159">将此元素中包含错误消息。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-159">The error message will be contained in this element.</span></span> <span data-ttu-id="1d2a3-160">您的架构应如以下所示：</span><span class="sxs-lookup"><span data-stu-id="1d2a3-160">Your schema should look like the following:</span></span>  
  
     <span data-ttu-id="1d2a3-161">![已完成的信封架构](../core/media/envelope-schema.gif "envelope_schema")</span><span class="sxs-lookup"><span data-stu-id="1d2a3-161">![Completed envelope schema](../core/media/envelope-schema.gif "envelope_schema")</span></span>  
  
7.  <span data-ttu-id="1d2a3-162">创建包含一个信封、 一个或多个示例消息的示例消息。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-162">Create a sample message containing an envelope and one or more sample messages.</span></span> <span data-ttu-id="1d2a3-163">示例消息为：</span><span class="sxs-lookup"><span data-stu-id="1d2a3-163">An example message is:</span></span>  
  
    ```  
    <Envelope xmlns="http://BasicXMLEnvelope">  
      <Error>  
        <ID>102</ID>  
        <Type>0</Type>  
        <Priority>High</Priority>  
        <Description>Sprocket query fails.</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
      <Error>  
        <ID>16502</ID>  
        <Type>2</Type>  
        <Priority>Low</Priority>  
        <Description>Time threshold exceeded.</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
    </Envelope>  
    ```  
  
     <span data-ttu-id="1d2a3-164">将此消息保存在项目目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-164">Save this message in a file in the project directory.</span></span>  
  
### <a name="deploy-and-configure-the-send-and-receive-ports"></a><span data-ttu-id="1d2a3-165">部署并配置发送和接收端口</span><span class="sxs-lookup"><span data-stu-id="1d2a3-165">Deploy and Configure the Send and Receive Ports</span></span>  
 <span data-ttu-id="1d2a3-166">创建架构后，您需要编译和部署项目。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-166">With the schemas created, you need to compile and deploy the project.</span></span> <span data-ttu-id="1d2a3-167">在部署后，可以使用 BizTalk Server 管理控制台来配置发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-167">After it is deployed, you can use the BizTalk Server Administration console to configure the send and receive ports.</span></span>  
  
##### <a name="to-deploy-basicxmlenvelope"></a><span data-ttu-id="1d2a3-168">若要部署 BasicXMLEnvelope</span><span class="sxs-lookup"><span data-stu-id="1d2a3-168">To deploy BasicXMLEnvelope</span></span>  
  
1. <span data-ttu-id="1d2a3-169">从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，选择**部署 BasicXMLEnvelope**从生成菜单。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-169">From [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], choose **Deploy BasicXMLEnvelope** from the Build menu.</span></span> <span data-ttu-id="1d2a3-170">这将生成并将其部署到 BizTalk Server，作为应用程序"BasicXMLEnvelope"。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-170">This will build and deploy it to BizTalk Server as the application "BasicXMLEnvelope".</span></span>  
  
2. <span data-ttu-id="1d2a3-171">在 BizTalk Server 管理控制台中，展开**应用程序**组，以验证**BasicXMLEnvelope**是显示为自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-171">In the BizTalk Server Administration console, expand the **Applications** group to verify that **BasicXMLEnvelope** is present as a custom application.</span></span>  
  
##### <a name="to-configure-the-receive-port"></a><span data-ttu-id="1d2a3-172">若要配置接收端口</span><span class="sxs-lookup"><span data-stu-id="1d2a3-172">To configure the receive port</span></span>  
  
1.  <span data-ttu-id="1d2a3-173">使用 Windows 资源管理器下创建一个名为"Receive"目录**BasicXMLEnvelope**项目目录。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-173">Use Windows Explorer to create a directory named "Receive" under the **BasicXMLEnvelope** project directory.</span></span>  
  
2.  <span data-ttu-id="1d2a3-174">在 BizTalk Server 管理控制台中，展开**BasicXMLEnvelope**应用程序中，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-174">In the BizTalk Server Administration console, expand the **BasicXMLEnvelope** application, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
3.  <span data-ttu-id="1d2a3-175">在中**接收端口属性**对话框框中，设置为"Receive"的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-175">In the **Receive Port Properties** dialog box, set the name of the port to "Receive".</span></span>  
  
4.  <span data-ttu-id="1d2a3-176">右键单击接收位置，然后单击**新建**添加接收端口。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-176">Right-click Receive Locations, and then click **New** to add a receive port.</span></span> <span data-ttu-id="1d2a3-177">新的端口"为 ReceiveError"的名称。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-177">Name the new port "ReceiveError".</span></span> <span data-ttu-id="1d2a3-178">设置**接收管道**到**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-178">Set the **Receive Pipeline** to **XMLReceive**.</span></span> <span data-ttu-id="1d2a3-179">有关**传输类型**，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-179">For **Transport Type**, select **FILE**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="1d2a3-180">选择上面创建的接收目录，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-180">Select the receive directory created above and click **OK**.</span></span> <span data-ttu-id="1d2a3-181">在接收端口应现在已配置。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-181">Your receive port should now be configured.</span></span> <span data-ttu-id="1d2a3-182">单击**确定**关闭。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-182">Click **OK** to close.</span></span>  
  
##### <a name="to-configure-the-send-port"></a><span data-ttu-id="1d2a3-183">若要配置的发送端口</span><span class="sxs-lookup"><span data-stu-id="1d2a3-183">To configure the send port</span></span>  
  
1.  <span data-ttu-id="1d2a3-184">使用 Windows 资源管理器下创建一个名为"发送" **BasicXMLEnvelope**项目目录。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-184">Use Windows Explorer to create a directory named "Send" under the **BasicXMLEnvelope** project directory.</span></span>  
  
2.  <span data-ttu-id="1d2a3-185">在 BizTalk Server 管理控制台中，展开**BasicXMLEnvelope**应用程序中，右键单击**发送端口**，指向**新建**，然后单击**静态单向**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-185">In the BizTalk Server Administration console, expand the **BasicXMLEnvelope** application, right-click **Send Ports**, point to **New**, and then click **Static One-Way**.</span></span>  
  
3.  <span data-ttu-id="1d2a3-186">在中**发送端口属性**对话框框中，设置为"Send"的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-186">In the **Send Port Properties** dialog box, set the name of the port to "Send".</span></span>  
  
4.  <span data-ttu-id="1d2a3-187">有关**传输类型**，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-187">For **Transport Type**, select **FILE**, and then click **Configure**.</span></span> <span data-ttu-id="1d2a3-188">目标文件夹设置为前面创建的发送目录，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-188">Set the destination folder to the send directory you created earlier and click **OK**.</span></span>  
  
5.  <span data-ttu-id="1d2a3-189">单击**筛选器**并添加一个筛选器：</span><span class="sxs-lookup"><span data-stu-id="1d2a3-189">Click **Filters** and add a single filter:</span></span>  
  
    -   <span data-ttu-id="1d2a3-190">BTS.MessageType == **http://BasicXMLEnvelope#Error**</span><span class="sxs-lookup"><span data-stu-id="1d2a3-190">BTS.MessageType == **http://BasicXMLEnvelope#Error**</span></span>  
  
6.  <span data-ttu-id="1d2a3-191">单击**确定**完成发送端口配置。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-191">Click **OK** to complete the send port configuration.</span></span> <span data-ttu-id="1d2a3-192">应配置您的发送端口。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-192">Your send port should be configured.</span></span>  
  
### <a name="run-the-example"></a><span data-ttu-id="1d2a3-193">运行示例</span><span class="sxs-lookup"><span data-stu-id="1d2a3-193">Run the Example</span></span>  
 <span data-ttu-id="1d2a3-194">它现在是要运行该示例的时间。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-194">It is now time to run the example.</span></span> <span data-ttu-id="1d2a3-195">使用 BizTalk Server 管理控制台启动 BasicXMLEnvelope 应用程序之后, 将测试文件复制到接收位置，并观察在发送位置生成的内容。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-195">After using the BizTalk Server Management console to start the BasicXMLEnvelope application, you will copy the test files to the receive location and observe what is produced in the send location.</span></span>  
  
##### <a name="to-run-the-basicxmlenvelope-example"></a><span data-ttu-id="1d2a3-196">若要运行 BasicXMLEnvelope 示例</span><span class="sxs-lookup"><span data-stu-id="1d2a3-196">To run the BasicXMLEnvelope example</span></span>  
  
1.  <span data-ttu-id="1d2a3-197">在 BizTalk Server 管理控制台中，右键单击**BasicXMLEnvelope**应用程序，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-197">In the BizTalk Server Administration console, right-click the **BasicXMLEnvelope** application and then click **Start**.</span></span> <span data-ttu-id="1d2a3-198">这将登记并启动发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-198">This will enlist and start the send and receive ports.</span></span>  
  
2.  <span data-ttu-id="1d2a3-199">放入接收目录中的每个示例文件。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-199">Drop each of the sample files into the receive directory.</span></span> <span data-ttu-id="1d2a3-200">如果您使用前面给出的示例，应完成处理后发送位置找到三个单独的错误消息。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-200">If you use the samples given earlier, you should find three individual error messages in the send location when processing is completed.</span></span>  
  
## <a name="extending-the-example"></a><span data-ttu-id="1d2a3-201">扩展示例</span><span class="sxs-lookup"><span data-stu-id="1d2a3-201">Extending the Example</span></span>  
 <span data-ttu-id="1d2a3-202">您可以扩展该示例以满足其他要求。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-202">You can extend the example to accommodate other requirements.</span></span> <span data-ttu-id="1d2a3-203">本部分解决了两种常见方案：</span><span class="sxs-lookup"><span data-stu-id="1d2a3-203">This section addresses two common scenarios:</span></span>  
  
- <span data-ttu-id="1d2a3-204">如果在一个信封提交一批错误时，单个消息失败的反汇编应不会妨碍其他无错误消息进一步处理。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-204">If a batch of errors is submitted within an envelope, individual message failures in disassembly should not prohibit other nonfailing messages from being further processed.</span></span>  
  
- <span data-ttu-id="1d2a3-205">错误应传递到不同的位置根据错误优先级。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-205">Errors should be delivered to different locations based on error priority.</span></span> <span data-ttu-id="1d2a3-206">而其他优先级的处理按照常规方式将加快高优先级的消息。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-206">High-priority messages are expedited while other priorities are handled through normal channels.</span></span>  
  
  <span data-ttu-id="1d2a3-207">以下各节将扩展以处理这些要求的示例。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-207">The following sections extend the example to handle these requirements.</span></span>  
  
### <a name="recoverable-interchange-processing"></a><span data-ttu-id="1d2a3-208">可恢复交换处理</span><span class="sxs-lookup"><span data-stu-id="1d2a3-208">Recoverable Interchange Processing</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="1d2a3-209">支持可恢复交换处理。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-209">supports recoverable interchange processing.</span></span> <span data-ttu-id="1d2a3-210">通过使用此功能，可以确保消息批的拆装和不是作为一批单独故障。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-210">By using this feature, you can ensure that batches of messages fail individually in disassembly and not as a batch.</span></span>  
  
##### <a name="to-configure-the-example-for-recoverable-interchange-processing"></a><span data-ttu-id="1d2a3-211">若要配置可恢复交换处理的示例</span><span class="sxs-lookup"><span data-stu-id="1d2a3-211">To configure the example for recoverable interchange processing</span></span>  
  
1.  <span data-ttu-id="1d2a3-212">在 BizTalk Server 管理控制台中，展开**BasicXMLEnvelope**应用程序中，单击**接收端口**，然后双击接收端口。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-212">In the BizTalk Server Administration console, expand the **BasicXMLEnvelope** application, click **Receive Ports**, and then double-click the Receive port.</span></span> <span data-ttu-id="1d2a3-213">这是你之前创建的端口。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-213">This is the port you created previously.</span></span>  
  
2.  <span data-ttu-id="1d2a3-214">在中**接收端口属性**对话框中，单击**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-214">In the **Receive Port Properties** dialog box, click **Receive Locations**.</span></span> <span data-ttu-id="1d2a3-215">单击**属性**以打开**ReceiveError 接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-215">Click **Properties** to bring up the **ReceiveError Receive Location Properties** dialog box.</span></span> <span data-ttu-id="1d2a3-216">单击省略号 ( **...** ) 按钮**接收管道**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-216">Click the ellipsis (**...**) button for the **Receive Pipeline**.</span></span>  
  
3.  <span data-ttu-id="1d2a3-217">在中**配置管道-XMLReceive**对话框中，将**可恢复交换处理**属性设置为`True`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-217">In the **Configure Pipeline - XMLReceive** dialog box, set the **Recoverable Interchange Processing** property to `True`, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="1d2a3-218">单击**确定**以关闭**接收位置属性**对话框中，然后单击**确定**以关闭**接收端口属性**对话框框。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-218">Click **OK** to close the **Receive Location Properties** dialog box, and then click **OK** to close the **Receive Port Properties** dialog box.</span></span>  
  
##### <a name="to-create-a-sample-file-and-run-the-example"></a><span data-ttu-id="1d2a3-219">若要创建示例文件并运行示例</span><span class="sxs-lookup"><span data-stu-id="1d2a3-219">To create a sample file and run the example</span></span>  
  
1.  <span data-ttu-id="1d2a3-220">若要创建示例文件，制作一份示例中创建的信封示例文件，将不存在命名空间添加到其中一个错误实例中，然后保存该文件：</span><span class="sxs-lookup"><span data-stu-id="1d2a3-220">To create a sample file, make a copy of the envelope sample file created in the example, add a nonexistent namespace to one of the Error instances, and then save the file:</span></span>  
  
    ```  
    <Envelope xmlns="http://BasicXMLEnvelope">  
      <Error>  
        <ID>102</ID>  
        <Type>0</Type>  
        <Priority>High</Priority>  
        <Description>Sprocket query fails to return any sprockets even though some exist</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
      <Error xmlns="http://ThisIsAnError">  
        <ID>16502</ID>  
        <Type>2</Type>  
        <Priority>Low</Priority>  
        <Description>Time threshold exceeded.</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
    </Envelope>  
    ```  
  
2.  <span data-ttu-id="1d2a3-221">在 BizTalk Server 管理控制台中，单击**应用程序**并确认**BasicXMLEnvelope**运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-221">In the BizTalk Server Administration console, click **Applications** and verify that the **BasicXMLEnvelope** application is running.</span></span>  
  
3.  <span data-ttu-id="1d2a3-222">该消息放入接收位置。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-222">Drop the message in the receive location.</span></span> <span data-ttu-id="1d2a3-223">在处理后，应在发送位置和挂起队列中的第二个、 低优先级消息中找到的第一个消息。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-223">After processing, you should find the first message in the send location and the second, low-priority, message in the Suspended queue.</span></span>  
  
### <a name="content-based-routing-cbr"></a><span data-ttu-id="1d2a3-224">基于内容的路由 (CBR)</span><span class="sxs-lookup"><span data-stu-id="1d2a3-224">Content-Based Routing (CBR)</span></span>  
 <span data-ttu-id="1d2a3-225">可以使用基于内容的路由来路由消息根据其内容。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-225">You can use content-based routing to route messages based on their content.</span></span> <span data-ttu-id="1d2a3-226">在此方案中，路由基于优先级，具有高消息路由到一个发送位置和低和中的消息路由到不同的发送位置。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-226">In this scenario, routing is based on priority, with High messages going to one send location and Low and Medium messages going to a different send location.</span></span>  
  
 <span data-ttu-id="1d2a3-227">若要扩展该示例，必须完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="1d2a3-227">To extend the sample, you must complete the following tasks:</span></span>  
  
1.  <span data-ttu-id="1d2a3-228">将提升**优先级**字段 BasicXMLEnvelope 项目中的错误架构中。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-228">Promote the **Priority** field in the Error schema in the BasicXMLEnvelope project.</span></span> <span data-ttu-id="1d2a3-229">基于内容的路由都依赖于将消息路由到已升级属性。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-229">Content-based routing relies on promoted properties to route messages.</span></span> <span data-ttu-id="1d2a3-230">有关详细信息，请参阅[升级属性](../core/promoting-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-230">For more information, see [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
2.  <span data-ttu-id="1d2a3-231">创建并配置两个其他发送端口。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-231">Create and configure two additional send ports.</span></span> <span data-ttu-id="1d2a3-232">端口使用筛选器来确保其接收相应的消息。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-232">The ports use a filter to ensure they receive appropriate messages.</span></span>  
  
##### <a name="to-promote-the-priority-field-in-the-error-schema"></a><span data-ttu-id="1d2a3-233">若要升级错误架构中的优先级字段</span><span class="sxs-lookup"><span data-stu-id="1d2a3-233">To promote the Priority field in the Error schema</span></span>  
  
1. <span data-ttu-id="1d2a3-234">与**BasicXMLEnvelope**中打开项目[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开**错误**架构和展开**错误**节点。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-234">With the **BasicXMLEnvelope** project open in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the **Error** schema and expand the **Error** node.</span></span>  
  
2. <span data-ttu-id="1d2a3-235">右键单击**优先级**元素，指向**Promote**，然后单击**Quick Promote**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-235">Right-click the **Priority** element, point to **Promote**, and then click **Quick Promote**.</span></span>  
  
3. <span data-ttu-id="1d2a3-236">单击**确定**以确认添加的新属性架构的已升级属性。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-236">Click **OK** to confirm the addition of a new property schema for the promoted properties.</span></span>  
  
4. <span data-ttu-id="1d2a3-237">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器中打开新的属性架构 PropertySchema.xsd。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-237">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], in Solution Explorer, open the new property schema PropertySchema.xsd.</span></span> <span data-ttu-id="1d2a3-238">从架构中删除"Field1"。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-238">Remove "Field1" from the schema.</span></span>  
  
5. <span data-ttu-id="1d2a3-239">现在重新编译和重新部署解决方案。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-239">Now recompile and redeploy the solution.</span></span> <span data-ttu-id="1d2a3-240">在生成菜单上选择部署 BasicXMLEnvelope。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-240">On the Build menu, choose Deploy BasicXMLEnvelope.</span></span>  
  
6. <span data-ttu-id="1d2a3-241">该项目已配置为重新部署解决方案时重置主机实例。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-241">The project was configured to reset the host instance when the solution is redeployed.</span></span> <span data-ttu-id="1d2a3-242">如果已更改此，需要停止并重新启动主机。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-242">If you have changed this, you need to stop and start the host.</span></span>  
  
##### <a name="to-configure-the-low-and-medium-priority-send-port"></a><span data-ttu-id="1d2a3-243">若要配置的低和中优先级发送端口</span><span class="sxs-lookup"><span data-stu-id="1d2a3-243">To configure the low and medium-priority send port</span></span>  
  
1.  <span data-ttu-id="1d2a3-244">使用 Windows 资源管理器下创建名为"SendLowMediumPriority"的目录**BasicXMLEnvelope**项目目录。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-244">Use Windows Explorer to create a directory named "SendLowMediumPriority" under the **BasicXMLEnvelope** project directory.</span></span>  
  
2.  <span data-ttu-id="1d2a3-245">在 BizTalk Server 管理控制台中，展开**BasicXMLEnvelope**应用程序中，右键单击**发送端口**，指向**新建**，然后单击**静态单向**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-245">In the BizTalk Server Administration console, expand the **BasicXMLEnvelope** application, right-click **Send Ports**, point to **New**, and then click **Static One-Way**.</span></span>  
  
3.  <span data-ttu-id="1d2a3-246">在中**发送端口属性**对话框框中，设置为"SendLowMediumPriority"的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-246">In the **Send Port Properties** dialog box, set the name of the port to "SendLowMediumPriority".</span></span>  
  
4.  <span data-ttu-id="1d2a3-247">有关**传输类型**，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-247">For **Transport Type**, select **FILE**, and then click **Configure**.</span></span> <span data-ttu-id="1d2a3-248">将目标文件夹设置为前面创建的目录。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-248">Set the destination folder to the directory you created earlier.</span></span> <span data-ttu-id="1d2a3-249">单击**确定**关闭。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-249">Click **OK** to close.</span></span>  
  
5.  <span data-ttu-id="1d2a3-250">单击**筛选器**然后添加三个筛选器表达式：</span><span class="sxs-lookup"><span data-stu-id="1d2a3-250">Click **Filters** and add three filter expressions:</span></span>  
  
    -   <span data-ttu-id="1d2a3-251">BTS。MessageType == http://BasicXMLEnvelope#Error 和</span><span class="sxs-lookup"><span data-stu-id="1d2a3-251">BTS.MessageType == http://BasicXMLEnvelope#Error And</span></span>  
  
    -   <span data-ttu-id="1d2a3-252">BasicXMLEnvelope.PropertySchema.Priority == Low Or</span><span class="sxs-lookup"><span data-stu-id="1d2a3-252">BasicXMLEnvelope.PropertySchema.Priority == Low Or</span></span>  
  
    -   <span data-ttu-id="1d2a3-253">BasicXMLEnvelope.PropertySchema.Priority == Medium</span><span class="sxs-lookup"><span data-stu-id="1d2a3-253">BasicXMLEnvelope.PropertySchema.Priority == Medium</span></span>  
  
6.  <span data-ttu-id="1d2a3-254">单击**确定**，完成低和中优先级发送端口配置。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-254">Click **OK** to complete the low and medium-priority send port configuration.</span></span>  
  
##### <a name="to-configure-the-high-priority-send-port"></a><span data-ttu-id="1d2a3-255">若要配置高优先级发送端口</span><span class="sxs-lookup"><span data-stu-id="1d2a3-255">To configure the high-priority send port</span></span>  
  
1.  <span data-ttu-id="1d2a3-256">使用 Windows 资源管理器下创建名为"SendHighPriority"的目录**BasicXMLEnvelope**项目目录。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-256">Use Windows Explorer to create a directory named "SendHighPriority" under the **BasicXMLEnvelope** project directory.</span></span>  
  
2.  <span data-ttu-id="1d2a3-257">在 BizTalk Server 管理控制台中，展开**BasicXMLEnvelope**应用程序中，右键单击**发送端口**，指向**新建**，然后单击**静态单向**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-257">In the BizTalk Server Administration console, expand the **BasicXMLEnvelope** application, right-click **Send Ports**, point to **New**, and then click **Static One-Way**.</span></span>  
  
3.  <span data-ttu-id="1d2a3-258">在中**发送端口属性**对话框框中，设置为"SendHighPriority"的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-258">In the **Send Port Properties** dialog box, set the name of the port to "SendHighPriority".</span></span>  
  
4.  <span data-ttu-id="1d2a3-259">有关**传输类型**，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-259">For **Transport Type**, select **FILE**, and then click **Configure**.</span></span> <span data-ttu-id="1d2a3-260">将目标文件夹设置为前面创建的目录。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-260">Set the destination folder to the directory you created earlier.</span></span> <span data-ttu-id="1d2a3-261">单击**确定**关闭。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-261">Click **OK** to close.</span></span>  
  
5.  <span data-ttu-id="1d2a3-262">单击**筛选器**和添加两个筛选器表达式：</span><span class="sxs-lookup"><span data-stu-id="1d2a3-262">Click **Filters** and add two filter expressions:</span></span>  
  
    -   <span data-ttu-id="1d2a3-263">BTS。MessageType == http://BasicXMLEnvelope#Error 和</span><span class="sxs-lookup"><span data-stu-id="1d2a3-263">BTS.MessageType == http://BasicXMLEnvelope#Error And</span></span>  
  
    -   <span data-ttu-id="1d2a3-264">BasicXMLEnvelope.PropertySchema.Priority == High</span><span class="sxs-lookup"><span data-stu-id="1d2a3-264">BasicXMLEnvelope.PropertySchema.Priority == High</span></span>  
  
6.  <span data-ttu-id="1d2a3-265">单击**确定**完成高优先级发送端口配置。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-265">Click **OK** to complete the high-priority send port configuration.</span></span>  
  
##### <a name="to-test-the-routing-solution"></a><span data-ttu-id="1d2a3-266">若要测试路由解决方案</span><span class="sxs-lookup"><span data-stu-id="1d2a3-266">To test the routing solution</span></span>  
  
1.  <span data-ttu-id="1d2a3-267">在 BizTalk Server 管理控制台中，展开**应用程序**组中，右键单击**BasicXMLEnvelope**应用程序，，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-267">In the BizTalk Server Administration console, expand the **Applications** group, right-click the **BasicXMLEnvelope** application, and then click **Start**.</span></span> <span data-ttu-id="1d2a3-268">当系统提示你确认，单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-268">When prompted to confirm, click **Start**.</span></span> <span data-ttu-id="1d2a3-269">这将登记新发送端口。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-269">This enlists the new send ports.</span></span>  
  
2.  <span data-ttu-id="1d2a3-270">测试消息放入接收位置。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-270">Drop the test message into the receive location.</span></span> <span data-ttu-id="1d2a3-271">请注意如何将错误消息路由到不同的发送位置：</span><span class="sxs-lookup"><span data-stu-id="1d2a3-271">Notice how error messages are routed to the different send locations:</span></span>  
  
    -   <span data-ttu-id="1d2a3-272">具有低、 中或高优先级和消息处理没有失败的错误消息被路由到原始发送位置 （在核心示例中配置） 和发送位置两个按优先级别。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-272">Error messages that have a Low, Medium, or High priority and do not fail message processing are routed both to the original send location (configured in the core example) and the send location by priority.</span></span> <span data-ttu-id="1d2a3-273">对于具有较低或中等优先级的消息，副本会显示在原始发送位置和低/中发送位置中。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-273">For messages with a Low or Medium priority, a copy appears in both the original send location and the Low/Medium send location.</span></span>  
  
    -   <span data-ttu-id="1d2a3-274">如果启用可恢复交换处理，则不会路由失败的错误消息，并按预期正确路由没有失败的消息。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-274">If recoverable interchange processing is enabled, the failed error message is not routed and the nonfailed message is properly routed as expected.</span></span> <span data-ttu-id="1d2a3-275">因为其消息类型不匹配的已配置的筛选器中使用的类型，不路由失败的消息。</span><span class="sxs-lookup"><span data-stu-id="1d2a3-275">The failed message is not routed because its message type does not match the type used in the configured filters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d2a3-276">请参阅</span><span class="sxs-lookup"><span data-stu-id="1d2a3-276">See Also</span></span>  
 <span data-ttu-id="1d2a3-277">[可恢复交换处理](../core/recoverable-interchange-processing.md) </span><span class="sxs-lookup"><span data-stu-id="1d2a3-277">[Recoverable Interchange Processing](../core/recoverable-interchange-processing.md) </span></span>  
 <span data-ttu-id="1d2a3-278">[升级属性](../core/promoting-properties.md) </span><span class="sxs-lookup"><span data-stu-id="1d2a3-278">[Promoting Properties](../core/promoting-properties.md) </span></span>  
 [<span data-ttu-id="1d2a3-279">CBRSample（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="1d2a3-279">CBRSample (BizTalk Server Sample)</span></span>](../core/cbrsample-biztalk-server-sample.md)