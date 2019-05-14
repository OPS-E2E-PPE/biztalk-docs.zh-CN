---
title: 演练 (X12):发送 EDI 交换 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05533821-b9eb-44bc-af65-b6fb0b545137
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50db444708b4960f1e3e12236b3f3006fd2567e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246467"
---
# <a name="walkthrough-x12-sending-edi-interchanges"></a><span data-ttu-id="760b2-102">演练 (X12):发送 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="760b2-102">Walkthrough (X12): Sending EDI Interchanges</span></span>
<span data-ttu-id="760b2-103">本演练提供了创建一个发送 EDI 解决方案的分步操作过程一交换使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="760b2-103">This walkthrough provides a set of step-by-step procedures that creates a solution for sending EDI interchanges using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="760b2-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="760b2-104">Prerequisites</span></span>  
 <span data-ttu-id="760b2-105">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="760b2-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  

## <a name="how-the-solution-sends-edi-interchanges"></a><span data-ttu-id="760b2-106">解决方案如何发送 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="760b2-106">How the Solution Sends EDI Interchanges</span></span>  
 <span data-ttu-id="760b2-107">该解决方案将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="760b2-107">The solution will do the following:</span></span>  

1.  <span data-ttu-id="760b2-108">一个单向 FILE 接收端口从 Fabrikam 接收 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="760b2-108">A one-way FILE receive port receives an EDI message from Fabrikam.</span></span>  

2.  <span data-ttu-id="760b2-109">使用 EdiReceive 管道，接收端口将检查该消息并将其转换为 XML。</span><span class="sxs-lookup"><span data-stu-id="760b2-109">Using the EdiReceive pipeline, the receive port checks the message and converts it into XML.</span></span> <span data-ttu-id="760b2-110">接收端口然后将测试消息放入 MeassageBox。</span><span class="sxs-lookup"><span data-stu-id="760b2-110">The receive port then drops the test message into the MeassageBox.</span></span>  

3.  <span data-ttu-id="760b2-111">静态单向发送端口提取 XML 消息从 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="760b2-111">A static one-way send port picks up the XML message from the MessageBox.</span></span>  

4.  <span data-ttu-id="760b2-112">静态单向发送端口验证针对消息架构的 EDI 消息，EDI 消息序列化为 EDI 交换，然后将 EDI 消息发送到贸易合作伙伴 Contoso 本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="760b2-112">The static one-way send port validates the EDI message against the message schema, serializes the EDI message into an EDI interchange, and then sends the EDI message to the trading partner Contoso's local folder.</span></span>  

## <a name="the-functionality-in-this-solution"></a><span data-ttu-id="760b2-113">此解决方案中的功能</span><span class="sxs-lookup"><span data-stu-id="760b2-113">The Functionality in this Solution</span></span>  
 <span data-ttu-id="760b2-114">本演练使用以下功能：</span><span class="sxs-lookup"><span data-stu-id="760b2-114">This walkthrough uses the following functionality:</span></span>  

- <span data-ttu-id="760b2-115">在本演练中，不测试接收确认。</span><span class="sxs-lookup"><span data-stu-id="760b2-115">Receiving an acknowledgment is not tested in this walkthrough.</span></span> <span data-ttu-id="760b2-116">若要了解如何接收确认，请参阅演示[演练 (X12):接收 EDI 交换并发送回确认](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)</span><span class="sxs-lookup"><span data-stu-id="760b2-116">To understand how to receive an acknowledgment, see demonstrated [Walkthrough (X12): Receiving EDI Interchanges and Sending Back an Acknowledgement](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)</span></span>  

- <span data-ttu-id="760b2-117">该解决方案专用于使用 X12 编码而不是 EDIFACT 交换编码。</span><span class="sxs-lookup"><span data-stu-id="760b2-117">The solution is designed for interchanges using X12 encoding, not EDIFACT encoding.</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="760b2-118">用于 HIPAA 和 EDIFACT 编码的配置是近与用于 X12 编码。</span><span class="sxs-lookup"><span data-stu-id="760b2-118">The configuration used for HIPAA and for EDIFACT encoding is closely parallel to that used for X12 encoding.</span></span>  

- <span data-ttu-id="760b2-119">EDI 类型和扩展的验证将传出交换上执行。</span><span class="sxs-lookup"><span data-stu-id="760b2-119">EDI type and extended validation will be performed on the outgoing interchange.</span></span>  

- <span data-ttu-id="760b2-120">使用 FILE 传输类型，该解决方案使用静态单向发送端口。</span><span class="sxs-lookup"><span data-stu-id="760b2-120">The solution uses a static one-way send port with a FILE transport type.</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="760b2-121">而不是静态单向发送端口，可以使用静态双向发送端口以将交换发送和接收确认。</span><span class="sxs-lookup"><span data-stu-id="760b2-121">Instead of a static one-way send port, you could use a static two-way send port to send the interchange and receive the acknowledgment.</span></span> <span data-ttu-id="760b2-122">此外可以使用动态单向发送端口以发送交换。</span><span class="sxs-lookup"><span data-stu-id="760b2-122">You could also use a dynamic one-way send port to send the interchange.</span></span> <span data-ttu-id="760b2-123">使用动态发送端口的详细信息，请参阅[配置为发送 EDI 交换和确认的动态发送端口](../core/configuring-a-dynamic-send-port-to-send-edi-interchanges-and-acknowledgments.md)。</span><span class="sxs-lookup"><span data-stu-id="760b2-123">For more information on using a dynamic send port, see [Configuring a Dynamic Send Port to Send EDI Interchanges and Acknowledgments](../core/configuring-a-dynamic-send-port-to-send-edi-interchanges-and-acknowledgments.md).</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="760b2-124">可以使用 HTTP 适配器和 AS2 传输。</span><span class="sxs-lookup"><span data-stu-id="760b2-124">You can use an HTTP adapter and AS2 transport.</span></span> <span data-ttu-id="760b2-125">有关执行此操作的详细信息，请参阅[演练 (AS2):使用同步 MDN 通过 AS2 发送 EDI](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md)或[演练 (AS2):使用异步 MDN 通过 AS2 发送 EDI](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md)。</span><span class="sxs-lookup"><span data-stu-id="760b2-125">For more information on doing so, see [Walkthrough (AS2): Sending EDI over AS2 with a Synchronous MDN](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md) or [Walkthrough (AS2): Sending EDI over AS2 with an Asynchronous MDN](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md).</span></span>  

