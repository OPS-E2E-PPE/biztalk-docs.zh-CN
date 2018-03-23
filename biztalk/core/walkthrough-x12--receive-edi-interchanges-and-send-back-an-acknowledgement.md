---
title: 演练 (X12)： 接收 EDI 交换和发回确认 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 25d2b5f3-6bd1-413c-aace-e4dd71f80403
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79eb16ac77f2f1573735c36b19fa6aa68c001c76
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="walkthrough-x12-receiving-edi-interchanges-and-sending-back-an-acknowledgement"></a><span data-ttu-id="3e969-102">演练 (X12)：接收 EDI 交换并发送回确认信息</span><span class="sxs-lookup"><span data-stu-id="3e969-102">Walkthrough (X12): Receiving EDI Interchanges and Sending Back an Acknowledgement</span></span>
<span data-ttu-id="3e969-103">本演练将介绍使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 为接收 EDI 交换创建解决方案的分步操作过程。</span><span class="sxs-lookup"><span data-stu-id="3e969-103">This walkthrough provides a set of step-by-step procedures that creates a solution for receiving EDI interchanges using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="3e969-104">在此解决方案中，EDI 从贸易合作伙伴 (Fabrikam) 发送到另一贸易合作伙伴 (Contoso)。</span><span class="sxs-lookup"><span data-stu-id="3e969-104">In this solution, an EDI interchange is sent from a trading partner, Fabrikam, to another trading partner, Contoso.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3e969-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="3e969-105">Prerequisites</span></span>  
 <span data-ttu-id="3e969-106">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="3e969-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="how-the-solution-receives-edi-interchanges"></a><span data-ttu-id="3e969-107">解决方案如何接收 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="3e969-107">How the Solution Receives EDI Interchanges</span></span>  
 <span data-ttu-id="3e969-108">该解决方案将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3e969-108">The solution will do the following:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e969-109">此列表中的事件可能不会按所示顺序发生。</span><span class="sxs-lookup"><span data-stu-id="3e969-109">The events in this list may not occur in the order shown.</span></span>  
  
1.  <span data-ttu-id="3e969-110">接收来自贸易合作伙伴 Fabrikam 的平面文件 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="3e969-110">Receive a flat-file EDI interchange from the trading partner Fabrikam.</span></span>  
  
2.  <span data-ttu-id="3e969-111">对照 EDI 交换的架构验证该交换，将消息拆装成 XML，并将消息 XML 放置到 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="3e969-111">Validate the EDI interchange against its schema, disassemble the message into XML, and drop the message XML into the MessageBox.</span></span>  
  
3.  <span data-ttu-id="3e969-112">为收到的 EDI 交换生成 997 确认，并将其放置到 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="3e969-112">Generate a 997 acknowledgment to the received EDI interchange, and drop it in the MessageBox.</span></span>  
  
4.  <span data-ttu-id="3e969-113">为收到的 EDI 交换生成 TA1 确认，并将其放置到 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="3e969-113">Generate a TA1 acknowledgment to the received EDI interchange, and drop it in the MessageBox.</span></span>  
  
5.  <span data-ttu-id="3e969-114">通过单向发送端口提取消息 XML，并组装消息 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="3e969-114">Pick up the message XML by a one-way send port, and assemble the message EDI interchange.</span></span>  
  
6.  <span data-ttu-id="3e969-115">将 EDI 交换发送给 Contoso。</span><span class="sxs-lookup"><span data-stu-id="3e969-115">Send the EDI interchange to Contoso.</span></span>  
  
7.  <span data-ttu-id="3e969-116">通过单向发送端口提取 997 XML，并组装 997 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="3e969-116">Pick up the 997 XML by a one-way send port, and assemble the 997 EDI interchange.</span></span>  
  
8.  <span data-ttu-id="3e969-117">将 997 交换发送给 Fabrikam。</span><span class="sxs-lookup"><span data-stu-id="3e969-117">Send the 997 interchange to Fabrikam.</span></span>  
  
9. <span data-ttu-id="3e969-118">通过单向发送端口提取 TA1 XML，并组装 TA1 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="3e969-118">Pick up the TA1 XML by a one-way send port, and assemble the TA1 EDI interchange.</span></span>  
  
10. <span data-ttu-id="3e969-119">将 TA1 交换发送给 Fabrikam。</span><span class="sxs-lookup"><span data-stu-id="3e969-119">Send the TA1 interchange to Fabrikam.</span></span>  
  
## <a name="the-functionality-in-this-solution"></a><span data-ttu-id="3e969-120">此解决方案中的功能</span><span class="sxs-lookup"><span data-stu-id="3e969-120">The Functionality in this Solution</span></span>  
 <span data-ttu-id="3e969-121">为进行此演练，将启用以下功能：</span><span class="sxs-lookup"><span data-stu-id="3e969-121">For the purposes of this walkthrough, the following functionality will be enabled:</span></span>  
  
-   <span data-ttu-id="3e969-122">该解决方案专用于使用 X12 编码而不是 EDIFACT 编码的交换。</span><span class="sxs-lookup"><span data-stu-id="3e969-122">The solution is designed for interchanges using X12 encoding, not EDIFACT encoding.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e969-123">用于 HIPAA 的配置与用于 X12 编码的配置几近相同。</span><span class="sxs-lookup"><span data-stu-id="3e969-123">The configuration used for HIPAA closely parallel to that used for X12 encoding.</span></span> <span data-ttu-id="3e969-124">有关如何为 EDIFACT 创建类似的解决方案的说明，请参阅[演练 (EDIFACT): 接收 EDI 交换和发送回确认](../core/walkthrough-edifact--receive-edi-interchanges-and-send-an-acknowledgement.md)。</span><span class="sxs-lookup"><span data-stu-id="3e969-124">For instructions on how to create a similar solution for EDIFACT, see [Walkthrough (EDIFACT): Receiving EDI Interchanges and Sending Back an Acknowledgement](../core/walkthrough-edifact--receive-edi-interchanges-and-send-an-acknowledgement.md).</span></span>  
  
-   <span data-ttu-id="3e969-125">EDI 类型和扩展的验证将在传入交换上执行。</span><span class="sxs-lookup"><span data-stu-id="3e969-125">EDI type and extended validation will be performed on the incoming interchange.</span></span>  
  
-   <span data-ttu-id="3e969-126">将生成技术确认和功能确认，以返回给交换的发送方。</span><span class="sxs-lookup"><span data-stu-id="3e969-126">Technical and functional acknowledgments will be generated for returning to the sender of the interchange.</span></span>  
  
-   <span data-ttu-id="3e969-127">该解决方案使用传输类型为 FILE 的单向接收位置。</span><span class="sxs-lookup"><span data-stu-id="3e969-127">The solution uses a one-way receive location with a FILE transport type.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e969-128">您可以使用双向要求响应接收端口和位置来接收消息，但如果这样，接收位置将无法使用 FILE 传输类型。</span><span class="sxs-lookup"><span data-stu-id="3e969-128">You can use a two-way solicit response receive port and location to receive the message, but if you do so, you will not be able to use a FILE transport type for the receive location.</span></span> <span data-ttu-id="3e969-129">有关详细信息，请参阅[配置端口以接收 EDI 消息以及确认](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md)。</span><span class="sxs-lookup"><span data-stu-id="3e969-129">For more information, see [Configuring a Port to Receive EDI Messages and Acknowledgments](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md).</span></span>  
  
