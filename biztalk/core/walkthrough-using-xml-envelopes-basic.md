---
title: 演练： 使用 XML 信封 （基础） |Microsoft Docs
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
ms.openlocfilehash: 2b637f37c8d0953417ca628204fe299318b91266
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022091"
---
# <a name="walkthrough-using-xml-envelopes-basic"></a><span data-ttu-id="5ad88-102">演练： 使用 XML 信封 （基础）</span><span class="sxs-lookup"><span data-stu-id="5ad88-102">Walkthrough: Using XML Envelopes (Basic)</span></span>
<span data-ttu-id="5ad88-103">本示例通过实现部分虚构的错误跟踪系统来演示基本的 XML 信封拆装。</span><span class="sxs-lookup"><span data-stu-id="5ad88-103">This example demonstrates basic XML envelope disassembly by implementing part of a fictitious error-tracking system.</span></span> <span data-ttu-id="5ad88-104">该示例要满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="5ad88-104">The example meets the following requirements:</span></span>  
  
1.  <span data-ttu-id="5ad88-105">错误消息记录在公司内部不同的物理地点，并发送到一个中央位置，供各种后端系统进行处理。</span><span class="sxs-lookup"><span data-stu-id="5ad88-105">Error messages are logged at various physical sites within the company and sent to a central location for processing into various back-end systems.</span></span>  
  
2.  <span data-ttu-id="5ad88-106">错误信息以 XML 格式编写。</span><span class="sxs-lookup"><span data-stu-id="5ad88-106">Error messages are written in XML format.</span></span>  
  
