---
title: '演练 (AS2): 使用异步 MDN 通过 AS2 发送 EDI |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83644ac9-7023-4b09-966c-7c41d36f6b11
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56bdad99f9929c298aa6a047f7c20667f6f7d924
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974502"
---
# <a name="walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn"></a><span data-ttu-id="6a929-102">演练 (AS2)：使用异步 MDN 通过 AS2 发送 EDI</span><span class="sxs-lookup"><span data-stu-id="6a929-102">Walkthrough (AS2): Sending EDI over AS2 with an Asynchronous MDN</span></span>
<span data-ttu-id="6a929-103">本演练将介绍创建通过 AS2 用异步 MDN 发送 EDI 消息的解决方案的分步操作过程。</span><span class="sxs-lookup"><span data-stu-id="6a929-103">This walkthrough provides a set of step-by-step procedures that creates a solution for sending EDI messages over AS2, with an asynchronous MDN.</span></span>  <span data-ttu-id="6a929-104">您可以在单台计算机上创建并测试本演练中的完整解决方案</span><span class="sxs-lookup"><span data-stu-id="6a929-104">You can create and test the full solution in this walkthrough on a single computer</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6a929-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="6a929-105">Prerequisites</span></span>  
 <span data-ttu-id="6a929-106">以下为执行本主题中的过程的前提条件：</span><span class="sxs-lookup"><span data-stu-id="6a929-106">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
- <span data-ttu-id="6a929-107">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="6a929-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
- <span data-ttu-id="6a929-108">运行演练的计算机必须安装了 Internet 信息服务 (IIS)。</span><span class="sxs-lookup"><span data-stu-id="6a929-108">The computer that runs the walkthrough must have Internet Information Services (IIS) 7 installed.</span></span>  
  