-   <span data-ttu-id="3e969-130">系统将启用 EDI 报告功能，并保存事务集以便从交换状态报告进行查看。</span><span class="sxs-lookup"><span data-stu-id="3e969-130">EDI reporting will be enabled, and transaction sets will be saved for viewing from the interchange status report.</span></span>  
  
-   <span data-ttu-id="3e969-131">出于测试目的，解决方案使用三个发送端口将 EDI 交换和创建的确认发送到本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e969-131">For testing purposes, the solution uses three send ports to send the EDI interchange and the ACKs created to local folders.</span></span>  
  
 <span data-ttu-id="3e969-132">下图显示了此解决方案的结构：</span><span class="sxs-lookup"><span data-stu-id="3e969-132">The following figure shows the architecture for this solution:</span></span>  
  
 <span data-ttu-id="3e969-133">![接收 EDI 交换](../core/media/c54cca56-c658-4081-9e2f-bf28ba647cda.gif "c54cca56-c658-4081-9e2f-bf28ba647cda")</span><span class="sxs-lookup"><span data-stu-id="3e969-133">![Receiving EDI interchanges](../core/media/c54cca56-c658-4081-9e2f-bf28ba647cda.gif "c54cca56-c658-4081-9e2f-bf28ba647cda")</span></span>  
  
## <a name="configuring-and-testing-the-walkthrough"></a><span data-ttu-id="3e969-134">配置和测试演练</span><span class="sxs-lookup"><span data-stu-id="3e969-134">Configuring and Testing the Walkthrough</span></span>  
 <span data-ttu-id="3e969-135">该解决方案所需的过程包括：</span><span class="sxs-lookup"><span data-stu-id="3e969-135">The procedures required for this solution include the following:</span></span>  
  
-   <span data-ttu-id="3e969-136">将必需的消息架构添加到 BizTalk 项目，然后生成并部署该项目，使 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在处理收到的交换时可以使用相应架构。</span><span class="sxs-lookup"><span data-stu-id="3e969-136">Add the required message schema(s) to a BizTalk project, and then build and deploy the project, making the schema(s) available for use by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in processing the received interchange.</span></span>  
  
-   <span data-ttu-id="3e969-137">为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建一个单向接收端口，以便接收来自贸易合作伙伴的 EDI 交换，并生成确认。</span><span class="sxs-lookup"><span data-stu-id="3e969-137">Create a one-way receive port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive the EDI interchange from the trading partner and generate an acknowledgment.</span></span> <span data-ttu-id="3e969-138">此接收位置与 Fabrikam 存放要发送到 Contoso 的 EDI 交换的 file 文件夹相关联。</span><span class="sxs-lookup"><span data-stu-id="3e969-138">This receive location is tied to the file folder where Fabrikam drops the EDI interchange to be sent to Contoso.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e969-139">你可以使用的双向请求作出响应接收端口和位置，以便接收该消息，但如果这样做，你将不能用于接收位置的文件传输类型。</span><span class="sxs-lookup"><span data-stu-id="3e969-139">You can use a two-way solicit response receive port and location to receive the message, but if you do, you will not be able to use a FILE transport type for the receive location.</span></span>  
  
-   <span data-ttu-id="3e969-140">创建三个发送端口，分别用于向本地 Contoso 文件夹发送 EDI 交换、向本地 Fabrikam 文件夹发送 997 确认以及向本地 Fabrikam 文件夹发送 TA1 确认。</span><span class="sxs-lookup"><span data-stu-id="3e969-140">Create one send port that sends the EDI interchange to a local Contoso folder, another that sends the 997 ACK to a local Fabrikam folder, and another that sends the TA1 ACK to a local Fabrikam folder.</span></span>  
  
-   <span data-ttu-id="3e969-141">为 Fabrikam 和 Contoso 创建参与方（贸易合作伙伴）。</span><span class="sxs-lookup"><span data-stu-id="3e969-141">Create a party (trading partner) for both Fabrikam and Contoso.</span></span>  
  
-   <span data-ttu-id="3e969-142">为两个贸易合作伙伴分别创建一个业务配置文件。</span><span class="sxs-lookup"><span data-stu-id="3e969-142">Create a business profile each for both the trading partners.</span></span>  
  
-   <span data-ttu-id="3e969-143">创建通过配置接收消息的 EDI 属性的两个配置文件和确认之间发送的协议。</span><span class="sxs-lookup"><span data-stu-id="3e969-143">Create an agreement between the two profiles by configuring the EDI properties for the message to be received and the acknowledgment to be sent.</span></span>  
  
-   <span data-ttu-id="3e969-144">使用测试 EDI 交换测试演练。</span><span class="sxs-lookup"><span data-stu-id="3e969-144">Test the walkthrough using a test EDI interchange.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e969-145">对于测试消息，您可以使用在 EDI 接口开发人员教程中使用的 SamplePO.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="3e969-145">For a test message, you can use the SamplePO.txt file that is used in the EDI Interface Developer tutorial.</span></span> <span data-ttu-id="3e969-146">该文件位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\EDI Interface Developer Tutorial\ 文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e969-146">That file is shipped in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ folder.</span></span> <span data-ttu-id="3e969-147">这是一个 X12 850 消息。</span><span class="sxs-lookup"><span data-stu-id="3e969-147">This is an X12 850 message.</span></span>  
  
### <a name="configuring-the-walkthrough"></a><span data-ttu-id="3e969-148">配置演练</span><span class="sxs-lookup"><span data-stu-id="3e969-148">Configuring the Walkthrough</span></span>  
 <span data-ttu-id="3e969-149">本部分介绍配置演练的步骤。</span><span class="sxs-lookup"><span data-stu-id="3e969-149">This section describes the procedures to configure the walkthrough.</span></span>  
  
##### <a name="to-deploy-the-message-schema"></a><span data-ttu-id="3e969-150">部署消息架构</span><span class="sxs-lookup"><span data-stu-id="3e969-150">To deploy the message schema</span></span>  
  
1.  <span data-ttu-id="3e969-151">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，创建或打开 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="3e969-151">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create or open a BizTalk project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e969-152">本主题假定你已从你的应用程序添加了对包含 EDI 架构、管道和业务流程的 BizTalk EDI 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="3e969-152">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="3e969-153">如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。</span><span class="sxs-lookup"><span data-stu-id="3e969-153">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
2.  <span data-ttu-id="3e969-154">右键单击你的项目，指向 **添加**, ，然后单击 **现有项**。</span><span class="sxs-lookup"><span data-stu-id="3e969-154">Right-click your project, point to **Add**, and then click **Existing Item**.</span></span> <span data-ttu-id="3e969-155">移动到您架构所在的 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] XSD_Schema\EDI 文件夹中，然后双击架构。</span><span class="sxs-lookup"><span data-stu-id="3e969-155">Move to the folder that your schema is in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI, and then double-click your schema.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e969-156">如果不具有已 EDI 架构解压缩到 \XSD_Schema\EDI 文件夹中，执行 **MicrosoftEdiXSDTemplates.exe** \XSD_Schema\EDI 文件夹来解压缩到默认文件夹的架构中的文件。</span><span class="sxs-lookup"><span data-stu-id="3e969-156">If the EDI schemas have not been unzipped into the \XSD_Schema\EDI folders, execute the **MicrosoftEdiXSDTemplates.exe** file in the \XSD_Schema\EDI folder to unzip the schemas into the default folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e969-157">如果您使用 EDI 接口开发人员教程中使用的 SamplePO.txt 文件，则必须使用 X12_00401_850.xsd 架构，该架构位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="3e969-157">If you use the SamplePO.txt file that is used in the EDI Interface Developer tutorial, you must use the X12_00401_850.xsd schema that is shipped in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI folder.</span></span> <span data-ttu-id="3e969-158">不能使用位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] XSD_Schema 文件夹的 X12 850 架构。</span><span class="sxs-lookup"><span data-stu-id="3e969-158">You must not use the X12 850 schema in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema folder.</span></span>  
  