- <span data-ttu-id="760b2-126">将启用 EDI 报告，并保存事务集以从交换状态报告进行查看。</span><span class="sxs-lookup"><span data-stu-id="760b2-126">EDI reporting will be enabled, and transaction sets will be saved for viewing from the interchange status report.</span></span>  

- <span data-ttu-id="760b2-127">出于测试目的，该解决方案使用的接收位置用于接收测试消息。</span><span class="sxs-lookup"><span data-stu-id="760b2-127">For testing purposes, the solution uses a receive location to receive a test message.</span></span>  

  <span data-ttu-id="760b2-128">下图显示了此解决方案中，使用静态单向发送端口的体系结构。</span><span class="sxs-lookup"><span data-stu-id="760b2-128">The following figure shows the architecture for this solution, which uses a static one-way send port.</span></span>  

  <span data-ttu-id="760b2-129">![发送 EDI 交换](../core/media/6915024c-687c-4076-a730-3f7b9d2db7fb.gif "6915024c-687c-4076-a730-3f7b9d2db7fb")</span><span class="sxs-lookup"><span data-stu-id="760b2-129">![Sending EDI interchanges](../core/media/6915024c-687c-4076-a730-3f7b9d2db7fb.gif "6915024c-687c-4076-a730-3f7b9d2db7fb")</span></span>  

## <a name="configuring-and-testing-the-walkthrough"></a><span data-ttu-id="760b2-130">配置和测试演练</span><span class="sxs-lookup"><span data-stu-id="760b2-130">Configuring and Testing the Walkthrough</span></span>  
 <span data-ttu-id="760b2-131">此解决方案所需的过程包括：</span><span class="sxs-lookup"><span data-stu-id="760b2-131">The procedures required for this solution include the following:</span></span>  

- <span data-ttu-id="760b2-132">将必需的消息架构添加到 BizTalk 项目，然后生成并部署该项目，使架构可供使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在处理出站交换。</span><span class="sxs-lookup"><span data-stu-id="760b2-132">Add the required message schema(s) to a BizTalk project, and then build and deploy the project, making the schemas available for use by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in processing the outbound interchange.</span></span>  

- <span data-ttu-id="760b2-133">创建接收端口和位置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="760b2-133">Create a receive port and location for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive the EDI interchange.</span></span> <span data-ttu-id="760b2-134">此接收位置与 Fabrikam 存放要发送到 Contoso 的 EDI 交换文件文件夹相关联。</span><span class="sxs-lookup"><span data-stu-id="760b2-134">This receive location is tied to the file folder where Fabrikam drops the EDI interchange to be sent to Contoso.</span></span> <span data-ttu-id="760b2-135">接收位置将使用 EdiReceive 接收管道。</span><span class="sxs-lookup"><span data-stu-id="760b2-135">The receive location will use an EdiReceive receive pipeline.</span></span>  

- <span data-ttu-id="760b2-136">创建发送端口的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]向 Contoso 发送 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="760b2-136">Create a send port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send the EDI interchange to Contoso.</span></span> <span data-ttu-id="760b2-137">在本演练中，将创建一个静态单向发送端口。</span><span class="sxs-lookup"><span data-stu-id="760b2-137">In this walkthrough, you will create a static one-way send port.</span></span>  

- <span data-ttu-id="760b2-138">为 Fabrikam 和 Contoso 创建参与方 （贸易合作伙伴）。</span><span class="sxs-lookup"><span data-stu-id="760b2-138">Create a party (trading partner) for both Fabrikam and Contoso.</span></span>  

- <span data-ttu-id="760b2-139">为这两个贸易合作伙伴创建业务配置文件每个。</span><span class="sxs-lookup"><span data-stu-id="760b2-139">Create a business profile each for both the trading partners.</span></span>  

- <span data-ttu-id="760b2-140">创建通过配置要接收的消息的 EDI 属性的两个配置文件之间的协议。</span><span class="sxs-lookup"><span data-stu-id="760b2-140">Create an agreement between the two profiles by configuring the EDI properties for the message to be received.</span></span>  

