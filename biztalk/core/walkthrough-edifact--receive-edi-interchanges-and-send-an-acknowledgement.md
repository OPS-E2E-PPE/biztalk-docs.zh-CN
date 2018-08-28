---
title: '演练 (EDIFACT): 接收 EDI 交换并发送回确认 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02751f0c-8e7e-4879-93e4-8bc475640756
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b221d47a64f603db697b99c7e5a60b1cb1a67bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018887"
---
# <a name="walkthrough-edifact-receiving-edi-interchanges-and-sending-back-an-acknowledgement"></a><span data-ttu-id="e72d0-102">演练 (EDIFACT)：接收 EDI 交换并发送回确认信息</span><span class="sxs-lookup"><span data-stu-id="e72d0-102">Walkthrough (EDIFACT): Receiving EDI Interchanges and Sending Back an Acknowledgement</span></span>
<span data-ttu-id="e72d0-103">本演练将介绍使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 为接收 EDIFACT 交换创建解决方案的分步操作过程。</span><span class="sxs-lookup"><span data-stu-id="e72d0-103">This walkthrough provides a set of step-by-step procedures that creates a solution for receiving EDIFACT interchanges using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="e72d0-104">在此解决方案中，EDIFACT 交换从贸易合作伙伴 （Fabrikam) 发送到另一个贸易合作伙伴 Contoso。</span><span class="sxs-lookup"><span data-stu-id="e72d0-104">In this solution, an EDIFACT interchange is sent from a trading partner, Fabrikam, to another trading partner, Contoso.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="e72d0-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="e72d0-105">Prerequisites</span></span>  
 <span data-ttu-id="e72d0-106">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="e72d0-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  

## <a name="how-the-solution-receives-edifact-interchanges"></a><span data-ttu-id="e72d0-107">解决方案如何接收 EDIFACT 交换</span><span class="sxs-lookup"><span data-stu-id="e72d0-107">How the Solution Receives EDIFACT Interchanges</span></span>  
 <span data-ttu-id="e72d0-108">该解决方案将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e72d0-108">The solution will do the following:</span></span>  

> [!NOTE]
>  <span data-ttu-id="e72d0-109">此列表中的事件可能不会按所示顺序发生。</span><span class="sxs-lookup"><span data-stu-id="e72d0-109">The events in this list may not occur in the order shown.</span></span>  

1.  <span data-ttu-id="e72d0-110">接收来自贸易合作伙伴 Fabrikam 的平面文件 EDIFACT 交换。</span><span class="sxs-lookup"><span data-stu-id="e72d0-110">Receive a flat-file EDIFACT interchange from the trading partner Fabrikam.</span></span>  

2.  <span data-ttu-id="e72d0-111">验证针对其架构的 EDIFACT 交换，将消息拆装成 XML，并将消息 XML 放置到 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="e72d0-111">Validate the EDIFACT interchange against its schema, disassemble the message into XML, and drop the message XML into the MessageBox.</span></span>  

3.  <span data-ttu-id="e72d0-112">为收到的 EDI 交换生成技术确认 （收到的消息） 并放置到 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="e72d0-112">Generate a technical acknowledgement (receipt of message) to the received EDI interchange, and drop it in the MessageBox.</span></span>  

4.  <span data-ttu-id="e72d0-113">生成功能确认 （接受或拒绝收到的 EDI 交换），并放置到 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="e72d0-113">Generate a functional acknowledgment (acceptance or rejection of the received EDI interchange), and drop it in the MessageBox.</span></span>  

5.  <span data-ttu-id="e72d0-114">提取消息 XML 通过单向 FILE 发送端口，并组装消息 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="e72d0-114">Pick up the message XML by a one-way FILE send port, and assemble the message EDI interchange.</span></span>  

6.  <span data-ttu-id="e72d0-115">将 EDI 交换发送到 Contoso 本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="e72d0-115">Send the EDI interchange to Contoso local folder.</span></span>  

7.  <span data-ttu-id="e72d0-116">提取的技术确认的单向 FILE 发送端口，并组装交换。</span><span class="sxs-lookup"><span data-stu-id="e72d0-116">Pick up the technical acknowledgement by a one-way FILE send port, and assemble the interchange.</span></span>  

8.  <span data-ttu-id="e72d0-117">将技术确认发送到 Fabrikam 本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="e72d0-117">Send the technical acknowledgement to the Fabrikam local folder.</span></span>  

9. <span data-ttu-id="e72d0-118">选择功能确认的单向 FILE 发送端口，并组装交换。</span><span class="sxs-lookup"><span data-stu-id="e72d0-118">Pick up the functional acknowledgement by a one-way FILE send port, and assemble the interchange.</span></span>  

10. <span data-ttu-id="e72d0-119">向 Fabrikam 发送功能确认。</span><span class="sxs-lookup"><span data-stu-id="e72d0-119">Send the functional acknowledgement to Fabrikam.</span></span>  

## <a name="the-functionality-in-this-solution"></a><span data-ttu-id="e72d0-120">此解决方案中的功能</span><span class="sxs-lookup"><span data-stu-id="e72d0-120">The Functionality in this Solution</span></span>  
 <span data-ttu-id="e72d0-121">为进行此演练，将启用以下功能：</span><span class="sxs-lookup"><span data-stu-id="e72d0-121">For the purposes of this walkthrough, the following functionality will be enabled:</span></span>  

- <span data-ttu-id="e72d0-122">该解决方案专用于使用 EDIFACT 编码的交换</span><span class="sxs-lookup"><span data-stu-id="e72d0-122">The solution is designed for interchanges using EDIFACT encoding</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="e72d0-123">有关如何创建类似的解决方案，对于 X12 交换的说明，请参阅[演练 (X12)： 接收 EDI 交换并发送回确认信息](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)。</span><span class="sxs-lookup"><span data-stu-id="e72d0-123">For instructions on how to create a similar solution for X12 interchanges, see [Walkthrough (X12): Receiving EDI Interchanges and Sending Back an Acknowledgement](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md).</span></span>  

- <span data-ttu-id="e72d0-124">EDI 类型和扩展的验证将在传入交换上执行。</span><span class="sxs-lookup"><span data-stu-id="e72d0-124">EDI type and extended validation will be performed on the incoming interchange.</span></span>  

- <span data-ttu-id="e72d0-125">将生成技术确认和功能确认，以返回给交换的发送方。</span><span class="sxs-lookup"><span data-stu-id="e72d0-125">Technical and functional acknowledgments will be generated for returning to the sender of the interchange.</span></span>  