3.  <span data-ttu-id="3e969-159">将程序集密钥文件添加到项目中，然后生成并部署程序集。</span><span class="sxs-lookup"><span data-stu-id="3e969-159">Add the assembly key file to the project, and then build and deploy the assembly.</span></span>  
  
##### <a name="to-create-a-one-way-receive-port-for-fabrikam-to-receive-the-edi-interchange"></a><span data-ttu-id="3e969-160">若要创建单向接收端口 （对于 Fabrikam) 接收 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="3e969-160">To create a one-way receive port (for Fabrikam) to receive the EDI interchange</span></span>  
  
1.  <span data-ttu-id="3e969-161">在 Windows 资源管理器，创建要接收该交换的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e969-161">In Windows Explorer, create a local folder to receive the interchange.</span></span>  
  
2.  <span data-ttu-id="3e969-162">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**节点下的**BizTalk 应用程序 1**节点，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="3e969-162">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Receive Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
3.  <span data-ttu-id="3e969-163">将接收端口，然后单击 **接收位置** 在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="3e969-163">Name the receive port, and then click **Receive Locations** in the console tree.</span></span>  
  
4.  <span data-ttu-id="3e969-164">单击 **“新建”**。</span><span class="sxs-lookup"><span data-stu-id="3e969-164">Click **New**.</span></span>  
  
5.  <span data-ttu-id="3e969-165">名称的接收位置中，选择 **文件** 为 **类型**, ，然后单击 **配置**。</span><span class="sxs-lookup"><span data-stu-id="3e969-165">Name the receive location, select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="3e969-166">浏览到文件夹 **接收文件夹** 文本框。</span><span class="sxs-lookup"><span data-stu-id="3e969-166">Browse to a folder for **Receive folder** text box.</span></span> <span data-ttu-id="3e969-167">在此过程中的步骤 1 中创建此文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e969-167">You created this folder in step 1 of this procedure.</span></span> <span data-ttu-id="3e969-168">输入文件掩码，如 **\*.edi** 或 **\*.txt**。</span><span class="sxs-lookup"><span data-stu-id="3e969-168">Enter a file mask, such as **\*.edi** or **\*.txt**.</span></span>  
  
7.  <span data-ttu-id="3e969-169">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="3e969-169">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="3e969-170">有关 **接收管道**, ，选择 **EdiReceive**。</span><span class="sxs-lookup"><span data-stu-id="3e969-170">For **Receive pipeline**, select **EdiReceive**.</span></span>  
  
9. <span data-ttu-id="3e969-171">单击 **确定** 中 **接收位置属性** 对话框。</span><span class="sxs-lookup"><span data-stu-id="3e969-171">Click **OK** in the **Receive Location Properties** dialog box.</span></span> <span data-ttu-id="3e969-172">单击 **确定** 再次在 **接收端口属性** 对话框。</span><span class="sxs-lookup"><span data-stu-id="3e969-172">Click **OK** again in the **Receive Port Properties** dialog box.</span></span>  
  
10. <span data-ttu-id="3e969-173">在控制台树中，单击 **接收位置**。</span><span class="sxs-lookup"><span data-stu-id="3e969-173">In the console tree, click **Receive Locations**.</span></span> <span data-ttu-id="3e969-174">在 **接收位置** 窗格中，右键单击你接收位置，并依次 **启用**。</span><span class="sxs-lookup"><span data-stu-id="3e969-174">In the **Receive Locations** pane, right-click your receive location, and then click **Enable**.</span></span>  
  
##### <a name="to-create-a-static-one-way-send-port-for-contoso-to-send-the-edi-interchange"></a><span data-ttu-id="3e969-175">若要创建静态单向发送端口 （对于 Contoso) 发送 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="3e969-175">To create a static one-way send port (for Contoso) to send the EDI interchange</span></span>  
  
1.  <span data-ttu-id="3e969-176">在 Windows 资源管理器中，创建一个用于接收测试交换的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e969-176">In Windows Explorer, create a local folder to send the test interchange to.</span></span>  
  
2.  <span data-ttu-id="3e969-177">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk 应用程序 1**节点，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="3e969-177">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
3.  <span data-ttu-id="3e969-178">在 **发送端口属性** 对话框中，名称发送端口。</span><span class="sxs-lookup"><span data-stu-id="3e969-178">In the **Send Port Properties** dialog box, name the send port.</span></span>  
  
4.  <span data-ttu-id="3e969-179">在 **传输** 部分中，选择 **文件** 为 **类型**, ，然后单击 **配置**。</span><span class="sxs-lookup"><span data-stu-id="3e969-179">In the **Transport** section, select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="3e969-180">有关 **目标文件夹**, ，浏览到要接收该交换的文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e969-180">For **Destination folder**, browse to the folder to receive the interchange.</span></span> <span data-ttu-id="3e969-181">在此过程中的步骤 1 中创建此文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e969-181">You created this folder in step 1 of this procedure.</span></span> <span data-ttu-id="3e969-182">有关 **文件掩码**, ，输入交换格式，如 **\*.edi** 或 **\*.xml**。</span><span class="sxs-lookup"><span data-stu-id="3e969-182">For **File mask**, enter the interchange format, such as **\*.edi** or **\*.xml**.</span></span>  
  
6.  <span data-ttu-id="3e969-183">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="3e969-183">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="3e969-184">在 **发送管道**, ，选择 **EdiSend**。</span><span class="sxs-lookup"><span data-stu-id="3e969-184">In **Send pipeline**, select **EdiSend**.</span></span>  
  
8.  <span data-ttu-id="3e969-185">在控制台树中，选择 **筛选器**。</span><span class="sxs-lookup"><span data-stu-id="3e969-185">In the console tree, select **Filters**.</span></span> <span data-ttu-id="3e969-186">输入用于订阅 EDI 交换的筛选器。</span><span class="sxs-lookup"><span data-stu-id="3e969-186">Enter a filter to subscribe to the EDI interchange.</span></span> <span data-ttu-id="3e969-187">例如，对于**属性**，输入**BTS。MessageType**; 对于**运算符**，输入**==**; 以及**值**输入架构的交换，例如， http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_850.</span><span class="sxs-lookup"><span data-stu-id="3e969-187">For example, for **Property**, enter **BTS.MessageType**; for **Operator**, enter **==**; and for **Value** enter the schema for the interchange, for example, http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_850.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e969-188">以上筛选器设置可确保将交换（而不是确认）发送到与此发送端口相关联的文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e969-188">The above filter setting ensures that interchanges, not acknowledgments, will be sent to the folder associated with this send port.</span></span>  
  