- <span data-ttu-id="760b2-141">测试使用测试 EDI 交换演练。</span><span class="sxs-lookup"><span data-stu-id="760b2-141">Test the walkthrough using a test EDI interchange.</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="760b2-142">对于测试消息，可以使用在 EDI 接口开发人员教程中使用的 SamplePO.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="760b2-142">For a test message, you can use the SamplePO.txt file that is used in the EDI Interface Developer tutorial.</span></span> <span data-ttu-id="760b2-143">该文件中都随附[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ 文件夹。</span><span class="sxs-lookup"><span data-stu-id="760b2-143">That file is shipped in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ folder.</span></span> <span data-ttu-id="760b2-144">这是一个 X12 850 消息。</span><span class="sxs-lookup"><span data-stu-id="760b2-144">This is an X12 850 message.</span></span>  

### <a name="configuring-the-walkthrough"></a><span data-ttu-id="760b2-145">配置演练</span><span class="sxs-lookup"><span data-stu-id="760b2-145">Configuring the Walkthrough</span></span>  
 <span data-ttu-id="760b2-146">本部分介绍配置本演练的步骤。</span><span class="sxs-lookup"><span data-stu-id="760b2-146">This section describes the procedures to configure the walkthrough.</span></span>  

##### <a name="to-deploy-the-message-schema"></a><span data-ttu-id="760b2-147">若要部署的消息架构</span><span class="sxs-lookup"><span data-stu-id="760b2-147">To deploy the message schema</span></span>  

1. <span data-ttu-id="760b2-148">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，创建或打开 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="760b2-148">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create or open a BizTalk project.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="760b2-149">本主题假定你已从对 BizTalk EDI 应用程序，其中包含 EDI 架构、 管道和业务流程应用程序中添加了一个引用。</span><span class="sxs-lookup"><span data-stu-id="760b2-149">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="760b2-150">如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。</span><span class="sxs-lookup"><span data-stu-id="760b2-150">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  

2. <span data-ttu-id="760b2-151">右键单击你的项目，指向**外**，然后单击**现有项**。</span><span class="sxs-lookup"><span data-stu-id="760b2-151">Right-click your project, point to **Add**, and then click **Existing Item**.</span></span> <span data-ttu-id="760b2-152">转到您的架构是中的文件夹[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI，然后双击您的架构。</span><span class="sxs-lookup"><span data-stu-id="760b2-152">Move to the folder that your schema is in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI, and then double-click your schema.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="760b2-153">如果 EDI 架构尚未解压缩到 \XSD_Schema\EDI 文件夹，则执行**MicrosoftEdiXSDTemplates.exe** \XSD_Schema\EDI 文件夹将架构解压缩到默认文件夹中的文件。</span><span class="sxs-lookup"><span data-stu-id="760b2-153">If the EDI schemas have not been unzipped into the \XSD_Schema\EDI folders, execute the **MicrosoftEdiXSDTemplates.exe** file in the \XSD_Schema\EDI folder to unzip the schemas into the default folder.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="760b2-154">如果您使用 EDI 接口开发人员教程中使用的 SamplePO.txt 文件，则必须使用 X12_00401_850.xsd 架构，在该架构[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI 文件夹。</span><span class="sxs-lookup"><span data-stu-id="760b2-154">If you use the SamplePO.txt file that is used in the EDI Interface Developer tutorial, you must use the X12_00401_850.xsd schema that is shipped in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI folder.</span></span> <span data-ttu-id="760b2-155">必须使用 X12 850 性架构中的[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema 文件夹。</span><span class="sxs-lookup"><span data-stu-id="760b2-155">You must not use the X12 850 schema in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema folder.</span></span>  

3. <span data-ttu-id="760b2-156">将程序集密钥文件添加到项目中，然后生成并部署该程序集。</span><span class="sxs-lookup"><span data-stu-id="760b2-156">Add the assembly key file to the project, and then build and deploy the assembly.</span></span>  

##### <a name="to-create-a-one-way-receive-port-for-fabrikam-to-receive-the-edi-interchange"></a><span data-ttu-id="760b2-157">若要创建一个单向接收端口 （对于 Fabrikam) 接收 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="760b2-157">To create a one-way receive port (for Fabrikam) to receive the EDI interchange</span></span>  

1. <span data-ttu-id="760b2-158">在 Windows 资源管理器中，创建用于接收交换中的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="760b2-158">In Windows Explorer, create a local folder to receive the interchange in.</span></span>  

2. <span data-ttu-id="760b2-159">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="760b2-159">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Receive Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **One-way Receive Port**.</span></span>  

3. <span data-ttu-id="760b2-160">接收端口的名称，然后单击**接收位置**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="760b2-160">Name the receive port, and then click **Receive Locations** in the console tree.</span></span>  

4. <span data-ttu-id="760b2-161">单击 **“新建”**。</span><span class="sxs-lookup"><span data-stu-id="760b2-161">Click **New**.</span></span>  

5. <span data-ttu-id="760b2-162">名称的接收位置，选择**文件**有关**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="760b2-162">Name the receive location, select **FILE** for **Type**, and then click **Configure**.</span></span>  

6. <span data-ttu-id="760b2-163">输入一个文件夹**接收文件夹**，并输入 **\*.txt**文件掩码。</span><span class="sxs-lookup"><span data-stu-id="760b2-163">Enter a folder for **Receive folder**, and enter **\*.txt** for the file mask.</span></span>  

7. <span data-ttu-id="760b2-164">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="760b2-164">Click **OK**.</span></span>  

8. <span data-ttu-id="760b2-165">有关**接收管道**，选择**EdiReceive**。</span><span class="sxs-lookup"><span data-stu-id="760b2-165">For **Receive pipeline**, select **EdiReceive**.</span></span>  

9. <span data-ttu-id="760b2-166">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="760b2-166">Click **OK**, and then click **OK** again.</span></span>  

10. <span data-ttu-id="760b2-167">在控制台树中，单击**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="760b2-167">In the console tree, click **Receive Locations**.</span></span> <span data-ttu-id="760b2-168">在中**接收位置**窗格中，右键单击将接收位置，然后依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="760b2-168">In the **Receive Locations** pane, right-click your receive location, and then click **Enable**.</span></span>  

##### <a name="to-create-a-static-one-way-send-port-for-contoso-to-send-the-edi-interchange"></a><span data-ttu-id="760b2-169">（为 Contoso) 创建静态单向发送端口以发送 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="760b2-169">To create a static one-way send port (for Contoso) to send the EDI interchange</span></span>  

1. <span data-ttu-id="760b2-170">在 Windows 资源管理器中，创建一个用于接收 EDI 交换的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="760b2-170">In Windows Explorer, create a local folder to send the EDI interchange to.</span></span>  

2. <span data-ttu-id="760b2-171">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="760b2-171">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static One-way Send Port**.</span></span>  

3. <span data-ttu-id="760b2-172">在中**发送端口属性**对话框中，发送端口名称。</span><span class="sxs-lookup"><span data-stu-id="760b2-172">In the **Send Port Properties** dialog box, name the send port.</span></span>  

4. <span data-ttu-id="760b2-173">在中**传输**部分中，选择**类型**，例如，**文件**。</span><span class="sxs-lookup"><span data-stu-id="760b2-173">In the **Transport** section, select the **Type**, for example, **FILE**.</span></span>  

5. <span data-ttu-id="760b2-174">如果使用的文件类型，请单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="760b2-174">If using a FILE type, click **Configure**.</span></span> <span data-ttu-id="760b2-175">在中**目标文件夹**，浏览到要接收交换的文件夹。</span><span class="sxs-lookup"><span data-stu-id="760b2-175">In **Destination folder**, browse to a folder to send the interchange to.</span></span> <span data-ttu-id="760b2-176">有关**文件名**，输入 **%MessageID%.edi**。</span><span class="sxs-lookup"><span data-stu-id="760b2-176">For **File name**, enter **%MessageID%.edi**.</span></span> <span data-ttu-id="760b2-177">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="760b2-177">Click **OK**.</span></span>  

6. <span data-ttu-id="760b2-178">在中**发送管道**，选择**EdiSend**。</span><span class="sxs-lookup"><span data-stu-id="760b2-178">In **Send pipeline**, select **EdiSend**.</span></span>  

7. <span data-ttu-id="760b2-179">在控制台树中，选择**筛选器**，并输入要用于订阅消息的发送端口的筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="760b2-179">In the console tree, select **Filters**, and enter a filter expression for the send port to use to subscribe to the message.</span></span> <span data-ttu-id="760b2-180">例如，可以使用接收位置将接收原始测试消息与筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="760b2-180">For example, you could use the receive location that will receive the original test message as a filter expression.</span></span> <span data-ttu-id="760b2-181">为此，对于**属性**，输入**BTS。ReceivePortName**; 对于**运算符**，输入**==**; 对于**值**输入到创建的接收端口的名称从 Fabrikam 接收 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="760b2-181">To do so, for **Property**, enter **BTS.ReceivePortName**; for **Operator**, enter **==**; and for **Value** enter the name of the receive port that you created to receive the XML message from Fabrikam.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="760b2-182">您可以筛选所选的另一个属性，如 BTS。MessageType。</span><span class="sxs-lookup"><span data-stu-id="760b2-182">You could filter on another property of your choice, for example, on BTS.MessageType.</span></span>  

8. <span data-ttu-id="760b2-183">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="760b2-183">Click **OK**.</span></span>  

9. <span data-ttu-id="760b2-184">单击**发送端口**节点中管理控制台中，右键单击您的发送端口，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="760b2-184">Click the **Send Ports** node in the Administration Console, right-click your send port, and then click **Start**.</span></span>  

##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a><span data-ttu-id="760b2-185">创建 Fabrikam 参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="760b2-185">To create a party and a business profile for Fabrikam</span></span>  

1. <span data-ttu-id="760b2-186">右键单击**参与方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="760b2-186">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  

2. <span data-ttu-id="760b2-187">输入中的参与方的名称**名称**文本框中，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="760b2-187">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="760b2-188">通过选择**本地 BizTalk 处理接收的来自此参与方发送消息的参与方或支持消息**复选框，可以指定要创建的参与方是为同一组织与托管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="760b2-188">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="760b2-189">此基础，某些属性将启用，或禁用在创建协议时。</span><span class="sxs-lookup"><span data-stu-id="760b2-189">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="760b2-190">但是，对于此演练中，可以选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="760b2-190">However, for this walkthrough, you can leave this check box selected.</span></span>  

3. <span data-ttu-id="760b2-191">右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="760b2-191">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  

4. <span data-ttu-id="760b2-192">在中**配置文件属性**对话框中，在**常规**页上，输入**Fabrikam_Profile**中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="760b2-192">In the **Profile Properties** dialog box, on the **General** page, enter **Fabrikam_Profile** in the **Name** text box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="760b2-193">创建一个参与方时，还创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="760b2-193">When you create a party, a profile is also created.</span></span> <span data-ttu-id="760b2-194">可以重命名，并使用该配置文件而不是创建一个新。</span><span class="sxs-lookup"><span data-stu-id="760b2-194">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="760b2-195">若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="760b2-195">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="760b2-196">在中**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="760b2-196">In the **General** page, specify a name for the profile.</span></span>  

##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a><span data-ttu-id="760b2-197">为 Contoso 创建参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="760b2-197">To create a party and a business profile for Contoso</span></span>  

1. <span data-ttu-id="760b2-198">右键单击**参与方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="760b2-198">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  

2. <span data-ttu-id="760b2-199">输入中的参与方的名称**名称**文本框中，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="760b2-199">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="760b2-200">通过选择**本地 BizTalk 处理接收的来自此参与方发送消息的参与方或支持消息**复选框，可以指定要创建的参与方是为同一组织与托管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="760b2-200">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="760b2-201">此基础，某些属性将启用，或禁用在创建协议时。</span><span class="sxs-lookup"><span data-stu-id="760b2-201">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="760b2-202">但是，对于此演练中，可以选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="760b2-202">However, for this walkthrough, you can leave this check box selected.</span></span>  

3. <span data-ttu-id="760b2-203">右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="760b2-203">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  

4. <span data-ttu-id="760b2-204">在中**配置文件属性**对话框中，在**常规**页上，输入**Contoso_Profile**中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="760b2-204">In the **Profile Properties** dialog box, on the **General** page, enter **Contoso_Profile** in the **Name** text box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="760b2-205">创建一个参与方时，还创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="760b2-205">When you create a party, a profile is also created.</span></span> <span data-ttu-id="760b2-206">可以重命名，并使用该配置文件而不是创建一个新。</span><span class="sxs-lookup"><span data-stu-id="760b2-206">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="760b2-207">若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="760b2-207">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="760b2-208">在中**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="760b2-208">In the **General** page, specify a name for the profile.</span></span>  

##### <a name="to-create-an-agreement-between-the-two-business-profiles"></a><span data-ttu-id="760b2-209">若要创建的两个业务配置文件之间的协议</span><span class="sxs-lookup"><span data-stu-id="760b2-209">To create an agreement between the two business profiles</span></span>  

1. <span data-ttu-id="760b2-210">右键单击**Fabrikam_Profile**，依次指向**新建**，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="760b2-210">Right-click **Fabrikam_Profile**, point to **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="760b2-211">在**常规属性**页上，对于**名称**文字框中，输入协议的名称。</span><span class="sxs-lookup"><span data-stu-id="760b2-211">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  

3. <span data-ttu-id="760b2-212">从**协议**下拉列表中，选择**X12**。</span><span class="sxs-lookup"><span data-stu-id="760b2-212">From the **Protocol** drop-down list, select **X12**.</span></span>  

4. <span data-ttu-id="760b2-213">在中**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**Contoso**。</span><span class="sxs-lookup"><span data-stu-id="760b2-213">In the **Second Partner** section, from the **Name** drop-down list, select **Contoso**.</span></span>  

5. <span data-ttu-id="760b2-214">在中**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**Contoso_Profile**。</span><span class="sxs-lookup"><span data-stu-id="760b2-214">In the **Second Partner** section, from the **Profile** drop-down list, select **Contoso_Profile**.</span></span>  

    <span data-ttu-id="760b2-215">你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡用于配置一个单向协议，每个单向协议代表消息 （包括消息传输和确认传输） 的一次完整事务。</span><span class="sxs-lookup"><span data-stu-id="760b2-215">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way agreement and each one-way agreement represents one complete transaction of message (including message transfer and acknowledgement transfer).</span></span>  

6. <span data-ttu-id="760b2-216">在中**常规**选项卡中，**常规属性**页上，在**公用主机设置**部分中，选择**打开报告**，，然后选择**存储消息负载以用于报告**。</span><span class="sxs-lookup"><span data-stu-id="760b2-216">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**, and then select **Store message payload for reporting**.</span></span>  

7. <span data-ttu-id="760b2-217">在执行以下任务**Fabrikam-> Contoso**选项卡。</span><span class="sxs-lookup"><span data-stu-id="760b2-217">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  

   1. <span data-ttu-id="760b2-218">上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，并**ISA8**) 的测试消息中这些标头字段的值相对应。</span><span class="sxs-lookup"><span data-stu-id="760b2-218">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="760b2-219">需要发送方和接收方限定符和标识符字段才能执行协议解析。</span><span class="sxs-lookup"><span data-stu-id="760b2-219">requires the qualifier and identifier fields for sender and receiver in order to perform agreement resolution.</span></span> <span data-ttu-id="760b2-220">它将匹配的值**ISA5**， **ISA6**， **ISA7**，以及**ISA8**与协议属性中的交换标头中。</span><span class="sxs-lookup"><span data-stu-id="760b2-220">It will match the values of **ISA5**, **ISA6**, **ISA7**, and **ISA8** in the interchange header with those in the properties of an agreement.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="760b2-221">此外将通过匹配发送方限定符和标识符 （不接收方限定符和标识符） 来解析协议。</span><span class="sxs-lookup"><span data-stu-id="760b2-221">will also resolve the agreement by matching the sender qualifier and identifier (without the receiver qualifier and identifier).</span></span> <span data-ttu-id="760b2-222">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不能解析协议，它将使用后备协议属性。</span><span class="sxs-lookup"><span data-stu-id="760b2-222">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot resolve the agreement, it will use the fallback agreement properties.</span></span>  
      > 
      > [!NOTE]
      >  <span data-ttu-id="760b2-223">如果将"EDI 接口开发人员教程"中的 SamplePO.txt 文件用作测试消息，设置**ISA5**到**ZZ**， **ISA6**到**THEM**， **ISA7**到**ZZ**，并**ISA8**到**美国**。</span><span class="sxs-lookup"><span data-stu-id="760b2-223">If you are using the SamplePO.txt file from the “EDI Interface Developer Tutorial” as your test message, set **ISA5** to **ZZ**, **ISA6** to **THEM**, **ISA7** to **ZZ**, and **ISA8** to **US**.</span></span>  

   2. <span data-ttu-id="760b2-224">上**验证**页**交换设置**部分中，请确保**检查重复的 isa13**选项处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="760b2-224">On the **Validation** page under the **Interchange Settings** section, make sure **Check for duplicate ISA13** option is unchecked.</span></span>  

      > [!NOTE]
      >  <span data-ttu-id="760b2-225">清除**检查重复的 isa13**属性使您能够接收同一消息的多个实例。</span><span class="sxs-lookup"><span data-stu-id="760b2-225">Clearing the **Check for duplicate ISA13** property enables you to receive multiple instances of the same message.</span></span>  

   3. <span data-ttu-id="760b2-226">上**字符集和分隔符**页**交换设置**部分中，选择**CR LF**选项。</span><span class="sxs-lookup"><span data-stu-id="760b2-226">On the **Charset and Separators** page under the **Interchange Settings** section, select the **CR LF** option.</span></span>  

   4. <span data-ttu-id="760b2-227">上**发送端口**页**交换设置**部分中，关联将从 Fabrikam 接收 EDI 交换的发送端口。</span><span class="sxs-lookup"><span data-stu-id="760b2-227">On the **Send Ports** page under the **Interchange Settings** section, associate the send port that will be receiving the EDI interchange from Fabrikam.</span></span> <span data-ttu-id="760b2-228">在中**发送端口**网格下**名称**列，再单击某个空单元格，并从下拉列表中，选择创建用于从 Fabrikam 接收 EDI 交换的发送端口。</span><span class="sxs-lookup"><span data-stu-id="760b2-228">In the **Send ports** grid, under the **Name** column, click an empty cell, and from the drop-down list, select the send port created for receiving the EDI interchange from Fabrikam.</span></span>  

   5. <span data-ttu-id="760b2-229">上**验证**页**事务集设置**部分中，保留**EDI 类型验证**检查，并检查**扩展验证**.</span><span class="sxs-lookup"><span data-stu-id="760b2-229">On the **Validation** page under the **Transaction Set Settings** section, leave **EDI Type Validation** checked and check **Extended validation**.</span></span>  

   6. <span data-ttu-id="760b2-230">如果你使用附带的标准架构之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后在**本地主机设置**页下**事务集设置**部分中，选择要使用的架构的命名空间处理传入的交换。</span><span class="sxs-lookup"><span data-stu-id="760b2-230">If you are using one of the standard schemas shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], on the **Local Host Settings** page under the **Transaction Set Settings** section, select the namespace for the schema to be used to process the incoming interchange.</span></span>  


      |       <span data-ttu-id="760b2-231">使用此选项</span><span class="sxs-lookup"><span data-stu-id="760b2-231">Use this</span></span>       |                           <span data-ttu-id="760b2-232">执行的操作</span><span class="sxs-lookup"><span data-stu-id="760b2-232">To do this</span></span>                            |
      |----------------------|-----------------------------------------------------------------|
      |     <span data-ttu-id="760b2-233">**默认**</span><span class="sxs-lookup"><span data-stu-id="760b2-233">**Default**</span></span>      |                <span data-ttu-id="760b2-234">列中选中的复选框</span><span class="sxs-lookup"><span data-stu-id="760b2-234">Select the checkbox in the column</span></span>                |
      |     <span data-ttu-id="760b2-235">**对于 ST1**</span><span class="sxs-lookup"><span data-stu-id="760b2-235">**For ST1**</span></span>      |                <span data-ttu-id="760b2-236">选择**850 – 采购订单**。</span><span class="sxs-lookup"><span data-stu-id="760b2-236">Select **850 - Purchase Order**.</span></span>                 |
      |       <span data-ttu-id="760b2-237">**GS2**</span><span class="sxs-lookup"><span data-stu-id="760b2-237">**GS2**</span></span>        |                         <span data-ttu-id="760b2-238">输入**THEM**。</span><span class="sxs-lookup"><span data-stu-id="760b2-238">Enter **THEM**.</span></span>                         |
      | <span data-ttu-id="760b2-239">**目标 Namespace**</span><span class="sxs-lookup"><span data-stu-id="760b2-239">**Target Namespace**</span></span> | <span data-ttu-id="760b2-240">选择 <http://schemas.microsoft.com/BizTalk/EDI/X12/2006>。</span><span class="sxs-lookup"><span data-stu-id="760b2-240">Select **<http://schemas.microsoft.com/BizTalk/EDI/X12/2006>**.</span></span> |

      > [!NOTE]
      >  <span data-ttu-id="760b2-241">设置属性后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来确定要处理传入 850 交换时使用的架构。</span><span class="sxs-lookup"><span data-stu-id="760b2-241">Setting the properties enables [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to determine the schema to be used in processing the incoming 850 interchange.</span></span> <span data-ttu-id="760b2-242">如果交换具有网格的行输入的 GS02 和 ST01 值，然后将使用在同一行的目标命名空间来确定要使用的架构。</span><span class="sxs-lookup"><span data-stu-id="760b2-242">If an interchange has the values of GS02 and ST01 that are entered on a line of the grid, then the target namespace for the same line will be used to determine the schema to be used.</span></span>  

   7. <span data-ttu-id="760b2-243">上**信封**页**事务集设置**部分中，输入在网格的第一行中的所有列的值。</span><span class="sxs-lookup"><span data-stu-id="760b2-243">On the **Envelopes** page under the **Transaction Set Settings** section, enter values for all columns in the first line of the grid.</span></span>  


      |       <span data-ttu-id="760b2-244">使用此选项</span><span class="sxs-lookup"><span data-stu-id="760b2-244">Use this</span></span>       |                                                                                                                                               <span data-ttu-id="760b2-245">执行的操作</span><span class="sxs-lookup"><span data-stu-id="760b2-245">To do this</span></span>                                                                                                                                               |
      |----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |     <span data-ttu-id="760b2-246">**默认**</span><span class="sxs-lookup"><span data-stu-id="760b2-246">**Default**</span></span>      | <span data-ttu-id="760b2-247">选择中的复选框**默认**列。</span><span class="sxs-lookup"><span data-stu-id="760b2-247">Select the checkbox in the **Default** column.</span></span> <span data-ttu-id="760b2-248">**注意：** 选择此行作为默认值的值**GS1**， **GS2**， **GS3**， **GS7**，并**GS8**是即使使用的值**事务类型**，**版本/发行版**，并**目标命名空间**不是消息的匹配项。</span><span class="sxs-lookup"><span data-stu-id="760b2-248">**Note:**  When you select this row as the default, the values for **GS1**, **GS2**, **GS3**, **GS7**, and **GS8** are used even if the values for **Transaction Type**, **Version/Release**, and **Target namespace** are not a match for the message.</span></span> |
      | <span data-ttu-id="760b2-249">**事务类型**</span><span class="sxs-lookup"><span data-stu-id="760b2-249">**Transaction Type**</span></span> |                                                                                                                <span data-ttu-id="760b2-250">选择你的测试消息的消息类型**850 – 采购订单**。</span><span class="sxs-lookup"><span data-stu-id="760b2-250">Select the message type of your test message, **850 - Purchase Order**.</span></span>                                                                                                                 |
      | <span data-ttu-id="760b2-251">**版本/发行版**</span><span class="sxs-lookup"><span data-stu-id="760b2-251">**Version/Release**</span></span>  |                                                                                                                                   <span data-ttu-id="760b2-252">输入 EDI 版本， **00401**。</span><span class="sxs-lookup"><span data-stu-id="760b2-252">Enter the EDI version, **00401**.</span></span>                                                                                                                                    |
      | <span data-ttu-id="760b2-253">**目标命名空间**</span><span class="sxs-lookup"><span data-stu-id="760b2-253">**Target namespace**</span></span> |                                                                                                                    <span data-ttu-id="760b2-254">选择 <http://schemas.microsoft.com/BizTalk/Edi/X12/2006>。</span><span class="sxs-lookup"><span data-stu-id="760b2-254">Select **<http://schemas.microsoft.com/BizTalk/Edi/X12/2006>**.</span></span>                                                                                                                     |
      |       <span data-ttu-id="760b2-255">**GS1**</span><span class="sxs-lookup"><span data-stu-id="760b2-255">**GS1**</span></span>        |                                                                                                      <span data-ttu-id="760b2-256">验证是否已选中的测试消息的消息类型， **PO-采购订单 (850)**。</span><span class="sxs-lookup"><span data-stu-id="760b2-256">Verify that the message type of the test message is selected, **PO - Purchase Order (850)**.</span></span>                                                                                                      |
      |       <span data-ttu-id="760b2-257">**GS2**</span><span class="sxs-lookup"><span data-stu-id="760b2-257">**GS2**</span></span>        |                                                                                                                               <span data-ttu-id="760b2-258">输入应用程序发送方的值。</span><span class="sxs-lookup"><span data-stu-id="760b2-258">Enter a value for the Application sender.</span></span>                                                                                                                                |
      |       <span data-ttu-id="760b2-259">**GS3**</span><span class="sxs-lookup"><span data-stu-id="760b2-259">**GS3**</span></span>        |                                                                                                                              <span data-ttu-id="760b2-260">输入应用程序接收方的值。</span><span class="sxs-lookup"><span data-stu-id="760b2-260">Enter a value for the Application receiver.</span></span>                                                                                                                               |
      |       <span data-ttu-id="760b2-261">**GS4**</span><span class="sxs-lookup"><span data-stu-id="760b2-261">**GS4**</span></span>        |            <span data-ttu-id="760b2-262">选择所需的日期格式。</span><span class="sxs-lookup"><span data-stu-id="760b2-262">Select the date format that you want.</span></span> <span data-ttu-id="760b2-263">**注意：** 您必须下拉列表中选择一个值，而不仅仅是单击该字段以显示默认值。</span><span class="sxs-lookup"><span data-stu-id="760b2-263">**Note:**  You have to select the value in the drop-down list, not just click in the field to display the default.</span></span> <span data-ttu-id="760b2-264">如果您单击字段而无需从下拉列表中选择值，该值将不实际选择。</span><span class="sxs-lookup"><span data-stu-id="760b2-264">If you click in the field without selecting the value from the drop-down list, the value will not actually be selected.</span></span>            |
      |       <span data-ttu-id="760b2-265">**GS5**</span><span class="sxs-lookup"><span data-stu-id="760b2-265">**GS5**</span></span>        |                                                                                                                                 <span data-ttu-id="760b2-266">选择所需的时间格式。</span><span class="sxs-lookup"><span data-stu-id="760b2-266">Select the time format that you want.</span></span>                                                                                                                                  |
      |       <span data-ttu-id="760b2-267">**GS7**</span><span class="sxs-lookup"><span data-stu-id="760b2-267">**GS7**</span></span>        |                                                                                                                           <span data-ttu-id="760b2-268">选择**X-公认的标准委员会 X12**。</span><span class="sxs-lookup"><span data-stu-id="760b2-268">Select **X - Accredited Standards Committee X12**.</span></span>                                                                                                                           |
      |       <span data-ttu-id="760b2-269">**GS8**</span><span class="sxs-lookup"><span data-stu-id="760b2-269">**GS8**</span></span>        |                                                                                                                        <span data-ttu-id="760b2-270">验证已输入 EDI 版本， **00401**。</span><span class="sxs-lookup"><span data-stu-id="760b2-270">Verify that the EDI version has been entered, **00401**.</span></span>                                                                                                                        |

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="760b2-271">将设置 GS01、 GS02、 GS03、 GS04、 GS05、 GS07 和基于为输入的值对出站确认的 GS08**事务类型**，**版本/发行版**，和**目标命名空间**。</span><span class="sxs-lookup"><span data-stu-id="760b2-271">will set the values for GS01, GS02, GS03, GS04, GS05, GS07, and GS08 of the outbound acknowledgments based on the values entered for **Transaction Type**, **Version/Release**, and **Target namespace**.</span></span> <span data-ttu-id="760b2-272">发送管道将尝试匹配事务集类型、 X12 版本和消息的标头中的相应值的目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="760b2-272">The send pipeline attempts to match the transaction set type, the X12 version, and the target namespace with the corresponding values in the header of the message.</span></span> <span data-ttu-id="760b2-273">如果成功，它将使用与关联的 GS 值**事务类型**，**版本/发行版**，并**目标命名空间**值。</span><span class="sxs-lookup"><span data-stu-id="760b2-273">If successful, it uses the GS values associated with the **Transaction Type**, **Version/Release**, and **Target namespace** values.</span></span>  

8. <span data-ttu-id="760b2-274">在执行以下任务**Contoso-> Fabrikam**选项卡。</span><span class="sxs-lookup"><span data-stu-id="760b2-274">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="760b2-275">在本演练中，我们指定的选项卡中所需的值，以便可以成功创建协议。</span><span class="sxs-lookup"><span data-stu-id="760b2-275">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="760b2-276">若要成功创建协议，两个单向协议选项卡必须具有定义为值**ISA5**， **ISA6**， **ISA7**，以及**ISA8**。</span><span class="sxs-lookup"><span data-stu-id="760b2-276">To successfully create an agreement, both one-way agreement tabs must have values defined for **ISA5**, **ISA6**, **ISA7**, and **ISA8**.</span></span>  

   1.  <span data-ttu-id="760b2-277">上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，并**ISA8**) 的测试消息中这些标头字段的值相对应。</span><span class="sxs-lookup"><span data-stu-id="760b2-277">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  

       > [!NOTE]
       >  <span data-ttu-id="760b2-278">如果将"EDI 接口开发人员教程"中的 SamplePO.txt 文件用作测试消息，设置**ISA5**到**ZZ**， **ISA6**到**美国**， **ISA7**到**ZZ**，并**ISA8**到**THEM**。</span><span class="sxs-lookup"><span data-stu-id="760b2-278">If you are using the SamplePO.txt file from the “EDI Interface Developer Tutorial” as your test message, set **ISA5** to **ZZ**, **ISA6** to **US**, **ISA7** to **ZZ**, and **ISA8** to **THEM**.</span></span>  

9. <span data-ttu-id="760b2-279">单击 **“应用”**。</span><span class="sxs-lookup"><span data-stu-id="760b2-279">Click **Apply**.</span></span>  

10. <span data-ttu-id="760b2-280">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="760b2-280">Click **OK**.</span></span> <span data-ttu-id="760b2-281">中列出新添加的协议**协议**一部分**参与方和业务配置文件**窗格。</span><span class="sxs-lookup"><span data-stu-id="760b2-281">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="760b2-282">默认情况下启用新添加的协议。</span><span class="sxs-lookup"><span data-stu-id="760b2-282">The newly added agreement is enabled by default.</span></span>  

### <a name="testing-the-walkthrough"></a><span data-ttu-id="760b2-283">测试演练</span><span class="sxs-lookup"><span data-stu-id="760b2-283">Testing the Walkthrough</span></span>  
 <span data-ttu-id="760b2-284">本部分提供有关如何测试演练的信息。</span><span class="sxs-lookup"><span data-stu-id="760b2-284">This section provides information on how to test the walkthrough.</span></span>  

##### <a name="to-test-the-walkthrough"></a><span data-ttu-id="760b2-285">若要测试演练</span><span class="sxs-lookup"><span data-stu-id="760b2-285">To test the walkthrough</span></span>  

1. <span data-ttu-id="760b2-286">在 Windows 资源管理器拖放测试 EDI 交换到本地接收文件夹中。</span><span class="sxs-lookup"><span data-stu-id="760b2-286">In Windows Explorer, drop the test EDI interchange into your local receive folder.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="760b2-287">对于测试消息，可以使用在 EDI 接口开发人员教程中使用的 SamplePO.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="760b2-287">For a test message, you can use the SamplePO.txt file that is used in the EDI Interface Developer tutorial.</span></span> <span data-ttu-id="760b2-288">该文件中都随附[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial 文件夹。</span><span class="sxs-lookup"><span data-stu-id="760b2-288">That file is shipped in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial folder.</span></span> <span data-ttu-id="760b2-289">这是一个 X12 850 消息。</span><span class="sxs-lookup"><span data-stu-id="760b2-289">This is an X12 850 message.</span></span> <span data-ttu-id="760b2-290">如果您使用此消息，则必须已经部署 X12_00401_850.xsd 架构，在该架构[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI 文件夹。</span><span class="sxs-lookup"><span data-stu-id="760b2-290">If you use this message, you must have deployed the X12_00401_850.xsd schema that is shipped in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI folder.</span></span> <span data-ttu-id="760b2-291">必须使用 X12 850 性架构中的[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema 文件夹。</span><span class="sxs-lookup"><span data-stu-id="760b2-291">You must not use the X12 850 schema in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema folder.</span></span>  

2. <span data-ttu-id="760b2-292">在 Windows 资源管理器中，打开为发送端口指定的目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="760b2-292">In Windows Explorer, open the destination folder specified for the send port.</span></span> <span data-ttu-id="760b2-293">验证该文件夹包含输出 EDI 交换的 ISA、 GS 和 ST 标头与协议属性中输入的值匹配。</span><span class="sxs-lookup"><span data-stu-id="760b2-293">Verify that the folder contains an output EDI interchange that has ISA, GS, and ST headers that match the values that you entered in the agreement properties.</span></span>  

## <a name="see-also"></a><span data-ttu-id="760b2-294">请参阅</span><span class="sxs-lookup"><span data-stu-id="760b2-294">See Also</span></span>  
 [<span data-ttu-id="760b2-295">开发和配置 BizTalk Server EDI 解决方案</span><span class="sxs-lookup"><span data-stu-id="760b2-295">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)