- <span data-ttu-id="e72d0-126">该解决方案使用传输类型为 FILE 的单向接收位置。</span><span class="sxs-lookup"><span data-stu-id="e72d0-126">The solution uses a one-way receive location with a FILE transport type.</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="e72d0-127">您可以使用双向要求响应接收端口和位置来接收消息，但如果这样，接收位置将无法使用 FILE 传输类型。</span><span class="sxs-lookup"><span data-stu-id="e72d0-127">You can use a two-way solicit response receive port and location to receive the message, but if you do so, you will not be able to use a FILE transport type for the receive location.</span></span> <span data-ttu-id="e72d0-128">有关详细信息，请参阅[配置为接收 EDI 消息和确认的端口](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md)。</span><span class="sxs-lookup"><span data-stu-id="e72d0-128">For more information, see [Configuring a Port to Receive EDI Messages and Acknowledgments](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md).</span></span>  

- <span data-ttu-id="e72d0-129">系统将启用 EDI 报告功能，并保存事务集以便从交换状态报告进行查看。</span><span class="sxs-lookup"><span data-stu-id="e72d0-129">EDI reporting will be enabled, and transaction sets will be saved for viewing from the interchange status report.</span></span>  

- <span data-ttu-id="e72d0-130">出于测试目的，解决方案使用三个发送端口将 EDIFACT 交换和创建的确认发送到本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="e72d0-130">For testing purposes, the solution uses three send ports to send the EDIFACT interchange and the ACKs created to local folders.</span></span>  

  <span data-ttu-id="e72d0-131">下图显示了此解决方案的结构：</span><span class="sxs-lookup"><span data-stu-id="e72d0-131">The following figure shows the architecture for this solution:</span></span>  

  <span data-ttu-id="e72d0-132">![接收 EDIFACT 交换和发送确认](../core/media/edifact-walkthrough.gif "EDIFACT_Walkthrough")</span><span class="sxs-lookup"><span data-stu-id="e72d0-132">![Receiving EDIFACT interchange and sending an ACK](../core/media/edifact-walkthrough.gif "EDIFACT_Walkthrough")</span></span>  

## <a name="configuring-and-testing-the-walkthrough"></a><span data-ttu-id="e72d0-133">配置和测试演练</span><span class="sxs-lookup"><span data-stu-id="e72d0-133">Configuring and Testing the Walkthrough</span></span>  
 <span data-ttu-id="e72d0-134">该解决方案所需的过程包括：</span><span class="sxs-lookup"><span data-stu-id="e72d0-134">The procedures required for this solution include the following:</span></span>  

- <span data-ttu-id="e72d0-135">将必需的消息架构添加到 BizTalk 项目，然后生成并部署该项目，使 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在处理收到的交换时可以使用相应架构。</span><span class="sxs-lookup"><span data-stu-id="e72d0-135">Add the required message schema(s) to a BizTalk project, and then build and deploy the project, making the schema(s) available for use by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in processing the received interchange.</span></span>  

- <span data-ttu-id="e72d0-136">为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建一个单向接收端口，以便接收来自贸易合作伙伴的 EDIFACT 交换，并生成确认。</span><span class="sxs-lookup"><span data-stu-id="e72d0-136">Create a one-way receive port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive the EDIFACT interchange from the trading partner and generate an acknowledgment.</span></span> <span data-ttu-id="e72d0-137">此接收位置与 Fabrikam 存放要发送到 Contoso 的 EDIFACT 交换的 file 文件夹相关联。</span><span class="sxs-lookup"><span data-stu-id="e72d0-137">This receive location is tied to the file folder where Fabrikam drops the EDIFACT interchange to be sent to Contoso.</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="e72d0-138">可以使用双向要求响应接收端口和位置来接收消息，但如果这样做，您将不能为接收位置使用 FILE 传输类型。</span><span class="sxs-lookup"><span data-stu-id="e72d0-138">You can use a two-way solicit response receive port and location to receive the message, but if you do, you will not be able to use a FILE transport type for the receive location.</span></span>  

- <span data-ttu-id="e72d0-139">创建一个用于向地 Contoso 文件夹发送 EDI 交换的发送端口，以及一个用于向本地 Fabrikam 文件夹发送技术和功能确认的发送端口。</span><span class="sxs-lookup"><span data-stu-id="e72d0-139">Create one send port that sends the EDI interchange to a local Contoso folder and another that sends the technical and functional acknowledgements to a local Fabrikam folder.</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="e72d0-140">与 X12 确认不同，功能确认和技术确认的消息类型相同。</span><span class="sxs-lookup"><span data-stu-id="e72d0-140">Unlike X12 acknowledgements, the message types for both the functional and technical acknowledgements are same.</span></span> <span data-ttu-id="e72d0-141">因此，使用 `BTS.MessageType` 上下文属性创建的发送端口筛选器将筛选这两种确认，并将其传递到同一文件夹。</span><span class="sxs-lookup"><span data-stu-id="e72d0-141">Hence, the send port filter created using the `BTS.MessageType` context property filters both the acknowledgements and delivers them to the same folder.</span></span>  

- <span data-ttu-id="e72d0-142">为 Fabrikam 和 Contoso 创建参与方（贸易合作伙伴）。</span><span class="sxs-lookup"><span data-stu-id="e72d0-142">Create a party (trading partner) for both Fabrikam and Contoso.</span></span>  

- <span data-ttu-id="e72d0-143">为两个贸易合作伙伴分别创建一个业务配置文件。</span><span class="sxs-lookup"><span data-stu-id="e72d0-143">Create a business profile each for both the trading partners.</span></span>  

- <span data-ttu-id="e72d0-144">创建通过配置要接收的消息的 EDI 属性的两个配置文件和确认之间的协议来发送。</span><span class="sxs-lookup"><span data-stu-id="e72d0-144">Create an agreement between the two profiles by configuring the EDI properties for the message to be received and the acknowledgment to be sent.</span></span>  

- <span data-ttu-id="e72d0-145">测试本演练使用 EDIFACT 交换的测试。</span><span class="sxs-lookup"><span data-stu-id="e72d0-145">Test the walkthrough using a test EDIFACT interchange.</span></span> <span data-ttu-id="e72d0-146">在本演练中，可以复制并粘贴以下内容的文本文件。</span><span class="sxs-lookup"><span data-stu-id="e72d0-146">For this walkthrough, you can copy-paste the following into a text file.</span></span> <span data-ttu-id="e72d0-147">此文件的架构是 EFACT_D98A_APERAK.xsd。</span><span class="sxs-lookup"><span data-stu-id="e72d0-147">The schema for this file is EFACT_D98A_APERAK.xsd.</span></span>  

  ```  
  UNA:+,?*'  
  UNB+UNOB:1+7654321:ZZZ+1234567:ZZZ+353501:3023+UNB5'  
  UNG+INVOIC+UNG2.1:ZZZ+UNG3.1:ZZZ+060413:2314+UNG5+UN+D:98B'  
  UNH+UNH1+APERAK:D:98A:UN++13+UNH5.1+UNH6.1+UNH7.1'  
  BGM+1+C10601'  
  DTM+10'  
  FTX+AAA++C10701+C10801'  
  CNT+1:14'  
  RFF+AAA'  
  DTM+10'  
  NAD+AA+C08201+C05801+C08001+C05901'  
  CTA++C05601'  
  COM+C07601:AA'  
  ERC+C90101'  
  FTX+AAA++C10701+C10801'  
  RFF+AAA'  
  FTX+AAA++C10701+C10801'  
  UNT+15+UNH1'  
  UNE+1+UNG5'  
  UNZ+1+UNB5'  
  ```  