9. <span data-ttu-id="3e969-189">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="3e969-189">Click **OK**.</span></span>  
  
10. <span data-ttu-id="3e969-190">在控制台树中，单击 **发送端口**。</span><span class="sxs-lookup"><span data-stu-id="3e969-190">In the console tree, click **Send Ports**.</span></span> <span data-ttu-id="3e969-191">在 **发送端口** 窗格中，右键单击你发送端口，并依次 **启动**。</span><span class="sxs-lookup"><span data-stu-id="3e969-191">In the **Send Ports** pane, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-static-one-way-send-port-to-send-the-997n-acknowledgment"></a><span data-ttu-id="3e969-192">创建静态单向发送端口以发送 997 确认</span><span class="sxs-lookup"><span data-stu-id="3e969-192">To create a static one-way send port to send the 997n acknowledgment</span></span>  
  
1.  <span data-ttu-id="3e969-193">在 Windows 资源管理器中，创建一个用于接收 997 确认的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e969-193">In Windows Explorer, create a local folder to send the 997 acknowledgment to.</span></span>  
  
2.  <span data-ttu-id="3e969-194">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk 应用程序 1**节点，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="3e969-194">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
3.  <span data-ttu-id="3e969-195">在 **发送端口属性** 对话框中，名称发送端口。</span><span class="sxs-lookup"><span data-stu-id="3e969-195">In the **Send Port Properties** dialog box, name the send port.</span></span>  
  
4.  <span data-ttu-id="3e969-196">在 **传输** 部分中，选择 **文件** 为 **类型**, ，然后单击 **配置**。</span><span class="sxs-lookup"><span data-stu-id="3e969-196">In the **Transport** section, select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="3e969-197">有关 **目标文件夹**, ，浏览到要收到 997 确认的文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e969-197">For **Destination folder**, browse to a folder to receive the 997 acknowledgment.</span></span> <span data-ttu-id="3e969-198">在此过程中的步骤 1 中创建此文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e969-198">You created this folder in step 1 of this procedure.</span></span> <span data-ttu-id="3e969-199">有关 **文件掩码**, ，输入交换格式，如 **\*.edi** 或 **\*.txt**。</span><span class="sxs-lookup"><span data-stu-id="3e969-199">For **File mask**, enter the interchange format, such as **\*.edi** or **\*.txt**.</span></span>  
  
6.  <span data-ttu-id="3e969-200">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="3e969-200">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="3e969-201">在 **发送管道**, ，选择 **EdiSend**。</span><span class="sxs-lookup"><span data-stu-id="3e969-201">In **Send pipeline**, select **EdiSend**.</span></span>  
  
8.  <span data-ttu-id="3e969-202">在控制台树中，选择 **筛选器**。</span><span class="sxs-lookup"><span data-stu-id="3e969-202">In the console tree, select **Filters**.</span></span> <span data-ttu-id="3e969-203">输入用于订阅 997 确认的筛选器。</span><span class="sxs-lookup"><span data-stu-id="3e969-203">Enter a filter to subscribe to the 997 acknowledgment.</span></span> <span data-ttu-id="3e969-204">例如，对于 **属性**, ，输入 **BTS。MessageType**; 对于 **运算符**, ，输入 **==**; 以及 **值** 确认，例如，输入架构 `http://schemas.microsoft.com/Edi/X12#X12_997_Root`。</span><span class="sxs-lookup"><span data-stu-id="3e969-204">For example, for **Property**, enter **BTS.MessageType**; for **Operator**, enter **==**; and for **Value** enter the schema for the acknowledgment, for example, `http://schemas.microsoft.com/Edi/X12#X12_997_Root`.</span></span>  
  
9. <span data-ttu-id="3e969-205">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="3e969-205">Click **OK**.</span></span>  
  
10. <span data-ttu-id="3e969-206">在控制台树中，单击 **发送端口**。</span><span class="sxs-lookup"><span data-stu-id="3e969-206">In the console tree, click **Send Ports**.</span></span> <span data-ttu-id="3e969-207">在 **发送端口** 窗格中，右键单击你发送端口，并依次 **启动**。</span><span class="sxs-lookup"><span data-stu-id="3e969-207">In the **Send Ports** pane, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-static-one-way-send-port-to-send-the-ta1-acknowledgment"></a><span data-ttu-id="3e969-208">创建静态单向发送端口以发送 TA1 确认</span><span class="sxs-lookup"><span data-stu-id="3e969-208">To create a static one-way send port to send the TA1 acknowledgment</span></span>  
  
1.  <span data-ttu-id="3e969-209">在 Windows 资源管理器中，创建一个用于接收 TA1 确认的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e969-209">In Windows Explorer, create a local folder to send the TA1 acknowledgment to.</span></span>  
  
2.  <span data-ttu-id="3e969-210">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk 应用程序 1**节点，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="3e969-210">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
3.  <span data-ttu-id="3e969-211">在 **发送端口属性** 对话框中，名称发送端口。</span><span class="sxs-lookup"><span data-stu-id="3e969-211">In the **Send Port Properties** dialog box, name the send port.</span></span>  
  
4.  <span data-ttu-id="3e969-212">在 **传输** 部分中，选择 **文件** 为 **类型**, ，然后单击 **配置**。</span><span class="sxs-lookup"><span data-stu-id="3e969-212">In the **Transport** section, select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="3e969-213">有关 **目标文件夹**, ，浏览到要收到 TA1 确认的文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e969-213">For **Destination folder**, browse to a folder to receive the TA1 acknowledgment.</span></span> <span data-ttu-id="3e969-214">在此过程中的步骤 1 中创建此文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e969-214">You created this folder in step 1 of this procedure.</span></span> <span data-ttu-id="3e969-215">有关 **文件掩码**, ，输入交换格式，如 **\*.edi** 或 **\*.txt**。</span><span class="sxs-lookup"><span data-stu-id="3e969-215">For **File mask**, enter the interchange format, such as **\*.edi** or **\*.txt**.</span></span>  
  
6.  <span data-ttu-id="3e969-216">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="3e969-216">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="3e969-217">在 **发送管道**, ，选择 **EdiSend**。</span><span class="sxs-lookup"><span data-stu-id="3e969-217">In **Send pipeline**, select **EdiSend**.</span></span>  
  
8.  <span data-ttu-id="3e969-218">在控制台树中，选择 **筛选器**。</span><span class="sxs-lookup"><span data-stu-id="3e969-218">In the console tree, select **Filters**.</span></span> <span data-ttu-id="3e969-219">输入用于订阅 TA1 确认的筛选器。</span><span class="sxs-lookup"><span data-stu-id="3e969-219">Enter a filter to subscribe to the TA1 acknowledgment.</span></span> <span data-ttu-id="3e969-220">例如，对于**属性**，输入**BTS。MessageType**; 对于**运算符**，输入**==**; 以及**值**确认，例如，输入架构http://schemas.microsoft.com/Edi/X12#X12_TA1_Root.</span><span class="sxs-lookup"><span data-stu-id="3e969-220">For example, for **Property**, enter **BTS.MessageType**; for **Operator**, enter **==**; and for **Value** enter the schema for the acknowledgment, for example, http://schemas.microsoft.com/Edi/X12#X12_TA1_Root.</span></span>  
  
