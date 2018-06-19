---
title: '演练 (AS2): 通过使用同步 MDN 的 AS2 发送 EDI |Microsoft 文档'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21891d29-eb22-4b31-9258-14b72ae675dc
caps.latest.revision: 34
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4953e0f3cdc5373d20497d1510fafd9f24991c30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22292341"
---
# <a name="walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn"></a><span data-ttu-id="b2b73-102">演练 (AS2)：使用同步 MDN 通过 AS2 发送 EDI</span><span class="sxs-lookup"><span data-stu-id="b2b73-102">Walkthrough (AS2): Sending EDI over AS2 with a Synchronous MDN</span></span>
<span data-ttu-id="b2b73-103">本演练将介绍创建一个通过 AS2 用同步 MDN 发送 EDI 消息的解决方案的分步操作过程。</span><span class="sxs-lookup"><span data-stu-id="b2b73-103">This walkthrough provides a set of step-by-step procedures that creates a solution for sending EDI messages over AS2, with a synchronous MDN.</span></span> <span data-ttu-id="b2b73-104">您可以在单台计算机上创建并测试本演练中的完整解决方案。</span><span class="sxs-lookup"><span data-stu-id="b2b73-104">You can create and test the full solution in this walkthrough on a single computer.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b2b73-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="b2b73-105">Prerequisites</span></span>  
 <span data-ttu-id="b2b73-106">以下为执行本主题中的过程的前提条件：</span><span class="sxs-lookup"><span data-stu-id="b2b73-106">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="b2b73-107">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="b2b73-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
-   <span data-ttu-id="b2b73-108">运行演练的计算机必须安装了 Internet 信息服务 (IIS)。</span><span class="sxs-lookup"><span data-stu-id="b2b73-108">The computer that runs the walkthrough must have Internet Information Services (IIS) 7 installed.</span></span>  
  