### <a name="configuring-the-walkthrough"></a><span data-ttu-id="e72d0-148">配置演练</span><span class="sxs-lookup"><span data-stu-id="e72d0-148">Configuring the Walkthrough</span></span>  
 <span data-ttu-id="e72d0-149">本部分介绍配置本演练的步骤。</span><span class="sxs-lookup"><span data-stu-id="e72d0-149">This section describes the procedures to configure the walkthrough.</span></span>  

##### <a name="to-deploy-the-message-schema"></a><span data-ttu-id="e72d0-150">部署消息架构</span><span class="sxs-lookup"><span data-stu-id="e72d0-150">To deploy the message schema</span></span>  

1. <span data-ttu-id="e72d0-151">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，创建或打开 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="e72d0-151">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create or open a BizTalk project.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="e72d0-152">本主题假定你已从你的应用程序添加了对包含 EDI 架构、管道和业务流程的 BizTalk EDI 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="e72d0-152">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="e72d0-153">如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。</span><span class="sxs-lookup"><span data-stu-id="e72d0-153">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  

2. <span data-ttu-id="e72d0-154">右键单击你的项目，指向**外**，然后单击**现有项**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-154">Right-click your project, point to **Add**, and then click **Existing Item**.</span></span> <span data-ttu-id="e72d0-155">转到您的架构是中的文件夹[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\EDIFACT\D98A，然后双击您的架构 (**EFACT_D98A_APERAK.xsd**)。</span><span class="sxs-lookup"><span data-stu-id="e72d0-155">Move to the folder that your schema is in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\EDIFACT\D98A, and then double-click your schema (**EFACT_D98A_APERAK.xsd**).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="e72d0-156">如果你使用本主题中提供的示例测试消息，则必须使用**EFACT_D98A_APERAK.xsd**架构。</span><span class="sxs-lookup"><span data-stu-id="e72d0-156">If you are using the sample test message provided in this topic, you must use the **EFACT_D98A_APERAK.xsd** schema.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="e72d0-157">如果 EDI 架构尚未解压缩到 \XSD_Schema\EDI 文件夹，则执行**MicrosoftEdiXSDTemplates.exe** \XSD_Schema\EDI 文件夹将架构解压缩到默认文件夹中的文件。</span><span class="sxs-lookup"><span data-stu-id="e72d0-157">If the EDI schemas have not been unzipped into the \XSD_Schema\EDI folders, execute the **MicrosoftEdiXSDTemplates.exe** file in the \XSD_Schema\EDI folder to unzip the schemas into the default folder.</span></span>  

3. <span data-ttu-id="e72d0-158">将程序集密钥文件添加到项目中，然后生成并部署该程序集。</span><span class="sxs-lookup"><span data-stu-id="e72d0-158">Add the assembly key file to the project, and then build and deploy the assembly.</span></span>  

##### <a name="to-create-a-one-way-receive-port-for-fabrikam-to-receive-the-edi-interchange"></a><span data-ttu-id="e72d0-159">若要创建一个单向接收端口 （对于 Fabrikam) 接收 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="e72d0-159">To create a one-way receive port (for Fabrikam) to receive the EDI interchange</span></span>  

1. <span data-ttu-id="e72d0-160">在 Windows 资源管理器中，创建用于接收交换的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="e72d0-160">In Windows Explorer, create a local folder to receive the interchange.</span></span>  

2. <span data-ttu-id="e72d0-161">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-161">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Receive Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **One-way Receive Port**.</span></span>  

3. <span data-ttu-id="e72d0-162">接收端口的名称，然后单击**接收位置**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="e72d0-162">Name the receive port, and then click **Receive Locations** in the console tree.</span></span>  

4. <span data-ttu-id="e72d0-163">单击 **“新建”**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-163">Click **New**.</span></span>  

5. <span data-ttu-id="e72d0-164">名称的接收位置，选择**文件**有关**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-164">Name the receive location, select **FILE** for **Type**, and then click **Configure**.</span></span>  

6. <span data-ttu-id="e72d0-165">浏览到文件夹**接收文件夹**文本框。</span><span class="sxs-lookup"><span data-stu-id="e72d0-165">Browse to a folder for **Receive folder** text box.</span></span> <span data-ttu-id="e72d0-166">在此过程的步骤 1 中创建此文件夹。</span><span class="sxs-lookup"><span data-stu-id="e72d0-166">You created this folder in step 1 of this procedure.</span></span> <span data-ttu-id="e72d0-167">输入文件掩码，如 **\*.edi**或 **\*.txt**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-167">Enter a file mask, such as **\*.edi** or **\*.txt**.</span></span>  

7. <span data-ttu-id="e72d0-168">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="e72d0-168">Click **OK**.</span></span>  

8. <span data-ttu-id="e72d0-169">有关**接收管道**，选择**EdiReceive**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-169">For **Receive pipeline**, select **EdiReceive**.</span></span>  

9. <span data-ttu-id="e72d0-170">单击**确定**中**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="e72d0-170">Click **OK** in the **Receive Location Properties** dialog box.</span></span> <span data-ttu-id="e72d0-171">单击**确定**中再次**接收端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="e72d0-171">Click **OK** again in the **Receive Port Properties** dialog box.</span></span>  

10. <span data-ttu-id="e72d0-172">在控制台树中，单击**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-172">In the console tree, click **Receive Locations**.</span></span> <span data-ttu-id="e72d0-173">在中**接收位置**窗格中，右键单击将接收位置，然后依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-173">In the **Receive Locations** pane, right-click your receive location, and then click **Enable**.</span></span>  

##### <a name="to-create-a-static-one-way-send-port-for-contoso-to-send-the-edi-interchange"></a><span data-ttu-id="e72d0-174">（为 Contoso) 创建静态单向发送端口以发送 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="e72d0-174">To create a static one-way send port (for Contoso) to send the EDI interchange</span></span>  

1. <span data-ttu-id="e72d0-175">在 Windows 资源管理器中，创建一个用于接收测试交换的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="e72d0-175">In Windows Explorer, create a local folder to send the test interchange to.</span></span>  

2. <span data-ttu-id="e72d0-176">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-176">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static One-way Send Port**.</span></span>  