- <span data-ttu-id="6a929-109">如果运行此演练的计算机安装了 64 位版本的 Windows，则您必须确保 BizTalk 主机标记只能为 32 位。</span><span class="sxs-lookup"><span data-stu-id="6a929-109">If the computer that runs the walkthrough is installed with a 64-bit version of Windows, you must ensure that the BizTalk hosts are marked as 32-bit only.</span></span> <span data-ttu-id="6a929-110">您还必须确保 IIS 已将“为应用程序池启用 32 位应用程序设置”设置为 True。 </span><span class="sxs-lookup"><span data-stu-id="6a929-110">You must also ensure IIS has the Enable 32-Bit Application Setting for the Application Pools set to True.</span></span> <span data-ttu-id="6a929-111">有关详细信息，请参阅[教程 3: AS2 教程](../core/tutorial-3-as2-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="6a929-111">For more information, see [Tutorial 3: AS2 Tutorial](../core/tutorial-3-as2-tutorial.md).</span></span>  
  
## <a name="how-the-solution-sends-an-edias2-message-and-returns-an-asynchronous-mdn"></a><span data-ttu-id="6a929-112">解决方案如何发送 EDI/AS2 消息并返回异步 MDN</span><span class="sxs-lookup"><span data-stu-id="6a929-112">How the Solution Sends an EDI/AS2 Message and Returns an Asynchronous MDN</span></span>  
 <span data-ttu-id="6a929-113">该解决方案将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6a929-113">The solution will do the following:</span></span>  
  
1. <span data-ttu-id="6a929-114">一个单向 FILE 接收端口从 Contoso 接收 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="6a929-114">A one-way FILE receive port receives an EDI interchange from Contoso.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6a929-115">此列表中的事件可能不会按所示顺序发生。</span><span class="sxs-lookup"><span data-stu-id="6a929-115">The events in this list may not occur in the order shown.</span></span>  
  
2. <span data-ttu-id="6a929-116">使用直通接收管道，接收端口将测试消息放入 MeassageBox 保持不变。</span><span class="sxs-lookup"><span data-stu-id="6a929-116">Using a passthrough receive pipeline, the receive port drops the test message into the MeassageBox unchanged.</span></span>  
  
3. <span data-ttu-id="6a929-117">静态单向发送端口提取 EDI 交换并将其编码为 AS2 格式。</span><span class="sxs-lookup"><span data-stu-id="6a929-117">A static one-way send port picks up the EDI interchange and encodes it into AS2 format.</span></span>  
  
4. <span data-ttu-id="6a929-118">发送端口通过 AS2 传输类型将 EDI 交换发送至 Fabrikam 参与方。</span><span class="sxs-lookup"><span data-stu-id="6a929-118">The send port sends the EDI interchange over AS2 transport to the Fabrikam party.</span></span>  
  
5. <span data-ttu-id="6a929-119">Fabrikam 的单向接收端口使用 Fabrikam 虚拟目录接收 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="6a929-119">The one-way receive port at Fabrikam receives the AS2 message using the Fabrikam virtual directory.</span></span> <span data-ttu-id="6a929-120">接收管道将来自 AS2 的 EDI 交换解码并放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="6a929-120">The receive pipeline decodes the EDI interchange from AS2, and drops the EDI interchange into the MessageBox.</span></span>  
  
6. <span data-ttu-id="6a929-121">同一个单向接收端口还会生成 MDN 并将此 MDN 放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="6a929-121">The same one-way receive port also generates an MDN and drops the MDN into the MessageBox.</span></span>  
  
7. <span data-ttu-id="6a929-122">静态单向发送端口提取 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="6a929-122">A static one-way send port pick up the EDI message.</span></span>  
  
8. <span data-ttu-id="6a929-123">该静态单向发送端口将 EDI 消息发送至本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a929-123">The static one-way send port sends the EDI message to a local folder.</span></span>  
  
9. <span data-ttu-id="6a929-124">单向动态发送端口提取异步 MDN。</span><span class="sxs-lookup"><span data-stu-id="6a929-124">A one-way dynamic send port picks up the asynchronous MDN.</span></span>  
  
10. <span data-ttu-id="6a929-125">该单向动态发送端口可将 MDN 发送至 Contoso。</span><span class="sxs-lookup"><span data-stu-id="6a929-125">The one-way dynamic send port sends the MDN to Contoso.</span></span>  
  
11. <span data-ttu-id="6a929-126">单向接收端口接收 MDN，并将其放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="6a929-126">A one-way receive port receives the MDN, and drops it into the MessageBox.</span></span>  
  
12. <span data-ttu-id="6a929-127">带有直通发送管道的静态单向发送端口提取 MDN。</span><span class="sxs-lookup"><span data-stu-id="6a929-127">A static one-way send port with a passthrough send pipeline picks up the MDN.</span></span>  
  
13. <span data-ttu-id="6a929-128">该单向发送端口将 MDN 发送至本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a929-128">The one-way send port sends the MDN to a local folder.</span></span>  
  
    <span data-ttu-id="6a929-129">下图显示出此解决方案的结构。</span><span class="sxs-lookup"><span data-stu-id="6a929-129">The following figure shows the architecture for this solution.</span></span>  
  
    <span data-ttu-id="6a929-130">![使用异步 MDN 的 AS2 发送](../core/media/343bbfcc-5387-426c-8700-db9738816218.gif "343bbfcc-5387-426c-8700-db9738816218")</span><span class="sxs-lookup"><span data-stu-id="6a929-130">![AS2 sending with an asynchronous MDN](../core/media/343bbfcc-5387-426c-8700-db9738816218.gif "343bbfcc-5387-426c-8700-db9738816218")</span></span>  
  
## <a name="the-functionality-in-this-solution"></a><span data-ttu-id="6a929-131">此解决方案中的功能</span><span class="sxs-lookup"><span data-stu-id="6a929-131">The Functionality in this Solution</span></span>  
 <span data-ttu-id="6a929-132">本演练的功能具有以下特点：</span><span class="sxs-lookup"><span data-stu-id="6a929-132">The following applies to the functionality of this walkthrough:</span></span>  
  
-   <span data-ttu-id="6a929-133">本演练针对的是 AS2 功能，而非 EDI 功能。</span><span class="sxs-lookup"><span data-stu-id="6a929-133">This walkthrough deals with AS2 functionality, not EDI functionality.</span></span> <span data-ttu-id="6a929-134">因此，AS2 处理所涉及的所有端口使用的是 AS2Receive 或 AS2Send 管道，而非 AS2EdiReceive 和 AS2EdiSend。</span><span class="sxs-lookup"><span data-stu-id="6a929-134">As a result, all ports involved in AS2 processing use either AS2Receive or AS2Send pipelines, not AS2EdiReceive or AS2EdiSend.</span></span> <span data-ttu-id="6a929-135">AS2 处理未涉及到的端口使用 PassThruReceive 或 PassThruTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="6a929-135">Ports that are not involved in AS2 processing use PassThruReceive or PassThruTransmit pipelines.</span></span>  
  
-   <span data-ttu-id="6a929-136">状态报告未启用。</span><span class="sxs-lookup"><span data-stu-id="6a929-136">Status reporting is not enabled.</span></span>  
  
-   <span data-ttu-id="6a929-137">此解决方案不在不可否认数据库中配置签名、压缩、加密或消息存储。</span><span class="sxs-lookup"><span data-stu-id="6a929-137">This solution does not configure signing, compression, encryption, or message storage in the non-repudiation database.</span></span> <span data-ttu-id="6a929-138">有关配置这些属性的过程，请参阅[配置 AS2 属性](../core/configuring-as2-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="6a929-138">For procedures on configuring those properties, see [Configuring AS2 Properties](../core/configuring-as2-properties.md).</span></span>  
  
## <a name="configuring-and-testing-the-walkthrough"></a><span data-ttu-id="6a929-139">配置和测试演练</span><span class="sxs-lookup"><span data-stu-id="6a929-139">Configuring and Testing the Walkthrough</span></span>  
 <span data-ttu-id="6a929-140">该解决方案所需的过程包括：</span><span class="sxs-lookup"><span data-stu-id="6a929-140">The procedures required for this solution include the following:</span></span>  
  
- <span data-ttu-id="6a929-141">使用所需的消息架构生成并部署 BizTalk 项目，并将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 设置为在处理接收的交换时使用这些架构。</span><span class="sxs-lookup"><span data-stu-id="6a929-141">Build and deploy a BizTalk project with the required message schema, making the schema available for use by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in processing the received interchange.</span></span>  
  
- <span data-ttu-id="6a929-142">启用接收 AS2 消息时使用的 BTS ISAPI 筛选器。</span><span class="sxs-lookup"><span data-stu-id="6a929-142">Enable the BTS ISAPI filter used in receiving the AS2 message.</span></span>  
  
- <span data-ttu-id="6a929-143">按照接收位置中的配置，创建一个用于从 Contoso 接收 AS2 消息的 Fabrikam 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="6a929-143">Create a Fabrikam virtual directory that receives the AS2 message from Contoso, as configured in the receive location.</span></span>  
  
- <span data-ttu-id="6a929-144">按照接收位置中的配置，创建一个用于从 Fabrikam 接收 AS2 消息的 Contoso 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="6a929-144">Create a Contoso virtual directory that receives the AS2 message from Fabrikam, as configured in the receive location.</span></span>  
  
- <span data-ttu-id="6a929-145">指定 Windows SharePoint Services 不对 Fabrikam 和 Contoso 虚拟目录进行管理。</span><span class="sxs-lookup"><span data-stu-id="6a929-145">Specify that the Fabrikam and Contoso virtual directories are not managed by Windows SharePoint Services.</span></span>  
  
- <span data-ttu-id="6a929-146">创建一个单向 FILE 接收端口接收通过 AS2 传输方法发送的 EDI 测试消息。</span><span class="sxs-lookup"><span data-stu-id="6a929-146">Create a one-way FILE receive port to receive the EDI test message that will be sent via AS2 transport.</span></span> <span data-ttu-id="6a929-147">创建接收测试消息的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a929-147">Create the local folder to receive the test message.</span></span>  
  
- <span data-ttu-id="6a929-148">为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建一个静态单向 HTTP 发送端口，以将包含 EDI 业务文档的 AS2 消息发送至 Fabrikam。</span><span class="sxs-lookup"><span data-stu-id="6a929-148">Create a static one-way HTTP send port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send the AS2 message containing the EDI business document to Fabrikam.</span></span> <span data-ttu-id="6a929-149">将发送管道配置为 AS2Send 管道。</span><span class="sxs-lookup"><span data-stu-id="6a929-149">Configure the send pipeline to be the AS2Send pipeline.</span></span>  
  
- <span data-ttu-id="6a929-150">为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建一个用于接收 AS2 消息的单向 HTTP 接收端口。</span><span class="sxs-lookup"><span data-stu-id="6a929-150">Create a one-way HTTP receive port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive the AS2 message.</span></span> <span data-ttu-id="6a929-151">将接收管道配置为 AS2Receive 管道。</span><span class="sxs-lookup"><span data-stu-id="6a929-151">Configure the receive pipeline to be the AS2Receive pipeline.</span></span> <span data-ttu-id="6a929-152">配置用于接收经 Fabrikam 虚拟目录发送的 AS2 消息的接收位置。</span><span class="sxs-lookup"><span data-stu-id="6a929-152">Configure the receive location to receive the AS2 message via the Fabrikam virtual directory.</span></span>  
  
- <span data-ttu-id="6a929-153">创建一个带有直通发送管道的单向 FILE 发送端口以将消息负载路由至本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a929-153">Create a static one-way FILE send port (with a passthrough send pipeline) to route the message payload to a local folder.</span></span> <span data-ttu-id="6a929-154">创建本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a929-154">Create the local folder.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="6a929-155">如果没有用于订阅该消息负载的发送端口，它将会在 MessageBox 中挂起。 </span><span class="sxs-lookup"><span data-stu-id="6a929-155">If you do not have a send port to subscribe to the message payload, it will be suspended in the MessageBox.</span></span>  
  
- <span data-ttu-id="6a929-156">创建一个用于向 Contoso 返回 MDN 的动态单向 HTTP 发送端口。</span><span class="sxs-lookup"><span data-stu-id="6a929-156">Create a dynamic one-way HTTP send port to return the MDN to Contoso.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="6a929-157">测试解决方案在单台计算机上执行，因此用于从 Contoso 发送 AS2 消息的单向发送端口和从 Fabrikam 发送 MDN 响应的单向发送端口都在同一计算机上。</span><span class="sxs-lookup"><span data-stu-id="6a929-157">The test solution is on a single computer; as a result, the one-way send port sending the AS2 message (from Contoso) and the one-way send port sending the MDN response (from Fabrikam) are on the same computer.</span></span>  
  
- <span data-ttu-id="6a929-158">为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建一个用于接收来自 Fabrikam 的 MDN 响应的单向接收端口。</span><span class="sxs-lookup"><span data-stu-id="6a929-158">Create a one-way receive port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive the MDN response from Fabrikam.</span></span>  
  
- <span data-ttu-id="6a929-159">创建一个带有直通发送管道的单向 FILE 发送端口以将 MDN 路由至本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a929-159">Create a static one-way FILE send port (with a passthrough send pipeline) to route the MDN to a local folder.</span></span> <span data-ttu-id="6a929-160">创建本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a929-160">Create the local folder.</span></span>  
  
- <span data-ttu-id="6a929-161">为 Fabrikam 和 Contoso 创建参与方（贸易合作伙伴）。</span><span class="sxs-lookup"><span data-stu-id="6a929-161">Create a party (trading partner) for both Fabrikam and Contoso.</span></span>  
  
- <span data-ttu-id="6a929-162">为这两个贸易参与方创建业务配置文件每个。</span><span class="sxs-lookup"><span data-stu-id="6a929-162">Create a business profile each for both the trading parties.</span></span>  
  
- <span data-ttu-id="6a929-163">在 Fabrikam 和 Contoso 的业务配置文件之间创建一个 AS2 协议。</span><span class="sxs-lookup"><span data-stu-id="6a929-163">Create an AS2 agreement between the business profiles for Fabrikam and Contoso.</span></span> <span data-ttu-id="6a929-164">AS2 协议中将包含发送 AS2 消息并接收返回的异步 MDN 的属性。</span><span class="sxs-lookup"><span data-stu-id="6a929-164">The AS2 agreement would contain properties to send an AS2 message and receive an asynchronous MDN in return.</span></span>  
  
- <span data-ttu-id="6a929-165">使用测试 EDI 交换测试演练。</span><span class="sxs-lookup"><span data-stu-id="6a929-165">Test the walkthrough using a test EDI interchange.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="6a929-166">对于测试消息，您可以使用在 EDI 接口开发人员教程中使用的 SamplePO.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="6a929-166">For a test message, you can use the SamplePO.txt file that is used in the EDI Interface Developer tutorial.</span></span> <span data-ttu-id="6a929-167">该文件位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\EDI Interface Developer Tutorial\ 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a929-167">That file is shipped in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\EDI Interface Developer Tutorial\ folder.</span></span> <span data-ttu-id="6a929-168">这是一个 X12 850 消息。</span><span class="sxs-lookup"><span data-stu-id="6a929-168">This is an X12 850 message.</span></span>  
  
### <a name="configuring-the-walkthrough"></a><span data-ttu-id="6a929-169">配置演练</span><span class="sxs-lookup"><span data-stu-id="6a929-169">Configuring the Walkthrough</span></span>  
 <span data-ttu-id="6a929-170">本部分介绍配置本演练的步骤。</span><span class="sxs-lookup"><span data-stu-id="6a929-170">This section describes the procedures to configure the walkthrough.</span></span>  
  
##### <a name="to-deploy-the-message-schema"></a><span data-ttu-id="6a929-171">部署消息架构</span><span class="sxs-lookup"><span data-stu-id="6a929-171">To deploy the message schema</span></span>  
  
1. <span data-ttu-id="6a929-172">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，创建或打开 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="6a929-172">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create or open a BizTalk project.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6a929-173">本主题假定你已从你的应用程序添加了对包含 EDI 架构、管道和业务流程的 BizTalk EDI 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="6a929-173">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="6a929-174">如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。</span><span class="sxs-lookup"><span data-stu-id="6a929-174">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
2. <span data-ttu-id="6a929-175">右键单击你的项目，指向**外**，然后单击**现有项**。</span><span class="sxs-lookup"><span data-stu-id="6a929-175">Right-click your project, point to **Add**, and then click **Existing Item**.</span></span> <span data-ttu-id="6a929-176">要使用 SamplePO.txt 文件测试您的解决方案，请访问 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a929-176">To use the SamplePO.txt file to test your solution, move to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI folder.</span></span> <span data-ttu-id="6a929-177">选择 X12_00401_850.xsd 架构，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="6a929-177">Select the X12_00401_850.xsd schema, and then click **Add**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6a929-178">若要使用其他 EDI 架构，请转到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_SchemaEDI 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a929-178">To use a different EDI schema, go to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_SchemaEDI folder.</span></span> <span data-ttu-id="6a929-179">如果 EDI 架构尚未解压缩到 XSD_SchemaEDI 文件夹，则执行**MicrosoftEdiXSDTemplates.exe** XSD_SchemaEDI 文件夹将架构解压缩到默认文件夹中的文件。</span><span class="sxs-lookup"><span data-stu-id="6a929-179">If the EDI schemas have not been unzipped into the XSD_SchemaEDI folders, execute the **MicrosoftEdiXSDTemplates.exe** file in the XSD_SchemaEDI folder to unzip the schemas into the default folder.</span></span>  
  
3. <span data-ttu-id="6a929-180">设置程序集密钥文件，然后生成并部署该程序集。</span><span class="sxs-lookup"><span data-stu-id="6a929-180">Set the assembly key file, and then build and deploy the assembly.</span></span>  
  
##### <a name="to-enable-the-bts-isapi-filter"></a><span data-ttu-id="6a929-181">启用 BTS ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="6a929-181">To enable the BTS ISAPI Filter</span></span>  
  
1. <span data-ttu-id="6a929-182">单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="6a929-182">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
   > [!TIP]
   >  <span data-ttu-id="6a929-183">根据操作系统，管理工具启动菜单选项可能不可用。</span><span class="sxs-lookup"><span data-stu-id="6a929-183">Depending on the operating system, the Administrative Tools start menu option may not be available.</span></span> <span data-ttu-id="6a929-184">在这种情况下，单击**启动**，单击**运行**，然后输入`inetmgr`打开 Internet 信息服务 (IIS) 管理器。</span><span class="sxs-lookup"><span data-stu-id="6a929-184">In such cases, click **Start**, click **Run**, and enter `inetmgr` to open Internet Information Services (IIS) Manager.</span></span>  
  
2. <span data-ttu-id="6a929-185">选择根 Web 服务器条目并在**功能视图**，双击**处理程序映射**，然后在操作窗格中的单击**添加脚本映射**。</span><span class="sxs-lookup"><span data-stu-id="6a929-185">Select the root Web Server entry and in the **Features View**, double click **Handler Mappings** and then in the Actions pane click **Add Script Map**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6a929-186">在 Web 服务器级别配置的脚本映射将导致此映射应用于所有子网站。</span><span class="sxs-lookup"><span data-stu-id="6a929-186">Configuring the script mapping at the Web Server level will cause this mapping to apply to all child Web Sites.</span></span> <span data-ttu-id="6a929-187">如果你想要将映射限制到特定的网站或虚拟文件夹，选择文件夹而不是 Web 服务器的目标站点。</span><span class="sxs-lookup"><span data-stu-id="6a929-187">If you wish to restrict the mapping to a specific Web Site or Virtual Folder, select the target site or folder instead of the Web Server.</span></span>  
  
3. <span data-ttu-id="6a929-188">在中**添加脚本映射**对话框框中，输入`BtsHttpReceive.dll`中**请求路径**字段。</span><span class="sxs-lookup"><span data-stu-id="6a929-188">In the **Add Script Map** dialog box, enter `BtsHttpReceive.dll` in the **Request path** field.</span></span>  
  
4. <span data-ttu-id="6a929-189">在中**可执行文件**字段中，单击**省略号 （...）** 按钮并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive。</span><span class="sxs-lookup"><span data-stu-id="6a929-189">In the **Executable** field, click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive.</span></span> <span data-ttu-id="6a929-190">选择 BtsHttpReceive.dll，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6a929-190">Select BtsHttpReceive.dll and click **OK**.</span></span>  
  
5. <span data-ttu-id="6a929-191">输入`BizTalk HTTP Receive`中`Name`字段中，然后依次**请求限制**。</span><span class="sxs-lookup"><span data-stu-id="6a929-191">Enter `BizTalk HTTP Receive` in the `Name` field, and then click **Request Restrictions**.</span></span>  
  
6. <span data-ttu-id="6a929-192">在中**请求限制**对话框中，选择**谓词**选项卡，然后选择**以下谓词之一**。</span><span class="sxs-lookup"><span data-stu-id="6a929-192">In the **Request Restrictions** dialog box, select the **Verbs** tab and then select **One of the following verbs**.</span></span> <span data-ttu-id="6a929-193">输入`POST`作为谓词。</span><span class="sxs-lookup"><span data-stu-id="6a929-193">Enter `POST` as the verb.</span></span>  
  
7. <span data-ttu-id="6a929-194">上**访问**选项卡上，选择**脚本**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6a929-194">On the **Access** tab, select **Script** and then click **OK**.</span></span>  
  
8. <span data-ttu-id="6a929-195">单击**确定**并在提示是否允许 ISAPI 扩展，请单击**是**。</span><span class="sxs-lookup"><span data-stu-id="6a929-195">Click **OK** and when prompted to allow the ISAPI extension, click **Yes**.</span></span>  
  
##### <a name="to-configure-the-fabrikam-web-page"></a><span data-ttu-id="6a929-196">配置 Fabrikam 网页</span><span class="sxs-lookup"><span data-stu-id="6a929-196">To configure the Fabrikam Web page</span></span>  
  
1. <span data-ttu-id="6a929-197">在 IIS 管理器中，右键单击**应用程序池**，然后选择**添加应用程序池**。</span><span class="sxs-lookup"><span data-stu-id="6a929-197">In IIS Manager, right-click **Application Pools** and select **Add Application Pool**.</span></span>  
  
2. <span data-ttu-id="6a929-198">在中**添加应用程序池**对话框框中，输入**BizTalkAppPool**中**名称**，然后选择 **.NET Framework V4.0.30210**中 **.NET framework 版本**下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="6a929-198">In the **Add Application Pool** dialog box, enter **BizTalkAppPool** in **Name**, and then select **.NET Framework V4.0.30210** in the **.NET Framework version** dropdown list.</span></span> <span data-ttu-id="6a929-199">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="6a929-199">Click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6a929-200">根据计算机上安装的 [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] 版本，.NET Framework 的版本可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="6a929-200">The version number may vary depending on the version of [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] installed on the machine.</span></span>  
  
3. <span data-ttu-id="6a929-201">选择**应用程序池**，在**功能视图**选择**BizTalkAppPool**，然后单击**高级设置**中**操作**窗格。</span><span class="sxs-lookup"><span data-stu-id="6a929-201">Select **Application Pools**, in the **Features View** select **BizTalkAppPool**, and then click **Advanced Settings** in the **Actions** pane.</span></span>  
  
4. <span data-ttu-id="6a929-202">在中**高级设置**对话框中，选择**标识**，然后单击省略号 （...） 按钮。</span><span class="sxs-lookup"><span data-stu-id="6a929-202">In the **Advanced Settings** dialog box, select **Identity** and then click the ellipsis (…) button.</span></span>  
  
5. <span data-ttu-id="6a929-203">在中**应用程序池标识**对话框中，选择**自定义帐户**，然后单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="6a929-203">In the **Application Pool Identity** dialog box, select **Custom account** and then click **Set**.</span></span>  
  
6. <span data-ttu-id="6a929-204">输入**用户名**并**密码**是 administrators 组的成员的用户帐户，请输入中的密码**确认密码**，然后单击**确定**三次以返回到 IIS 管理器。</span><span class="sxs-lookup"><span data-stu-id="6a929-204">Enter the **User name** and **Password** for a user account that is a member of the administrators group, enter the password in **Confirm password** and then click **OK** three times to return to the IIS Manager.</span></span>  
  
7. <span data-ttu-id="6a929-205">在 IIS 管理器中，打开**站点**文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a929-205">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="6a929-206">右键单击默认网站，然后选择“添加应用程序”。</span><span class="sxs-lookup"><span data-stu-id="6a929-206">Right-click the Default Web Site and then select Add Application.</span></span>  
  
8. <span data-ttu-id="6a929-207">在中**添加应用程序**对话框框中，输入**Fabrikam**中**别名**，然后单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="6a929-207">In the **Add Application** dialog box, enter **Fabrikam** in **Alias**, and then click **Select**.</span></span>  
  
9. <span data-ttu-id="6a929-208">在中**选择应用程序池**对话框中，选择**BizTalkAppPool**然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6a929-208">In the **Select Application Pool** dialog box, select **BizTalkAppPool** and click **OK**.</span></span>  
  
10. <span data-ttu-id="6a929-209">单击省略号 （...） 按钮并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]httpreceive 作为**物理路径**。</span><span class="sxs-lookup"><span data-stu-id="6a929-209">Click the ellipsis (…) button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive for the **Physical path**.</span></span>  
  
11. <span data-ttu-id="6a929-210">单击**测试设置**并验证是否没有显示在错误**测试连接**对话框。</span><span class="sxs-lookup"><span data-stu-id="6a929-210">Click **Test Settings** and verify that there are no errors displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="6a929-211">单击 **“关闭”**，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="6a929-211">Click **Close**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="6a929-212">在 IIS 管理器中，选择 Contoso 虚拟目录并在**功能视图**，双击**身份验证**。</span><span class="sxs-lookup"><span data-stu-id="6a929-212">In IIS Manager, select the Contoso virtual directory and in the **Features View**, double-click **Authentication**.</span></span>  
  
13. <span data-ttu-id="6a929-213">在中**身份验证**，选择**匿名身份验证**，并验证**状态**是**已启用**。</span><span class="sxs-lookup"><span data-stu-id="6a929-213">In **Authentication**, select **Anonymous Authentication** and verify that the **Status** is **Enabled**.</span></span> <span data-ttu-id="6a929-214">如果**状态**是**禁用**，单击**启用**中**操作**窗格。</span><span class="sxs-lookup"><span data-stu-id="6a929-214">If the **Status** is **Disabled**, click **Enable** in the **Actions** pane.</span></span>  
  
##### <a name="to-configure-the-contoso-web-page"></a><span data-ttu-id="6a929-215">配置 Contoso 网页</span><span class="sxs-lookup"><span data-stu-id="6a929-215">To configure the Contoso Web page</span></span>  
  
1. <span data-ttu-id="6a929-216">在 IIS 管理器中，打开**站点**文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a929-216">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="6a929-217">右键单击默认网站，然后选择“添加应用程序”。</span><span class="sxs-lookup"><span data-stu-id="6a929-217">Right-click the Default Web Site and then select Add Application.</span></span>  
  
2. <span data-ttu-id="6a929-218">在中**添加应用程序**对话框框中，输入**Contoso**中**别名**，然后单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="6a929-218">In the **Add Application** dialog box, enter **Contoso** in **Alias**, and then click **Select**.</span></span>  
  
3. <span data-ttu-id="6a929-219">在中**选择应用程序池**对话框中，选择**BizTalkAppPool**然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6a929-219">In the **Select Application Pool** dialog box, select **BizTalkAppPool** and click **OK**.</span></span>  
  
4. <span data-ttu-id="6a929-220">单击省略号 （...） 按钮并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]httpreceive 作为**物理路径**。</span><span class="sxs-lookup"><span data-stu-id="6a929-220">Click the ellipsis (…) button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive for the **Physical path**.</span></span>  
  