9. <span data-ttu-id="3e969-221">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="3e969-221">Click **OK**.</span></span>  
  
10. <span data-ttu-id="3e969-222">在控制台树中，单击 **发送端口**。</span><span class="sxs-lookup"><span data-stu-id="3e969-222">In the console tree, click **Send Ports**.</span></span> <span data-ttu-id="3e969-223">在 **发送端口** 窗格中，右键单击你发送端口，并依次 **启动**。</span><span class="sxs-lookup"><span data-stu-id="3e969-223">In the **Send Ports** pane, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a><span data-ttu-id="3e969-224">若要为 Fabrikam 创建方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="3e969-224">To create a party and a business profile for Fabrikam</span></span>  
  
1.  <span data-ttu-id="3e969-225">右键单击**方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="3e969-225">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="3e969-226">输入的名称在方 **名称** 文本中，然后单击 **确定**。</span><span class="sxs-lookup"><span data-stu-id="3e969-226">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e969-227">通过选择**本地 BizTalk 处理接收的消息从该参与方发送方或支持消息**复选框，你可以指定当事方正在创建将为同一个组织还承载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e969-227">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="3e969-228">此基础，某些属性将启用，或当您创建了协议时，禁用。</span><span class="sxs-lookup"><span data-stu-id="3e969-228">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="3e969-229">但是，对于本演练中，可以选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="3e969-229">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3.  <span data-ttu-id="3e969-230">右键单击方名称，指向 **新建**, ，然后单击 **业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="3e969-230">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4.  <span data-ttu-id="3e969-231">在 **配置文件属性** 对话框中，在 **常规** 页上，输入 **Fabrikam_Profile** 中 **名称** 文本框。</span><span class="sxs-lookup"><span data-stu-id="3e969-231">In the **Profile Properties** dialog box, on the **General** page, enter **Fabrikam_Profile** in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e969-232">在创建参与方时，也将创建一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="3e969-232">When you create a party, a profile is also created.</span></span> <span data-ttu-id="3e969-233">你可以重命名，并使用该配置文件而不是创建一个新。</span><span class="sxs-lookup"><span data-stu-id="3e969-233">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="3e969-234">若要重命名配置文件，右键单击配置文件，然后选择 **属性**。</span><span class="sxs-lookup"><span data-stu-id="3e969-234">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="3e969-235">在 **常规** 页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="3e969-235">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a><span data-ttu-id="3e969-236">为 Contoso 创建参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="3e969-236">To create a party and a business profile for Contoso</span></span>  
  
1.  <span data-ttu-id="3e969-237">右键单击**方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="3e969-237">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="3e969-238">输入的名称在方 **名称** 文本中，然后单击 **确定**。</span><span class="sxs-lookup"><span data-stu-id="3e969-238">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e969-239">通过选择**本地 BizTalk 处理接收的消息从该参与方发送方或支持消息**复选框，你可以指定当事方正在创建将为同一个组织还承载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e969-239">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="3e969-240">此基础，某些属性将启用，或当您创建了协议时，禁用。</span><span class="sxs-lookup"><span data-stu-id="3e969-240">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="3e969-241">但是，对于本演练中，可以选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="3e969-241">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3.  <span data-ttu-id="3e969-242">右键单击方名称，指向 **新建**, ，然后单击 **业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="3e969-242">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4.  <span data-ttu-id="3e969-243">在 **配置文件属性** 对话框中，在 **常规** 页上，输入 **Contoso_Profile** 中 **名称** 文本框。</span><span class="sxs-lookup"><span data-stu-id="3e969-243">In the **Profile Properties** dialog box, on the **General** page, enter **Contoso_Profile** in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e969-244">在创建参与方时，也将创建一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="3e969-244">When you create a party, a profile is also created.</span></span> <span data-ttu-id="3e969-245">你可以重命名，并使用该配置文件而不是创建一个新。</span><span class="sxs-lookup"><span data-stu-id="3e969-245">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="3e969-246">若要重命名配置文件，右键单击配置文件，然后选择 **属性**。</span><span class="sxs-lookup"><span data-stu-id="3e969-246">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="3e969-247">在 **常规** 页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="3e969-247">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-an-agreement-between-the-two-business-profiles"></a><span data-ttu-id="3e969-248">在两个业务配置文件之间创建协议</span><span class="sxs-lookup"><span data-stu-id="3e969-248">To create an agreement between the two business profiles</span></span>  
  
1.  <span data-ttu-id="3e969-249">右键单击 **Fabrikam_Profile**, ，指向 **新建**, ，然后单击 **协议**。</span><span class="sxs-lookup"><span data-stu-id="3e969-249">Right-click **Fabrikam_Profile**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="3e969-250">在 **常规属性** 页上，为 **名称** 文本框中，输入协议的名称。</span><span class="sxs-lookup"><span data-stu-id="3e969-250">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  
  
3.  <span data-ttu-id="3e969-251">从 **协议** 下拉列表中，选择 **X12**。</span><span class="sxs-lookup"><span data-stu-id="3e969-251">From the **Protocol** drop-down list, select **X12**.</span></span>  
  
4.  <span data-ttu-id="3e969-252">在 **第二个合作伙伴** 部分中，从 **名称** 下拉列表中，选择 **Contoso**。</span><span class="sxs-lookup"><span data-stu-id="3e969-252">In the **Second Partner** section, from the **Name** drop-down list, select **Contoso**.</span></span>  
  
5.  <span data-ttu-id="3e969-253">在 **第二个合作伙伴** 部分中，从 **配置文件** 下拉列表中，选择 **Contoso_Profile**。</span><span class="sxs-lookup"><span data-stu-id="3e969-253">In the **Second Partner** section, from the **Profile** drop-down list, select **Contoso_Profile**.</span></span>  
  
     <span data-ttu-id="3e969-254">你将注意到两个新选项卡获取旁边添加 **常规** 选项卡。每个选项卡配置一个单向协议，每个单向协议代表消息的一次完整事务（包括消息传输和确认传输）。</span><span class="sxs-lookup"><span data-stu-id="3e969-254">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way agreement and each one-way agreement represents one complete transaction of message (including message transfer and acknowledgement transfer).</span></span>  
  
6.  <span data-ttu-id="3e969-255">在 **常规** 选项卡上，在 **常规属性** 页上，在 **常见主机设置** 部分中，选择 **打开 reporting**, ，然后选择 **用于报告的应用商店消息负载**。</span><span class="sxs-lookup"><span data-stu-id="3e969-255">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**, and then select **Store message payload for reporting**.</span></span>  
  