3. <span data-ttu-id="e72d0-177">在中**发送端口属性**对话框中，发送端口名称。</span><span class="sxs-lookup"><span data-stu-id="e72d0-177">In the **Send Port Properties** dialog box, name the send port.</span></span>  

4. <span data-ttu-id="e72d0-178">在中**传输**部分中，选择**文件**有关**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-178">In the **Transport** section, select **FILE** for **Type**, and then click **Configure**.</span></span>  

5. <span data-ttu-id="e72d0-179">有关**目标文件夹**，浏览到要接收的交换的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e72d0-179">For **Destination folder**, browse to the folder to receive the interchange.</span></span> <span data-ttu-id="e72d0-180">在此过程的步骤 1 中创建此文件夹。</span><span class="sxs-lookup"><span data-stu-id="e72d0-180">You created this folder in step 1 of this procedure.</span></span> <span data-ttu-id="e72d0-181">有关**文件掩码**，输入交换格式，如 **\*.edi**或 **\*.txt**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-181">For **File mask**, enter the interchange format, such as **\*.edi** or **\*.txt**.</span></span>  

6. <span data-ttu-id="e72d0-182">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="e72d0-182">Click **OK**.</span></span>  

7. <span data-ttu-id="e72d0-183">在中**发送管道**，选择**EdiSend**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-183">In **Send pipeline**, select **EdiSend**.</span></span>  

8. <span data-ttu-id="e72d0-184">在控制台树中，选择**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-184">In the console tree, select **Filters**.</span></span> <span data-ttu-id="e72d0-185">输入用于订阅 EDI 交换的筛选器。</span><span class="sxs-lookup"><span data-stu-id="e72d0-185">Enter a filter to subscribe to the EDI interchange.</span></span> <span data-ttu-id="e72d0-186">例如，对于**属性**，输入**BTS。MessageType**; 对于**运算符**，输入**==**; 对于**值**交换，请输入架构`http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006#EFACT_D98A_APERAK`。</span><span class="sxs-lookup"><span data-stu-id="e72d0-186">For example, for **Property**, enter **BTS.MessageType**; for **Operator**, enter **==**; and for **Value** enter the schema for the interchange, `http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006#EFACT_D98A_APERAK`.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="e72d0-187">以上筛选器设置可确保将交换（而不是确认）发送到与此发送端口相关联的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e72d0-187">The above filter setting ensures that interchanges, not acknowledgments, will be sent to the folder associated with this send port.</span></span>  

9. <span data-ttu-id="e72d0-188">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="e72d0-188">Click **OK**.</span></span>  

10. <span data-ttu-id="e72d0-189">在控制台树中，单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-189">In the console tree, click **Send Ports**.</span></span> <span data-ttu-id="e72d0-190">在中**发送端口**窗格中，右键单击您的发送端口，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-190">In the **Send Ports** pane, right-click your send port, and then click **Start**.</span></span>  

##### <a name="to-create-a-static-one-way-send-port-to-send-the-acknowledgments"></a><span data-ttu-id="e72d0-191">若要创建静态单向发送端口以发送确认</span><span class="sxs-lookup"><span data-stu-id="e72d0-191">To create a static one-way send port to send the acknowledgments</span></span>  

1. <span data-ttu-id="e72d0-192">在 Windows 资源管理器中，创建一个用于接收到的技术和功能确认的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="e72d0-192">In Windows Explorer, create a local folder to send the technical and functional acknowledgments to.</span></span>  

2. <span data-ttu-id="e72d0-193">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-193">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static One-way Send Port**.</span></span>  

3. <span data-ttu-id="e72d0-194">在中**发送端口属性**对话框中，发送端口名称。</span><span class="sxs-lookup"><span data-stu-id="e72d0-194">In the **Send Port Properties** dialog box, name the send port.</span></span>  

4. <span data-ttu-id="e72d0-195">在中**传输**部分中，选择**文件**有关**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-195">In the **Transport** section, select **FILE** for **Type**, and then click **Configure**.</span></span>  

5. <span data-ttu-id="e72d0-196">有关**目标文件夹**，浏览到用于接收两个确认的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e72d0-196">For **Destination folder**, browse to a folder to receive the two acknowledgments.</span></span> <span data-ttu-id="e72d0-197">在此过程的步骤 1 中创建此文件夹。</span><span class="sxs-lookup"><span data-stu-id="e72d0-197">You created this folder in step 1 of this procedure.</span></span> <span data-ttu-id="e72d0-198">有关**文件掩码**，输入交换格式，如 **\*.edi**或 **\*.txt**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-198">For **File mask**, enter the interchange format, such as **\*.edi** or **\*.txt**.</span></span>  

6. <span data-ttu-id="e72d0-199">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="e72d0-199">Click **OK**.</span></span>  

7. <span data-ttu-id="e72d0-200">在中**发送管道**，选择**EdiSend**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-200">In **Send pipeline**, select **EdiSend**.</span></span>  

8. <span data-ttu-id="e72d0-201">在控制台树中，选择**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-201">In the console tree, select **Filters**.</span></span> <span data-ttu-id="e72d0-202">输入用于订阅确认的筛选器。</span><span class="sxs-lookup"><span data-stu-id="e72d0-202">Enter a filter to subscribe to acknowledgments.</span></span> <span data-ttu-id="e72d0-203">例如，对于**属性**，输入**BTS。MessageType**; 对于**运算符**，输入**==**; 对于**值**确认，请输入架构`http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`。</span><span class="sxs-lookup"><span data-stu-id="e72d0-203">For example, for **Property**, enter **BTS.MessageType**; for **Operator**, enter **==**; and for **Value** enter the schema for the acknowledgment, `http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`.</span></span>  

9. <span data-ttu-id="e72d0-204">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="e72d0-204">Click **OK**.</span></span>  

10. <span data-ttu-id="e72d0-205">在控制台树中，单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-205">In the console tree, click **Send Ports**.</span></span> <span data-ttu-id="e72d0-206">在中**发送端口**窗格中，右键单击您的发送端口，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-206">In the **Send Ports** pane, right-click your send port, and then click **Start**.</span></span>  

##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a><span data-ttu-id="e72d0-207">创建 Fabrikam 参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="e72d0-207">To create a party and a business profile for Fabrikam</span></span>  

1. <span data-ttu-id="e72d0-208">右键单击**参与方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-208">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  

2. <span data-ttu-id="e72d0-209">输入中的参与方的名称**名称**文本框中，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-209">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="e72d0-210">通过选择**本地 BizTalk 处理接收的来自此参与方发送消息的参与方或支持消息**复选框，可以指定要创建的参与方是为同一组织与托管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e72d0-210">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="e72d0-211">此基础，某些属性将启用，或禁用在创建协议时。</span><span class="sxs-lookup"><span data-stu-id="e72d0-211">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="e72d0-212">但是，对于此演练中，可以选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="e72d0-212">However, for this walkthrough, you can leave this check box selected.</span></span>  