5. <span data-ttu-id="6a929-221">单击**测试设置**并验证是否没有显示在错误**测试连接**对话框。</span><span class="sxs-lookup"><span data-stu-id="6a929-221">Click **Test Settings** and verify that there are no errors displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="6a929-222">单击 **“关闭”**，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="6a929-222">Click **Close**, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="6a929-223">在 IIS 管理器中，选择 Contoso 虚拟目录并在**功能视图**，双击**身份验证**。</span><span class="sxs-lookup"><span data-stu-id="6a929-223">In IIS Manager, select the Contoso virtual directory and in the **Features View**, double-click **Authentication**.</span></span>  
  
7. <span data-ttu-id="6a929-224">在中**身份验证**，选择**匿名身份验证**，并验证**状态**是**已启用**。</span><span class="sxs-lookup"><span data-stu-id="6a929-224">In **Authentication**, select **Anonymous Authentication** and verify that the **Status** is **Enabled**.</span></span> <span data-ttu-id="6a929-225">如果**状态**是**禁用**，单击**启用**中**操作**窗格。</span><span class="sxs-lookup"><span data-stu-id="6a929-225">If the **Status** is **Disabled**, click **Enable** in the **Actions** pane.</span></span>  
  
##### <a name="to-specify-that-the-fabrikam-and-contoso-virtual-directories-are-not-managed-by-windows-sharepoint-services"></a><span data-ttu-id="6a929-226">指定 Windows SharePoint Services 不管理 Fabrikam 和 Contoso 虚拟目录</span><span class="sxs-lookup"><span data-stu-id="6a929-226">To specify that the Fabrikam and Contoso virtual directories are not managed by Windows SharePoint Services</span></span>  
  