7.  <span data-ttu-id="3e969-256">在上执行以下任务 **Fabrikam-> Contoso** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3e969-256">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  
  
    1.  <span data-ttu-id="3e969-257">上 **标识符** 下页上 **交换设置** 部分中，输入限定符和标识符字段的值 (**ISA5**, ，**ISA6**, ，**ISA7**, ，和 **ISA8**) 对应于测试消息中这些标头字段的值。</span><span class="sxs-lookup"><span data-stu-id="3e969-257">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3e969-258"> 要求为发送方和接收方的限定符和标识符字段输入值才能执行协议解析。</span><span class="sxs-lookup"><span data-stu-id="3e969-258"> requires the qualifier and identifier fields for sender and receiver in order to perform agreement resolution.</span></span> <span data-ttu-id="3e969-259">它将与匹配的值 **ISA5**, ，**ISA6**, ，**ISA7**, ，和 **ISA8** 与协议的属性中的交换标头中。</span><span class="sxs-lookup"><span data-stu-id="3e969-259">It will match the values of **ISA5**, **ISA6**, **ISA7**, and **ISA8** in the interchange header with those in the properties of an agreement.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3e969-260"> 此外将匹配的发件人限定符和 （而不是收件人限定符和标识符） 的标识符来解析协议。</span><span class="sxs-lookup"><span data-stu-id="3e969-260"> will also resolve the agreement by matching the sender qualifier and identifier (without the receiver qualifier and identifier).</span></span> <span data-ttu-id="3e969-261">如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法解析协议，则将使用后备协议属性。</span><span class="sxs-lookup"><span data-stu-id="3e969-261">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot resolve the agreement, it will use the fallback agreement properties.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3e969-262">如果你使用"EDI 接口开发人员教程"中的 SamplePO.txt 文件作为测试消息，设置 **ISA5** 到 **ZZ**, ，**ISA6** 到 **THEM**, ，**ISA7** 到 **ZZ**, ，和 **ISA8** 到 **美国**。</span><span class="sxs-lookup"><span data-stu-id="3e969-262">If you are using the SamplePO.txt file from the “EDI Interface Developer Tutorial” as your test message, set **ISA5** to **ZZ**, **ISA6** to **THEM**, **ISA7** to **ZZ**, and **ISA8** to **US**.</span></span>  
  
    2.  <span data-ttu-id="3e969-263">上 **确认** 下页上 **交换设置** 部分，选中 **预期的 TA1** 和 **997 预期**。</span><span class="sxs-lookup"><span data-stu-id="3e969-263">On the **Acknowledgement** page under the **Interchange Settings** section, check **TA1 Expected** and **997 Expected**.</span></span>  
  
    3.  <span data-ttu-id="3e969-264">上 **验证** 下页上 **交换设置** 部分中，请确保 **检查重复的 isa13** 选项处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="3e969-264">On the **Validation** page under the **Interchange Settings** section, make sure **Check for duplicate ISA13** option is unchecked.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3e969-265">清除 **检查重复的 isa13** 属性使您能够接收同一消息的多个实例。</span><span class="sxs-lookup"><span data-stu-id="3e969-265">Clearing the **Check for duplicate ISA13** property enables you to receive multiple instances of the same message.</span></span>  
  
    4.  <span data-ttu-id="3e969-266">上 **字符集和分隔符** 下页上 **交换设置** 部分中，选择 **CR LF** 选项。</span><span class="sxs-lookup"><span data-stu-id="3e969-266">On the **Charset and Separators** page under the **Interchange Settings** section, select the **CR LF** option.</span></span>  
  
    5.  <span data-ttu-id="3e969-267">上 **本地主机设置** 下页上 **交换设置** 部分中，清除 **路由 ACK 发送管道请求-响应接收端口** 选项。</span><span class="sxs-lookup"><span data-stu-id="3e969-267">On the **Local Host Settings** page under the **Interchange Settings** section, clear the **Route ACK to send pipeline on request-response receive port** option.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3e969-268">如果你使用的双向接收端口以接收交换并返回该确认，您需要检查 **路由 ACK 发送管道请求-响应接收端口**。</span><span class="sxs-lookup"><span data-stu-id="3e969-268">If you were using a two-way receive port to receive the interchange and return the acknowledgment, you would check **Route ACK to send pipeline on request-response receive port**.</span></span>  
  
    6.  <span data-ttu-id="3e969-269">上 **发送端口** 下页上 **交换设置** 部分中，将从 Fabrikam 交换将接收发送端口和将从 Contoso 接收确认发送端口相关联。</span><span class="sxs-lookup"><span data-stu-id="3e969-269">On the **Send Ports** page under the **Interchange Settings** section, associate the send ports that will be receiving the interchange from Fabrikam and the send ports that will be receiving the acknowledgements from Contoso.</span></span> <span data-ttu-id="3e969-270">在 **发送端口** 网格下 **名称** 列中，单击空单元格，然后从下拉列表中，选择创建用于从 Fabrikam 接收 EDI 交换发送端口。</span><span class="sxs-lookup"><span data-stu-id="3e969-270">In the **Send ports** grid, under the **Name** column, click an empty cell, and from the drop-down list, select the send port created for receiving the EDI interchange from Fabrikam.</span></span> <span data-ttu-id="3e969-271">对为接收 TA1 确认而创建的发送端口和为接收 997 确认而创建的发送端口重复执行该步骤。</span><span class="sxs-lookup"><span data-stu-id="3e969-271">Repeat the step for the send port created for receiving the TA1 acknowledgement and the send port created for receiving the 997 acknowledgement.</span></span>  
  
    7.  <span data-ttu-id="3e969-272">上 **验证** 下页上 **事务设置设置** 部分中，保留 **EDI 类型验证** 检查并检查 **扩展验证**。</span><span class="sxs-lookup"><span data-stu-id="3e969-272">On the **Validation** page under the **Transaction Set Settings** section, leave **EDI Type Validation** checked and check **Extended validation**.</span></span>  
  
    8.  <span data-ttu-id="3e969-273">如果你使用其中一个标准架构附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上**本地主机设置**下页上**事务设置设置**部分中，选择要用于对架构的命名空间处理传入的交换。</span><span class="sxs-lookup"><span data-stu-id="3e969-273">If you are using one of the standard schemas shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], on the **Local Host Settings** page under the **Transaction Set Settings** section, select the namespace for the schema to be used to process the incoming interchange.</span></span> <span data-ttu-id="3e969-274">如果使用自定义架构，输入中的值**自定义目标命名空间**网格中，以便[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以确定使用组和事务的命名空间设置标头值。</span><span class="sxs-lookup"><span data-stu-id="3e969-274">If using a custom schema, enter values in the **Customize Target namespace** grid, so that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can determine the namespace using group and transaction set header values.</span></span>  
  
    9. <span data-ttu-id="3e969-275">上 **包络线** 下页上 **事务设置设置** 部分中，输入网格的第一行中的所有列的值。</span><span class="sxs-lookup"><span data-stu-id="3e969-275">On the **Envelopes** page under the **Transaction Set Settings** section, enter values for all columns in the first line of the grid.</span></span>  
  
        |<span data-ttu-id="3e969-276">使用此选项</span><span class="sxs-lookup"><span data-stu-id="3e969-276">Use this</span></span>|<span data-ttu-id="3e969-277">执行的操作</span><span class="sxs-lookup"><span data-stu-id="3e969-277">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="3e969-278">**默认值**</span><span class="sxs-lookup"><span data-stu-id="3e969-278">**Default**</span></span>|<span data-ttu-id="3e969-279">选择 **默认**。</span><span class="sxs-lookup"><span data-stu-id="3e969-279">Select **Default**.</span></span> <span data-ttu-id="3e969-280">**注意︰**  当作为默认值的值选择此行 **GS1**, ，**GS2**, ，**GS3**, ，**GS7**, ，和 **GS8** 使用即使的值 **事务类型**, ，**版本/发行版**, ，和  **目标命名空间** 不是消息的匹配项。</span><span class="sxs-lookup"><span data-stu-id="3e969-280">**Note:**  When you select this row as the default, the values for **GS1**, **GS2**, **GS3**, **GS7**, and **GS8** are used even if the values for **Transaction Type**, **Version/Release**, and  **Target namespace** are not a match for the message.</span></span>|  
        |<span data-ttu-id="3e969-281">**事务类型**</span><span class="sxs-lookup"><span data-stu-id="3e969-281">**Transaction Type**</span></span>|<span data-ttu-id="3e969-282">选择你的测试消息的消息类型 **850-采购订单**。</span><span class="sxs-lookup"><span data-stu-id="3e969-282">Select the message type of your test message, **850 - Purchase Order**.</span></span>|  
        |<span data-ttu-id="3e969-283">**版本/发行版**</span><span class="sxs-lookup"><span data-stu-id="3e969-283">**Version/Release**</span></span>|<span data-ttu-id="3e969-284">输入的 EDI 版本中， **00401**。</span><span class="sxs-lookup"><span data-stu-id="3e969-284">Enter the EDI version, **00401**.</span></span>|  
        |<span data-ttu-id="3e969-285">**目标命名空间**</span><span class="sxs-lookup"><span data-stu-id="3e969-285">**Target namespace**</span></span>|<span data-ttu-id="3e969-286">选择**http://schemas.microsoft.com/Edi/X12**。</span><span class="sxs-lookup"><span data-stu-id="3e969-286">Select **http://schemas.microsoft.com/Edi/X12**.</span></span>|  
        |<span data-ttu-id="3e969-287">**GS1**</span><span class="sxs-lookup"><span data-stu-id="3e969-287">**GS1**</span></span>|<span data-ttu-id="3e969-288">验证是否已选中测试消息的消息类型， **PO-采购订单 (850)**。</span><span class="sxs-lookup"><span data-stu-id="3e969-288">Verify that the message type of the test message is selected, **PO - Purchase Order (850)**.</span></span>|  
        |<span data-ttu-id="3e969-289">**GS2**</span><span class="sxs-lookup"><span data-stu-id="3e969-289">**GS2**</span></span>|<span data-ttu-id="3e969-290">输入应用程序发送方的值。</span><span class="sxs-lookup"><span data-stu-id="3e969-290">Enter a value for the Application sender.</span></span>|  
        |<span data-ttu-id="3e969-291">**GS3**</span><span class="sxs-lookup"><span data-stu-id="3e969-291">**GS3**</span></span>|<span data-ttu-id="3e969-292">输入应用程序接收方的值。</span><span class="sxs-lookup"><span data-stu-id="3e969-292">Enter a value for the Application receiver.</span></span>|  
        |<span data-ttu-id="3e969-293">**GS4**</span><span class="sxs-lookup"><span data-stu-id="3e969-293">**GS4**</span></span>|<span data-ttu-id="3e969-294">选择所需的日期格式。</span><span class="sxs-lookup"><span data-stu-id="3e969-294">Select the date format that you want.</span></span> <span data-ttu-id="3e969-295">**注意︰**  你需要在下拉列表中选择值，而不仅仅是在要显示默认值的字段中单击。</span><span class="sxs-lookup"><span data-stu-id="3e969-295">**Note:**  You have to select the value in the drop-down list, not just click in the field to display the default.</span></span> <span data-ttu-id="3e969-296">如果你仅单击字段，而没有从下拉列表中选择值，则实际上并未选择值。</span><span class="sxs-lookup"><span data-stu-id="3e969-296">If you click in the field without selecting the value from the drop-down list, the value will not actually be selected.</span></span>|  
        |<span data-ttu-id="3e969-297">**GS5**</span><span class="sxs-lookup"><span data-stu-id="3e969-297">**GS5**</span></span>|<span data-ttu-id="3e969-298">选择所需的时间格式。</span><span class="sxs-lookup"><span data-stu-id="3e969-298">Select the time format that you want.</span></span>|  
        |<span data-ttu-id="3e969-299">**GS7**</span><span class="sxs-lookup"><span data-stu-id="3e969-299">**GS7**</span></span>|<span data-ttu-id="3e969-300">选择 **X 的公认的标准委员会 X12**。</span><span class="sxs-lookup"><span data-stu-id="3e969-300">Select **X - Accredited Standards Committee X12**.</span></span>|  
        |<span data-ttu-id="3e969-301">**GS8**</span><span class="sxs-lookup"><span data-stu-id="3e969-301">**GS8**</span></span>|<span data-ttu-id="3e969-302">验证 EDI 版本具有输入 **00401**。</span><span class="sxs-lookup"><span data-stu-id="3e969-302">Verify that the EDI version has been entered, **00401**.</span></span>|  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3e969-303"> 将为 GS01、 GS02、 GS03、 GS04、 GS05、 GS07 和基于为输入的值的出站确认 GS08 设置值**事务类型**，**版本/发行版**，和**目标命名空间**。</span><span class="sxs-lookup"><span data-stu-id="3e969-303"> will set the values for GS01, GS02, GS03, GS04, GS05, GS07, and GS08 of the outbound acknowledgments based on the values entered for **Transaction Type**, **Version/Release**, and **Target namespace**.</span></span> <span data-ttu-id="3e969-304">发送管道尝试将事务集类型、X12 版本和目标命名空间与消息标头中的对应值相匹配。</span><span class="sxs-lookup"><span data-stu-id="3e969-304">The send pipeline attempts to match the transaction set type, the X12 version, and the target namespace with the corresponding values in the header of the message.</span></span> <span data-ttu-id="3e969-305">如果成功，它将使用与关联的 GS 值 **事务类型**, ，**版本/发行版**, ，和 **目标命名空间** 值。</span><span class="sxs-lookup"><span data-stu-id="3e969-305">If successful, it uses the GS values associated with the **Transaction Type**, **Version/Release**, and **Target namespace** values.</span></span>  
  
8.  <span data-ttu-id="3e969-306">在上执行以下任务 **Contoso-> Fabrikam** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3e969-306">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e969-307">在此演练中，我们将指定的选项卡中所需的值，以便可以成功创建协议。</span><span class="sxs-lookup"><span data-stu-id="3e969-307">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="3e969-308">若要成功创建了协议，这两个单向协议选项必须为定义的值 **ISA5**, ，**ISA6**, ，**ISA7**, ，和 **ISA8**。</span><span class="sxs-lookup"><span data-stu-id="3e969-308">To successfully create an agreement, both one-way agreement tabs must have values defined for **ISA5**, **ISA6**, **ISA7**, and **ISA8**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e969-309">即使确认信息是相同的消息事务的一部分，在中配置应如何生成确认与相关属性 **Contoso-> Fabrikam** 选项卡。这是必需的因为确认上下文属性为发送者和接收者限定符设置为与中指定的值的符号相反**Contoso-> Fabrikam**选项卡。例如，如果发送方和接收方标识符设置为它们和中的美国**Fabrikam-> Contoso**选项卡、 发送和接收上下文属性将设置为美国和它们在确认消息。</span><span class="sxs-lookup"><span data-stu-id="3e969-309">Even though the acknowledgement is part of the same message transaction, the properties related to how the acknowledgement should be generated are configured in the **Contoso->Fabrikam** tab. This is required because the acknowledgement context properties for the sender and receiver qualifiers are set to the opposite of the values you specified in the **Contoso->Fabrikam** tab. For example, if sender and receiver identifiers are set to THEM and US in the **Fabrikam->Contoso** tab, the sender and receiver context properties will be set to US and THEM in the acknowledgement.</span></span> <span data-ttu-id="3e969-310">通常，其他单向协议选项卡中的发送方和接收方标识符也应分别设置为 US 和 THEM。</span><span class="sxs-lookup"><span data-stu-id="3e969-310">Typically, the other one-way agreement tab would also have the sender and receiver identifiers set to US and THEM respectively.</span></span> <span data-ttu-id="3e969-311">因此，确认消息将解析为该协议，并且将提取属性设置。</span><span class="sxs-lookup"><span data-stu-id="3e969-311">Hence, the acknowledgement message would resolve to that agreement and the properties setting will be picked.</span></span> <span data-ttu-id="3e969-312">因此，如果你想要使用不同的元素分隔符或如果你想要使用 CR LF 确认的确认，将指定的属性中 **Contoso-> Fabrikam** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3e969-312">So, if you want to have the acknowledgement to use different element separators or if you want to have the acknowledgement to use CR LF, specify the properties in the **Contoso->Fabrikam** tab.</span></span>  
    >   
    >  <span data-ttu-id="3e969-313">从概念上讲，将从任何单向协议选项卡上提取具有与确认上下文属性中设置的相同发件人和接收方限定符的确认的属性。</span><span class="sxs-lookup"><span data-stu-id="3e969-313">Conceptually, the properties for the acknowledgement will be picked from any one-way agreement tab that has the same sender and receiver qualifiers as set in the acknowledgement’s context properties.</span></span> <span data-ttu-id="3e969-314">但是，为了便于实际使用，你通常会在你创建的交换将解析为的协议的其他单向协议选项卡中设置此属性。</span><span class="sxs-lookup"><span data-stu-id="3e969-314">However, for ease of practical use, you would typically set this in the other one-way agreement tab of the agreement that you created to which the interchange would have resolved.</span></span>  
  
    1.  <span data-ttu-id="3e969-315">上 **标识符** 下页上 **交换设置** 部分中，输入限定符和标识符字段的值 (**ISA5**, ，**ISA6**, ，**ISA7**, ，和 **ISA8**) 对应于测试消息中这些标头字段的值。</span><span class="sxs-lookup"><span data-stu-id="3e969-315">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3e969-316">如果你使用"EDI 接口开发人员教程"中的 SamplePO.txt 文件作为测试消息，设置 **ISA5** 到 **ZZ**, ，**ISA6** 到 **美国**, ，**ISA7** 到 **ZZ**, ，和 **ISA8** 到 **THEM**。</span><span class="sxs-lookup"><span data-stu-id="3e969-316">If you are using the SamplePO.txt file from the “EDI Interface Developer Tutorial” as your test message, set **ISA5** to **ZZ**, **ISA6** to **US**, **ISA7** to **ZZ**, and **ISA8** to **THEM**.</span></span>  
  
9. <span data-ttu-id="3e969-317">单击 **“应用”**。</span><span class="sxs-lookup"><span data-stu-id="3e969-317">Click **Apply**.</span></span>  
  
10. <span data-ttu-id="3e969-318">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="3e969-318">Click **OK**.</span></span> <span data-ttu-id="3e969-319">新添加的协议被列入 **协议** 部分 **方和业务配置文件** 窗格。</span><span class="sxs-lookup"><span data-stu-id="3e969-319">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="3e969-320">默认情况下，启用新添加的协议。</span><span class="sxs-lookup"><span data-stu-id="3e969-320">The newly added agreement is enabled by default.</span></span>  
  
### <a name="testing-the-walkthrough"></a><span data-ttu-id="3e969-321">测试演练</span><span class="sxs-lookup"><span data-stu-id="3e969-321">Testing the Walkthrough</span></span>  
 <span data-ttu-id="3e969-322">本部分提供有关如何测试演练的信息。</span><span class="sxs-lookup"><span data-stu-id="3e969-322">This section provides information on how to test the walkthrough.</span></span>  
  
##### <a name="to-test-the-walkthrough"></a><span data-ttu-id="3e969-323">若要测试演练</span><span class="sxs-lookup"><span data-stu-id="3e969-323">To test the walkthrough</span></span>  
  
1.  <span data-ttu-id="3e969-324">在 Windows 资源管理器中，将测试 EDI 交换放置到本地接收文件夹中。</span><span class="sxs-lookup"><span data-stu-id="3e969-324">In Windows Explorer, drop the test EDI interchange into your local receive folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e969-325">对于测试消息，您可以使用在 EDI 接口开发人员教程中使用的 SamplePO.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="3e969-325">For a test message, you can use the SamplePO.txt file that is used in the EDI Interface Developer tutorial.</span></span> <span data-ttu-id="3e969-326">该文件位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial 文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e969-326">That file is shipped in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial folder.</span></span> <span data-ttu-id="3e969-327">这是一个 X12 850 消息。</span><span class="sxs-lookup"><span data-stu-id="3e969-327">This is an X12 850 message.</span></span> <span data-ttu-id="3e969-328">如果您使用此消息，则必须已经部署了 X12_00401_850.xsd 架构，该架构位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="3e969-328">If you use this message, you must have deployed the X12_00401_850.xsd schema that is shipped in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI folder.</span></span> <span data-ttu-id="3e969-329">不能使用位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] XSD_Schema 文件夹的 X12 850 架构。</span><span class="sxs-lookup"><span data-stu-id="3e969-329">You must not use the X12 850 schema in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema folder.</span></span>  
  
2.  <span data-ttu-id="3e969-330">打开与交换的发送端口关联的文件夹，并验证该文件夹是否包含 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="3e969-330">Open the folder that you associated with the send port for interchanges, and verify that it contains the EDI interchange.</span></span>  
  
3.  <span data-ttu-id="3e969-331">打开与 997 确认的发送端口关联的文件夹，并验证该文件夹是否包含 997 确认。</span><span class="sxs-lookup"><span data-stu-id="3e969-331">Open the folder that you associated with the send port for the 997 acknowledgment, and verify that it contains a 997 acknowledgment.</span></span>  
  
4.  <span data-ttu-id="3e969-332">打开与 TA1 确认的发送端口关联的文件夹，并验证该文件夹是否包含 TA1 确认。</span><span class="sxs-lookup"><span data-stu-id="3e969-332">Open the folder that you associated with the send port for the TA1 acknowledgment, and verify that it contains a TA1 acknowledgment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e969-333">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e969-333">See Also</span></span>  
 [<span data-ttu-id="3e969-334">开发和配置 BizTalk Server EDI 解决方案</span><span class="sxs-lookup"><span data-stu-id="3e969-334">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)