3. <span data-ttu-id="e72d0-213">右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-213">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  

4. <span data-ttu-id="e72d0-214">在中**配置文件属性**对话框中，在**常规**页上，输入**Fabrikam_Profile**中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="e72d0-214">In the **Profile Properties** dialog box, on the **General** page, enter **Fabrikam_Profile** in the **Name** text box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="e72d0-215">创建一个参与方时，还创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="e72d0-215">When you create a party, a profile is also created.</span></span> <span data-ttu-id="e72d0-216">可以重命名，并使用该配置文件而不是创建一个新。</span><span class="sxs-lookup"><span data-stu-id="e72d0-216">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="e72d0-217">若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-217">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="e72d0-218">在中**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="e72d0-218">In the **General** page, specify a name for the profile.</span></span>  

##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a><span data-ttu-id="e72d0-219">为 Contoso 创建参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="e72d0-219">To create a party and a business profile for Contoso</span></span>  

1. <span data-ttu-id="e72d0-220">右键单击**参与方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-220">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  

2. <span data-ttu-id="e72d0-221">输入中的参与方的名称**名称**文本框中，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-221">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="e72d0-222">通过选择**本地 BizTalk 处理接收的来自此参与方发送消息的参与方或支持消息**复选框，可以指定要创建的参与方是为同一组织与托管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e72d0-222">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="e72d0-223">此基础，某些属性将启用，或禁用在创建协议时。</span><span class="sxs-lookup"><span data-stu-id="e72d0-223">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="e72d0-224">但是，对于此演练中，可以选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="e72d0-224">However, for this walkthrough, you can leave this check box selected.</span></span>  

3. <span data-ttu-id="e72d0-225">右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-225">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  

4. <span data-ttu-id="e72d0-226">在中**配置文件属性**对话框中，在**常规**页上，输入**Contoso_Profile**中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="e72d0-226">In the **Profile Properties** dialog box, on the **General** page, enter **Contoso_Profile** in the **Name** text box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="e72d0-227">创建一个参与方时，还创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="e72d0-227">When you create a party, a profile is also created.</span></span> <span data-ttu-id="e72d0-228">可以重命名，并使用该配置文件而不是创建一个新。</span><span class="sxs-lookup"><span data-stu-id="e72d0-228">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="e72d0-229">若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-229">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="e72d0-230">在中**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="e72d0-230">In the **General** page, specify a name for the profile.</span></span>  

##### <a name="to-create-an-agreement-between-the-two-business-profiles"></a><span data-ttu-id="e72d0-231">在两个业务配置文件之间创建协议</span><span class="sxs-lookup"><span data-stu-id="e72d0-231">To create an agreement between the two business profiles</span></span>  

1. <span data-ttu-id="e72d0-232">右键单击**Fabrikam_Profile**，依次指向**新建**，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-232">Right-click **Fabrikam_Profile**, point to **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="e72d0-233">在**常规属性**页上，对于**名称**文字框中，输入协议的名称。</span><span class="sxs-lookup"><span data-stu-id="e72d0-233">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  

3. <span data-ttu-id="e72d0-234">从**协议**下拉列表中，选择**EDIFACT**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-234">From the **Protocol** drop-down list, select **EDIFACT**.</span></span>  

4. <span data-ttu-id="e72d0-235">在中**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**Contoso**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-235">In the **Second Partner** section, from the **Name** drop-down list, select **Contoso**.</span></span>  

5. <span data-ttu-id="e72d0-236">在中**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**Contoso_Profile**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-236">In the **Second Partner** section, from the **Profile** drop-down list, select **Contoso_Profile**.</span></span>  

    <span data-ttu-id="e72d0-237">你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡配置一个单向协议，每个单向协议代表消息的一次完整事务（包括消息传输和确认传输）。</span><span class="sxs-lookup"><span data-stu-id="e72d0-237">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way agreement and each one-way agreement represents one complete transaction of message (including message transfer and acknowledgement transfer).</span></span>  

6. <span data-ttu-id="e72d0-238">在中**常规**选项卡中，**常规属性**页上，在**公用主机设置**部分中，选择**打开报告**，，然后选择**存储消息负载以用于报告**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-238">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**, and then select **Store message payload for reporting**.</span></span>  