3.  <span data-ttu-id="5ad88-107">可不用信封就将错误消息发送出去，也可以包含在一个信封中，成批发送出去。</span><span class="sxs-lookup"><span data-stu-id="5ad88-107">An error message can be sent singly without an envelope or as a batch contained within an envelope.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5ad88-108">必要條件</span><span class="sxs-lookup"><span data-stu-id="5ad88-108">Prerequisites</span></span>  
 <span data-ttu-id="5ad88-109">对于本示例，您需要熟悉以下操作：创建 BizTalk 项目、签署程序集、使用 BizTalk Server 管理控制台查看应用程序和端口。</span><span class="sxs-lookup"><span data-stu-id="5ad88-109">For this example you need to be comfortable with creating BizTalk projects, signing an assembly, and using the BizTalk Server Administration console to view applications and ports.</span></span> <span data-ttu-id="5ad88-110">您还应熟悉与中列出的观点[演练： 部署基本 BizTalk 应用程序](../core/walkthrough-deploying-a-basic-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="5ad88-110">You should also be comfortable with the ideas presented in [Walkthrough: Deploying a Basic BizTalk Application](../core/walkthrough-deploying-a-basic-biztalk-application.md).</span></span>  
  
## <a name="what-this-example-does"></a><span data-ttu-id="5ad88-111">此示例的用途</span><span class="sxs-lookup"><span data-stu-id="5ad88-111">What This Example Does</span></span>  
 <span data-ttu-id="5ad88-112">该示例通过定义一个信封架构并使用 XmlDisassembler 管道来处理包含单个错误消息或一批错误消息的入站消息。</span><span class="sxs-lookup"><span data-stu-id="5ad88-112">The example processes inbound messages containing either a single error message or a batch of error messages by defining an envelope schema and using the XmlDisassembler pipeline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ad88-113">示例</span><span class="sxs-lookup"><span data-stu-id="5ad88-113">Example</span></span>  
 <span data-ttu-id="5ad88-114">若要创建该示例，请按照下述步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="5ad88-114">To create the example, follow the steps outlined in the following sections.</span></span>  
  
### <a name="create-a-new-biztalk-project"></a><span data-ttu-id="5ad88-115">创建新 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="5ad88-115">Create a New BizTalk Project</span></span>  
 <span data-ttu-id="5ad88-116">生成解决方案前，需要先创建一个 BizTalk 项目，确保要对其进行强命名，并为其指定一个应用程序名。</span><span class="sxs-lookup"><span data-stu-id="5ad88-116">Before building a solution you need to create a BizTalk project, ensure that it is strongly named, and assign it an application name.</span></span> <span data-ttu-id="5ad88-117">指定应用程序名可防止 BizTalk Server 将该解决方案部署到默认 BizTalk 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="5ad88-117">Assigning an application name prevents BizTalk Server from deploying the solution into the default BizTalk application.</span></span>  
  
##### <a name="to-create-and-configure-a-new-biztalk-project"></a><span data-ttu-id="5ad88-118">创建并配置新的 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="5ad88-118">To create and configure a new BizTalk project</span></span>  
  
1. <span data-ttu-id="5ad88-119">使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]若要创建新的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="5ad88-119">Use [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to create a new BizTalk project.</span></span> <span data-ttu-id="5ad88-120">调用项目**BasicXMLEnvelope**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-120">Call the project **BasicXMLEnvelope**.</span></span>  
  
2. <span data-ttu-id="5ad88-121">生成密钥文件，并将其分配给该项目。</span><span class="sxs-lookup"><span data-stu-id="5ad88-121">Generate a key file and assign it to the project.</span></span> <span data-ttu-id="5ad88-122">有关此任务的详细信息，请参阅[如何配置强名称程序集密钥文件](../core/how-to-configure-a-strong-name-assembly-key-file.md)。</span><span class="sxs-lookup"><span data-stu-id="5ad88-122">For more information about this task, see [How to Configure a Strong Name Assembly Key File](../core/how-to-configure-a-strong-name-assembly-key-file.md).</span></span>  
  
3. <span data-ttu-id="5ad88-123">在项目的部署配置属性，将分配**应用程序名称**并设置**重新启动主机实例**到`True`。</span><span class="sxs-lookup"><span data-stu-id="5ad88-123">In the deployment configuration properties for the project, assign an **Application Name** and set **Restart Host Instances** to `True`.</span></span> <span data-ttu-id="5ad88-124">设置此标志的作用是通知主机清除该程序集的所有缓存的实例。</span><span class="sxs-lookup"><span data-stu-id="5ad88-124">Setting this flag tells the host to clear any cached instances of the assembly.</span></span>  
  
### <a name="create-the-error-schema"></a><span data-ttu-id="5ad88-125">创建架构时出现错误</span><span class="sxs-lookup"><span data-stu-id="5ad88-125">Create the Error Schema</span></span>  
 <span data-ttu-id="5ad88-126">在此步骤中，您将创建 Error（错误）架构。</span><span class="sxs-lookup"><span data-stu-id="5ad88-126">In this step you create the Error schema.</span></span> <span data-ttu-id="5ad88-127">该架构定义系统的重要消息。</span><span class="sxs-lookup"><span data-stu-id="5ad88-127">It defines the key message for the system.</span></span>  
  
##### <a name="to-create-the-error-schema"></a><span data-ttu-id="5ad88-128">若要创建错误架构</span><span class="sxs-lookup"><span data-stu-id="5ad88-128">To create the Error schema</span></span>  
  
1. <span data-ttu-id="5ad88-129">向项目中添加名称为“Error”的新架构。</span><span class="sxs-lookup"><span data-stu-id="5ad88-129">Add a new schema named "Error" to the project.</span></span>  
  
2. <span data-ttu-id="5ad88-130">更改到架构的目标命名空间**http://BasicXMLEnvelope**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-130">Change the target namespace for the schema to **http://BasicXMLEnvelope**.</span></span>  
  
3. <span data-ttu-id="5ad88-131">更改架构属性**Element FormDefault**下**高级**到类别**限定**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-131">Change the schema property **Element FormDefault** under the **Advanced** category to **Qualified**.</span></span> <span data-ttu-id="5ad88-132">这指明本地声明的元素必须受到实例文档中的目标命名空间的限定。</span><span class="sxs-lookup"><span data-stu-id="5ad88-132">This indicates that locally declared elements must be qualified by the target namespace in an instance document.</span></span>  
  
4. <span data-ttu-id="5ad88-133">重命名根节点“Error”，并创建 5 个子元素，类型如下：</span><span class="sxs-lookup"><span data-stu-id="5ad88-133">Rename the root node "Error" and create five child elements with the types indicated:</span></span>  
  
   - <span data-ttu-id="5ad88-134">ID、 xs: int</span><span class="sxs-lookup"><span data-stu-id="5ad88-134">ID, xs:int</span></span>  
  
   - <span data-ttu-id="5ad88-135">类型 xs: int</span><span class="sxs-lookup"><span data-stu-id="5ad88-135">Type, xs:int</span></span>  
  
   - <span data-ttu-id="5ad88-136">优先级，xs: string</span><span class="sxs-lookup"><span data-stu-id="5ad88-136">Priority, xs:string</span></span>  
  
   - <span data-ttu-id="5ad88-137">说明，xs: string</span><span class="sxs-lookup"><span data-stu-id="5ad88-137">Description, xs:string</span></span>  
  
   - <span data-ttu-id="5ad88-138">ErrorDateTime，xs: string</span><span class="sxs-lookup"><span data-stu-id="5ad88-138">ErrorDateTime, xs:string</span></span>  
  
     <span data-ttu-id="5ad88-139">您所创建的架构应基本如下：</span><span class="sxs-lookup"><span data-stu-id="5ad88-139">Your schema should look like the following:</span></span>  
  
     <span data-ttu-id="5ad88-140">![架构已完成时出现错误](../core/media/error-schema.gif "error_schema")</span><span class="sxs-lookup"><span data-stu-id="5ad88-140">![Completed Error schema](../core/media/error-schema.gif "error_schema")</span></span>  
  
5. <span data-ttu-id="5ad88-141">为此架构创建一个示例消息。</span><span class="sxs-lookup"><span data-stu-id="5ad88-141">Create a sample message for this schema.</span></span> <span data-ttu-id="5ad88-142">此消息用于检验对信封外的单个消息的处理是否正确。</span><span class="sxs-lookup"><span data-stu-id="5ad88-142">This is used to verify that single messages outside of an envelope are processed properly.</span></span> <span data-ttu-id="5ad88-143">下面是一个示例消息：</span><span class="sxs-lookup"><span data-stu-id="5ad88-143">An example sample message is:</span></span>  
  
   ```  
   <Error xmlns="http://BasicXMLEnvelope">  
     <ID>1</ID>  
     <Type>5</Type>  
     <Priority>Low</Priority>  
     <Description>Sprocket widget prints reports slowly.</Description>  
     <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
   </Error>  
   ```  
  
    <span data-ttu-id="5ad88-144">将此消息保存到项目目录下的文件中。</span><span class="sxs-lookup"><span data-stu-id="5ad88-144">Save this message in a file in the project directory.</span></span>  
  
### <a name="create-the-envelope-schema"></a><span data-ttu-id="5ad88-145">创建信封架构</span><span class="sxs-lookup"><span data-stu-id="5ad88-145">Create the Envelope Schema</span></span>  
 <span data-ttu-id="5ad88-146">该信封包含一个或多个错误消息。</span><span class="sxs-lookup"><span data-stu-id="5ad88-146">The envelope contains one or more error messages.</span></span> <span data-ttu-id="5ad88-147">在本基本示例中，信封没有自己的属性和元素。</span><span class="sxs-lookup"><span data-stu-id="5ad88-147">In this basic example, the envelope does not have properties and elements of its own.</span></span>  
  
##### <a name="to-create-the-envelope-schema"></a><span data-ttu-id="5ad88-148">若要创建信封架构</span><span class="sxs-lookup"><span data-stu-id="5ad88-148">To create the envelope schema</span></span>  
  
1.  <span data-ttu-id="5ad88-149">向项目 BasicXMLEnvelope 添加名称为“Envelope”的新架构。</span><span class="sxs-lookup"><span data-stu-id="5ad88-149">Add a new schema named "Envelope" to the BasicXMLEnvelope project.</span></span>  
  
2.  <span data-ttu-id="5ad88-150">更改到的目标命名空间**http://BasicXMLEnvelope**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-150">Change the target namespace to **http://BasicXMLEnvelope**.</span></span>  
  
3.  <span data-ttu-id="5ad88-151">将根节点的名称从“Root”改为“Envelope”。</span><span class="sxs-lookup"><span data-stu-id="5ad88-151">Change the name of the root node from "Root" to "Envelope".</span></span>  
  
4.  <span data-ttu-id="5ad88-152">现在，将该架构标记为信封架构。</span><span class="sxs-lookup"><span data-stu-id="5ad88-152">Now mark the schema as an envelope schema.</span></span> <span data-ttu-id="5ad88-153">单击**\<架构\>** 节点。</span><span class="sxs-lookup"><span data-stu-id="5ad88-153">Click the **\<Schema\>** node.</span></span> <span data-ttu-id="5ad88-154">在属性窗格中，将架构引用属性设置**信封**到`OK`。</span><span class="sxs-lookup"><span data-stu-id="5ad88-154">In the Properties pane, set the schema reference property **Envelope** to `OK`.</span></span>  
  
5.  <span data-ttu-id="5ad88-155">设置**正文 XPath**属性。</span><span class="sxs-lookup"><span data-stu-id="5ad88-155">Set the **Body XPath** property.</span></span> <span data-ttu-id="5ad88-156">若要执行此操作，请单击**信封**节点。</span><span class="sxs-lookup"><span data-stu-id="5ad88-156">To do this, click the **Envelope** node.</span></span> <span data-ttu-id="5ad88-157">在属性窗口中，单击省略号 (**...**) 按钮**正文 XPath**属性中，选择**信封**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-157">In the Properties window, click the ellipsis (**...**) button in the **Body XPath** property, select **Envelope**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="5ad88-158">向“Envelope”节点任意添加一个“任何元素”子级。</span><span class="sxs-lookup"><span data-stu-id="5ad88-158">Add an Any element child to the Envelope node.</span></span> <span data-ttu-id="5ad88-159">错误信息将包含在此元素中。</span><span class="sxs-lookup"><span data-stu-id="5ad88-159">The error message will be contained in this element.</span></span> <span data-ttu-id="5ad88-160">您所创建的架构应基本如下：</span><span class="sxs-lookup"><span data-stu-id="5ad88-160">Your schema should look like the following:</span></span>  
  
     <span data-ttu-id="5ad88-161">![已完成的信封架构](../core/media/envelope-schema.gif "envelope_schema")</span><span class="sxs-lookup"><span data-stu-id="5ad88-161">![Completed envelope schema](../core/media/envelope-schema.gif "envelope_schema")</span></span>  
  
7.  <span data-ttu-id="5ad88-162">创建一个包含一个信封、一个或多个示例消息的示例消息。</span><span class="sxs-lookup"><span data-stu-id="5ad88-162">Create a sample message containing an envelope and one or more sample messages.</span></span> <span data-ttu-id="5ad88-163">示例消息为：</span><span class="sxs-lookup"><span data-stu-id="5ad88-163">An example message is:</span></span>  
  
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
  
     <span data-ttu-id="5ad88-164">将此消息保存到项目目录下的文件中。</span><span class="sxs-lookup"><span data-stu-id="5ad88-164">Save this message in a file in the project directory.</span></span>  
  
### <a name="deploy-and-configure-the-send-and-receive-ports"></a><span data-ttu-id="5ad88-165">部署并配置发送和接收端口</span><span class="sxs-lookup"><span data-stu-id="5ad88-165">Deploy and Configure the Send and Receive Ports</span></span>  
 <span data-ttu-id="5ad88-166">创建架构后，还需要编译和部署项目。</span><span class="sxs-lookup"><span data-stu-id="5ad88-166">With the schemas created, you need to compile and deploy the project.</span></span> <span data-ttu-id="5ad88-167">部署完毕后，就可使用 BizTalk Server 管理控制台来配置发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="5ad88-167">After it is deployed, you can use the BizTalk Server Administration console to configure the send and receive ports.</span></span>  
  
##### <a name="to-deploy-basicxmlenvelope"></a><span data-ttu-id="5ad88-168">若要部署 BasicXMLEnvelope</span><span class="sxs-lookup"><span data-stu-id="5ad88-168">To deploy BasicXMLEnvelope</span></span>  
  
1. <span data-ttu-id="5ad88-169">从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，选择**部署 BasicXMLEnvelope**从生成菜单。</span><span class="sxs-lookup"><span data-stu-id="5ad88-169">From [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], choose **Deploy BasicXMLEnvelope** from the Build menu.</span></span> <span data-ttu-id="5ad88-170">这将生成“BasicXMLEnvelope”并将其作为应用程序部署到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="5ad88-170">This will build and deploy it to BizTalk Server as the application "BasicXMLEnvelope".</span></span>  
  
2. <span data-ttu-id="5ad88-171">在 BizTalk Server 管理控制台中，展开**应用程序**组，以验证**BasicXMLEnvelope**是显示为自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="5ad88-171">In the BizTalk Server Administration console, expand the **Applications** group to verify that **BasicXMLEnvelope** is present as a custom application.</span></span>  
  
##### <a name="to-configure-the-receive-port"></a><span data-ttu-id="5ad88-172">若要配置接收端口</span><span class="sxs-lookup"><span data-stu-id="5ad88-172">To configure the receive port</span></span>  
  
1.  <span data-ttu-id="5ad88-173">使用 Windows 资源管理器下创建一个名为"Receive"目录**BasicXMLEnvelope**项目目录。</span><span class="sxs-lookup"><span data-stu-id="5ad88-173">Use Windows Explorer to create a directory named "Receive" under the **BasicXMLEnvelope** project directory.</span></span>  
  
2.  <span data-ttu-id="5ad88-174">在 BizTalk Server 管理控制台中，展开**BasicXMLEnvelope**应用程序中，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-174">In the BizTalk Server Administration console, expand the **BasicXMLEnvelope** application, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
3.  <span data-ttu-id="5ad88-175">在中**接收端口属性**对话框框中，设置为"Receive"的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="5ad88-175">In the **Receive Port Properties** dialog box, set the name of the port to "Receive".</span></span>  
  
4.  <span data-ttu-id="5ad88-176">右键单击接收位置，然后单击**新建**添加接收端口。</span><span class="sxs-lookup"><span data-stu-id="5ad88-176">Right-click Receive Locations, and then click **New** to add a receive port.</span></span> <span data-ttu-id="5ad88-177">将新端口命名为“ReceiveError”。</span><span class="sxs-lookup"><span data-stu-id="5ad88-177">Name the new port "ReceiveError".</span></span> <span data-ttu-id="5ad88-178">设置**接收管道**到**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-178">Set the **Receive Pipeline** to **XMLReceive**.</span></span> <span data-ttu-id="5ad88-179">有关**传输类型**，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-179">For **Transport Type**, select **FILE**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="5ad88-180">选择上面创建的接收目录，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-180">Select the receive directory created above and click **OK**.</span></span> <span data-ttu-id="5ad88-181">现在接收端口配置完毕。</span><span class="sxs-lookup"><span data-stu-id="5ad88-181">Your receive port should now be configured.</span></span> <span data-ttu-id="5ad88-182">单击**确定**关闭。</span><span class="sxs-lookup"><span data-stu-id="5ad88-182">Click **OK** to close.</span></span>  
  
##### <a name="to-configure-the-send-port"></a><span data-ttu-id="5ad88-183">若要配置的发送端口</span><span class="sxs-lookup"><span data-stu-id="5ad88-183">To configure the send port</span></span>  
  
1.  <span data-ttu-id="5ad88-184">使用 Windows 资源管理器下创建一个名为"发送" **BasicXMLEnvelope**项目目录。</span><span class="sxs-lookup"><span data-stu-id="5ad88-184">Use Windows Explorer to create a directory named "Send" under the **BasicXMLEnvelope** project directory.</span></span>  
  
2.  <span data-ttu-id="5ad88-185">在 BizTalk Server 管理控制台中，展开**BasicXMLEnvelope**应用程序中，右键单击**发送端口**，指向**新建**，然后单击**静态单向**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-185">In the BizTalk Server Administration console, expand the **BasicXMLEnvelope** application, right-click **Send Ports**, point to **New**, and then click **Static One-Way**.</span></span>  
  
3.  <span data-ttu-id="5ad88-186">在中**发送端口属性**对话框框中，设置为"Send"的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="5ad88-186">In the **Send Port Properties** dialog box, set the name of the port to "Send".</span></span>  
  
4.  <span data-ttu-id="5ad88-187">有关**传输类型**，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-187">For **Transport Type**, select **FILE**, and then click **Configure**.</span></span> <span data-ttu-id="5ad88-188">目标文件夹设置为前面创建的发送目录，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-188">Set the destination folder to the send directory you created earlier and click **OK**.</span></span>  
  
5.  <span data-ttu-id="5ad88-189">单击**筛选器**并添加一个筛选器：</span><span class="sxs-lookup"><span data-stu-id="5ad88-189">Click **Filters** and add a single filter:</span></span>  
  
    -   <span data-ttu-id="5ad88-190">BTS.MessageType == **http://BasicXMLEnvelope#Error**</span><span class="sxs-lookup"><span data-stu-id="5ad88-190">BTS.MessageType == **http://BasicXMLEnvelope#Error**</span></span>  
  
6.  <span data-ttu-id="5ad88-191">单击**确定**完成发送端口配置。</span><span class="sxs-lookup"><span data-stu-id="5ad88-191">Click **OK** to complete the send port configuration.</span></span> <span data-ttu-id="5ad88-192">现在发送端口配置完毕。</span><span class="sxs-lookup"><span data-stu-id="5ad88-192">Your send port should be configured.</span></span>  
  
### <a name="run-the-example"></a><span data-ttu-id="5ad88-193">运行示例</span><span class="sxs-lookup"><span data-stu-id="5ad88-193">Run the Example</span></span>  
 <span data-ttu-id="5ad88-194">现在该运行示例了。</span><span class="sxs-lookup"><span data-stu-id="5ad88-194">It is now time to run the example.</span></span> <span data-ttu-id="5ad88-195">使用 BizTalk Server 管理控制台启动 BasicXMLEnvelope 应用程序后，您应将测试文件复制到接收位置，然后观察发送位置生成的内容。</span><span class="sxs-lookup"><span data-stu-id="5ad88-195">After using the BizTalk Server Management console to start the BasicXMLEnvelope application, you will copy the test files to the receive location and observe what is produced in the send location.</span></span>  
  
##### <a name="to-run-the-basicxmlenvelope-example"></a><span data-ttu-id="5ad88-196">若要运行 BasicXMLEnvelope 示例</span><span class="sxs-lookup"><span data-stu-id="5ad88-196">To run the BasicXMLEnvelope example</span></span>  
  
1.  <span data-ttu-id="5ad88-197">在 BizTalk Server 管理控制台中，右键单击**BasicXMLEnvelope**应用程序，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-197">In the BizTalk Server Administration console, right-click the **BasicXMLEnvelope** application and then click **Start**.</span></span> <span data-ttu-id="5ad88-198">此时将登记并启动发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="5ad88-198">This will enlist and start the send and receive ports.</span></span>  
  
2.  <span data-ttu-id="5ad88-199">将所有示例文件放入接收目录中。</span><span class="sxs-lookup"><span data-stu-id="5ad88-199">Drop each of the sample files into the receive directory.</span></span> <span data-ttu-id="5ad88-200">如果您使用前面给出的示例，则操作完毕时，应在发送位置找到三个单个错误消息。</span><span class="sxs-lookup"><span data-stu-id="5ad88-200">If you use the samples given earlier, you should find three individual error messages in the send location when processing is completed.</span></span>  
  
## <a name="extending-the-example"></a><span data-ttu-id="5ad88-201">扩展示例</span><span class="sxs-lookup"><span data-stu-id="5ad88-201">Extending the Example</span></span>  
 <span data-ttu-id="5ad88-202">您可扩展该示例以满足其他要求。</span><span class="sxs-lookup"><span data-stu-id="5ad88-202">You can extend the example to accommodate other requirements.</span></span> <span data-ttu-id="5ad88-203">此处主要介绍两种常见方案：</span><span class="sxs-lookup"><span data-stu-id="5ad88-203">This section addresses two common scenarios:</span></span>  
  
- <span data-ttu-id="5ad88-204">如果一批错误是装入信封中提交的，则单个消息的拆装错误不应阻止其他无错误消息的进一步处理。</span><span class="sxs-lookup"><span data-stu-id="5ad88-204">If a batch of errors is submitted within an envelope, individual message failures in disassembly should not prohibit other nonfailing messages from being further processed.</span></span>  
  
- <span data-ttu-id="5ad88-205">应根据错误优先级，将错误发送到不同位置。</span><span class="sxs-lookup"><span data-stu-id="5ad88-205">Errors should be delivered to different locations based on error priority.</span></span> <span data-ttu-id="5ad88-206">高优先级的消息应迅速处理，而其他优先级的消息应按照常规方式进行处理。</span><span class="sxs-lookup"><span data-stu-id="5ad88-206">High-priority messages are expedited while other priorities are handled through normal channels.</span></span>  
  
  <span data-ttu-id="5ad88-207">以下部分扩展了该示例，以处理这些要求。</span><span class="sxs-lookup"><span data-stu-id="5ad88-207">The following sections extend the example to handle these requirements.</span></span>  
  
### <a name="recoverable-interchange-processing"></a><span data-ttu-id="5ad88-208">可恢复交换处理</span><span class="sxs-lookup"><span data-stu-id="5ad88-208">Recoverable Interchange Processing</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5ad88-209"> 支持可恢复交换处理。</span><span class="sxs-lookup"><span data-stu-id="5ad88-209"> supports recoverable interchange processing.</span></span> <span data-ttu-id="5ad88-210">借助此功能，您可确保成批消息的拆装中只会单个消息失败，而不会整批单位。</span><span class="sxs-lookup"><span data-stu-id="5ad88-210">By using this feature, you can ensure that batches of messages fail individually in disassembly and not as a batch.</span></span>  
  
##### <a name="to-configure-the-example-for-recoverable-interchange-processing"></a><span data-ttu-id="5ad88-211">若要配置可恢复交换处理的示例</span><span class="sxs-lookup"><span data-stu-id="5ad88-211">To configure the example for recoverable interchange processing</span></span>  
  
1.  <span data-ttu-id="5ad88-212">在 BizTalk Server 管理控制台中，展开**BasicXMLEnvelope**应用程序中，单击**接收端口**，然后双击接收端口。</span><span class="sxs-lookup"><span data-stu-id="5ad88-212">In the BizTalk Server Administration console, expand the **BasicXMLEnvelope** application, click **Receive Ports**, and then double-click the Receive port.</span></span> <span data-ttu-id="5ad88-213">它是您先前创建的端口。</span><span class="sxs-lookup"><span data-stu-id="5ad88-213">This is the port you created previously.</span></span>  
  
2.  <span data-ttu-id="5ad88-214">在中**接收端口属性**对话框中，单击**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-214">In the **Receive Port Properties** dialog box, click **Receive Locations**.</span></span> <span data-ttu-id="5ad88-215">单击**属性**以打开**ReceiveError 接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="5ad88-215">Click **Properties** to bring up the **ReceiveError Receive Location Properties** dialog box.</span></span> <span data-ttu-id="5ad88-216">单击省略号 (**...**) 按钮**接收管道**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-216">Click the ellipsis (**...**) button for the **Receive Pipeline**.</span></span>  
  
3.  <span data-ttu-id="5ad88-217">在中**配置管道-XMLReceive**对话框中，将**可恢复交换处理**属性设置为`True`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-217">In the **Configure Pipeline - XMLReceive** dialog box, set the **Recoverable Interchange Processing** property to `True`, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="5ad88-218">单击**确定**以关闭**接收位置属性**对话框中，然后单击**确定**以关闭**接收端口属性**对话框框。</span><span class="sxs-lookup"><span data-stu-id="5ad88-218">Click **OK** to close the **Receive Location Properties** dialog box, and then click **OK** to close the **Receive Port Properties** dialog box.</span></span>  
  
##### <a name="to-create-a-sample-file-and-run-the-example"></a><span data-ttu-id="5ad88-219">若要创建示例文件并运行示例</span><span class="sxs-lookup"><span data-stu-id="5ad88-219">To create a sample file and run the example</span></span>  
  
1.  <span data-ttu-id="5ad88-220">若要创建示例文件，请复制在示例中创建的信封示例文件，并向其中一个“Error”实例添加一个并不存在的命名空间，然后保存该文件：</span><span class="sxs-lookup"><span data-stu-id="5ad88-220">To create a sample file, make a copy of the envelope sample file created in the example, add a nonexistent namespace to one of the Error instances, and then save the file:</span></span>  
  
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
  
2.  <span data-ttu-id="5ad88-221">在 BizTalk Server 管理控制台中，单击**应用程序**并确认**BasicXMLEnvelope**运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="5ad88-221">In the BizTalk Server Administration console, click **Applications** and verify that the **BasicXMLEnvelope** application is running.</span></span>  
  
3.  <span data-ttu-id="5ad88-222">将该消息放入接收位置。</span><span class="sxs-lookup"><span data-stu-id="5ad88-222">Drop the message in the receive location.</span></span> <span data-ttu-id="5ad88-223">操作完毕后，您应在发送位置找到第一条消息，并在挂起队列中找到优先级较低的第二条消息。</span><span class="sxs-lookup"><span data-stu-id="5ad88-223">After processing, you should find the first message in the send location and the second, low-priority, message in the Suspended queue.</span></span>  
  
### <a name="content-based-routing-cbr"></a><span data-ttu-id="5ad88-224">基于内容的路由 (CBR)</span><span class="sxs-lookup"><span data-stu-id="5ad88-224">Content-Based Routing (CBR)</span></span>  
 <span data-ttu-id="5ad88-225">借助基于内容的路由，您可根据消息的内容来路由消息。</span><span class="sxs-lookup"><span data-stu-id="5ad88-225">You can use content-based routing to route messages based on their content.</span></span> <span data-ttu-id="5ad88-226">在本方案中，路由是基于优先级进行的，高优先级的消息路由到一个发送位置，低优先级和中优先级的消息路由到另一个发送位置。</span><span class="sxs-lookup"><span data-stu-id="5ad88-226">In this scenario, routing is based on priority, with High messages going to one send location and Low and Medium messages going to a different send location.</span></span>  
  
 <span data-ttu-id="5ad88-227">若要扩展该示例，必须完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="5ad88-227">To extend the sample, you must complete the following tasks:</span></span>  
  
1.  <span data-ttu-id="5ad88-228">将提升**优先级**字段 BasicXMLEnvelope 项目中的错误架构中。</span><span class="sxs-lookup"><span data-stu-id="5ad88-228">Promote the **Priority** field in the Error schema in the BasicXMLEnvelope project.</span></span> <span data-ttu-id="5ad88-229">基于内容的路由依靠升级的属性来路由消息。</span><span class="sxs-lookup"><span data-stu-id="5ad88-229">Content-based routing relies on promoted properties to route messages.</span></span> <span data-ttu-id="5ad88-230">有关详细信息，请参阅[升级属性](../core/promoting-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="5ad88-230">For more information, see [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
2.  <span data-ttu-id="5ad88-231">创建并配置其他两个发送端口。</span><span class="sxs-lookup"><span data-stu-id="5ad88-231">Create and configure two additional send ports.</span></span> <span data-ttu-id="5ad88-232">这些端口使用筛选器来确保其接收正确的消息。</span><span class="sxs-lookup"><span data-stu-id="5ad88-232">The ports use a filter to ensure they receive appropriate messages.</span></span>  
  
##### <a name="to-promote-the-priority-field-in-the-error-schema"></a><span data-ttu-id="5ad88-233">若要升级错误架构中的优先级字段</span><span class="sxs-lookup"><span data-stu-id="5ad88-233">To promote the Priority field in the Error schema</span></span>  
  
1. <span data-ttu-id="5ad88-234">与**BasicXMLEnvelope**中打开项目[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开**错误**架构和展开**错误**节点。</span><span class="sxs-lookup"><span data-stu-id="5ad88-234">With the **BasicXMLEnvelope** project open in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the **Error** schema and expand the **Error** node.</span></span>  
  
2. <span data-ttu-id="5ad88-235">右键单击**优先级**元素，指向**Promote**，然后单击**Quick Promote**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-235">Right-click the **Priority** element, point to **Promote**, and then click **Quick Promote**.</span></span>  
  
3. <span data-ttu-id="5ad88-236">单击**确定**以确认添加的新属性架构的已升级属性。</span><span class="sxs-lookup"><span data-stu-id="5ad88-236">Click **OK** to confirm the addition of a new property schema for the promoted properties.</span></span>  
  
4. <span data-ttu-id="5ad88-237">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器中打开新的属性架构 PropertySchema.xsd。</span><span class="sxs-lookup"><span data-stu-id="5ad88-237">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], in Solution Explorer, open the new property schema PropertySchema.xsd.</span></span> <span data-ttu-id="5ad88-238">从架构中删除"Field1"。</span><span class="sxs-lookup"><span data-stu-id="5ad88-238">Remove "Field1" from the schema.</span></span>  
  
5. <span data-ttu-id="5ad88-239">现在重新编译并重新部署该解决方案。</span><span class="sxs-lookup"><span data-stu-id="5ad88-239">Now recompile and redeploy the solution.</span></span> <span data-ttu-id="5ad88-240">在“生成”菜单中，选择“部署 BasicXMLEnvelope”。</span><span class="sxs-lookup"><span data-stu-id="5ad88-240">On the Build menu, choose Deploy BasicXMLEnvelope.</span></span>  
  
6. <span data-ttu-id="5ad88-241">该项目原本配置为在重新部署解决方案时，重置主机实例。</span><span class="sxs-lookup"><span data-stu-id="5ad88-241">The project was configured to reset the host instance when the solution is redeployed.</span></span> <span data-ttu-id="5ad88-242">如果您对此进行了更改，则需要停止并重新启动主机。</span><span class="sxs-lookup"><span data-stu-id="5ad88-242">If you have changed this, you need to stop and start the host.</span></span>  
  
##### <a name="to-configure-the-low-and-medium-priority-send-port"></a><span data-ttu-id="5ad88-243">若要配置的低和中优先级发送端口</span><span class="sxs-lookup"><span data-stu-id="5ad88-243">To configure the low and medium-priority send port</span></span>  
  
1.  <span data-ttu-id="5ad88-244">使用 Windows 资源管理器下创建名为"SendLowMediumPriority"的目录**BasicXMLEnvelope**项目目录。</span><span class="sxs-lookup"><span data-stu-id="5ad88-244">Use Windows Explorer to create a directory named "SendLowMediumPriority" under the **BasicXMLEnvelope** project directory.</span></span>  
  
2.  <span data-ttu-id="5ad88-245">在 BizTalk Server 管理控制台中，展开**BasicXMLEnvelope**应用程序中，右键单击**发送端口**，指向**新建**，然后单击**静态单向**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-245">In the BizTalk Server Administration console, expand the **BasicXMLEnvelope** application, right-click **Send Ports**, point to **New**, and then click **Static One-Way**.</span></span>  
  
3.  <span data-ttu-id="5ad88-246">在中**发送端口属性**对话框框中，设置为"SendLowMediumPriority"的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="5ad88-246">In the **Send Port Properties** dialog box, set the name of the port to "SendLowMediumPriority".</span></span>  
  
4.  <span data-ttu-id="5ad88-247">有关**传输类型**，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-247">For **Transport Type**, select **FILE**, and then click **Configure**.</span></span> <span data-ttu-id="5ad88-248">将目标文件夹设置为前面创建的目录。</span><span class="sxs-lookup"><span data-stu-id="5ad88-248">Set the destination folder to the directory you created earlier.</span></span> <span data-ttu-id="5ad88-249">单击**确定**关闭。</span><span class="sxs-lookup"><span data-stu-id="5ad88-249">Click **OK** to close.</span></span>  
  
5.  <span data-ttu-id="5ad88-250">单击**筛选器**然后添加三个筛选器表达式：</span><span class="sxs-lookup"><span data-stu-id="5ad88-250">Click **Filters** and add three filter expressions:</span></span>  
  
    -   <span data-ttu-id="5ad88-251">BTS。MessageType == http://BasicXMLEnvelope#Error 和</span><span class="sxs-lookup"><span data-stu-id="5ad88-251">BTS.MessageType == http://BasicXMLEnvelope#Error And</span></span>  
  
    -   <span data-ttu-id="5ad88-252">BasicXMLEnvelope.PropertySchema.Priority = = 低或</span><span class="sxs-lookup"><span data-stu-id="5ad88-252">BasicXMLEnvelope.PropertySchema.Priority == Low Or</span></span>  
  
    -   <span data-ttu-id="5ad88-253">BasicXMLEnvelope.PropertySchema.Priority = = Medium</span><span class="sxs-lookup"><span data-stu-id="5ad88-253">BasicXMLEnvelope.PropertySchema.Priority == Medium</span></span>  
  
6.  <span data-ttu-id="5ad88-254">单击**确定**，完成低和中优先级发送端口配置。</span><span class="sxs-lookup"><span data-stu-id="5ad88-254">Click **OK** to complete the low and medium-priority send port configuration.</span></span>  
  
##### <a name="to-configure-the-high-priority-send-port"></a><span data-ttu-id="5ad88-255">若要配置高优先级发送端口</span><span class="sxs-lookup"><span data-stu-id="5ad88-255">To configure the high-priority send port</span></span>  
  
1.  <span data-ttu-id="5ad88-256">使用 Windows 资源管理器下创建名为"SendHighPriority"的目录**BasicXMLEnvelope**项目目录。</span><span class="sxs-lookup"><span data-stu-id="5ad88-256">Use Windows Explorer to create a directory named "SendHighPriority" under the **BasicXMLEnvelope** project directory.</span></span>  
  
2.  <span data-ttu-id="5ad88-257">在 BizTalk Server 管理控制台中，展开**BasicXMLEnvelope**应用程序中，右键单击**发送端口**，指向**新建**，然后单击**静态单向**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-257">In the BizTalk Server Administration console, expand the **BasicXMLEnvelope** application, right-click **Send Ports**, point to **New**, and then click **Static One-Way**.</span></span>  
  
3.  <span data-ttu-id="5ad88-258">在中**发送端口属性**对话框框中，设置为"SendHighPriority"的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="5ad88-258">In the **Send Port Properties** dialog box, set the name of the port to "SendHighPriority".</span></span>  
  
4.  <span data-ttu-id="5ad88-259">有关**传输类型**，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-259">For **Transport Type**, select **FILE**, and then click **Configure**.</span></span> <span data-ttu-id="5ad88-260">将目标文件夹设置为前面创建的目录。</span><span class="sxs-lookup"><span data-stu-id="5ad88-260">Set the destination folder to the directory you created earlier.</span></span> <span data-ttu-id="5ad88-261">单击**确定**关闭。</span><span class="sxs-lookup"><span data-stu-id="5ad88-261">Click **OK** to close.</span></span>  
  
5.  <span data-ttu-id="5ad88-262">单击**筛选器**和添加两个筛选器表达式：</span><span class="sxs-lookup"><span data-stu-id="5ad88-262">Click **Filters** and add two filter expressions:</span></span>  
  
    -   <span data-ttu-id="5ad88-263">BTS。MessageType == http://BasicXMLEnvelope#Error 和</span><span class="sxs-lookup"><span data-stu-id="5ad88-263">BTS.MessageType == http://BasicXMLEnvelope#Error And</span></span>  
  
    -   <span data-ttu-id="5ad88-264">BasicXMLEnvelope.PropertySchema.Priority = = 高</span><span class="sxs-lookup"><span data-stu-id="5ad88-264">BasicXMLEnvelope.PropertySchema.Priority == High</span></span>  
  
6.  <span data-ttu-id="5ad88-265">单击**确定**完成高优先级发送端口配置。</span><span class="sxs-lookup"><span data-stu-id="5ad88-265">Click **OK** to complete the high-priority send port configuration.</span></span>  
  
##### <a name="to-test-the-routing-solution"></a><span data-ttu-id="5ad88-266">若要测试路由解决方案</span><span class="sxs-lookup"><span data-stu-id="5ad88-266">To test the routing solution</span></span>  
  
1.  <span data-ttu-id="5ad88-267">在 BizTalk Server 管理控制台中，展开**应用程序**组中，右键单击**BasicXMLEnvelope**应用程序，，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-267">In the BizTalk Server Administration console, expand the **Applications** group, right-click the **BasicXMLEnvelope** application, and then click **Start**.</span></span> <span data-ttu-id="5ad88-268">当系统提示你确认，单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="5ad88-268">When prompted to confirm, click **Start**.</span></span> <span data-ttu-id="5ad88-269">这将登记新发送端口。</span><span class="sxs-lookup"><span data-stu-id="5ad88-269">This enlists the new send ports.</span></span>  
  
2.  <span data-ttu-id="5ad88-270">将测试消息放入接收位置。</span><span class="sxs-lookup"><span data-stu-id="5ad88-270">Drop the test message into the receive location.</span></span> <span data-ttu-id="5ad88-271">请注意错误消息是如何被路由到不同的发送位置的：</span><span class="sxs-lookup"><span data-stu-id="5ad88-271">Notice how error messages are routed to the different send locations:</span></span>  
  
    -   <span data-ttu-id="5ad88-272">错误消息，不论其优先级是高、中还是低，只要消息处理没有失败，都会路由到两个位置：原始发送位置（在核心示例中配置）和相应优先级的发送位置。</span><span class="sxs-lookup"><span data-stu-id="5ad88-272">Error messages that have a Low, Medium, or High priority and do not fail message processing are routed both to the original send location (configured in the core example) and the send location by priority.</span></span> <span data-ttu-id="5ad88-273">对于低优先级和中优先级的消息，原始发送位置和低/中优先级发送位置均会出现该消息。</span><span class="sxs-lookup"><span data-stu-id="5ad88-273">For messages with a Low or Medium priority, a copy appears in both the original send location and the Low/Medium send location.</span></span>  
  
    -   <span data-ttu-id="5ad88-274">如果启用了可恢复的交换处理，则不会路由失败的错误消息，而没有失败的消息将按预期正确路由。</span><span class="sxs-lookup"><span data-stu-id="5ad88-274">If recoverable interchange processing is enabled, the failed error message is not routed and the nonfailed message is properly routed as expected.</span></span> <span data-ttu-id="5ad88-275">不路由失败消息的原因是，其消息类型与所配置的筛选器的类型不匹配。</span><span class="sxs-lookup"><span data-stu-id="5ad88-275">The failed message is not routed because its message type does not match the type used in the configured filters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ad88-276">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ad88-276">See Also</span></span>  
 <span data-ttu-id="5ad88-277">[可恢复交换处理](../core/recoverable-interchange-processing.md) </span><span class="sxs-lookup"><span data-stu-id="5ad88-277">[Recoverable Interchange Processing](../core/recoverable-interchange-processing.md) </span></span>  
 <span data-ttu-id="5ad88-278">[升级属性](../core/promoting-properties.md) </span><span class="sxs-lookup"><span data-stu-id="5ad88-278">[Promoting Properties](../core/promoting-properties.md) </span></span>  
 [<span data-ttu-id="5ad88-279">CBRSample（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="5ad88-279">CBRSample (BizTalk Server Sample)</span></span>](../core/cbrsample-biztalk-server-sample.md)