1.  <span data-ttu-id="6a929-227">如果您的计算机上安装 Windows SharePoint Services，请单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**SharePoint 3.0 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="6a929-227">If Windows SharePoint Services is installed on your computer, click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6a929-228">如果用于设置演练的同一计算机上还安装了 Windows SharePoint Server，则此过程是必需的。</span><span class="sxs-lookup"><span data-stu-id="6a929-228">This procedure is required if Windows SharePoint Server is installed on the same computer that you are setting the walkthrough up on.</span></span> <span data-ttu-id="6a929-229">在该情况下，您必须指定 IIS 虚拟目录不由 Windows SharePoint Server 托管。</span><span class="sxs-lookup"><span data-stu-id="6a929-229">In that case, you must specify that your IIS virtual directory is not being managed by Windows SharePoint Server.</span></span>  
  
2.  <span data-ttu-id="6a929-230">上**Central Administration**页面上，在**管理中心**，单击**应用程序管理**。</span><span class="sxs-lookup"><span data-stu-id="6a929-230">On the **Central Administration** page, under **Central Administration**, click **Application Management**.</span></span>  
  
3.  <span data-ttu-id="6a929-231">上**应用程序管理**页上，单击**定义管理路径**。</span><span class="sxs-lookup"><span data-stu-id="6a929-231">On the **Application Management** page, click **Define managed paths**.</span></span>  
  
4.  <span data-ttu-id="6a929-232">中**定义管理路径**页面上，在**添加新路径**，在**路径**文字框中，输入`Fabrikam`。</span><span class="sxs-lookup"><span data-stu-id="6a929-232">In the **Define Managed Paths** page, under **Add a New Path**, in the **Path** text box, enter `Fabrikam`.</span></span> <span data-ttu-id="6a929-233">下**类型**，单击**排除的路径**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6a929-233">Under **Type**, click **Excluded Path**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="6a929-234">请为 Contoso 虚拟目录重复步骤 4。</span><span class="sxs-lookup"><span data-stu-id="6a929-234">Repeat step 4 for the Contoso virtual directory.</span></span>  
  