-   <span data-ttu-id="b2b73-109">如果运行此演练的计算机安装了 64 位版本的 Windows，则您必须确保 BizTalk 主机标记只能为 32 位。</span><span class="sxs-lookup"><span data-stu-id="b2b73-109">If the computer that runs the walkthrough is installed with a 64-bit version of Windows, you must ensure that the BizTalk hosts are marked as 32-bit only.</span></span> <span data-ttu-id="b2b73-110">您还必须确保 IIS 已将“为应用程序池启用 32 位应用程序设置”设置为 True。 </span><span class="sxs-lookup"><span data-stu-id="b2b73-110">You must also ensure IIS has the Enable 32-Bit Application Setting for the Application Pools set to True.</span></span> <span data-ttu-id="b2b73-111">有关详细信息，请参阅[教程 3: AS2 教程](../core/tutorial-3-as2-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="b2b73-111">For more information, see [Tutorial 3: AS2 Tutorial](../core/tutorial-3-as2-tutorial.md).</span></span>  
  
## <a name="how-the-solution-sends-an-edias2-message-and-returns-a-synchronous-mdn"></a><span data-ttu-id="b2b73-112">解决方案如何发送 EDI/AS2 消息并返回同步 MDN</span><span class="sxs-lookup"><span data-stu-id="b2b73-112">How the Solution Sends an EDI/AS2 Message and Returns a Synchronous MDN</span></span>  
 <span data-ttu-id="b2b73-113">该解决方案将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b2b73-113">The solution will do the following:</span></span>  
  
1.  <span data-ttu-id="b2b73-114">一个单向 FILE 接收端口从 Contoso 接收 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="b2b73-114">A one-way FILE receive port receives an EDI interchange from Contoso.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2b73-115">此列表中的事件可能不会按所示顺序发生。</span><span class="sxs-lookup"><span data-stu-id="b2b73-115">The events in this list may not occur in the order shown.</span></span>  
  
2.  <span data-ttu-id="b2b73-116">使用直通接收管道时，接收端口会将测试消息原封不动地放入 MeassageBox。</span><span class="sxs-lookup"><span data-stu-id="b2b73-116">Using a passthrough receive pipeline, the receive port drops the test message into the MessageBox, unchanged.</span></span>  
  
3.  <span data-ttu-id="b2b73-117">静态双向发送端口提取 EDI 交换并将其编码为 AS2 格式。</span><span class="sxs-lookup"><span data-stu-id="b2b73-117">A static two-way send port picks up the EDI interchange and encodes it into AS2 format.</span></span>  
  
4.  <span data-ttu-id="b2b73-118">发送端口通过 AS2 传输将 AS2 编码的 EDI 交换发送至 Fabrikam 参与方。</span><span class="sxs-lookup"><span data-stu-id="b2b73-118">The send port sends the AS2-encoded EDI interchange over AS2 transport to the Fabrikam party.</span></span>  
  
5.  <span data-ttu-id="b2b73-119">Fabrikam 的双向接收端口使用 Fabrikam 虚拟目录接收 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="b2b73-119">The two-way receive port at Fabrikam receives the AS2 message using the Fabrikam virtual directory.</span></span> <span data-ttu-id="b2b73-120">接收管道将来自 AS2 的 EDI 交换解码并放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="b2b73-120">The receive pipeline decodes the EDI interchange from AS2, and drops the EDI interchange into the MessageBox.</span></span>  
  
6.  <span data-ttu-id="b2b73-121">与双向接收端口关联的发送端口返回同步 MDN。</span><span class="sxs-lookup"><span data-stu-id="b2b73-121">The send port associated with the two-way receive port returns a synchronous MDN.</span></span>  
  
7.  <span data-ttu-id="b2b73-122">与双向发送端口关联的接收端口接收 MDN 并将其放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="b2b73-122">The receive port associated with the two-way send port receives the MDN, and drops it in the MessageBox.</span></span>  
  
8.  <span data-ttu-id="b2b73-123">带有直通发送管道的静态单向发送端口提取 MDN。</span><span class="sxs-lookup"><span data-stu-id="b2b73-123">A static one-way send port with a passthrough send pipeline picks up the MDN.</span></span>  
  
9. <span data-ttu-id="b2b73-124">该单向发送端口将 MDN 发送至本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2b73-124">The one-way send port sends the MDN to a local folder.</span></span>  
  
10. <span data-ttu-id="b2b73-125">带有直通发送管道的静态单向发送端口提取 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="b2b73-125">A static one-way send port with a passthrough send pipeline picks up the EDI message.</span></span>  
  
11. <span data-ttu-id="b2b73-126">单向发送端口将 EDI 消息发送至一个本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2b73-126">The one-way send port sends the EDI message to a local folder.</span></span>  
  
 <span data-ttu-id="b2b73-127">下图显示出此解决方案的结构。</span><span class="sxs-lookup"><span data-stu-id="b2b73-127">The following figure shows the architecture for this solution.</span></span>  
  
 <span data-ttu-id="b2b73-128">![AS2 发送与同步 MDN](../core/media/270d24b7-3b5d-45cc-ba06-6c9f74717194.gif "270d24b7-3b5d-45cc-ba06-6c9f74717194")</span><span class="sxs-lookup"><span data-stu-id="b2b73-128">![AS2 sending with a Synchronous MDN](../core/media/270d24b7-3b5d-45cc-ba06-6c9f74717194.gif "270d24b7-3b5d-45cc-ba06-6c9f74717194")</span></span>  
  
## <a name="the-functionality-in-this-solution"></a><span data-ttu-id="b2b73-129">此解决方案中的功能</span><span class="sxs-lookup"><span data-stu-id="b2b73-129">The Functionality in this Solution</span></span>  
 <span data-ttu-id="b2b73-130">本演练的功能具有以下特点：</span><span class="sxs-lookup"><span data-stu-id="b2b73-130">The following applies to the functionality of this walkthrough:</span></span>  
  
-   <span data-ttu-id="b2b73-131">本演练针对的是 AS2 功能，而非 EDI 功能。</span><span class="sxs-lookup"><span data-stu-id="b2b73-131">This walkthrough deals with AS2 functionality, not EDI functionality.</span></span> <span data-ttu-id="b2b73-132">因此，AS2 处理所涉及的所有端口使用的是 AS2Receive 或 AS2Send 管道，而非 AS2EdiReceive 和 AS2EdiSend。</span><span class="sxs-lookup"><span data-stu-id="b2b73-132">As a result, all ports involved in AS2 processing use either AS2Receive or AS2Send pipelines, not AS2EdiReceive or AS2EdiSend.</span></span> <span data-ttu-id="b2b73-133">AS2 处理未涉及到的端口使用 PassThruReceive 或 PassThruTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="b2b73-133">Ports that are not involved in AS2 processing use PassThruReceive or PassThruTransmit pipelines.</span></span>  
  
-   <span data-ttu-id="b2b73-134">状态报告未启用。</span><span class="sxs-lookup"><span data-stu-id="b2b73-134">Status reporting is not enabled.</span></span>  
  
-   <span data-ttu-id="b2b73-135">此解决方案不在不可否认数据库中配置签名、压缩、加密或消息存储。</span><span class="sxs-lookup"><span data-stu-id="b2b73-135">This solution does not configure signing, compression, encryption, or message storage in the non-repudiation database.</span></span> <span data-ttu-id="b2b73-136">有关配置这些属性的过程，请参阅[配置 AS2 属性](../core/configuring-as2-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="b2b73-136">For procedures on configuring those properties, see [Configuring AS2 Properties](../core/configuring-as2-properties.md).</span></span>  
  
## <a name="configuring-and-testing-the-walkthrough"></a><span data-ttu-id="b2b73-137">配置和测试演练</span><span class="sxs-lookup"><span data-stu-id="b2b73-137">Configuring and Testing the Walkthrough</span></span>  
 <span data-ttu-id="b2b73-138">该解决方案所需的过程包括：</span><span class="sxs-lookup"><span data-stu-id="b2b73-138">The procedures required for this solution include the following:</span></span>  
  
-   <span data-ttu-id="b2b73-139">使用所需的消息架构生成并部署 BizTalk 项目，并将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 设置为在处理接收的交换时使用这些架构。</span><span class="sxs-lookup"><span data-stu-id="b2b73-139">Build and deploy a BizTalk project with the required message schema, making the schema available for use by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in processing the received interchange.</span></span>  
  
-   <span data-ttu-id="b2b73-140">启用接收 AS2 消息时使用的 BTS ISAPI 筛选器。</span><span class="sxs-lookup"><span data-stu-id="b2b73-140">Enable the BTS ISAPI filter used in receiving the AS2 message.</span></span>  
  
-   <span data-ttu-id="b2b73-141">按照接收位置中的配置，创建一个用于从 Contoso 接收 AS2 消息的 Fabrikam 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="b2b73-141">Create a Fabrikam virtual directory that receives the AS2 message from Contoso, as configured in the receive location.</span></span>  
  
-   <span data-ttu-id="b2b73-142">指定 Fabrikam 虚拟目录不由 Windows SharePoint Services 托管。</span><span class="sxs-lookup"><span data-stu-id="b2b73-142">Specify that the Fabrikam virtual directory is not managed by Windows SharePoint Services.</span></span>  
  
-   <span data-ttu-id="b2b73-143">创建一个单向 FILE 接收端口接收通过 AS2 传输方法发送的 EDI 测试消息。</span><span class="sxs-lookup"><span data-stu-id="b2b73-143">Create a one-way FILE receive port to receive the EDI test message that will be sent via AS2 transport.</span></span> <span data-ttu-id="b2b73-144">创建接收测试消息的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2b73-144">Create the local folder to receive the test message.</span></span>  
  
-   <span data-ttu-id="b2b73-145">为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建一个静态双向 HTTP 发送端口，以将包含 EDI 业务文档的 AS2 消息发送至 Fabrikam 并接收 MDN 响应。</span><span class="sxs-lookup"><span data-stu-id="b2b73-145">Create a static two-way HTTP send port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send the AS2 message containing the EDI business document to Fabrikam, and to receive the MDN response.</span></span> <span data-ttu-id="b2b73-146">将发送管道配置为 AS2Send 管道，将接收管道配置为 AS2Receive 管道。</span><span class="sxs-lookup"><span data-stu-id="b2b73-146">Configure the send pipeline to be the AS2Send pipeline and the receive pipeline to be the AS2Receive pipeline.</span></span>  
  
-   <span data-ttu-id="b2b73-147">为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建一个双向 HTTP 接收端口，用于接收 AS2 消息和发送 MDN 响应。</span><span class="sxs-lookup"><span data-stu-id="b2b73-147">Create a two-way HTTP receive port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive the AS2 message, and to send the MDN response.</span></span> <span data-ttu-id="b2b73-148">将接收管道配置为 AS2Receive 管道，将发送管道配置为 AS2Send 管道。</span><span class="sxs-lookup"><span data-stu-id="b2b73-148">Configure the receive pipeline to be the AS2Receive pipeline and the send pipeline to be the AS2Send pipeline.</span></span> <span data-ttu-id="b2b73-149">配置用于接收经 Fabrikam 虚拟目录发送的 AS2 消息的接收位置。</span><span class="sxs-lookup"><span data-stu-id="b2b73-149">Configure the receive location to receive the AS2 message via the Fabrikam virtual directory.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2b73-150">此解决方案在单台计算机上执行；因此用于从 Contoso 发送 AS2 消息的双向发送端口和作为 Fabrikam 接收 AS2 消息的双向接收端口都在同一计算机上。</span><span class="sxs-lookup"><span data-stu-id="b2b73-150">This solution is targeted for a single computer; as a result, the two-way send port sending the AS2 message (from Contoso) and the two-way receive port receiving the AS2 message (as Fabrikam) are on the same computer.</span></span>  
  
-   <span data-ttu-id="b2b73-151">创建一个带有直通发送管道的单向 FILE 发送端口以将 MDN 路由至本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2b73-151">Create a static one-way FILE send port (with a passthrough send pipeline) to route the MDN to a local folder.</span></span> <span data-ttu-id="b2b73-152">创建本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2b73-152">Create the local folder.</span></span>  
  
-   <span data-ttu-id="b2b73-153">创建一个带有直通发送管道的单向 FILE 发送端口以将消息负载路由至本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2b73-153">Create a static one-way FILE send port (with a passthrough send pipeline) to route the message payload to a local folder.</span></span> <span data-ttu-id="b2b73-154">创建本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2b73-154">Create the local folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2b73-155">如果没有用于订阅该消息负载的发送端口，它将会在 MessageBox 中挂起。 </span><span class="sxs-lookup"><span data-stu-id="b2b73-155">If you do not have a send port to subscribe to the message payload, it will be suspended in the MessageBox.</span></span>  
  
-   <span data-ttu-id="b2b73-156">为 Fabrikam 和 Contoso 创建参与方（贸易合作伙伴）。</span><span class="sxs-lookup"><span data-stu-id="b2b73-156">Create a party (trading partner) for both Fabrikam and Contoso.</span></span>  
  
-   <span data-ttu-id="b2b73-157">为这两个贸易方创建业务配置文件每个。</span><span class="sxs-lookup"><span data-stu-id="b2b73-157">Create a business profile each for both the trading parties.</span></span>  
  
-   <span data-ttu-id="b2b73-158">在 Fabrikam 和 Contoso 的业务配置文件之间创建一个 AS2 协议。</span><span class="sxs-lookup"><span data-stu-id="b2b73-158">Create an AS2 agreement between the business profiles for Fabrikam and Contoso.</span></span> <span data-ttu-id="b2b73-159">AS2 协议将包含发送 AS2 消息和接收同步 MDN 中返回的属性。</span><span class="sxs-lookup"><span data-stu-id="b2b73-159">The AS2 agreement would contain properties to send an AS2 message and receive a synchronous MDN in return.</span></span>  
  
-   <span data-ttu-id="b2b73-160">使用测试 EDI 交换测试演练。</span><span class="sxs-lookup"><span data-stu-id="b2b73-160">Test the walkthrough using a test EDI interchange.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2b73-161">对于测试消息，您可以使用在 EDI 接口开发人员教程中使用的 SamplePO.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="b2b73-161">For a test message, you can use the SamplePO.txt file that is used in the EDI Interface Developer tutorial.</span></span> <span data-ttu-id="b2b73-162">该文件位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\EDI Interface Developer Tutorial\ 文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2b73-162">That file is shipped in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\EDI Interface Developer Tutorial\ folder.</span></span> <span data-ttu-id="b2b73-163">这是一个 X12 850 消息。</span><span class="sxs-lookup"><span data-stu-id="b2b73-163">This is an X12 850 message.</span></span>  
  
### <a name="configuring-the-walkthrough"></a><span data-ttu-id="b2b73-164">配置演练</span><span class="sxs-lookup"><span data-stu-id="b2b73-164">Configuring the Walkthrough</span></span>  
 <span data-ttu-id="b2b73-165">本部分介绍配置演练的步骤。</span><span class="sxs-lookup"><span data-stu-id="b2b73-165">This section describes the procedures to configure the walkthrough.</span></span>  
  
##### <a name="to-deploy-the-message-schema"></a><span data-ttu-id="b2b73-166">部署消息架构</span><span class="sxs-lookup"><span data-stu-id="b2b73-166">To deploy the message schema</span></span>  
  
1.  <span data-ttu-id="b2b73-167">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，创建或打开 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="b2b73-167">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create or open a BizTalk project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2b73-168">本主题假定你已从你的应用程序添加了对包含 EDI 架构、管道和业务流程的 BizTalk EDI 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="b2b73-168">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="b2b73-169">如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。</span><span class="sxs-lookup"><span data-stu-id="b2b73-169">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
2.  <span data-ttu-id="b2b73-170">右键单击你的项目，指向**添加**，然后单击**现有项**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-170">Right-click your project, point to **Add**, and then click **Existing Item**.</span></span> <span data-ttu-id="b2b73-171">要使用 SamplePO.txt 文件测试您的解决方案，请访问 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI 文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2b73-171">To use the SamplePO.txt file to test your solution, move to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI folder.</span></span> <span data-ttu-id="b2b73-172">选择 X12_00401_850.xsd 架构，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-172">Select the X12_00401_850.xsd schema, and then click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2b73-173">若要使用不同的 EDI 架构时，请转到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_SchemaEDI 文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2b73-173">To use a different EDI schema, go to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_SchemaEDI folder.</span></span> <span data-ttu-id="b2b73-174">如果不具有已 EDI 架构解压缩到 XSD_SchemaEDI 文件夹中，执行**MicrosoftEdiXSDTemplates.exe** XSD_SchemaEDI 文件夹来解压缩到默认文件夹的架构中的文件。</span><span class="sxs-lookup"><span data-stu-id="b2b73-174">If the EDI schemas have not been unzipped into the XSD_SchemaEDI folders, execute the **MicrosoftEdiXSDTemplates.exe** file in the XSD_SchemaEDI folder to unzip the schemas into the default folder.</span></span>  
  
3.  <span data-ttu-id="b2b73-175">设置程序集密钥文件，然后生成并部署该程序集。</span><span class="sxs-lookup"><span data-stu-id="b2b73-175">Set the assembly key file, and then build and deploy the assembly.</span></span>  
  
##### <a name="to-enable-the-bts-isapi-filter"></a><span data-ttu-id="b2b73-176">启用 BTS ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="b2b73-176">To enable the BTS ISAPI Filter</span></span>  
  
1.  <span data-ttu-id="b2b73-177">单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="b2b73-177">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="b2b73-178">具体取决于操作系统，管理工具开始菜单选项可能不可用。</span><span class="sxs-lookup"><span data-stu-id="b2b73-178">Depending on the operating system, the Administrative Tools start menu option may not be available.</span></span> <span data-ttu-id="b2b73-179">在这种情况下，单击**启动**，单击**运行**，并输入`inetmgr`若要打开 Internet 信息服务 (IIS) 管理器。</span><span class="sxs-lookup"><span data-stu-id="b2b73-179">In such cases, click **Start**, click **Run**, and enter `inetmgr` to open Internet Information Services (IIS) Manager.</span></span>  
  
2.  <span data-ttu-id="b2b73-180">选择的根 Web 服务器条目并在**功能视图**，双击**处理程序映射**然后在操作窗格中单击**添加脚本映射**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-180">Select the root Web Server entry and in the **Features View**, double click **Handler Mappings** and then in the Actions pane click **Add Script Map**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2b73-181">在 Web 服务器级别配置的脚本映射将导致此映射将应用于所有子网站。</span><span class="sxs-lookup"><span data-stu-id="b2b73-181">Configuring the script mapping at the Web Server level will cause this mapping to apply to all child Web Sites.</span></span> <span data-ttu-id="b2b73-182">如果你想要限制映射到特定的网站或虚拟文件夹，选择目标站点或而不是 Web 服务器的文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2b73-182">If you wish to restrict the mapping to a specific Web Site or Virtual Folder, select the target site or folder instead of the Web Server.</span></span>  
  
3.  <span data-ttu-id="b2b73-183">在**添加脚本映射**对话框框中，输入`BtsHttpReceive.dll`中**请求路径**字段。</span><span class="sxs-lookup"><span data-stu-id="b2b73-183">In the **Add Script Map** dialog box, enter `BtsHttpReceive.dll` in the **Request path** field.</span></span>  
  
4.  <span data-ttu-id="b2b73-184">在**可执行文件**字段中，单击**省略号 （...）** 按钮，然后浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive。</span><span class="sxs-lookup"><span data-stu-id="b2b73-184">In the **Executable** field, click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive.</span></span> <span data-ttu-id="b2b73-185">选择 BtsHttpReceive.dll，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-185">Select BtsHttpReceive.dll and click **OK**.</span></span>  
  
5.  <span data-ttu-id="b2b73-186">输入`BizTalk HTTP Receive`中`Name`字段，然后再单击**请求限制**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-186">Enter `BizTalk HTTP Receive` in the `Name` field, and then click **Request Restrictions**.</span></span>  
  
6.  <span data-ttu-id="b2b73-187">在**请求限制**对话框中，选择**谓词**选项卡上，然后选择**的以下谓词之一**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-187">In the **Request Restrictions** dialog box, select the **Verbs** tab and then select **One of the following verbs**.</span></span> <span data-ttu-id="b2b73-188">输入`POST`作为谓词。</span><span class="sxs-lookup"><span data-stu-id="b2b73-188">Enter `POST` as the verb.</span></span>  
  
7.  <span data-ttu-id="b2b73-189">上**访问**选项卡上，选择**脚本**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-189">On the **Access** tab, select **Script** and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="b2b73-190">单击**确定**出现提示时允许 ISAPI 扩展插件，则单击**是**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-190">Click **OK** and when prompted to allow the ISAPI extension, click **Yes**.</span></span>  
  
##### <a name="to-configure-the-fabrikam-web-page"></a><span data-ttu-id="b2b73-191">配置 Fabrikam 网页</span><span class="sxs-lookup"><span data-stu-id="b2b73-191">To configure the Fabrikam Web page</span></span>  
  
1.  <span data-ttu-id="b2b73-192">在 IIS 管理器中，右键单击**应用程序池**和选择**添加应用程序池**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-192">In IIS Manager, right-click **Application Pools** and select **Add Application Pool**.</span></span>  
  
2.  <span data-ttu-id="b2b73-193">在**添加应用程序池**对话框框中，输入**BizTalkAppPool**中**名称**，然后选择 **.NET Framework V4.0.30210**中 **.NET framework 版本**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="b2b73-193">In **the Add Application Pool** dialog box, enter **BizTalkAppPool** in **Name**, and then select **.NET Framework V4.0.30210** in the **.NET Framework version** drop-down list.</span></span> <span data-ttu-id="b2b73-194">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-194">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2b73-195">根据计算机上安装的 [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] 版本，.NET Framework 的版本可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="b2b73-195">The version number may vary depending on the version of [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] installed on the machine.</span></span>  
  
3.  <span data-ttu-id="b2b73-196">选择**应用程序池**中**功能视图**选择**BizTalkAppPool**，然后单击**高级设置**中**操作**窗格。</span><span class="sxs-lookup"><span data-stu-id="b2b73-196">Select **Application Pools**, in the **Features View** select **BizTalkAppPool**, and then click **Advanced Settings** in the **Actions** pane.</span></span>  
  
4.  <span data-ttu-id="b2b73-197">在**高级设置**对话框中，选择**标识**，然后单击省略号 （...） 按钮。</span><span class="sxs-lookup"><span data-stu-id="b2b73-197">In the **Advanced Settings** dialog box, select **Identity** and then click the ellipsis (…) button.</span></span>  
  
5.  <span data-ttu-id="b2b73-198">在**应用程序池标识**对话框中，选择**自定义帐户**，然后单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-198">In the **Application Pool Identity** dialog box, select **Custom account** and then click **Set**.</span></span>  
  
6.  <span data-ttu-id="b2b73-199">输入**用户名**和**密码**是 administrators 组的成员的用户帐户，输入中的密码**确认密码**，然后单击**确定**三次以返回到 IIS 管理器。</span><span class="sxs-lookup"><span data-stu-id="b2b73-199">Enter the **User name** and **Password** for a user account that is a member of the administrators group, enter the password in **Confirm password** and then click **OK** three times to return to the IIS Manager.</span></span>  
  
7.  <span data-ttu-id="b2b73-200">在 IIS 管理器中，打开**站点**文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2b73-200">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="b2b73-201">右键单击**Default Web Site**节点，，然后选择**添加应用程序**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-201">Right-click the **Default Web Site** node, and then select **Add Application**.</span></span>  
  
8.  <span data-ttu-id="b2b73-202">在**添加应用程序**对话框框中，输入**Fabrikam**中**别名**，然后单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-202">In the **Add Application** dialog box, enter **Fabrikam** in **Alias**, and then click **Select**.</span></span>  
  
9. <span data-ttu-id="b2b73-203">在**选择应用程序池**对话框中，选择**BizTalkAppPool**单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-203">In the **Select Application Pool** dialog box, select **BizTalkAppPool** and click **OK**.</span></span>  
  
10. <span data-ttu-id="b2b73-204">单击省略号 （…） 按钮，然后浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]为 HttpReceive**物理路径**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-204">Click the ellipsis (…) button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive for the **Physical path**.</span></span>  
  
11. <span data-ttu-id="b2b73-205">单击**测试设置**并验证没有显示在错误**测试连接**对话框。</span><span class="sxs-lookup"><span data-stu-id="b2b73-205">Click **Test Settings** and verify that there are no errors displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="b2b73-206">单击 **“关闭”**，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-206">Click **Close**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="b2b73-207">在 IIS 管理器中，选择 Fabrikam 虚拟目录和在**功能视图**，双击**身份验证**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-207">In IIS Manager, select the Fabrikam virtual directory and in the **Features View**, double-click **Authentication**.</span></span>  
  
13. <span data-ttu-id="b2b73-208">在**身份验证**页上，选择**匿名身份验证**并确认**状态**是**已启用**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-208">In the **Authentication** page, select **Anonymous Authentication** and verify that the **Status** is **Enabled**.</span></span> <span data-ttu-id="b2b73-209">如果**状态**是**禁用**，单击**启用**中**操作**窗格。</span><span class="sxs-lookup"><span data-stu-id="b2b73-209">If the **Status** is **Disabled**, click **Enable** in the **Actions** pane.</span></span>  
  
##### <a name="to-specify-that-your-virtual-directory-is-not-managed-by-windows-sharepoint-services"></a><span data-ttu-id="b2b73-210">指定虚拟目录不由 Windows SharePoint Services 托管</span><span class="sxs-lookup"><span data-stu-id="b2b73-210">To specify that your virtual directory is not managed by Windows SharePoint Services</span></span>  
  
1.  <span data-ttu-id="b2b73-211">如果您的计算机上安装 Windows SharePoint Services，请单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**SharePoint 3.0 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-211">If Windows SharePoint Services is installed on your computer, click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2b73-212">如果用于设置演练的同一计算机上还安装了 Windows SharePoint Server，则此过程是必需的。</span><span class="sxs-lookup"><span data-stu-id="b2b73-212">This procedure is required if Windows SharePoint Server is installed on the same computer that you are setting the walkthrough up on.</span></span> <span data-ttu-id="b2b73-213">在该情况下，您必须指定 IIS 虚拟目录不由 Windows SharePoint Server 托管。</span><span class="sxs-lookup"><span data-stu-id="b2b73-213">In that case, you must specify that your IIS virtual directory is not being managed by Windows SharePoint Server.</span></span>  
  
2.  <span data-ttu-id="b2b73-214">上**管理中心**页上，在**管理中心**，单击**应用程序管理**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-214">On the **Central Administration** page, under **Central Administration**, click **Application Management**.</span></span>  
  
3.  <span data-ttu-id="b2b73-215">上**应用程序管理**页上，单击**定义管理路径**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-215">On the **Application Management** page, click **Define managed paths**.</span></span>  
  
4.  <span data-ttu-id="b2b73-216">在**定义管理路径**页上，在**添加新路径**中**路径**文本框中，输入`Fabrikam`。</span><span class="sxs-lookup"><span data-stu-id="b2b73-216">In the **Define Managed Paths** page, under **Add a New Path**, in the **Path** text box, enter `Fabrikam`.</span></span> <span data-ttu-id="b2b73-217">下**类型**，单击**排除路径**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-217">Under **Type**, click **Excluded Path**, and then click **OK**.</span></span>  
  
##### <a name="to-create-a-receive-port-to-receive-the-edi-test-message"></a><span data-ttu-id="b2b73-218">创建接收 EDI 测试消息的接收端口</span><span class="sxs-lookup"><span data-stu-id="b2b73-218">To create a receive port to receive the EDI test message</span></span>  
  
1.  <span data-ttu-id="b2b73-219">在 Windows 资源管理器中，创建一个用于从 Contoso 接收 EDI 交换的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2b73-219">In Windows Explorer, create a local folder to receive the EDI interchange from Contoso.</span></span>  
  
2.  <span data-ttu-id="b2b73-220">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**节点下的**BizTalk 应用程序 1**节点，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-220">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the **Receive Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
3.  <span data-ttu-id="b2b73-221">名称为接收端口**RecvISAFromCont**，然后单击**接收位置**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="b2b73-221">Name the receive port as **RecvISAFromCont**, and then click **Receive Locations** in the console tree.</span></span>  
  
4.  <span data-ttu-id="b2b73-222">单击 **“新建”**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-222">Click **New**.</span></span>  
  
5.  <span data-ttu-id="b2b73-223">名称的接收位置中，选择**文件**为**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-223">Name the receive location, select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="b2b73-224">有关**接收文件夹**，输入你在步骤 1 中创建的文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="b2b73-224">For **Receive folder**, enter the name of the folder that you created in step 1.</span></span>  
  
7.  <span data-ttu-id="b2b73-225">有关**文件掩码**，输入你的文件的扩展名。</span><span class="sxs-lookup"><span data-stu-id="b2b73-225">For **File mask**, enter the extension of your file.</span></span> <span data-ttu-id="b2b73-226">如果你使用 SamplePO.txt 文件作为测试消息，请输入 **\*.txt**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-226">If you are using the SamplePO.txt file as your test message, enter **\*.txt**.</span></span> <span data-ttu-id="b2b73-227">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-227">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="b2b73-228">有关**接收管道**，接受默认的**PassThruReceive**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-228">For **Receive pipeline**, accept the default of **PassThruReceive**.</span></span>  
  
9. <span data-ttu-id="b2b73-229">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="b2b73-229">Click **OK**, and then click **OK** again.</span></span>  
  
10. <span data-ttu-id="b2b73-230">单击**接收位置**节点，右键单击你接收位置，并依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-230">Click the **Receive Locations** node, right-click your receive location, and then click **Enable**.</span></span>  
  
##### <a name="to-create-a-two-way-send-port-to-send-the-edi-interchange-over-as2-to-fabrikam-and-receive-an-mdn-response"></a><span data-ttu-id="b2b73-231">创建通过 AS2 将 EDI 交换发送至 Fabrikam 并接收 MDN 响应的双向发送端口</span><span class="sxs-lookup"><span data-stu-id="b2b73-231">To create a two-way send port to send the EDI interchange over AS2 to Fabrikam and receive an MDN response</span></span>  
  
1.  > [!NOTE]
    >  <span data-ttu-id="b2b73-232">静态双向发送端口提取 EDI 交换并将其编码为 AS2 格式。</span><span class="sxs-lookup"><span data-stu-id="b2b73-232">A static two-way send port picks up the EDI interchange and encodes it into AS2 format.</span></span> <span data-ttu-id="b2b73-233">然后通过 AS2 传输将 AS2 编码的 EDI 交换发送到 Fabrikam 参与方。</span><span class="sxs-lookup"><span data-stu-id="b2b73-233">It then sends the AS2-encoded EDI interchange over AS2 transport to the Fabrikam party.</span></span> <span data-ttu-id="b2b73-234">其后，与双向发送端口关联的接收端口接收来自 Fabrikam 的 MDN 并将其放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="b2b73-234">Later, the receive port associated with the two-way send port receives the MDN from Fabrikam, and drops it in the MessageBox.</span></span>  
  
     <span data-ttu-id="b2b73-235">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk 应用程序 1**节点，指向**新建**，然后单击**静态请求作出响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-235">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
2.  <span data-ttu-id="b2b73-236">在**发送端口属性**对话框中，名称发送端口。</span><span class="sxs-lookup"><span data-stu-id="b2b73-236">In the **Send Port Properties** dialog box, name the send port.</span></span> <span data-ttu-id="b2b73-237">对于此解决方案，将命名为发送端口**SendISAToFab_RecMDN**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-237">For this solution, name the send port as **SendISAToFab_RecMDN**.</span></span>  
  
3.  <span data-ttu-id="b2b73-238">在**传输**部分中，选择**HTTP**为**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-238">In the **Transport** section, select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="b2b73-239">在**HTTP 传输属性**对话框中，为**目标 URL**，输入**http://localhost/Fabrikam/BTSHttpReceive.dll**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-239">In the **HTTP Transport Properties** dialog box, for **Destination URL**, enter **http://localhost/Fabrikam/BTSHttpReceive.dll**.</span></span>  
  
5.  <span data-ttu-id="b2b73-240">清除**启用区块编码**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-240">Clear **Enable Chunked Encoding**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="b2b73-241">在**发送管道**，选择**AS2Send**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-241">In **Send pipeline**, select **AS2Send**.</span></span>  
  
7.  <span data-ttu-id="b2b73-242">在**接收管道**，选择**AS2Receive**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-242">In **Receive pipeline**, select **AS2Receive**.</span></span>  
  
8.  <span data-ttu-id="b2b73-243">在控制台树中，选择**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-243">In the console tree, select **Filters**.</span></span> <span data-ttu-id="b2b73-244">有关**属性**，输入**BTS。ReceivePortName**; 对于**运算符**，输入 **==** ; 以及**值**输入的名称将接收 EDI 接收端口交换 (`RecvISAFromCont`)。</span><span class="sxs-lookup"><span data-stu-id="b2b73-244">For **Property**, enter **BTS.ReceivePortName**; for **Operator**, enter **==**; and for **Value** enter the name of the receive port that will receive the EDI interchange (`RecvISAFromCont`).</span></span>  
  
9. <span data-ttu-id="b2b73-245">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-245">Click **OK**.</span></span>  
  
10. <span data-ttu-id="b2b73-246">单击**发送端口**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击你发送端口，并依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-246">Click the **Send Ports** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-two-way-receive-port-to-receive-the-as2-message-and-return-an-mdn"></a><span data-ttu-id="b2b73-247">创建接收 AS2 消息并返回 MDN 的双向接收端口</span><span class="sxs-lookup"><span data-stu-id="b2b73-247">To create a two-way receive port to receive the AS2 message and return an MDN</span></span>  
  
1.  > [!NOTE]
    >  <span data-ttu-id="b2b73-248">Fabrikam 的双向接收端口使用 Fabrikam 虚拟目录接收 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="b2b73-248">The two-way receive port at Fabrikam receives the AS2 message using the Fabrikam virtual directory.</span></span> <span data-ttu-id="b2b73-249">接收管道将来自 AS2 的 EDI 交换解码并放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="b2b73-249">The receive pipeline decodes the EDI interchange from AS2, and drops the EDI interchange into the MessageBox.</span></span> <span data-ttu-id="b2b73-250">与双向接收端口关联的发送端口返回同步 MDN。</span><span class="sxs-lookup"><span data-stu-id="b2b73-250">The send port associated with the two-way receive port returns a synchronous MDN.</span></span>  
  
     <span data-ttu-id="b2b73-251">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，在**BizTalk 应用程序 1**节点，右键单击**接收端口**，指向**新建**，然后单击**请求响应接收端口**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-251">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, under the **BizTalk Application 1** node, right-click **Receive Ports**, point to **New**, and then click **Request Response Receive Port**.</span></span>  
  
2.  <span data-ttu-id="b2b73-252">名称为接收端口**RecvAS2ForFab**，然后单击**接收位置**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="b2b73-252">Name the receive port as **RecvAS2ForFab**, and then click **Receive Locations** in the console tree.</span></span>  
  
3.  <span data-ttu-id="b2b73-253">单击 **“新建”**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-253">Click **New**.</span></span>  
  
4.  <span data-ttu-id="b2b73-254">在**接收位置属性**对话框中，名称你接收位置中，选择**HTTP**为**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-254">In the **Receive Location Properties** dialog box, name your receive location, select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="b2b73-255">在**HTTP 传输属性**对话框框中，输入 **/Fabrikam/BTSHttpReceive.dll**为**虚拟目录以及 ISAPI 扩展**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-255">In the **HTTP Transport Properties** dialog box, enter **/Fabrikam/BTSHttpReceive.dll** for **Virtual directory plus ISAPI extension**.</span></span> <span data-ttu-id="b2b73-256">清除**成功后返回的相关句柄**和选择**挂起失败的请求**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-256">Clear **Return correlation handle on success** and select **Suspend failed requests**.</span></span> <span data-ttu-id="b2b73-257">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-257">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="b2b73-258">选择**AS2Receive**为**接收管道**，和**AS2Send**为**发送管道**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-258">Select **AS2Receive** for the **Receive Pipeline**, and **AS2Send** for the **Send Pipeline**.</span></span> <span data-ttu-id="b2b73-259">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="b2b73-259">Click **OK**, and then click **OK** again.</span></span>  
  
7.  <span data-ttu-id="b2b73-260">单击**接收位置**节点，右键单击你接收位置，并依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-260">Click the **Receive Locations** node, right-click your receive location, and then click **Enable**.</span></span>  
  
##### <a name="to-create-a-send-port-to-send-the-edi-payload-to-a-local-folder"></a><span data-ttu-id="b2b73-261">创建用于将 EDI 负载发送到本地文件夹的发送端口</span><span class="sxs-lookup"><span data-stu-id="b2b73-261">To create a send port to send the EDI payload to a local folder</span></span>  
  
1.  <span data-ttu-id="b2b73-262">在 Windows 资源管理器中，创建一个用于接收 EDI 交换的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2b73-262">In Windows Explorer, create a local folder to send the EDI interchange to.</span></span>  
  
2.  <span data-ttu-id="b2b73-263">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-263">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
3.  <span data-ttu-id="b2b73-264">在**发送端口属性**对话框中，你发送端口作为名称**SendEDIMsg**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-264">In the **Send Port Properties** dialog box, name your send port as **SendEDIMsg**.</span></span> <span data-ttu-id="b2b73-265">选择**文件**为**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-265">Select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="b2b73-266">在**文件传输属性**对话框中，为**目标文件夹**，输入你创建的 EDI 负载的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2b73-266">In the **FILE Transport Properties** dialog box, for **Destination folder**, enter the local folder that you created for the EDI payload.</span></span>  
  
5.  <span data-ttu-id="b2b73-267">有关**文件名**，输入文件名称。</span><span class="sxs-lookup"><span data-stu-id="b2b73-267">For **File name**, enter the file name.</span></span> <span data-ttu-id="b2b73-268">如果你使用 SamplePO.txt 文件作为测试消息，请输入 **%MessageID%.txt**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-268">If you are using the SamplePO.txt file as your test message, enter **%MessageID%.txt**.</span></span> <span data-ttu-id="b2b73-269">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-269">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="b2b73-270">接受默认的**PassThruTransmit**为**发送管道**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-270">Accept the default of **PassThruTransmit** for **Send Pipeline**.</span></span>  
  
7.  <span data-ttu-id="b2b73-271">单击**筛选器**在控制台树，并添加筛选器属性为 EDI 负载中选取。</span><span class="sxs-lookup"><span data-stu-id="b2b73-271">Click **Filters** in the console tree, and add filter properties for picking up the EDI payload.</span></span> <span data-ttu-id="b2b73-272">在第一行中，为**属性**，输入**BTS。ReceivePortName**; 对于**运算符**，输入 **==** ; 对于**值**，输入接收 AS2 接收端口的名称消息 (`RecvAS2ForFab`); 以及**分组依据**，接受**和**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-272">On the first line, for **Property**, enter **BTS.ReceivePortName**; for **Operator**, enter **==**; for **Value**, enter the name of the receive port that receives the AS2 message (`RecvAS2ForFab`); and for **Group by**, accept **And**.</span></span> <span data-ttu-id="b2b73-273">在第二行中，为**属性**，输入**EdiIntAS.IsAS2PayloadMessage**; 对于**运算符**，输入 **==** ; 以及**值**，输入**True**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-273">On the second line, for **Property**, enter **EdiIntAS.IsAS2PayloadMessage**; for **Operator**, enter **==**; and for **Value**, enter **True**.</span></span>  
  
8.  <span data-ttu-id="b2b73-274">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-274">Click **OK**.</span></span>  
  
9. <span data-ttu-id="b2b73-275">单击**发送端口**节点，右键单击你发送端口，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-275">Click the **Send Ports** node, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-send-port-to-send-the-mdn-to-a-local-folder"></a><span data-ttu-id="b2b73-276">创建用于将 MDN 发送到本地文件夹的发送端口</span><span class="sxs-lookup"><span data-stu-id="b2b73-276">To create a send port to send the MDN to a local folder</span></span>  
  
1.  <span data-ttu-id="b2b73-277">在 Windows 资源管理器中，创建一个用于接收 MDN 的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2b73-277">In Windows Explorer, create a local folder to send the MDN to.</span></span>  
  
2.  <span data-ttu-id="b2b73-278">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-278">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
3.  <span data-ttu-id="b2b73-279">在**发送端口属性**对话框中，你发送端口作为名称**SendMDN**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-279">In the **Send Port Properties** dialog box, name your send port as **SendMDN**.</span></span> <span data-ttu-id="b2b73-280">选择**文件**为**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-280">Select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="b2b73-281">在**文件传输属性**对话框中，为**目标文件夹**，输入您创建要发送到 MDN 的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2b73-281">In the **FILE Transport Properties** dialog box, for **Destination folder**, enter the local folder you created to send the MDN to.</span></span>  
  
5.  <span data-ttu-id="b2b73-282">有关**文件名**，输入 **%MessageID%.msg**。单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-282">For **File name**, enter **%MessageID%.msg**. Click **OK**.</span></span>  
  
6.  <span data-ttu-id="b2b73-283">接受默认的**PassThruTransmit**为**发送管道**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-283">Accept the default of **PassThruTransmit** for **Send Pipeline**.</span></span>  
  
7.  <span data-ttu-id="b2b73-284">单击**筛选器**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="b2b73-284">Click **Filters** in the console tree.</span></span> <span data-ttu-id="b2b73-285">有关**属性**，输入**BTS。SPName**; 对于**运算符**，输入 **==** ; 对于**值**，输入将发送 AS2 消息的发送端口的名称 (`SendISAToFab_RecMDN`);和**分组依据**，接受**和**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-285">For **Property**, enter **BTS.SPName**; for **Operator**, enter **==**; for **Value**, enter the name of the send port that sends the AS2 message (`SendISAToFab_RecMDN`); and for **Group by**, accept **And**.</span></span> <span data-ttu-id="b2b73-286">在第二行中，为**属性**，输入**EdiIntAS.IsAS2MdnResponseMessage**; 对于**运算符**，输入 **==** ; 对于**值**，输入**True**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-286">On a second line, for **Property**, enter **EdiIntAS.IsAS2MdnResponseMessage**; for **Operator**, enter **==**; for **Value**, enter **True**.</span></span>  
  
8.  <span data-ttu-id="b2b73-287">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-287">Click **OK**.</span></span>  
  
9. <span data-ttu-id="b2b73-288">单击**发送端口**节点，右键单击你发送端口，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-288">Click the **Send Ports** node, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a><span data-ttu-id="b2b73-289">若要为 Fabrikam 创建方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="b2b73-289">To create a party and a business profile for Fabrikam</span></span>  
  
1.  <span data-ttu-id="b2b73-290">右键单击**方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-290">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="b2b73-291">输入的名称在方**名称**文本中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-291">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2b73-292">通过选择**本地 BizTalk 处理接收的消息从该参与方发送方或支持消息**复选框，你可以指定当事方正在创建将为同一个组织还承载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2b73-292">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="b2b73-293">此基础，某些属性将启用，或当您创建了协议时，禁用。</span><span class="sxs-lookup"><span data-stu-id="b2b73-293">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="b2b73-294">但是，对于本演练中，可以选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="b2b73-294">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3.  <span data-ttu-id="b2b73-295">右键单击方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-295">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4.  <span data-ttu-id="b2b73-296">在**配置文件属性**对话框中，在**常规**页上，输入**Fabrikam_Profile**中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="b2b73-296">In the **Profile Properties** dialog box, on the **General** page, enter **Fabrikam_Profile** in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2b73-297">在创建参与方时，也将创建一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="b2b73-297">When you create a party, a profile is also created.</span></span> <span data-ttu-id="b2b73-298">你可以重命名，并使用该配置文件而不是创建一个新。</span><span class="sxs-lookup"><span data-stu-id="b2b73-298">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="b2b73-299">若要重命名配置文件，右键单击配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-299">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="b2b73-300">在**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="b2b73-300">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a><span data-ttu-id="b2b73-301">为 Contoso 创建参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="b2b73-301">To create a party and a business profile for Contoso</span></span>  
  
1.  <span data-ttu-id="b2b73-302">右键单击**方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-302">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="b2b73-303">输入的名称在方**名称**文本中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-303">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2b73-304">通过选择**本地 BizTalk 处理接收的消息从该参与方发送方或支持消息**复选框，你可以指定当事方正在创建将为同一个组织还承载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2b73-304">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="b2b73-305">此基础，某些属性将启用，或当您创建了协议时，禁用。</span><span class="sxs-lookup"><span data-stu-id="b2b73-305">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="b2b73-306">但是，对于本演练中，可以选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="b2b73-306">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3.  <span data-ttu-id="b2b73-307">右键单击方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-307">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4.  <span data-ttu-id="b2b73-308">在**配置文件属性**对话框中，在**常规**页上，输入**Contoso_Profile**中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="b2b73-308">In the **Profile Properties** dialog box, on the **General** page, enter **Contoso_Profile** in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2b73-309">在创建参与方时，也将创建一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="b2b73-309">When you create a party, a profile is also created.</span></span> <span data-ttu-id="b2b73-310">你可以重命名，并使用该配置文件而不是创建一个新。</span><span class="sxs-lookup"><span data-stu-id="b2b73-310">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="b2b73-311">若要重命名配置文件，右键单击配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-311">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="b2b73-312">在**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="b2b73-312">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-an-as2-agreement-between-the-two-business-profiles"></a><span data-ttu-id="b2b73-313">在两个业务配置文件之间创建 AS2 协议</span><span class="sxs-lookup"><span data-stu-id="b2b73-313">To create an AS2 agreement between the two business profiles</span></span>  
  
1.  <span data-ttu-id="b2b73-314">右键单击**Contoso_Profile**，指向**新建**，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-314">Right-click **Contoso_Profile**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="b2b73-315">在**常规属性**页上，为**名称**文本框中，输入协议的名称。</span><span class="sxs-lookup"><span data-stu-id="b2b73-315">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  
  
3.  <span data-ttu-id="b2b73-316">从**协议**下拉列表中，选择**AS2**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-316">From the **Protocol** drop-down list, select **AS2**.</span></span>  
  
4.  <span data-ttu-id="b2b73-317">在**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**Fabrikam**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-317">In the **Second Partner** section, from the **Name** drop-down list, select **Fabrikam**.</span></span>  
  
5.  <span data-ttu-id="b2b73-318">在**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**Fabrikam_Profile**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-318">In the **Second Partner** section, from the **Profile** drop-down list, select **Fabrikam_Profile**.</span></span>  
  
     <span data-ttu-id="b2b73-319">你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡用于配置一个单向 AS2 协议。</span><span class="sxs-lookup"><span data-stu-id="b2b73-319">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way AS2 agreement.</span></span>  
  
6.  <span data-ttu-id="b2b73-320">在上执行以下任务**Contoso-> Fabrikam**选项卡。</span><span class="sxs-lookup"><span data-stu-id="b2b73-320">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  
  
    1.  <span data-ttu-id="b2b73-321">上**标识符**页上，输入值**AS2-从**和**AS2-到**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-321">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="b2b73-322">有关**AS2-从**，输入`Contoso`。</span><span class="sxs-lookup"><span data-stu-id="b2b73-322">For **AS2-From**, enter `Contoso`.</span></span> <span data-ttu-id="b2b73-323">有关**AS2-到**，输入`Fabrikam`。</span><span class="sxs-lookup"><span data-stu-id="b2b73-323">For **AS2- To**, enter `Fabrikam`.</span></span>  
  
    2.  <span data-ttu-id="b2b73-324">在**确认 (Mdn)** 页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b2b73-324">In the **Acknowledgements (MDNs)** page, do the following:</span></span>  
  
        1.  <span data-ttu-id="b2b73-325">选择**路由/传递到 MessageBox 处理入站的 MDN**复选框。</span><span class="sxs-lookup"><span data-stu-id="b2b73-325">Select the **Process inbound MDN into MessageBox for routing/delivery options** check box.</span></span>  
  
            > [!NOTE]
            >  <span data-ttu-id="b2b73-326">检查**路由/传递到 MessageBox 处理入站的 MDN**需本演练中，在测试，因为只有在那时将返回的 MDN 被放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="b2b73-326">Checking the **Process inbound MDN into MessageBox for routing/delivery options** is required for the testing of this walkthrough, because only then will the returned MDN be dropped into the MessageBox.</span></span> <span data-ttu-id="b2b73-327">这样，便可创建一个用于订阅 MDN 并将 MDN 发送至本地目录的发送端口，从而可以验证 AS2 传输。</span><span class="sxs-lookup"><span data-stu-id="b2b73-327">That enables you to create a send port to subscribe to the MDN, and to send the MDN to a local directory, so you can verify the AS2 transmission.</span></span>  
  
        2.  <span data-ttu-id="b2b73-328">选择**请求 MDN**复选框。</span><span class="sxs-lookup"><span data-stu-id="b2b73-328">Select the **Request MDN** check box.</span></span>  
  
        3.  <span data-ttu-id="b2b73-329">请确保**请求签名的 MDN**清除复选框。</span><span class="sxs-lookup"><span data-stu-id="b2b73-329">Make sure the **Request Signed MDN** check box is cleared.</span></span>  
  
        4.  <span data-ttu-id="b2b73-330">保留**请求异步 MDN**清除。</span><span class="sxs-lookup"><span data-stu-id="b2b73-330">Leave **Request asynchronous MDN** cleared.</span></span>  
  
        5.  <span data-ttu-id="b2b73-331">在**处置-到通知**，输入任何值。</span><span class="sxs-lookup"><span data-stu-id="b2b73-331">In **Disposition-Notification-To**, enter any value.</span></span> <span data-ttu-id="b2b73-332">在 AS2 处理期间，不会使用该字段的值，但该字段中必须输入值。</span><span class="sxs-lookup"><span data-stu-id="b2b73-332">The value of this field is not used during AS2 processing, but a value must be entered in the field.</span></span>  
  
    3.  <span data-ttu-id="b2b73-333">上**发送端口**页上，将会将 EDI 交换发送到 Fabrikam 双向发送端口相关联。</span><span class="sxs-lookup"><span data-stu-id="b2b73-333">On the **Send Ports** page, associate the two-way send port that will be sending the EDI interchange to Fabrikam.</span></span> <span data-ttu-id="b2b73-334">在**发送端口**网格下**名称**列中，单击空单元格，然后从下拉列表列表中，选择发送端口**SendISAToFab_RecMDN**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-334">In the **Send ports** grid, under the **Name** column, click an empty cell, and from the drop-down list, select the send port **SendISAToFab_RecMDN**.</span></span>  
  
7.  <span data-ttu-id="b2b73-335">在上执行以下任务**Fabrikam-> Contoso**选项卡。</span><span class="sxs-lookup"><span data-stu-id="b2b73-335">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2b73-336">在此演练中，我们将指定的选项卡中所需的值，以便可以成功创建协议。</span><span class="sxs-lookup"><span data-stu-id="b2b73-336">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="b2b73-337">若要成功创建了协议，这两个单向协议选项必须为定义的值**AS2_From**和**AS2-到**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-337">To successfully create an agreement, both one-way agreement tabs must have values defined for **AS2_From** and **AS2-To**.</span></span>  
  
    1.  <span data-ttu-id="b2b73-338">上**标识符**页上，输入值**AS2-从**和**AS2-到**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-338">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="b2b73-339">有关**AS2-从**，输入`Fabrikam`。</span><span class="sxs-lookup"><span data-stu-id="b2b73-339">For **AS2-From**, enter `Fabrikam`.</span></span> <span data-ttu-id="b2b73-340">有关**AS2-到**，输入`Contoso`。</span><span class="sxs-lookup"><span data-stu-id="b2b73-340">For **AS2- To**, enter `Contoso`.</span></span>  
  
8.  <span data-ttu-id="b2b73-341">单击 **“应用”**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-341">Click **Apply**.</span></span>  
  
9. <span data-ttu-id="b2b73-342">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b2b73-342">Click **OK**.</span></span> <span data-ttu-id="b2b73-343">新添加的协议被列入**协议**部分**方和业务配置文件**窗格。</span><span class="sxs-lookup"><span data-stu-id="b2b73-343">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="b2b73-344">默认情况下，启用新添加的协议。</span><span class="sxs-lookup"><span data-stu-id="b2b73-344">The newly added agreement is enabled by default.</span></span>  
  
### <a name="testing-the-walkthrough"></a><span data-ttu-id="b2b73-345">测试演练</span><span class="sxs-lookup"><span data-stu-id="b2b73-345">Testing the Walkthrough</span></span>  
 <span data-ttu-id="b2b73-346">本部分提供有关如何测试演练的信息。</span><span class="sxs-lookup"><span data-stu-id="b2b73-346">This section provides information on how to test the walkthrough.</span></span>  
  
##### <a name="to-test-the-solution"></a><span data-ttu-id="b2b73-347">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="b2b73-347">To test the solution</span></span>  
  
1.  <span data-ttu-id="b2b73-348">在 Windows 资源管理器中，转到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\EDI 界面开发人员教程。</span><span class="sxs-lookup"><span data-stu-id="b2b73-348">In Windows Explorer, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial.</span></span> <span data-ttu-id="b2b73-349">复制**SamplePO.txt**文件。</span><span class="sxs-lookup"><span data-stu-id="b2b73-349">Copy the **SamplePO.txt** file.</span></span>  
  
2.  <span data-ttu-id="b2b73-350">粘贴**SamplePO.txt**到本地文件夹，你创建用于从 Contoso 接收测试消息的文件。</span><span class="sxs-lookup"><span data-stu-id="b2b73-350">Paste the **SamplePO.txt** file into the local folder that you created to receive the test message from Contoso.</span></span>  
  
3.  <span data-ttu-id="b2b73-351">转到您创建的用于接收 EDI 负载的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2b73-351">Move to the local folder that you created to send the EDI payload to.</span></span> <span data-ttu-id="b2b73-352">确认文件夹中含有一个 EDI 文件。</span><span class="sxs-lookup"><span data-stu-id="b2b73-352">Confirm that the folder contains an EDI file.</span></span> <span data-ttu-id="b2b73-353">打开该文件和原始测试消息，验证它们的内容是否相同。</span><span class="sxs-lookup"><span data-stu-id="b2b73-353">Open the file and the original test message, and verify that they have the same content.</span></span>  
  
4.  <span data-ttu-id="b2b73-354">转到您创建的用于接收生成的 MDN 的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2b73-354">Move to the local folder that you created to send the resulting MDN to.</span></span> <span data-ttu-id="b2b73-355">确认文件夹中含有一个文件；打开该文件并确认它是一个 MDN 文件。</span><span class="sxs-lookup"><span data-stu-id="b2b73-355">Confirm that the folder contains a file; open the file and confirm that it is an MDN file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2b73-356">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2b73-356">See Also</span></span>  
 [<span data-ttu-id="b2b73-357">开发和配置 BizTalk Server AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="b2b73-357">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)