7. <span data-ttu-id="e72d0-239">在执行以下任务**Fabrikam-> Contoso**选项卡。</span><span class="sxs-lookup"><span data-stu-id="e72d0-239">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  

   1. <span data-ttu-id="e72d0-240">上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**UNB2.1**， **UNB2.2**， **UNB3.1**，和**UNB3.2**) 的测试消息中这些标头字段的值相对应。</span><span class="sxs-lookup"><span data-stu-id="e72d0-240">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**UNB2.1**, **UNB2.2**, **UNB3.1**, and **UNB3.2**) that correspond to the values for those header fields in your test message.</span></span>  

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e72d0-241"> 要求为发送方和接收方的限定符和标识符字段输入值才能执行协议解析。</span><span class="sxs-lookup"><span data-stu-id="e72d0-241"> requires the qualifier and identifier fields for sender and receiver in order to perform agreement resolution.</span></span> <span data-ttu-id="e72d0-242">它将匹配的值**UNB2.1**， **UNB2.2**， **UNB3.1**，以及**UNB3.2**与中的属性的交换标头中协议。</span><span class="sxs-lookup"><span data-stu-id="e72d0-242">It will match the values of **UNB2.1**, **UNB2.2**, **UNB3.1**, and **UNB3.2** in the interchange header with those in the properties of an agreement.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e72d0-243"> 此外将通过匹配发送方限定符和标识符 （不接收方限定符和标识符） 来解析协议。</span><span class="sxs-lookup"><span data-stu-id="e72d0-243"> will also resolve the agreement by matching the sender qualifier and identifier (without the receiver qualifier and identifier).</span></span> <span data-ttu-id="e72d0-244">如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法解析协议，则将使用后备协议属性。</span><span class="sxs-lookup"><span data-stu-id="e72d0-244">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot resolve the agreement, it will use the fallback agreement properties.</span></span>  
      > 
      > [!NOTE]
      >  <span data-ttu-id="e72d0-245">如果使用的提供作为测试消息的本主题中前面的示例消息，设置**UNB2.1**到**7654321**， **UNB2.2**到**ZZZ – 双方约定**， **UNB3.1**到**1234567**，并且**UNB3.2**到**ZZZ – 双方约定**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-245">If you are using the sample message provided earlier in this topic as your test message, set **UNB2.1** to **7654321**, **UNB2.2** to **ZZZ – Mutually Defined**, **UNB3.1** to **1234567**, and **UNB3.2** to **ZZZ – Mutually Defined**.</span></span>  

   2. <span data-ttu-id="e72d0-246">上**确认**页**交换设置**部分中，选择**预期接收消息 (CONTRL)** 和**确认 (预期的 CONTRL)**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-246">On the **Acknowledgements** page under the **Interchange Settings** section, check **Receipt of message (CONTRL) expected** and **Acknowledgement (CONTRL) expected**.</span></span>  

   3. <span data-ttu-id="e72d0-247">上**信封**页**交换设置**部分中，选择**应用 UNA 段 （字符串服务建议）** 和**应用 UNG 段 （功能组标头）**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-247">On the **Envelopes** page under the **Interchange Settings** section, check **Apply UNA segment (String service advice)** and **Apply UNG segments (Functional group header)**.</span></span>  

   4. <span data-ttu-id="e72d0-248">上**验证**页**交换设置**部分中，请确保**交换控制编号 (UNB5)** 选项处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="e72d0-248">On the **Validation** page under the **Interchange Settings** section, make sure **Interchange Control Number (UNB5)** option is unchecked.</span></span>  

      > [!NOTE]
      >  <span data-ttu-id="e72d0-249">清除**交换控制编号 (UNB5)** 属性使您能够接收同一消息的多个实例。</span><span class="sxs-lookup"><span data-stu-id="e72d0-249">Clearing the **Interchange Control Number (UNB5)** property enables you to receive multiple instances of the same message.</span></span>  

   5. <span data-ttu-id="e72d0-250">上**字符集和分隔符**页**交换设置**部分中，选择**CR LF**选项**UNA6 后缀**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-250">On the **Charset and Separators** page under the **Interchange Settings** section, select the **CR LF** option for **UNA6 Suffix**.</span></span>  

   6. <span data-ttu-id="e72d0-251">上**本地主机设置**页**交换设置**部分中，清除**确认路由到发送管道请求-响应接收端口**选项。</span><span class="sxs-lookup"><span data-stu-id="e72d0-251">On the **Local Host Settings** page under the **Interchange Settings** section, clear the **Route ACK to send pipeline on request-response receive port** option.</span></span>  

      > [!NOTE]
      >  <span data-ttu-id="e72d0-252">如果使用的双向接收端口以接收交换并返回确认，您将检查**将确认路由到发送管道请求-响应接收端口**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-252">If you were using a two-way receive port to receive the interchange and return the acknowledgment, you would check **Route ACK to send pipeline on request-response receive port**.</span></span>  

   7. <span data-ttu-id="e72d0-253">上**发送端口**页**交换设置**部分中，将会接收来自 Fabrikam 的交换的发送端口和接收的发送端口相关联从 Contoso 的确认。</span><span class="sxs-lookup"><span data-stu-id="e72d0-253">On the **Send Ports** page under the **Interchange Settings** section, associate the send ports that will be receiving the interchange from Fabrikam and the send ports that will be receiving the acknowledgements from Contoso.</span></span> <span data-ttu-id="e72d0-254">在中**发送端口**网格下**名称**列，再单击某个空单元格，并从下拉列表中，选择创建用于从 Fabrikam 接收 EDI 交换的发送端口。</span><span class="sxs-lookup"><span data-stu-id="e72d0-254">In the **Send ports** grid, under the **Name** column, click an empty cell, and from the drop-down list, select the send port created for receiving the EDI interchange from Fabrikam.</span></span> <span data-ttu-id="e72d0-255">为创建用于接收技术和功能确认的发送端口重复步骤。</span><span class="sxs-lookup"><span data-stu-id="e72d0-255">Repeat the step for the send port created for receiving the technical and functional acknowledgements.</span></span>  

   8. <span data-ttu-id="e72d0-256">上**验证**页**事务集设置**部分中，保留**EDI 类型验证**检查，并检查**扩展类型验证**.</span><span class="sxs-lookup"><span data-stu-id="e72d0-256">On the **Validation** page under the **Transaction Set Settings** section, leave **EDI type Validation** checked and check **Extended Type Validation**.</span></span>  

   9. <span data-ttu-id="e72d0-257">如果你使用附带的标准架构之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后在**本地主机设置**页下**事务集设置**部分中，选择要使用的架构的命名空间处理传入的交换。</span><span class="sxs-lookup"><span data-stu-id="e72d0-257">If you are using one of the standard schemas shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], on the **Local Host Settings** page under the **Transaction Set Settings** section, select the namespace for the schema to be used to process the incoming interchange.</span></span> <span data-ttu-id="e72d0-258">如果使用自定义架构，请输入中的值**自定义目标命名空间**网格中，以便[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以确定命名空间使用组和事务集标头值。</span><span class="sxs-lookup"><span data-stu-id="e72d0-258">If using a custom schema, enter values in the **Customize Target namespace** grid, so that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can determine the namespace using group and transaction set header values.</span></span>  

   10. <span data-ttu-id="e72d0-259">上**信封**页**事务集设置**部分中，输入在网格的第一行中的所有列的值。</span><span class="sxs-lookup"><span data-stu-id="e72d0-259">On the **Envelopes** page under the **Transaction Set Settings** section, enter values for all columns in the first line of the grid.</span></span>  


       |          <span data-ttu-id="e72d0-260">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e72d0-260">Use this</span></span>           |                                <span data-ttu-id="e72d0-261">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e72d0-261">To do this</span></span>                                 |
       |-----------------------------|---------------------------------------------------------------------------|
       |         <span data-ttu-id="e72d0-262">**Default**</span><span class="sxs-lookup"><span data-stu-id="e72d0-262">**Default**</span></span>         |                            <span data-ttu-id="e72d0-263">选择**默认**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-263">Select **Default**.</span></span>                            |
       | <span data-ttu-id="e72d0-264">**对于消息类型 UNH2.1**</span><span class="sxs-lookup"><span data-stu-id="e72d0-264">**For message type UNH2.1**</span></span> |         <span data-ttu-id="e72d0-265">选择你的测试消息的消息类型**APERAK**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-265">Select the message type of your test message, **APERAK**.</span></span>         |
       |         <span data-ttu-id="e72d0-266">**UNH2.2**</span><span class="sxs-lookup"><span data-stu-id="e72d0-266">**UNH2.2**</span></span>          |                       <span data-ttu-id="e72d0-267">输入 EDI 版本， **D**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-267">Enter the EDI version, **D**.</span></span>                       |
       |         <span data-ttu-id="e72d0-268">**UNH2.3**</span><span class="sxs-lookup"><span data-stu-id="e72d0-268">**UNH2.3**</span></span>          |                    <span data-ttu-id="e72d0-269">输入发行版号**98A**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-269">Enter the release number, **98A**.</span></span>                     |
       |         <span data-ttu-id="e72d0-270">**UNH2.5**</span><span class="sxs-lookup"><span data-stu-id="e72d0-270">**UNH2.5**</span></span>          |                         <span data-ttu-id="e72d0-271">您可以将其留空。</span><span class="sxs-lookup"><span data-stu-id="e72d0-271">You can leave this blank.</span></span>                         |
       |    <span data-ttu-id="e72d0-272">**目标命名空间**</span><span class="sxs-lookup"><span data-stu-id="e72d0-272">**Target namespace**</span></span>     |          <span data-ttu-id="e72d0-273">选择**<http://schemas.microsoft.com/Edi/Edifact>**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-273">Select **<http://schemas.microsoft.com/Edi/Edifact>**.</span></span>           |
       |          <span data-ttu-id="e72d0-274">**UNG1**</span><span class="sxs-lookup"><span data-stu-id="e72d0-274">**UNG1**</span></span>           |               <span data-ttu-id="e72d0-275">指定功能组 ID **INVOIC**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-275">Specify the functional group ID, **INVOIC**.</span></span>                |
       |         <span data-ttu-id="e72d0-276">**UNG2.1**</span><span class="sxs-lookup"><span data-stu-id="e72d0-276">**UNG2.1**</span></span>          |         <span data-ttu-id="e72d0-277">为应用程序发送方标识输入的值。</span><span class="sxs-lookup"><span data-stu-id="e72d0-277">Enter a value for the application sender identification.</span></span>          |
       |         <span data-ttu-id="e72d0-278">**UNG2.1**</span><span class="sxs-lookup"><span data-stu-id="e72d0-278">**UNG2.1**</span></span>          | <span data-ttu-id="e72d0-279">输入一个值，为应用程序发送方代码限定符，例如**ZZZ**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-279">Enter a value for the application sender code qualifier, such as **ZZZ**.</span></span> |
       |         <span data-ttu-id="e72d0-280">**UNG3.1**</span><span class="sxs-lookup"><span data-stu-id="e72d0-280">**UNG3.1**</span></span>          |          <span data-ttu-id="e72d0-281">应用程序接收方标识输入的值。</span><span class="sxs-lookup"><span data-stu-id="e72d0-281">Enter a value for application receiver identification.</span></span>           |
       |         <span data-ttu-id="e72d0-282">**UNG3.2**</span><span class="sxs-lookup"><span data-stu-id="e72d0-282">**UNG3.2**</span></span>          |  <span data-ttu-id="e72d0-283">输入一个值，为应用程序接收方代码限定符，例如**ZZZ**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-283">Enter a value for application receiver code qualifier, such as **ZZZ**.</span></span>  |
       |          <span data-ttu-id="e72d0-284">**UNG6**</span><span class="sxs-lookup"><span data-stu-id="e72d0-284">**UNG6**</span></span>           |        <span data-ttu-id="e72d0-285">输入控制机构的值。</span><span class="sxs-lookup"><span data-stu-id="e72d0-285">Enter a value for the controlling agency.</span></span> <span data-ttu-id="e72d0-286">示例中，**取消**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-286">Example, **UN**.</span></span>         |
       |         <span data-ttu-id="e72d0-287">**UNG7.1**</span><span class="sxs-lookup"><span data-stu-id="e72d0-287">**UNG7.1**</span></span>          |          <span data-ttu-id="e72d0-288">输入消息类型版本号。</span><span class="sxs-lookup"><span data-stu-id="e72d0-288">Enter the message type version number.</span></span> <span data-ttu-id="e72d0-289">示例中， **D**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-289">Example, **D**.</span></span>           |
       |         <span data-ttu-id="e72d0-290">**UNG7.2**</span><span class="sxs-lookup"><span data-stu-id="e72d0-290">**UNG7.2**</span></span>          |         <span data-ttu-id="e72d0-291">输入消息类型发行版号。</span><span class="sxs-lookup"><span data-stu-id="e72d0-291">Enter the message type release number.</span></span> <span data-ttu-id="e72d0-292">示例中， **98A**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-292">Example, **98A**.</span></span>          |
       |         <span data-ttu-id="e72d0-293">**UNG7.3**</span><span class="sxs-lookup"><span data-stu-id="e72d0-293">**UNG7.3**</span></span>          |                         <span data-ttu-id="e72d0-294">您可以将其留空。</span><span class="sxs-lookup"><span data-stu-id="e72d0-294">You can leave this blank.</span></span>                         |
       |          <span data-ttu-id="e72d0-295">**UNG8**</span><span class="sxs-lookup"><span data-stu-id="e72d0-295">**UNG8**</span></span>           |                         <span data-ttu-id="e72d0-296">您可以将其留空。</span><span class="sxs-lookup"><span data-stu-id="e72d0-296">You can leave this blank.</span></span>                         |


8. <span data-ttu-id="e72d0-297">在执行以下任务**Contoso-> Fabrikam**选项卡。</span><span class="sxs-lookup"><span data-stu-id="e72d0-297">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="e72d0-298">在本演练中，我们指定的选项卡中所需的值，以便可以成功创建协议。</span><span class="sxs-lookup"><span data-stu-id="e72d0-298">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="e72d0-299">若要成功创建协议，两个单向协议选项卡必须具有定义为值**UNG2.1**， **UNG2.2**， **UNG3.1**，和**UNG3.2**.</span><span class="sxs-lookup"><span data-stu-id="e72d0-299">To successfully create an agreement, both one-way agreement tabs must have values defined for **UNG2.1**, **UNG2.2**, **UNG3.1**, and **UNG3.2**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="e72d0-300">即使确认是相同消息事务的一部分，应如何生成确认相关的属性中配置**Contoso-> Fabrikam**选项卡。这是必需的因为确认上下文属性发送方和接收方限定符设置为在指定的值相反**Contoso-> Fabrikam**选项卡。例如，如果发送方和接收方标识符设置为 7654321 和在 1234567 **Fabrikam-> Contoso**选项卡中，发送方和接收方上下文属性将设置为 1234567 和 7654321 确认中。</span><span class="sxs-lookup"><span data-stu-id="e72d0-300">Even though the acknowledgement is part of the same message transaction, the properties related to how the acknowledgement should be generated are configured in the **Contoso->Fabrikam** tab. This is required because the acknowledgement context properties for the sender and receiver qualifiers are set to the opposite of the values you specified in the **Contoso->Fabrikam** tab. For example, if sender and receiver identifiers are set to 7654321 and 1234567 in the **Fabrikam->Contoso** tab, the sender and receiver context properties will be set to 1234567 and 7654321 in the acknowledgement.</span></span> <span data-ttu-id="e72d0-301">通常情况下，其他单向协议选项卡还会发送方和接收方的标识符分别设置为 1234567 和 7654321。</span><span class="sxs-lookup"><span data-stu-id="e72d0-301">Typically, the other one-way agreement tab would also have the sender and receiver identifiers set to 1234567 and 7654321 respectively.</span></span> <span data-ttu-id="e72d0-302">因此，确认消息将解析为该协议，并且将提取属性设置。</span><span class="sxs-lookup"><span data-stu-id="e72d0-302">Hence, the acknowledgement message would resolve to that agreement and the properties setting will be picked.</span></span> <span data-ttu-id="e72d0-303">因此，如果你想要让确认使用不同的元素分隔符或如果想要让确认使用 CR LF，指定的属性中**Contoso-> Fabrikam**选项卡。</span><span class="sxs-lookup"><span data-stu-id="e72d0-303">So, if you want to have the acknowledgement to use different element separators or if you want to have the acknowledgement to use CR LF, specify the properties in the **Contoso->Fabrikam** tab.</span></span>  
   >   
   >  <span data-ttu-id="e72d0-304">从概念上讲，将从任何单向协议选项卡上提取具有与确认上下文属性中设置的相同发件人和接收方限定符的确认的属性。</span><span class="sxs-lookup"><span data-stu-id="e72d0-304">Conceptually, the properties for the acknowledgement will be picked from any one-way agreement tab that has the same sender and receiver qualifiers as set in the acknowledgement’s context properties.</span></span> <span data-ttu-id="e72d0-305">但是，为了便于实际使用，你通常会在你创建的交换将解析为的协议的其他单向协议选项卡中设置此属性。</span><span class="sxs-lookup"><span data-stu-id="e72d0-305">However, for ease of practical use, you would typically set this in the other one-way agreement tab of the agreement that you created to which the interchange would have resolved.</span></span>  

   1.  <span data-ttu-id="e72d0-306">上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**UNG2.1**， **UNG2.2**， **UNG3.1**，和**UNG3.2**) 的测试消息中这些标头字段的值相对应。</span><span class="sxs-lookup"><span data-stu-id="e72d0-306">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**UNG2.1**, **UNG2.2**, **UNG3.1**, and **UNG3.2**) that correspond to the values for those header fields in your test message.</span></span>  

       > [!NOTE]
       >  <span data-ttu-id="e72d0-307">如果使用的提供作为测试消息的本主题中前面的示例消息，设置**UNB2.1**到**1234567**， **UNB2.2**到**ZZZ – 双方约定**， **UNB3.1**到**7654321**，并且**UNB3.2**到**ZZZ – 双方约定**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-307">If you are using the sample message provided earlier in this topic as your test message, set **UNB2.1** to **1234567**, **UNB2.2** to **ZZZ – Mutually Defined**, **UNB3.1** to **7654321**, and **UNB3.2** to **ZZZ – Mutually Defined**.</span></span>  