6.  <span data-ttu-id="6a929-235">关闭**定义管理路径**页。</span><span class="sxs-lookup"><span data-stu-id="6a929-235">Close the **Define Managed Paths** page.</span></span>  
  
##### <a name="to-create-a-receive-port-to-receive-the-edi-test-message"></a><span data-ttu-id="6a929-236">创建接收 EDI 测试消息的接收端口</span><span class="sxs-lookup"><span data-stu-id="6a929-236">To create a receive port to receive the EDI test message</span></span>  
  
1. <span data-ttu-id="6a929-237">在 Windows 资源管理器中，创建一个用于从 Contoso 接收 EDI 交换的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a929-237">In Windows Explorer, create a local folder to receive the EDI interchange from Contoso.</span></span>  
  
2. <span data-ttu-id="6a929-238">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="6a929-238">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the **Receive Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
3. <span data-ttu-id="6a929-239">为接收端口的名称**RecvISAFromCont**，然后单击**接收位置**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="6a929-239">Name the receive port as **RecvISAFromCont**, and then click **Receive Locations** in the console tree.</span></span>  
  
4. <span data-ttu-id="6a929-240">单击 **“新建”**。</span><span class="sxs-lookup"><span data-stu-id="6a929-240">Click **New**.</span></span>  
  
5. <span data-ttu-id="6a929-241">名称的接收位置，选择**文件**有关**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="6a929-241">Name the receive location, select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
6. <span data-ttu-id="6a929-242">有关**接收文件夹**，输入在步骤 1 中创建的文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="6a929-242">For **Receive folder**, enter the name of the folder that you created in step 1.</span></span>  
  
7. <span data-ttu-id="6a929-243">对于“文件掩码”，请输入文件的扩展名。</span><span class="sxs-lookup"><span data-stu-id="6a929-243">For File mask, enter the extension of your file.</span></span> <span data-ttu-id="6a929-244">如果您使用的 SamplePO.txt 文件作为测试消息，请输入 **\*.txt**。</span><span class="sxs-lookup"><span data-stu-id="6a929-244">If you are using the SamplePO.txt file as your test message, enter **\*.txt**.</span></span> <span data-ttu-id="6a929-245">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="6a929-245">Click **OK**.</span></span>  
  
8. <span data-ttu-id="6a929-246">有关**接收管道**，接受默认值为**PassThruReceive**。</span><span class="sxs-lookup"><span data-stu-id="6a929-246">For **Receive pipeline**, accept the default of **PassThruReceive**.</span></span>  
  
9. <span data-ttu-id="6a929-247">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="6a929-247">Click **OK**, and then click **OK** again.</span></span>  
  
10. <span data-ttu-id="6a929-248">单击**接收位置**节点，右键单击将接收位置，然后依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="6a929-248">Click the **Receive Locations** node, right-click your receive location, and then click **Enable**.</span></span>  
  
##### <a name="to-create-a-send-port-to-send-the-edi-interchange-over-as2-to-fabrikam"></a><span data-ttu-id="6a929-249">创建发送端口以通过 AS2 将 EDI 交换发送到 Fabrikam</span><span class="sxs-lookup"><span data-stu-id="6a929-249">To create a send port to send the EDI interchange over AS2 to Fabrikam</span></span>  
  
1. <span data-ttu-id="6a929-250">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="6a929-250">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2. <span data-ttu-id="6a929-251">在中**发送端口属性**对话框中，发送端口的名称作为**SendISAToFab**。</span><span class="sxs-lookup"><span data-stu-id="6a929-251">In the **Send Port Properties** dialog box, name the send port as **SendISAToFab**.</span></span>  
  
3. <span data-ttu-id="6a929-252">在中**传输**部分中，选择**HTTP**有关**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="6a929-252">In the **Transport** section, select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="6a929-253">在中**HTTP 传输属性**对话框中，对于**目标 URL**，输入**http://localhost/Fabrikam/BTSHttpReceive.dll**。</span><span class="sxs-lookup"><span data-stu-id="6a929-253">In the **HTTP Transport Properties** dialog box, for **Destination URL**, enter **http://localhost/Fabrikam/BTSHttpReceive.dll**.</span></span>  
  
5. <span data-ttu-id="6a929-254">清除**启用 Chunked 编码**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6a929-254">Clear **Enable Chunked Encoding**, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="6a929-255">在中**发送管道**，选择**AS2Send**。</span><span class="sxs-lookup"><span data-stu-id="6a929-255">In **Send pipeline**, select **AS2Send**.</span></span>  
  
7. <span data-ttu-id="6a929-256">在控制台树中，选择**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="6a929-256">In the console tree, select **Filters**.</span></span> <span data-ttu-id="6a929-257">有关**属性**，输入**BTS。ReceivePortName**; 对于**运算符**，输入**==**; 对于**值**输入将接收 EDI 的接收端口的名称交换 (`RecvISAFromCont`)。</span><span class="sxs-lookup"><span data-stu-id="6a929-257">For **Property**, enter **BTS.ReceivePortName**; for **Operator**, enter **==**; and for **Value** enter the name of the receive port that will receive the EDI interchange (`RecvISAFromCont`).</span></span>  
  
8. <span data-ttu-id="6a929-258">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="6a929-258">Click **OK**.</span></span>  
  
9. <span data-ttu-id="6a929-259">单击**发送端口**节点中管理控制台中，右键单击您的发送端口，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="6a929-259">Click the **Send Ports** node in the Administration Console, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-receive-port-for-fabrikam-to-receive-the-as2-message"></a><span data-ttu-id="6a929-260">创建用于接收 AS2 消息的 Fabrikam 接收端口</span><span class="sxs-lookup"><span data-stu-id="6a929-260">To create a receive port for Fabrikam to receive the AS2 message</span></span>  
  
1. <span data-ttu-id="6a929-261">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中的，在 BizTalk Application 1 节点中，右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**.</span><span class="sxs-lookup"><span data-stu-id="6a929-261">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, under the BizTalk Application 1 node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2. <span data-ttu-id="6a929-262">为接收端口的名称**RecvAS2ForFabrikam**，然后单击**接收位置**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="6a929-262">Name the receive port as **RecvAS2ForFabrikam**, and then click **Receive Locations** in the console tree.</span></span>  
  
3. <span data-ttu-id="6a929-263">单击 **“新建”**。</span><span class="sxs-lookup"><span data-stu-id="6a929-263">Click **New**.</span></span>  
  
4. <span data-ttu-id="6a929-264">在**接收位置属性**对话框中，名称在接收位置中，选择**HTTP**有关**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="6a929-264">In the **Receive Location Properties** dialog box, name your receive location, select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="6a929-265">在中**HTTP 传输属性**对话框框中，输入 **/Fabrikam/BTSHttpReceive.dll**有关**虚拟目录和 ISAPI 扩展**。</span><span class="sxs-lookup"><span data-stu-id="6a929-265">In the **HTTP Transport Properties** dialog box, enter **/Fabrikam/BTSHttpReceive.dll** for **Virtual directory plus ISAPI extension**.</span></span> <span data-ttu-id="6a929-266">清除**成功后的返回相关句柄**，然后选择**挂起失败的请求**。</span><span class="sxs-lookup"><span data-stu-id="6a929-266">Clear **Return correlation handle on success** and select **Suspend failed requests**.</span></span> <span data-ttu-id="6a929-267">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="6a929-267">Click **OK**.</span></span>  
  
6. <span data-ttu-id="6a929-268">选择**AS2Receive**有关**接收管道**。</span><span class="sxs-lookup"><span data-stu-id="6a929-268">Select **AS2Receive** for the **Receive Pipeline**.</span></span> <span data-ttu-id="6a929-269">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="6a929-269">Click **OK**, and then click **OK** again.</span></span>  
  
7. <span data-ttu-id="6a929-270">单击**接收位置**节点，右键单击将接收位置，然后依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="6a929-270">Click the **Receive Locations** node, right-click your receive location, and then click **Enable**.</span></span>  
  
##### <a name="to-create-a-send-port-to-send-the-edi-payload-to-a-local-folder"></a><span data-ttu-id="6a929-271">创建用于将 EDI 负载发送到本地文件夹的发送端口</span><span class="sxs-lookup"><span data-stu-id="6a929-271">To create a send port to send the EDI payload to a local folder</span></span>  
  
1. <span data-ttu-id="6a929-272">在 Windows 资源管理器中，创建一个用于接收 EDI 交换的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a929-272">In Windows Explorer, create a local folder to send the EDI interchange to.</span></span>  
  
2. <span data-ttu-id="6a929-273">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="6a929-273">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
3. <span data-ttu-id="6a929-274">在中**发送端口属性**对话框，为发送端口的名称**SendEDIToFab**。</span><span class="sxs-lookup"><span data-stu-id="6a929-274">In the **Send Port Properties** dialog box, name your send port as **SendEDIToFab**.</span></span> <span data-ttu-id="6a929-275">选择**文件**有关**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="6a929-275">Select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="6a929-276">在中**FILE 传输属性**对话框中，对于**目标文件夹**，输入为 EDI 负载创建的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a929-276">In the **FILE Transport Properties** dialog box, for **Destination folder**, enter the local folder that you created for the EDI payload.</span></span>  
  
5. <span data-ttu-id="6a929-277">有关**文件名**，输入文件名称。</span><span class="sxs-lookup"><span data-stu-id="6a929-277">For **File name**, enter the file name.</span></span> <span data-ttu-id="6a929-278">如果您使用的 SamplePO.txt 文件作为测试消息，请输入 **%MessageID%.txt**。</span><span class="sxs-lookup"><span data-stu-id="6a929-278">If you are using the SamplePO.txt file as your test message, enter **%MessageID%.txt**.</span></span> <span data-ttu-id="6a929-279">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="6a929-279">Click **OK**.</span></span>  
  
6. <span data-ttu-id="6a929-280">接受默认值为**PassThruTransmit**有关**发送管道**。</span><span class="sxs-lookup"><span data-stu-id="6a929-280">Accept the default of **PassThruTransmit** for **Send Pipeline**.</span></span>  
  
7. <span data-ttu-id="6a929-281">单击**筛选器**在控制台树，并添加用于提取 EDI 负载的筛选器属性。</span><span class="sxs-lookup"><span data-stu-id="6a929-281">Click **Filters** in the console tree, and add filter properties for picking up the EDI payload.</span></span> <span data-ttu-id="6a929-282">在第一行，对于**属性**，输入**BTS。ReceivePortName**; 对于**运算符**，输入**==**; 对于**值**，输入接收 AS2 的接收端口的名称消息 (`RecvAS2ForFabrikam`); 对于**分组依据**，接受**和**。</span><span class="sxs-lookup"><span data-stu-id="6a929-282">On the first line, for **Property**, enter **BTS.ReceivePortName**; for **Operator**, enter **==**; for **Value**, enter the name of the receive port that receives the AS2 message (`RecvAS2ForFabrikam`); and for **Group by**, accept **And**.</span></span> <span data-ttu-id="6a929-283">在第二行，对于**属性**，输入**EdiIntAS.IsAS2PayloadMessage**; 对于**运算符**，输入**==**; 以及**值**，输入**True**。</span><span class="sxs-lookup"><span data-stu-id="6a929-283">On the second line, for **Property**, enter **EdiIntAS.IsAS2PayloadMessage**; for **Operator**, enter **==**; and for **Value**, enter **True**.</span></span>  
  
8. <span data-ttu-id="6a929-284">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="6a929-284">Click **OK**.</span></span>  
  
9. <span data-ttu-id="6a929-285">单击**发送端口**节点，右键单击您的发送端口，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="6a929-285">Click the **Send Ports** node, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-dynamic-one-way-send-port-to-return-the-mdn"></a><span data-ttu-id="6a929-286">创建用于返回 MDN 的动态单向发送端口</span><span class="sxs-lookup"><span data-stu-id="6a929-286">To create a dynamic one-way send port to return the MDN</span></span>  
  
1. <span data-ttu-id="6a929-287">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**动态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="6a929-287">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **Send Ports**, point to **New**, and then click **Dynamic One-Way Send Port**.</span></span>  
  
2. <span data-ttu-id="6a929-288">在中**发送端口属性**对话框，为发送端口的名称**Send_MDN**。</span><span class="sxs-lookup"><span data-stu-id="6a929-288">In the **Send Port Properties** dialog box, name your send port as **Send_MDN**.</span></span>  
  
3. <span data-ttu-id="6a929-289">有关**发送管道**，输入 AS2Send。</span><span class="sxs-lookup"><span data-stu-id="6a929-289">For **Send Pipeline**, enter AS2Send.</span></span>  
  
4. <span data-ttu-id="6a929-290">单击**筛选器**在控制台树，并添加用于提取 EDI 负载的筛选器属性。</span><span class="sxs-lookup"><span data-stu-id="6a929-290">Click **Filters** in the console tree, and add filter properties for picking up the EDI payload.</span></span> <span data-ttu-id="6a929-291">在第一行，对于**属性**，输入**BTS。ReceivePortName**; 对于**运算符**，输入**==**; 对于**值**，输入接收 AS2 的接收端口的名称消息 (`RecvAS2ForFabrikam`); 对于**分组依据**，接受**和**。</span><span class="sxs-lookup"><span data-stu-id="6a929-291">On the first line, for **Property**, enter **BTS.ReceivePortName**; for **Operator**, enter **==**; for **Value**, enter the name of the receive port that receives the AS2 message (`RecvAS2ForFabrikam`); and for **Group by**, accept **And**.</span></span> <span data-ttu-id="6a929-292">在第二行，对于**属性**，输入**EdiIntAS.IsAS2AsynchronousMDN**; 对于**运算符**，输入**==**; 以及**值**，输入**True**。</span><span class="sxs-lookup"><span data-stu-id="6a929-292">On the second line, for **Property**, enter **EdiIntAS.IsAS2AsynchronousMDN**; for **Operator**, enter **==**; and for **Value**, enter **True**.</span></span>  
  
5. <span data-ttu-id="6a929-293">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="6a929-293">Click **OK**.</span></span>  
  
6. <span data-ttu-id="6a929-294">单击**发送端口**节点，右键单击您的发送端口，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="6a929-294">Click the **Send Ports** node, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-receive-port-to-receive-the-mdn-from-fabrikam"></a><span data-ttu-id="6a929-295">创建用于从 Fabrikam 接收 MDN 的接收端口</span><span class="sxs-lookup"><span data-stu-id="6a929-295">To create a receive port to receive the MDN from Fabrikam</span></span>  
  
1. <span data-ttu-id="6a929-296">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中的，在 BizTalk Application 1 节点中，右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**.</span><span class="sxs-lookup"><span data-stu-id="6a929-296">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, under the BizTalk Application 1 node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2. <span data-ttu-id="6a929-297">为接收端口的名称**RecvMDNFromFab**，然后单击**接收位置**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="6a929-297">Name the receive port as **RecvMDNFromFab**, and then click **Receive Locations** in the console tree.</span></span>  
  
3. <span data-ttu-id="6a929-298">单击 **“新建”**。</span><span class="sxs-lookup"><span data-stu-id="6a929-298">Click **New**.</span></span>  
  
4. <span data-ttu-id="6a929-299">在**接收位置属性**对话框中，名称在接收位置中，选择**HTTP**有关**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="6a929-299">In the **Receive Location Properties** dialog box, name your receive location, select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="6a929-300">在中**HTTP 传输属性**对话框框中，输入 **/Contoso/BTSHTTPReceive.dll**有关**虚拟目录和 ISAPI 扩展**。</span><span class="sxs-lookup"><span data-stu-id="6a929-300">In the **HTTP Transport Properties** dialog box, enter **/Contoso/BTSHTTPReceive.dll** for **Virtual directory plus ISAPI extension**.</span></span> <span data-ttu-id="6a929-301">清除**成功后的返回相关句柄**，然后选择**挂起失败的请求**。</span><span class="sxs-lookup"><span data-stu-id="6a929-301">Clear **Return correlation handle on success** and select **Suspend failed requests**.</span></span> <span data-ttu-id="6a929-302">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="6a929-302">Click **OK**.</span></span>  
  
6. <span data-ttu-id="6a929-303">选择**AS2Receive**有关**接收管道**。</span><span class="sxs-lookup"><span data-stu-id="6a929-303">Select **AS2Receive** for the **Receive Pipeline**.</span></span> <span data-ttu-id="6a929-304">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="6a929-304">Click **OK**, and then click **OK** again.</span></span>  
  