9. <span data-ttu-id="e72d0-308">单击 **“应用”**。</span><span class="sxs-lookup"><span data-stu-id="e72d0-308">Click **Apply**.</span></span>  

10. <span data-ttu-id="e72d0-309">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="e72d0-309">Click **OK**.</span></span> <span data-ttu-id="e72d0-310">中列出新添加的协议**协议**一部分**参与方和业务配置文件**窗格。</span><span class="sxs-lookup"><span data-stu-id="e72d0-310">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="e72d0-311">默认情况下，启用新添加的协议。</span><span class="sxs-lookup"><span data-stu-id="e72d0-311">The newly added agreement is enabled by default.</span></span>  

### <a name="testing-the-walkthrough"></a><span data-ttu-id="e72d0-312">测试演练</span><span class="sxs-lookup"><span data-stu-id="e72d0-312">Testing the Walkthrough</span></span>  
 <span data-ttu-id="e72d0-313">本部分提供有关如何测试演练的信息。</span><span class="sxs-lookup"><span data-stu-id="e72d0-313">This section provides information on how to test the walkthrough.</span></span>  

##### <a name="to-test-the-walkthrough"></a><span data-ttu-id="e72d0-314">若要测试演练</span><span class="sxs-lookup"><span data-stu-id="e72d0-314">To test the walkthrough</span></span>  