7. <span data-ttu-id="6a929-305">单击**接收位置**节点，右键单击将接收位置，然后依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="6a929-305">Click the **Receive Locations** node, right-click your receive location, and then click **Enable**.</span></span>  
  
##### <a name="to-create-a-send-port-to-send-the-mdn-to-a-local-folder"></a><span data-ttu-id="6a929-306">创建用于将 MDN 发送到本地文件夹的发送端口</span><span class="sxs-lookup"><span data-stu-id="6a929-306">To create a send port to send the MDN to a local folder</span></span>  
  
1. <span data-ttu-id="6a929-307">在 Windows 资源管理器中，创建一个用于接收 MDN 的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a929-307">In Windows Explorer, create a local folder to send the MDN to.</span></span>  
  
2. <span data-ttu-id="6a929-308">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="6a929-308">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
3. <span data-ttu-id="6a929-309">在中**发送端口属性**对话框框中，发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="6a929-309">In the **Send Port Properties** dialog box, name your send port.</span></span> <span data-ttu-id="6a929-310">选择**文件**有关**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="6a929-310">Select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="6a929-311">在中**FILE 传输属性**对话框中，对于**目标文件夹**，输入您创建的用于接收 MDN 的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a929-311">In the **FILE Transport Properties** dialog box, for **Destination folder**, enter the local folder you created to send the MDN to.</span></span>  
  
5. <span data-ttu-id="6a929-312">有关**文件名**，输入 **%MessageID%.msg**。单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6a929-312">For **File name**, enter **%MessageID%.msg**. Click **OK**.</span></span>  
  
6. <span data-ttu-id="6a929-313">接受默认值为**PassThruTransmit**有关**发送管道**。</span><span class="sxs-lookup"><span data-stu-id="6a929-313">Accept the default of **PassThruTransmit** for **Send Pipeline**.</span></span>  
  
7. <span data-ttu-id="6a929-314">单击**筛选器**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="6a929-314">Click **Filters** in the console tree.</span></span> <span data-ttu-id="6a929-315">有关**属性**，输入**BTS。ReceivePortName**; 对于**运算符**，输入**==**; 对于**值**，输入接收 MDN (的接收端口的名称`RecvMDNFromFab`);对于**分组依据**，接受**和**。</span><span class="sxs-lookup"><span data-stu-id="6a929-315">For **Property**, enter **BTS.ReceivePortName**; for **Operator**, enter **==**; for **Value**, enter the name of the receive port that receives the MDN (`RecvMDNFromFab`); and for **Group by**, accept **And**.</span></span> <span data-ttu-id="6a929-316">在第二个行中，对于**属性**，输入**EdiIntAS.IsAS2MdnResponseMessage**。</span><span class="sxs-lookup"><span data-stu-id="6a929-316">On a second line, for **Property**, enter **EdiIntAS.IsAS2MdnResponseMessage**.</span></span> <span data-ttu-id="6a929-317">有关**运算符**，输入**==**。</span><span class="sxs-lookup"><span data-stu-id="6a929-317">For **Operator**, enter **==**.</span></span> <span data-ttu-id="6a929-318">有关**值**，输入**True**。</span><span class="sxs-lookup"><span data-stu-id="6a929-318">For **Value**, enter **True**.</span></span>  
  
8. <span data-ttu-id="6a929-319">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="6a929-319">Click **OK**.</span></span>  
  
9. <span data-ttu-id="6a929-320">单击**发送端口**节点，右键单击您的发送端口，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="6a929-320">Click the **Send Ports** node, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a><span data-ttu-id="6a929-321">创建 Fabrikam 参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="6a929-321">To create a party and a business profile for Fabrikam</span></span>  
  
1. <span data-ttu-id="6a929-322">右键单击**参与方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="6a929-322">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2. <span data-ttu-id="6a929-323">输入中的参与方的名称**名称**文本框中，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6a929-323">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6a929-324">通过选择**本地 BizTalk 处理接收的来自此参与方发送消息的参与方或支持消息**复选框，可以指定要创建的参与方是为同一组织与托管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a929-324">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="6a929-325">此基础，某些属性将启用，或禁用在创建协议时。</span><span class="sxs-lookup"><span data-stu-id="6a929-325">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="6a929-326">但是，对于此演练中，可以选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="6a929-326">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3. <span data-ttu-id="6a929-327">右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="6a929-327">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4. <span data-ttu-id="6a929-328">在中**配置文件属性**对话框中，在**常规**页上，输入**Fabrikam_Profile**中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="6a929-328">In the **Profile Properties** dialog box, on the **General** page, enter **Fabrikam_Profile** in the **Name** text box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6a929-329">创建一个参与方时，还创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="6a929-329">When you create a party, a profile is also created.</span></span> <span data-ttu-id="6a929-330">可以重命名，并使用该配置文件而不是创建一个新。</span><span class="sxs-lookup"><span data-stu-id="6a929-330">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="6a929-331">若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="6a929-331">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="6a929-332">在中**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="6a929-332">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a><span data-ttu-id="6a929-333">为 Contoso 创建参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="6a929-333">To create a party and a business profile for Contoso</span></span>  
  
1. <span data-ttu-id="6a929-334">右键单击**参与方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="6a929-334">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2. <span data-ttu-id="6a929-335">输入中的参与方的名称**名称**文本框中，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6a929-335">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6a929-336">通过选择**本地 BizTalk 处理接收的来自此参与方发送消息的参与方或支持消息**复选框，可以指定要创建的参与方是为同一组织与托管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a929-336">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="6a929-337">此基础，某些属性将启用，或禁用在创建协议时。</span><span class="sxs-lookup"><span data-stu-id="6a929-337">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="6a929-338">但是，对于此演练中，可以选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="6a929-338">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3. <span data-ttu-id="6a929-339">右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="6a929-339">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4. <span data-ttu-id="6a929-340">在中**配置文件属性**对话框中，在**常规**页上，输入**Contoso_Profile**中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="6a929-340">In the **Profile Properties** dialog box, on the **General** page, enter **Contoso_Profile** in the **Name** text box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6a929-341">创建一个参与方时，还创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="6a929-341">When you create a party, a profile is also created.</span></span> <span data-ttu-id="6a929-342">可以重命名，并使用该配置文件而不是创建一个新。</span><span class="sxs-lookup"><span data-stu-id="6a929-342">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="6a929-343">若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="6a929-343">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="6a929-344">在中**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="6a929-344">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-an-as2-agreement-between-the-two-business-profiles"></a><span data-ttu-id="6a929-345">在两个业务配置文件之间创建 AS2 协议</span><span class="sxs-lookup"><span data-stu-id="6a929-345">To create an AS2 agreement between the two business profiles</span></span>  
  
1.  <span data-ttu-id="6a929-346">右键单击**Contoso_Profile**，依次指向**新建**，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="6a929-346">Right-click **Contoso_Profile**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="6a929-347">在**常规属性**页上，对于**名称**文字框中，输入协议的名称。</span><span class="sxs-lookup"><span data-stu-id="6a929-347">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  
  
3.  <span data-ttu-id="6a929-348">从**协议**下拉列表中，选择**AS2**。</span><span class="sxs-lookup"><span data-stu-id="6a929-348">From the **Protocol** drop-down list, select **AS2**.</span></span>  
  
4.  <span data-ttu-id="6a929-349">在中**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**Fabrikam**。</span><span class="sxs-lookup"><span data-stu-id="6a929-349">In the **Second Partner** section, from the **Name** drop-down list, select **Fabrikam**.</span></span>  
  
5.  <span data-ttu-id="6a929-350">在中**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**Fabrikam_Profile**。</span><span class="sxs-lookup"><span data-stu-id="6a929-350">In the **Second Partner** section, from the **Profile** drop-down list, select **Fabrikam_Profile**.</span></span>  
  
     <span data-ttu-id="6a929-351">你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡用于配置一个单向 AS2 协议。</span><span class="sxs-lookup"><span data-stu-id="6a929-351">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way AS2 agreement.</span></span>  
  
6.  <span data-ttu-id="6a929-352">在执行以下任务**Contoso-> Fabrikam**选项卡。</span><span class="sxs-lookup"><span data-stu-id="6a929-352">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  
  
    1.  <span data-ttu-id="6a929-353">上**标识符**页上，输入值**AS2-从**并**AS2-到**。</span><span class="sxs-lookup"><span data-stu-id="6a929-353">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="6a929-354">有关**AS2-从**，输入`Contoso`。</span><span class="sxs-lookup"><span data-stu-id="6a929-354">For **AS2-From**, enter `Contoso`.</span></span> <span data-ttu-id="6a929-355">有关**AS2-To**，输入`Fabrikam`。</span><span class="sxs-lookup"><span data-stu-id="6a929-355">For **AS2- To**, enter `Fabrikam`.</span></span>  
  
    2.  <span data-ttu-id="6a929-356">在中**确认 (Mdn)** 页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6a929-356">In the **Acknowledgements (MDNs)** page, do the following:</span></span>  
  
        1.  <span data-ttu-id="6a929-357">选择**到 MessageBox 中处理入站的 MDN 以进行路由/传递**复选框。</span><span class="sxs-lookup"><span data-stu-id="6a929-357">Select the **Process inbound MDN into MessageBox for routing/delivery options** check box.</span></span>  
  
            > [!NOTE]
            >  <span data-ttu-id="6a929-358">检查**到 MessageBox 中处理入站的 MDN 以进行路由/传递**需要本演练中，测试，因为只有这样将返回的 MDN 才能放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="6a929-358">Checking the **Process inbound MDN into MessageBox for routing/delivery options** is required for the testing of this walkthrough, because only then will the returned MDN be dropped into the MessageBox.</span></span> <span data-ttu-id="6a929-359">这样，便可创建一个用于订阅 MDN 并将 MDN 发送至本地目录的发送端口，从而可以验证 AS2 传输。</span><span class="sxs-lookup"><span data-stu-id="6a929-359">That enables you to create a send port to subscribe to the MDN, and to send the MDN to a local directory, so you can verify the AS2 transmission.</span></span>  
  
        2.  <span data-ttu-id="6a929-360">选择**请求 MDN**复选框。</span><span class="sxs-lookup"><span data-stu-id="6a929-360">Select the **Request MDN** check box.</span></span>  
  
        3.  <span data-ttu-id="6a929-361">请确保**请求经过签名的 MDN**清除复选框。</span><span class="sxs-lookup"><span data-stu-id="6a929-361">Make sure the **Request Signed MDN** check box is cleared.</span></span>  
  
        4.  <span data-ttu-id="6a929-362">选择**请求异步 MDN**复选框。</span><span class="sxs-lookup"><span data-stu-id="6a929-362">Select the **Request asynchronous MDN** check box.</span></span>  
  
        5.  <span data-ttu-id="6a929-363">在中**回执送达选项 (URL)**，输入**http://localhost/Contoso/BTSHttpReceive.dll**。</span><span class="sxs-lookup"><span data-stu-id="6a929-363">In **Receipt-Delivery-Option (URL)**, enter **http://localhost/Contoso/BTSHttpReceive.dll**.</span></span>  
  
        6.  <span data-ttu-id="6a929-364">**处置-到通知**默认情况下设置为值指定为**回执送达选项 (URL)** 属性。</span><span class="sxs-lookup"><span data-stu-id="6a929-364">The **Disposition-Notification-To** is by default set to the value you specified for **Receipt-Delivery-Option (URL)** property.</span></span> <span data-ttu-id="6a929-365">此字段中的值不会在 AS2 处理中使用。</span><span class="sxs-lookup"><span data-stu-id="6a929-365">The value of this field is not used during AS2 processing.</span></span>  
  
    3.  <span data-ttu-id="6a929-366">上**发送端口**页上，将会将 EDI 交换发送到 Fabrikam 的双向发送端口相关联。</span><span class="sxs-lookup"><span data-stu-id="6a929-366">On the **Send Ports** page, associate the two-way send port that will be sending the EDI interchange to Fabrikam.</span></span> <span data-ttu-id="6a929-367">在中**发送端口**网格下**名称**列中，单击空单元格，并从下拉列表中，选择发送端口**SendISAToFab**。</span><span class="sxs-lookup"><span data-stu-id="6a929-367">In the **Send ports** grid, under the **Name** column, click an empty cell, and from the drop-down list, select the send port **SendISAToFab**.</span></span>  
  
7.  <span data-ttu-id="6a929-368">在执行以下任务**Fabrikam-> Contoso**选项卡。</span><span class="sxs-lookup"><span data-stu-id="6a929-368">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6a929-369">在本演练中，我们指定的选项卡中所需的值，以便可以成功创建协议。</span><span class="sxs-lookup"><span data-stu-id="6a929-369">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="6a929-370">若要成功创建协议，两个单向协议选项卡必须具有定义为值**AS2_From**并**AS2-到**。</span><span class="sxs-lookup"><span data-stu-id="6a929-370">To successfully create an agreement, both one-way agreement tabs must have values defined for **AS2_From** and **AS2-To**.</span></span>  
  
    1.  <span data-ttu-id="6a929-371">上**标识符**页上，输入值**AS2-从**并**AS2-到**。</span><span class="sxs-lookup"><span data-stu-id="6a929-371">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="6a929-372">有关**AS2-从**，输入`Fabrikam`。</span><span class="sxs-lookup"><span data-stu-id="6a929-372">For **AS2-From**, enter `Fabrikam`.</span></span> <span data-ttu-id="6a929-373">有关**AS2-To**，输入`Contoso`。</span><span class="sxs-lookup"><span data-stu-id="6a929-373">For **AS2- To**, enter `Contoso`.</span></span>  
  
8.  <span data-ttu-id="6a929-374">单击 **“应用”**。</span><span class="sxs-lookup"><span data-stu-id="6a929-374">Click **Apply**.</span></span>  
  
9. <span data-ttu-id="6a929-375">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="6a929-375">Click **OK**.</span></span> <span data-ttu-id="6a929-376">中列出新添加的协议**协议**一部分**参与方和业务配置文件**窗格。</span><span class="sxs-lookup"><span data-stu-id="6a929-376">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="6a929-377">默认情况下，启用新添加的协议。</span><span class="sxs-lookup"><span data-stu-id="6a929-377">The newly added agreement is enabled by default.</span></span>  
  
### <a name="testing-the-walkthrough"></a><span data-ttu-id="6a929-378">测试演练</span><span class="sxs-lookup"><span data-stu-id="6a929-378">Testing the Walkthrough</span></span>  
 <span data-ttu-id="6a929-379">本部分提供有关如何测试演练的信息。</span><span class="sxs-lookup"><span data-stu-id="6a929-379">This section provides information on how to test the walkthrough.</span></span>  
  
##### <a name="to-test-the-solution"></a><span data-ttu-id="6a929-380">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="6a929-380">To test the solution</span></span>  
  
1. <span data-ttu-id="6a929-381">在 Windows 资源管理器中，转到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\EDI 界面开发人员教程。</span><span class="sxs-lookup"><span data-stu-id="6a929-381">In Windows Explorer, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial.</span></span> <span data-ttu-id="6a929-382">复制**SamplePO.txt**文件。</span><span class="sxs-lookup"><span data-stu-id="6a929-382">Copy the **SamplePO.txt** file.</span></span>  
  
2. <span data-ttu-id="6a929-383">粘贴**SamplePO.txt**文件到您创建的用于从 Contoso 接收测试消息的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a929-383">Paste the **SamplePO.txt** file into the local folder that you created to receive the test message from Contoso.</span></span>  
  
3. <span data-ttu-id="6a929-384">转到您创建的用于接收 EDI 负载的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a929-384">Move to the local folder that you created to send the EDI payload to.</span></span> <span data-ttu-id="6a929-385">确认文件夹中含有一个 EDI 文件。</span><span class="sxs-lookup"><span data-stu-id="6a929-385">Confirm that the folder contains an EDI file.</span></span> <span data-ttu-id="6a929-386">打开该文件和原始测试消息，验证它们的内容是否相同。</span><span class="sxs-lookup"><span data-stu-id="6a929-386">Open the file and the original test message, and verify that they have the same content.</span></span>  
  
4. <span data-ttu-id="6a929-387">转到您创建的用于接收生成的 MDN 的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a929-387">Move to the local folder that you created to send the resulting MDN to.</span></span> <span data-ttu-id="6a929-388">确认该文件夹包含一个测试文件；打开该文件并确认它是一个 MDN 文件。</span><span class="sxs-lookup"><span data-stu-id="6a929-388">Confirm that the folder contains a test file; open the file, and confirm that it is an MDN file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a929-389">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a929-389">See Also</span></span>  
 [<span data-ttu-id="6a929-390">开发和配置 BizTalk Server AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="6a929-390">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)