1. <span data-ttu-id="e72d0-315">在 Windows 资源管理器中，将测试 EDI 交换放置到本地接收文件夹中。</span><span class="sxs-lookup"><span data-stu-id="e72d0-315">In Windows Explorer, drop the test EDI interchange into your local receive folder.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="e72d0-316">对于测试消息，您可以使用本主题前面提供的示例消息。</span><span class="sxs-lookup"><span data-stu-id="e72d0-316">For a test message, you can use the sample message provided earlier in this topic.</span></span> <span data-ttu-id="e72d0-317">将消息复制到文本文件，并使用 .txt 扩展名保存文件。</span><span class="sxs-lookup"><span data-stu-id="e72d0-317">Copy the message to a text file and save the file with a .txt extension.</span></span> <span data-ttu-id="e72d0-318">如果使用此消息，则必须部署 EFACT_D98A_APERAK.xsd 架构。</span><span class="sxs-lookup"><span data-stu-id="e72d0-318">If you use this message, you must have deployed the EFACT_D98A_APERAK.xsd schema.</span></span> <span data-ttu-id="e72d0-319">架构是可通过执行**MicrosoftEdiXSDTemplates.exe**文件 （位于 \XSD_Schema\EDI 文件夹中） 将该架构解压缩到默认文件夹。</span><span class="sxs-lookup"><span data-stu-id="e72d0-319">The schema is available by executing the **MicrosoftEdiXSDTemplates.exe** file (in the \XSD_Schema\EDI folder) to unzip the schemas into the default folder.</span></span> <span data-ttu-id="e72d0-320">然后可以在 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\EDIFACT\D98A 下找到 EFACT_D98A_APERAK.xsd 架构。</span><span class="sxs-lookup"><span data-stu-id="e72d0-320">The EFACT_D98A_APERAK.xsd schema is then available under [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\EDIFACT\D98A.</span></span>  

2. <span data-ttu-id="e72d0-321">打开与交换的发送端口关联的文件夹，并验证该文件夹是否包含 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="e72d0-321">Open the folder that you associated with the send port for interchanges, and verify that it contains the EDI interchange.</span></span>  

3. <span data-ttu-id="e72d0-322">打开与确认的发送端口关联的文件夹，并验证该文件夹是否包含技术确认和功能确认。</span><span class="sxs-lookup"><span data-stu-id="e72d0-322">Open the folder that you associated with the send port for the acknowledgements, and verify that it contains the technical and functional acknowledgements.</span></span>  

## <a name="see-also"></a><span data-ttu-id="e72d0-323">请参阅</span><span class="sxs-lookup"><span data-stu-id="e72d0-323">See Also</span></span>  
 [<span data-ttu-id="e72d0-324">开发和配置 BizTalk Server EDI 解决方案</span><span class="sxs-lookup"><span data-stu-id="e72d0-324">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)