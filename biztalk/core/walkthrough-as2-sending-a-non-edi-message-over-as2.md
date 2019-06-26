---
title: 演练 (AS2):通过 AS2 发送非 EDI 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6120b81e-bdd5-44ad-9040-26be88c71258
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8b00f1b78ac994dbd9e5208996c0b46309aa1b5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398567"
---
# <a name="walkthrough-as2-sending-a-non-edi-message-over-as2"></a><span data-ttu-id="d6083-102">演练 (AS2):通过 AS2 发送非 EDI 消息</span><span class="sxs-lookup"><span data-stu-id="d6083-102">Walkthrough (AS2): Sending a Non-EDI Message over AS2</span></span>
<span data-ttu-id="d6083-103">本演练介绍创建通过 AS2 发送非 EDI 消息的解决方案的一组的分步过程。</span><span class="sxs-lookup"><span data-stu-id="d6083-103">This walkthrough provides a set of step-by-step procedures that creates a solution for sending non-EDI messages over AS2.</span></span> <span data-ttu-id="d6083-104">在此演练中，PIDX 消息是通过 AS2 发送的。</span><span class="sxs-lookup"><span data-stu-id="d6083-104">In this walkthrough, a PIDX message is sent over AS2.</span></span> <span data-ttu-id="d6083-105">此解决方案使用双向发送端口使用 AS2Send 发送管道及 AS2Receive 接收管道。</span><span class="sxs-lookup"><span data-stu-id="d6083-105">This solution uses a two-way send port with an AS2Send send pipeline and an AS2Receive receive pipeline.</span></span> <span data-ttu-id="d6083-106">可以创建和测试在本演练中在单台计算机上的完整解决方案。</span><span class="sxs-lookup"><span data-stu-id="d6083-106">You can create and test the full solution in this walkthrough on a single computer.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d6083-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="d6083-107">Prerequisites</span></span>  
 <span data-ttu-id="d6083-108">在本主题中执行该过程的先决条件如下：</span><span class="sxs-lookup"><span data-stu-id="d6083-108">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
- <span data-ttu-id="d6083-109">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="d6083-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
- <span data-ttu-id="d6083-110">运行此演练的计算机必须具有 Internet 信息服务 (IIS) 7 安装。</span><span class="sxs-lookup"><span data-stu-id="d6083-110">The computer that runs the walkthrough must have Internet Information Services (IIS) 7 installed.</span></span>  
  
- <span data-ttu-id="d6083-111">如果使用 64 位版本的 Windows 安装运行此演练的计算机，则必须确保 BizTalk 主机仅标记为 32 位。</span><span class="sxs-lookup"><span data-stu-id="d6083-111">If the computer that runs the walkthrough is installed with a 64-bit version of Windows, you must ensure that the BizTalk hosts are marked as 32-bit only.</span></span> <span data-ttu-id="d6083-112">此外必须确保 IIS 已设置为 True 的应用程序池启用 32 位应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="d6083-112">You must also ensure IIS has the Enable 32-Bit Application Setting for the Application Pools set to True.</span></span> <span data-ttu-id="d6083-113">有关详细信息，请参阅[教程 3:AS2 教程](../core/tutorial-3-as2-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="d6083-113">For more information, see [Tutorial 3: AS2 Tutorial](../core/tutorial-3-as2-tutorial.md).</span></span>  
  
## <a name="how-the-solution-sends-a-non-edias2-message-and-returns-a-synchronous-mdn"></a><span data-ttu-id="d6083-114">该解决方案如何发送非 EDI/AS2 消息并返回同步 MDN</span><span class="sxs-lookup"><span data-stu-id="d6083-114">How the Solution Sends a non-EDI/AS2 Message and Returns a Synchronous MDN</span></span>  
 <span data-ttu-id="d6083-115">该解决方案将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d6083-115">The solution will do the following:</span></span>  
  
1. <span data-ttu-id="d6083-116">一个单向 FILE 接收端口从 Contoso 接收 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="d6083-116">A one-way FILE receive port receives an XML message from Contoso.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d6083-117">显示的顺序可能不是此列表中的事件。</span><span class="sxs-lookup"><span data-stu-id="d6083-117">The events in this list may not occur in the order shown.</span></span>  
  
2. <span data-ttu-id="d6083-118">使用 XML 接收管道，接收端口将检查该消息。</span><span class="sxs-lookup"><span data-stu-id="d6083-118">Using the XML receive pipeline, the receive port checks the message.</span></span> <span data-ttu-id="d6083-119">接收端口随后将测试消息原样-入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="d6083-119">The receive port then drops the test message as-is into the MessageBox.</span></span>  
  
3. <span data-ttu-id="d6083-120">静态双向发送端口提取 XML 消息，接收端口接收的所有消息都订阅。</span><span class="sxs-lookup"><span data-stu-id="d6083-120">A static two-way send port picks up the XML message, subscribing to all messages received by the receive port.</span></span>  
  
4. <span data-ttu-id="d6083-121">双向接收端口 Fabrikam 接收 AS2 消息使用 Fabrikam 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="d6083-121">The two-way receive port at Fabrikam receives the AS2 message using the Fabrikam virtual directory.</span></span> <span data-ttu-id="d6083-122">接收管道对来自 AS2 消息进行解码，并会将消息放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="d6083-122">The receive pipeline decodes the message from AS2, and drops the message into the MessageBox.</span></span>  
  
5. <span data-ttu-id="d6083-123">带有直通发送管道的静态单向发送端口提取 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="d6083-123">A static one-way send port with a passthrough send pipeline picks up the XML message.</span></span>  
  
6. <span data-ttu-id="d6083-124">单向发送端口将 XML 消息发送到本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="d6083-124">The one-way send port sends the XML message to a local folder.</span></span>  
  
7. <span data-ttu-id="d6083-125">与双向关联的发送端口接收端口返回同步 MDN。</span><span class="sxs-lookup"><span data-stu-id="d6083-125">The send port associated with the two-way receive port returns a synchronous MDN.</span></span>  
  
8. <span data-ttu-id="d6083-126">与双向发送端口相关联的接收端口接收 MDN，并将其放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="d6083-126">The receive port associated with the two-way send port receives the MDN, and drops it in the MessageBox.</span></span>  
  
9. <span data-ttu-id="d6083-127">带有直通发送管道的静态单向发送端口提取 MDN。</span><span class="sxs-lookup"><span data-stu-id="d6083-127">A static one-way send port with a passthrough send pipeline picks up the MDN.</span></span>  
  
10. <span data-ttu-id="d6083-128">单向发送端口将 MDN 发送到本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="d6083-128">The one-way send port sends the MDN to a local folder.</span></span>  
  
    <span data-ttu-id="d6083-129">下图显示了解决方案的体系结构。</span><span class="sxs-lookup"><span data-stu-id="d6083-129">The following figure shows the architecture for the solution.</span></span>  
  
    <span data-ttu-id="d6083-130">![发送非&#45;通过 AS2 的 EDI 消息](../core/media/57b7dc54-b8e8-462e-98d1-9cddedd14107.gif "57b7dc54-b8e8-462e-98d1-9cddedd14107")</span><span class="sxs-lookup"><span data-stu-id="d6083-130">![Sending a non&#45;EDI message over AS2](../core/media/57b7dc54-b8e8-462e-98d1-9cddedd14107.gif "57b7dc54-b8e8-462e-98d1-9cddedd14107")</span></span>  
  
## <a name="the-functionality-in-this-solution"></a><span data-ttu-id="d6083-131">此解决方案中的功能</span><span class="sxs-lookup"><span data-stu-id="d6083-131">The Functionality in this Solution</span></span>  
 <span data-ttu-id="d6083-132">以下内容适用于本演练的功能：</span><span class="sxs-lookup"><span data-stu-id="d6083-132">The following applies to the functionality of this walkthrough:</span></span>  
  
-   <span data-ttu-id="d6083-133">本演练针对的是 AS2 功能。</span><span class="sxs-lookup"><span data-stu-id="d6083-133">This walkthrough deals with AS2 functionality.</span></span> <span data-ttu-id="d6083-134">因此，所有端口所都涉及的 AS2 处理使用是 AS2Receive 或 AS2Send 管道。</span><span class="sxs-lookup"><span data-stu-id="d6083-134">As a result, all ports involved in AS2 processing use either AS2Receive or AS2Send pipelines.</span></span> <span data-ttu-id="d6083-135">不涉及到的端口在 AS2 处理中使用 XMLReceive 或 PassThruTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="d6083-135">Ports that are not involved in AS2 processing use either the XMLReceive or PassThruTransmit pipelines.</span></span>  
  
-   <span data-ttu-id="d6083-136">本演练使用 XML 测试消息。</span><span class="sxs-lookup"><span data-stu-id="d6083-136">This walkthrough uses an XML test message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6083-137">必须提供 XML 测试消息和测试消息的架构。</span><span class="sxs-lookup"><span data-stu-id="d6083-137">You must provide an XML test message and a schema for the test message.</span></span>  
  
-   <span data-ttu-id="d6083-138">未启用状态报告。</span><span class="sxs-lookup"><span data-stu-id="d6083-138">Status reporting is not enabled.</span></span>  
  
-   <span data-ttu-id="d6083-139">此解决方案不会在不可否认数据库中配置签名、 压缩、 加密或消息存储。</span><span class="sxs-lookup"><span data-stu-id="d6083-139">This solution does not configure signing, compression, encryption, or message storage in the non-repudiation database.</span></span> <span data-ttu-id="d6083-140">有关配置这些属性的过程，请参阅[配置 AS2 属性](../core/configuring-as2-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="d6083-140">For procedures on configuring those properties, see [Configuring AS2 Properties](../core/configuring-as2-properties.md).</span></span>  
  
## <a name="configuring-and-testing-the-walkthrough"></a><span data-ttu-id="d6083-141">配置和测试演练</span><span class="sxs-lookup"><span data-stu-id="d6083-141">Configuring and Testing the Walkthrough</span></span>  
 <span data-ttu-id="d6083-142">此解决方案所需的过程包括：</span><span class="sxs-lookup"><span data-stu-id="d6083-142">The procedures required for this solution include the following:</span></span>  
  
- <span data-ttu-id="d6083-143">生成和部署具有必需的消息架构，使架构可供使用的 BizTalk 项目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在处理收到的消息。</span><span class="sxs-lookup"><span data-stu-id="d6083-143">Build and deploy a BizTalk project with the required message schema, making the schema available for use by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in processing the received message.</span></span>  
  
- <span data-ttu-id="d6083-144">启用接收 AS2 消息中使用的 BTS ISAPI 筛选器。</span><span class="sxs-lookup"><span data-stu-id="d6083-144">Enable the BTS ISAPI filter used in receiving the AS2 message.</span></span>  
  
- <span data-ttu-id="d6083-145">创建一个用于从 Contoso 接收 AS2 消息的 Fabrikam 虚拟目录，如接收位置中的配置。</span><span class="sxs-lookup"><span data-stu-id="d6083-145">Create a Fabrikam virtual directory that receives the AS2 message from Contoso, as configured in the receive location.</span></span>  
  
- <span data-ttu-id="d6083-146">指定 Fabrikam 虚拟目录不由 Windows SharePoint Services 托管。</span><span class="sxs-lookup"><span data-stu-id="d6083-146">Specify that the Fabrikam virtual directory is not managed by Windows SharePoint Services.</span></span>  
  
- <span data-ttu-id="d6083-147">创建一个单向 FILE 接收端口接收将通过 AS2 传输发送的 XML 测试消息。</span><span class="sxs-lookup"><span data-stu-id="d6083-147">Create a one-way FILE receive port to receive the XML test message that will be sent via AS2 transport.</span></span> <span data-ttu-id="d6083-148">创建用于接收测试消息的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="d6083-148">Create the local folder to receive the test message.</span></span>  
  
- <span data-ttu-id="d6083-149">创建静态要求响应 HTTP 发送端口，配置为 AS2Send 管道，接收管道为 AS2Receive 管道的发送管道。</span><span class="sxs-lookup"><span data-stu-id="d6083-149">Create a static solicit-response HTTP send port, configuring the send pipeline to be the AS2Send pipeline and the receive pipeline to be the AS2Receive pipeline.</span></span> <span data-ttu-id="d6083-150">端口将 AS2 消息发送到 Fabrikam 并接收来自 Fabrikam 的 MDN 响应并将其放入消息框。</span><span class="sxs-lookup"><span data-stu-id="d6083-150">The port sends the AS2 message to Fabrikam and receives the MDN response from Fabrikam and drops it to the Message box.</span></span>  
  
- <span data-ttu-id="d6083-151">创建一个双向 HTTP 接收端口[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于接收 AS2 消息和发送 MDN 响应。</span><span class="sxs-lookup"><span data-stu-id="d6083-151">Create a two-way HTTP receive port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive the AS2 message, and to send the MDN response.</span></span> <span data-ttu-id="d6083-152">接收管道配置为 AS2Receive 管道和发送管道为 AS2Send 管道。</span><span class="sxs-lookup"><span data-stu-id="d6083-152">Configure the receive pipeline to be the AS2Receive pipeline and the send pipeline to be the AS2Send pipeline.</span></span> <span data-ttu-id="d6083-153">配置接收位置接收 AS2 消息通过 Fabrikam 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="d6083-153">Configure the receive location to receive the AS2 message via the Fabrikam virtual directory.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="d6083-154">测试解决方案是在一台计算机;因此，双向发送端口从 Contoso 发送 AS2 消息和双向接收端口接收的 AS2 消息 （Fabrikam) 位于同一台计算机。</span><span class="sxs-lookup"><span data-stu-id="d6083-154">The test solution is on a single computer; as a result, the two-way send port sending the AS2 message (from Contoso) and the two-way receive port receiving the AS2 message (as Fabrikam) are on the same computer.</span></span>  
  
- <span data-ttu-id="d6083-155">创建静态单向 FILE 发送端口 （带有直通发送管道） 以将消息 XML 负载路由到本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="d6083-155">Create a static one-way FILE send port (with a passthrough send pipeline) to route the message XML payload to a local folder.</span></span> <span data-ttu-id="d6083-156">创建本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="d6083-156">Create the local folder.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="d6083-157">如果没有发送端口以订阅消息负载，它将在 MessageBox 中挂起。</span><span class="sxs-lookup"><span data-stu-id="d6083-157">If you do not have a send port to subscribe to the message payload, it will be suspended in the MessageBox.</span></span>  
  
- <span data-ttu-id="d6083-158">创建静态单向 FILE 发送端口 （带有直通发送管道） 以将 MDN 路由到本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="d6083-158">Create a static one-way FILE send port (with a passthrough send pipeline) to route the MDN to a local folder.</span></span> <span data-ttu-id="d6083-159">创建本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="d6083-159">Create the local folder.</span></span>  
  
- <span data-ttu-id="d6083-160">为 Fabrikam 和 Contoso 创建参与方 （贸易合作伙伴）。</span><span class="sxs-lookup"><span data-stu-id="d6083-160">Create a party (trading partner) for both Fabrikam and Contoso.</span></span>  
  
- <span data-ttu-id="d6083-161">为这两个贸易参与方创建业务配置文件每个。</span><span class="sxs-lookup"><span data-stu-id="d6083-161">Create a business profile each for both the trading parties.</span></span>  
  
- <span data-ttu-id="d6083-162">创建 AS2 协议的业务配置文件，Fabrikam 和 Contoso 之间。</span><span class="sxs-lookup"><span data-stu-id="d6083-162">Create an AS2 agreement between the business profiles for Fabrikam and Contoso.</span></span> <span data-ttu-id="d6083-163">AS2 协议中将包含要发送的 AS2 消息并接收返回同步 MDN 的属性。</span><span class="sxs-lookup"><span data-stu-id="d6083-163">The AS2 agreement would contain properties to send an AS2 message and receive a synchronous MDN in return.</span></span>  
  
- <span data-ttu-id="d6083-164">测试本演练使用 XML 测试消息。</span><span class="sxs-lookup"><span data-stu-id="d6083-164">Test the walkthrough using an XML test message.</span></span>  
  
### <a name="configuring-the-walkthrough"></a><span data-ttu-id="d6083-165">配置演练</span><span class="sxs-lookup"><span data-stu-id="d6083-165">Configuring the Walkthrough</span></span>  
 <span data-ttu-id="d6083-166">本部分介绍配置本演练的步骤。</span><span class="sxs-lookup"><span data-stu-id="d6083-166">This section describes the procedures to configure the walkthrough.</span></span>  
  
##### <a name="to-deploy-the-test-message-schema"></a><span data-ttu-id="d6083-167">若要部署的测试消息架构</span><span class="sxs-lookup"><span data-stu-id="d6083-167">To deploy the test message schema</span></span>  
  
1. <span data-ttu-id="d6083-168">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，创建或打开 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="d6083-168">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create or open a BizTalk project.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d6083-169">本主题假定你已从对 BizTalk EDI 应用程序，其中包含 EDI 架构、 管道和业务流程应用程序中添加了一个引用。</span><span class="sxs-lookup"><span data-stu-id="d6083-169">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="d6083-170">如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。</span><span class="sxs-lookup"><span data-stu-id="d6083-170">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
2. <span data-ttu-id="d6083-171">右键单击你的项目，指向**外**，然后单击**现有项**。</span><span class="sxs-lookup"><span data-stu-id="d6083-171">Right-click your project, point to **Add**, and then click **Existing Item**.</span></span> <span data-ttu-id="d6083-172">若要使用 XML 文件来测试你的解决方案，将移到本地文件夹包含 XSD 架构的 xml 测试消息，并选择 XSD 文件。</span><span class="sxs-lookup"><span data-stu-id="d6083-172">To use an XML file to test your solution, move to the local folder that contains the XSD schema for the XML test message, and select the XSD file.</span></span> <span data-ttu-id="d6083-173">单击 **“添加”** 。</span><span class="sxs-lookup"><span data-stu-id="d6083-173">Click **Add**.</span></span>  
  
3. <span data-ttu-id="d6083-174">设置程序集密钥文件，然后生成并部署该程序集。</span><span class="sxs-lookup"><span data-stu-id="d6083-174">Set the assembly key file, and then build and deploy the assembly.</span></span>  
  
##### <a name="to-enable-the-bts-isapi-filter"></a><span data-ttu-id="d6083-175">若要启用 BTS ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="d6083-175">To enable the BTS ISAPI Filter</span></span>  
  
1. <span data-ttu-id="d6083-176">单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="d6083-176">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
   > [!TIP]
   >  <span data-ttu-id="d6083-177">根据操作系统，管理工具启动菜单选项可能不可用。</span><span class="sxs-lookup"><span data-stu-id="d6083-177">Depending on the operating system, the Administrative Tools start menu option may not be available.</span></span> <span data-ttu-id="d6083-178">在这种情况下，单击**启动**，单击**运行**，然后输入`inetmgr`打开 Internet 信息服务 (IIS) 管理器。</span><span class="sxs-lookup"><span data-stu-id="d6083-178">In such cases, click **Start**, click **Run**, and enter `inetmgr` to open Internet Information Services (IIS) Manager.</span></span>  
  
2. <span data-ttu-id="d6083-179">选择根 Web 服务器条目并在**功能视图**，双击**处理程序映射**，然后在操作窗格中的单击**添加脚本映射**。</span><span class="sxs-lookup"><span data-stu-id="d6083-179">Select the root Web Server entry and in the **Features View**, double click **Handler Mappings** and then in the Actions pane click **Add Script Map**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d6083-180">在 Web 服务器级别配置的脚本映射将导致此映射应用于所有子网站。</span><span class="sxs-lookup"><span data-stu-id="d6083-180">Configuring the script mapping at the Web Server level will cause this mapping to apply to all child Web Sites.</span></span> <span data-ttu-id="d6083-181">如果你想要将映射限制到特定的网站或虚拟文件夹，选择文件夹而不是 Web 服务器的目标站点。</span><span class="sxs-lookup"><span data-stu-id="d6083-181">If you wish to restrict the mapping to a specific Web Site or Virtual Folder, select the target site or folder instead of the Web Server.</span></span>  
  
3. <span data-ttu-id="d6083-182">在中**添加脚本映射**对话框框中，输入`BtsHttpReceive.dll`中**请求路径**字段。</span><span class="sxs-lookup"><span data-stu-id="d6083-182">In the **Add Script Map** dialog box, enter `BtsHttpReceive.dll` in the **Request path** field.</span></span>  
  
4. <span data-ttu-id="d6083-183">在中**可执行文件**字段中，单击**省略号 （...）** 按钮并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive。</span><span class="sxs-lookup"><span data-stu-id="d6083-183">In the **Executable** field, click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive.</span></span> <span data-ttu-id="d6083-184">选择 BtsHttpReceive.dll，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d6083-184">Select BtsHttpReceive.dll and click **OK**.</span></span>  
  
5. <span data-ttu-id="d6083-185">输入`BizTalk HTTP Receive`中`Name`字段中，然后依次**请求限制**。</span><span class="sxs-lookup"><span data-stu-id="d6083-185">Enter `BizTalk HTTP Receive` in the `Name` field, and then click **Request Restrictions**.</span></span>  
  
6. <span data-ttu-id="d6083-186">在中**请求限制**对话框中，选择**谓词**选项卡，然后选择**以下谓词之一**。</span><span class="sxs-lookup"><span data-stu-id="d6083-186">In the **Request Restrictions** dialog box, select the **Verbs** tab and then select **One of the following verbs**.</span></span> <span data-ttu-id="d6083-187">输入`POST`作为谓词。</span><span class="sxs-lookup"><span data-stu-id="d6083-187">Enter `POST` as the verb.</span></span>  
  
7. <span data-ttu-id="d6083-188">上**访问**选项卡上，选择**脚本**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d6083-188">On the **Access** tab, select **Script** and then click **OK**.</span></span>  
  
8. <span data-ttu-id="d6083-189">单击**确定**并在提示是否允许 ISAPI 扩展，请单击**是**。</span><span class="sxs-lookup"><span data-stu-id="d6083-189">Click **OK** and when prompted to allow the ISAPI extension, click **Yes**.</span></span>  
  
##### <a name="to-configure-the-fabrikam-web-page"></a><span data-ttu-id="d6083-190">若要配置 Fabrikam 网页</span><span class="sxs-lookup"><span data-stu-id="d6083-190">To configure the Fabrikam Web page</span></span>  
  
1. <span data-ttu-id="d6083-191">在 IIS 管理器中，右键单击**应用程序池**，然后选择**添加应用程序池**。</span><span class="sxs-lookup"><span data-stu-id="d6083-191">In IIS Manager, right-click **Application Pools** and select **Add Application Pool**.</span></span>  
  
2. <span data-ttu-id="d6083-192">在中**添加应用程序池**对话框框中，输入**BizTalkAppPool**中**名称**，然后选择 **.NET Framework V4.0.30210**中 **.NET framework 版本**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="d6083-192">In **the Add Application Pool** dialog box, enter **BizTalkAppPool** in **Name**, and then select **.NET Framework V4.0.30210** in the **.NET Framework version** drop-down list.</span></span> <span data-ttu-id="d6083-193">单击“确定”  。</span><span class="sxs-lookup"><span data-stu-id="d6083-193">Click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d6083-194">版本号可能会有所不同，具体取决于版本的[!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]在计算机上安装。</span><span class="sxs-lookup"><span data-stu-id="d6083-194">The version number may vary depending on the version of [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] installed on the machine.</span></span>  
  
3. <span data-ttu-id="d6083-195">选择**应用程序池**，在**功能视图**选择**BizTalkAppPool**，然后单击**高级设置**中**操作**窗格。</span><span class="sxs-lookup"><span data-stu-id="d6083-195">Select **Application Pools**, in the **Features View** select **BizTalkAppPool**, and then click **Advanced Settings** in the **Actions** pane.</span></span>  
  
4. <span data-ttu-id="d6083-196">在中**高级设置**对话框中，选择**标识**，然后单击省略号 （...） 按钮。</span><span class="sxs-lookup"><span data-stu-id="d6083-196">In the **Advanced Settings** dialog box, select **Identity** and then click the ellipsis (…) button.</span></span>  
  
5. <span data-ttu-id="d6083-197">在中**应用程序池标识**对话框中，选择**自定义帐户**，然后单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="d6083-197">In the **Application Pool Identity** dialog box, select **Custom account** and then click **Set**.</span></span>  
  
6. <span data-ttu-id="d6083-198">输入**用户名**并**密码**是 administrators 组的成员的用户帐户，请输入中的密码**确认密码**，然后单击**确定**三次以返回到 IIS 管理器。</span><span class="sxs-lookup"><span data-stu-id="d6083-198">Enter the **User name** and **Password** for a user account that is a member of the administrators group, enter the password in **Confirm password** and then click **OK** three times to return to the IIS Manager.</span></span>  
  
7. <span data-ttu-id="d6083-199">在 IIS 管理器中，打开**站点**文件夹。</span><span class="sxs-lookup"><span data-stu-id="d6083-199">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="d6083-200">右键单击**Default Web Site**节点，并选择**添加应用程序**。</span><span class="sxs-lookup"><span data-stu-id="d6083-200">Right-click the **Default Web Site** node, and then select **Add Application**.</span></span>  
  
8. <span data-ttu-id="d6083-201">在中**添加应用程序**对话框框中，输入**Fabrikam**中**别名**，然后单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="d6083-201">In the **Add Application** dialog box, enter **Fabrikam** in **Alias**, and then click **Select**.</span></span>  
  
9. <span data-ttu-id="d6083-202">在中**选择应用程序池**对话框中，选择**BizTalkAppPool**然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d6083-202">In the **Select Application Pool** dialog box, select **BizTalkAppPool** and click **OK**.</span></span>  
  
10. <span data-ttu-id="d6083-203">单击省略号 （...） 按钮并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]httpreceive 作为**物理路径**。</span><span class="sxs-lookup"><span data-stu-id="d6083-203">Click the ellipsis (…) button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive for the **Physical path**.</span></span>  
  
11. <span data-ttu-id="d6083-204">单击**测试设置**并验证是否没有显示在错误**测试连接**对话框。</span><span class="sxs-lookup"><span data-stu-id="d6083-204">Click **Test Settings** and verify that there are no errors displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="d6083-205">单击 **“关闭”** ，然后单击 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="d6083-205">Click **Close**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="d6083-206">在 IIS 管理器中，选择 Fabrikam 虚拟目录并在**功能视图**，双击**身份验证**。</span><span class="sxs-lookup"><span data-stu-id="d6083-206">In IIS Manager, select the Fabrikam virtual directory and in the **Features View**, double-click **Authentication**.</span></span>  
  
13. <span data-ttu-id="d6083-207">在中**身份验证**页上，选择**匿名身份验证**，并验证**状态**是**已启用**。</span><span class="sxs-lookup"><span data-stu-id="d6083-207">In the **Authentication** page, select **Anonymous Authentication** and verify that the **Status** is **Enabled**.</span></span> <span data-ttu-id="d6083-208">如果**状态**是**禁用**，单击**启用**中**操作**窗格。</span><span class="sxs-lookup"><span data-stu-id="d6083-208">If the **Status** is **Disabled**, click **Enable** in the **Actions** pane.</span></span>  
  
##### <a name="to-specify-that-your-virtual-directory-is-not-managed-by-windows-sharepoint-services"></a><span data-ttu-id="d6083-209">若要指定虚拟目录不由 Windows SharePoint Services 托管</span><span class="sxs-lookup"><span data-stu-id="d6083-209">To specify that your virtual directory is not managed by Windows SharePoint Services</span></span>  
  
1.  <span data-ttu-id="d6083-210">如果您的计算机上安装 Windows SharePoint Services，请单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**SharePoint 3.0 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="d6083-210">If Windows SharePoint Services is installed on your computer, click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6083-211">如果您设置演练了在同一台计算机上安装 Windows SharePoint 服务器，则需要此过程。</span><span class="sxs-lookup"><span data-stu-id="d6083-211">This procedure is required if Windows SharePoint Server is installed on the same computer that you are setting the walkthrough up on.</span></span> <span data-ttu-id="d6083-212">在这种情况下，必须指定 IIS 虚拟目录未正在由 Windows SharePoint Server 托管。</span><span class="sxs-lookup"><span data-stu-id="d6083-212">In that case, you must specify that your IIS virtual directory is not being managed by Windows SharePoint Server.</span></span>  
  
2.  <span data-ttu-id="d6083-213">上**Central Administration**页面上，在**管理中心**，单击**应用程序管理**。</span><span class="sxs-lookup"><span data-stu-id="d6083-213">On the **Central Administration** page, under **Central Administration**, click **Application Management**.</span></span>  
  
3.  <span data-ttu-id="d6083-214">上**应用程序管理**页上，单击**定义管理路径**。</span><span class="sxs-lookup"><span data-stu-id="d6083-214">On the **Application Management** page, click **Define managed paths**.</span></span>  
  
4.  <span data-ttu-id="d6083-215">中**定义管理路径**页面上，在**添加新路径**，在**路径**文字框中，输入`Fabrikam`。</span><span class="sxs-lookup"><span data-stu-id="d6083-215">In the **Define Managed Paths** page, under **Add a New Path**, in the **Path** text box, enter `Fabrikam`.</span></span> <span data-ttu-id="d6083-216">下**类型**，单击**排除的路径**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d6083-216">Under **Type**, click **Excluded Path**, and then click **OK**.</span></span>  
  
##### <a name="to-create-a-receive-port-to-receive-the-test-message"></a><span data-ttu-id="d6083-217">若要创建用于接收测试消息的接收端口</span><span class="sxs-lookup"><span data-stu-id="d6083-217">To create a receive port to receive the test message</span></span>  
  
1. <span data-ttu-id="d6083-218">在 Windows 资源管理器中，创建一个用于从 Contoso 接收 EDI 交换本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="d6083-218">In Windows Explorer, create a local folder to receive the EDI interchange from Contoso.</span></span>  
  
2. <span data-ttu-id="d6083-219">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="d6083-219">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Receive Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
3. <span data-ttu-id="d6083-220">在中**接收端口属性**对话框的接收端口的名称作为**RecvXMLFromCont**。</span><span class="sxs-lookup"><span data-stu-id="d6083-220">In the **Receive Port Properties** dialog box, name the receive port as **RecvXMLFromCont**.</span></span>  
  
4. <span data-ttu-id="d6083-221">单击**接收位置**在控制台树中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="d6083-221">Click **Receive Locations** in the console tree, and then click **New**.</span></span>  
  
5. <span data-ttu-id="d6083-222">名称的接收位置，选择**文件**有关**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d6083-222">Name the receive location, select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
6. <span data-ttu-id="d6083-223">有关**接收文件夹**，输入在步骤 1 中创建的文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="d6083-223">For **Receive folder**, enter the name of the folder that you created in step 1.</span></span>  
  
7. <span data-ttu-id="d6083-224">在中**文件掩码**，输入 **\*.xml**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d6083-224">In **File mask**, enter **\*.xml**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="d6083-225">在接收管道中，选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="d6083-225">In Receive pipeline, select **XMLReceive**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d6083-226">如果在使用另一个非 EDI 之外的文件类型，XML 中，输入**PassThruTranmit**。</span><span class="sxs-lookup"><span data-stu-id="d6083-226">If you are using another non-EDI file type, other than XML, enter **PassThruTranmit**.</span></span>  
  
9. <span data-ttu-id="d6083-227">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="d6083-227">Click **OK**, and then click **OK** again.</span></span>  
  
10. <span data-ttu-id="d6083-228">单击**接收位置**节点，右键单击将接收位置，然后依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="d6083-228">Click the **Receive Locations** node, right-click your receive location, and then click **Enable**.</span></span>  
  
##### <a name="to-create-a-send-port-to-send-the-as2-message-to-fabrikam"></a><span data-ttu-id="d6083-229">若要创建用于将 AS2 消息发送到 Fabrikam 的发送端口</span><span class="sxs-lookup"><span data-stu-id="d6083-229">To create a send port to send the AS2 message to Fabrikam</span></span>  
  
1. <span data-ttu-id="d6083-230">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**静态要求响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="d6083-230">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d6083-231">如果使用 BizTalk Application 1，您必须添加引用 BizTalk Application 1 中对 BizTalk EDI 应用程序，因此，你的应用程序可以使用其项目。</span><span class="sxs-lookup"><span data-stu-id="d6083-231">If you use BizTalk Application 1, you must add a reference in BizTalk Application 1 to the BizTalk EDI Application, so your application can use its artifacts.</span></span> <span data-ttu-id="d6083-232">有关详细信息，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。</span><span class="sxs-lookup"><span data-stu-id="d6083-232">For more information, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
2. <span data-ttu-id="d6083-233">在中**发送端口属性**对话框中，发送端口的名称作为**SendToFab_RecvMDN**。</span><span class="sxs-lookup"><span data-stu-id="d6083-233">In the **Send Port Properties** dialog box, name the send port as **SendToFab_RecvMDN**.</span></span>  
  
3. <span data-ttu-id="d6083-234">在中**传输**部分中，选择**HTTP**有关**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d6083-234">In the **Transport** section, select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="d6083-235">在中**HTTP 传输属性**对话框中，对于**目标 URL**，输入 **http://localhost/Fabrikam/BTSHttpReceive.dll** 。</span><span class="sxs-lookup"><span data-stu-id="d6083-235">In the **HTTP Transport Properties** dialog box, for **Destination URL**, enter **http://localhost/Fabrikam/BTSHttpReceive.dll**.</span></span>  
  
5. <span data-ttu-id="d6083-236">清除**启用 chunked 编码**。</span><span class="sxs-lookup"><span data-stu-id="d6083-236">Clear **Enable chunked encoding**.</span></span> <span data-ttu-id="d6083-237">单击“确定”  。</span><span class="sxs-lookup"><span data-stu-id="d6083-237">Click **OK**.</span></span>  
  
6. <span data-ttu-id="d6083-238">有关**发送管道**，选择**AS2Send**。</span><span class="sxs-lookup"><span data-stu-id="d6083-238">For **Send pipeline**, select **AS2Send**.</span></span>  
  
7. <span data-ttu-id="d6083-239">有关**接收管道**，选择**AS2Receive**。</span><span class="sxs-lookup"><span data-stu-id="d6083-239">For **Receive pipeline**, select **AS2Receive**.</span></span>  
  
8. <span data-ttu-id="d6083-240">在控制台树中，选择**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="d6083-240">In the console tree, select **Filters**.</span></span> <span data-ttu-id="d6083-241">有关**属性**，输入**BTS。ReceivePortName**; 对于**运算符**，输入 **==** ; 对于**值**输入将接收 EDI 的接收端口的名称交换 (`RecvXMLFromCont`)。</span><span class="sxs-lookup"><span data-stu-id="d6083-241">For **Property**, enter **BTS.ReceivePortName**; for **Operator**, enter **==**; and for **Value** enter the name of the receive port that will receive the EDI interchange (`RecvXMLFromCont`).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d6083-242">如果要发送 PIDX 消息，则可以创建筛选器的筛选器表达式上的消息类型 (**PIDX**)。</span><span class="sxs-lookup"><span data-stu-id="d6083-242">If you are sending a PIDX message, you can create a filter expression that filters on the type of the message (**PIDX**).</span></span>  
  
9. <span data-ttu-id="d6083-243">如果你想要应用映射以转换 XML 文档中，单击**出站映射**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="d6083-243">If you want to apply a map to transform the XML document, click **Outbound Maps** in the console tree.</span></span> <span data-ttu-id="d6083-244">输入**源文档**出站映射中，选择**地图**，然后输入**目标文档**。</span><span class="sxs-lookup"><span data-stu-id="d6083-244">Enter the **Source Document** for the outbound map, select the **Map**, and then enter the **Target Document**.</span></span> <span data-ttu-id="d6083-245">单击“确定”  。</span><span class="sxs-lookup"><span data-stu-id="d6083-245">Click **OK**.</span></span>  
  
10. <span data-ttu-id="d6083-246">单击“确定”  。</span><span class="sxs-lookup"><span data-stu-id="d6083-246">Click **OK**.</span></span>  
  
11. <span data-ttu-id="d6083-247">单击**发送端口**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击您的发送端口，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="d6083-247">Click the **Send Ports** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-receive-port-to-receive-the-as2-message-and-return-an-acknowledgment"></a><span data-ttu-id="d6083-248">若要创建用于接收 AS2 消息并返回确认的接收端口</span><span class="sxs-lookup"><span data-stu-id="d6083-248">To create a receive port to receive the AS2 message and return an acknowledgment</span></span>  
  
1. <span data-ttu-id="d6083-249">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在**BizTalk Application 1**节点，右键单击**接收端口**，指向**新建**，然后单击**请求响应接收端口**。</span><span class="sxs-lookup"><span data-stu-id="d6083-249">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **BizTalk Application 1** node, right-click **Receive Ports**, point to **New**, and then click **Request Response Receive Port**.</span></span>  
  
2. <span data-ttu-id="d6083-250">为接收端口的名称**RecvAS2Msg**，然后单击**接收位置**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="d6083-250">Name the receive port as **RecvAS2Msg**, and then click **Receive Locations** in the console tree.</span></span>  
  
3. <span data-ttu-id="d6083-251">单击 **“新建”** 。</span><span class="sxs-lookup"><span data-stu-id="d6083-251">Click **New**.</span></span>  
  
4. <span data-ttu-id="d6083-252">在**接收位置属性**对话框中，名称在接收位置中，选择**HTTP**有关**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d6083-252">In the **Receive Location Properties** dialog box, name your receive location, select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="d6083-253">在中**HTTP 传输属性**对话框框中，输入 **/Fabrikam/BTSHttpReceive.dll**有关**虚拟目录和 ISAPI 扩展**。</span><span class="sxs-lookup"><span data-stu-id="d6083-253">In the **HTTP Transport Properties** dialog box, enter **/Fabrikam/BTSHttpReceive.dll** for **Virtual directory plus ISAPI extension**.</span></span> <span data-ttu-id="d6083-254">清除**成功后的返回相关句柄**，然后选择**挂起失败的请求**。</span><span class="sxs-lookup"><span data-stu-id="d6083-254">Clear **Return correlation handle on success** and select **Suspend failed requests**.</span></span> <span data-ttu-id="d6083-255">单击“确定”  。</span><span class="sxs-lookup"><span data-stu-id="d6083-255">Click **OK**.</span></span>  
  
6. <span data-ttu-id="d6083-256">选择**AS2Receive**有关**接收管道**，并**AS2Send**有关**发送管道**。</span><span class="sxs-lookup"><span data-stu-id="d6083-256">Select **AS2Receive** for the **Receive Pipeline**, and **AS2Send** for the **Send Pipeline**.</span></span> <span data-ttu-id="d6083-257">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="d6083-257">Click **OK**, and then click **OK** again.</span></span>  
  
7. <span data-ttu-id="d6083-258">单击**接收位置**节点，右键单击将接收位置，然后依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="d6083-258">Click the **Receive Locations** node, right-click your receive location, and then click **Enable**.</span></span>  
  
##### <a name="to-create-a-send-port-to-send-the-test-xml-payload-to-a-local-folder"></a><span data-ttu-id="d6083-259">若要创建用于将测试 XML 负载发送到本地文件夹的发送端口</span><span class="sxs-lookup"><span data-stu-id="d6083-259">To create a send port to send the test XML payload to a local folder</span></span>  
  
1. <span data-ttu-id="d6083-260">在 Windows 资源管理器中，创建一个用于接收 EDI 交换的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="d6083-260">In Windows Explorer, create a local folder to send the EDI interchange to.</span></span>  
  
2. <span data-ttu-id="d6083-261">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="d6083-261">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
3. <span data-ttu-id="d6083-262">在中**发送端口属性**对话框，为发送端口的名称**SendXMLPayload**。</span><span class="sxs-lookup"><span data-stu-id="d6083-262">In the **Send Port Properties** dialog box, name your send port as **SendXMLPayload**.</span></span> <span data-ttu-id="d6083-263">选择**文件**有关**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d6083-263">Select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="d6083-264">在中**FILE 传输属性**对话框中，对于**目标文件夹**，输入为 EDI 负载创建的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="d6083-264">In the **FILE Transport Properties** dialog box, for **Destination folder**, enter the local folder that you created for the EDI payload.</span></span>  
  
5. <span data-ttu-id="d6083-265">有关**文件名**，输入文件名称。</span><span class="sxs-lookup"><span data-stu-id="d6083-265">For **File name**, enter the file name.</span></span> <span data-ttu-id="d6083-266">如果使用的 XML 文件作为测试消息，请输入 **%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="d6083-266">If you are using an XML file as your test message, enter **%MessageID%.xml**.</span></span> <span data-ttu-id="d6083-267">单击“确定”  。</span><span class="sxs-lookup"><span data-stu-id="d6083-267">Click **OK**.</span></span>  
  
6. <span data-ttu-id="d6083-268">接受默认值为**PassThruTransmit**有关**发送管道**。</span><span class="sxs-lookup"><span data-stu-id="d6083-268">Accept the default of **PassThruTransmit** for **Send Pipeline**.</span></span>  
  
7. <span data-ttu-id="d6083-269">单击**筛选器**在控制台树，并添加用于提取 EDI 负载的筛选器属性。</span><span class="sxs-lookup"><span data-stu-id="d6083-269">Click **Filters** in the console tree, and add filter properties for picking up the EDI payload.</span></span> <span data-ttu-id="d6083-270">在第一行，对于**属性**，输入**BTS。ReceivePortName**; 对于**运算符**，输入 **==** ; 对于**值**，输入接收 AS2 的接收端口的名称消息 (`RecvAS2Msg`); 对于**分组依据**，接受**和**。</span><span class="sxs-lookup"><span data-stu-id="d6083-270">On the first line, for **Property**, enter **BTS.ReceivePortName**; for **Operator**, enter **==**; for **Value**, enter the name of the receive port that receives the AS2 message (`RecvAS2Msg`); and for **Group by**, accept **And**.</span></span> <span data-ttu-id="d6083-271">在第二行，对于**属性**，输入**EdiIntAS.IsAS2PayloadMessage**; 对于**运算符**，输入 **==** ; 以及**值**，输入**True**。</span><span class="sxs-lookup"><span data-stu-id="d6083-271">On the second line, for **Property**, enter **EdiIntAS.IsAS2PayloadMessage**; for **Operator**, enter **==**; and for **Value**, enter **True**.</span></span>  
  
8. <span data-ttu-id="d6083-272">单击“确定”  。</span><span class="sxs-lookup"><span data-stu-id="d6083-272">Click **OK**.</span></span>  
  
9. <span data-ttu-id="d6083-273">单击**发送端口**节点，右键单击您的发送端口，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="d6083-273">Click the **Send Ports** node, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-send-port-to-send-the-mdn-to-a-local-folder"></a><span data-ttu-id="d6083-274">若要创建的发送端口将 MDN 发送到本地文件夹</span><span class="sxs-lookup"><span data-stu-id="d6083-274">To create a send port to send the MDN to a local folder</span></span>  
  
1. <span data-ttu-id="d6083-275">在 Windows 资源管理器中，创建一个用于接收 MDN 的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="d6083-275">In Windows Explorer, create a local folder to send the MDN to.</span></span>  
  
2. <span data-ttu-id="d6083-276">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="d6083-276">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
3. <span data-ttu-id="d6083-277">在中**发送端口属性**对话框，为发送端口的名称**SendMDNToContoso**。</span><span class="sxs-lookup"><span data-stu-id="d6083-277">In the **Send Port Properties** dialog box, name your send port as **SendMDNToContoso**.</span></span> <span data-ttu-id="d6083-278">选择**文件**有关**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d6083-278">Select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="d6083-279">在中**FILE 传输属性**对话框中，对于**目标文件夹**，输入您创建的用于接收 MDN 的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="d6083-279">In the **FILE Transport Properties** dialog box, for **Destination folder**, enter the local folder you created to send the MDN to.</span></span>  
  
5. <span data-ttu-id="d6083-280">有关**文件名**，输入 **%MessageID%.msg**。单击“确定”  。</span><span class="sxs-lookup"><span data-stu-id="d6083-280">For **File name**, enter **%MessageID%.msg**. Click **OK**.</span></span>  
  
6. <span data-ttu-id="d6083-281">接受默认值为**PassThruTransmit**有关**发送管道**。</span><span class="sxs-lookup"><span data-stu-id="d6083-281">Accept the default of **PassThruTransmit** for **Send Pipeline**.</span></span>  
  
7. <span data-ttu-id="d6083-282">单击**筛选器**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="d6083-282">Click **Filters** in the console tree.</span></span> <span data-ttu-id="d6083-283">有关**属性**，输入**BTS。SPName**; 对于**运算符**，输入 **==** ; 对于**值**，输入将发送 AS2 消息的发送端口的名称 (`SendToFab_RecvMDN`);对于**分组依据**，接受**和**。</span><span class="sxs-lookup"><span data-stu-id="d6083-283">For **Property**, enter **BTS.SPName**; for **Operator**, enter **==**; for **Value**, enter the name of the send port that sends the AS2 message (`SendToFab_RecvMDN`); and for **Group by**, accept **And**.</span></span> <span data-ttu-id="d6083-284">在第二个行中，对于**属性**，输入**EdiIntAS.IsAS2MdnResponseMessage**。</span><span class="sxs-lookup"><span data-stu-id="d6083-284">On a second line, for **Property**, enter **EdiIntAS.IsAS2MdnResponseMessage**.</span></span> <span data-ttu-id="d6083-285">有关**运算符**，输入 **==** 。</span><span class="sxs-lookup"><span data-stu-id="d6083-285">For **Operator**, enter **==**.</span></span> <span data-ttu-id="d6083-286">有关**值**，输入**True**。</span><span class="sxs-lookup"><span data-stu-id="d6083-286">For **Value**, enter **True**.</span></span>  
  
8. <span data-ttu-id="d6083-287">单击“确定”  。</span><span class="sxs-lookup"><span data-stu-id="d6083-287">Click **OK**.</span></span>  
  
9. <span data-ttu-id="d6083-288">单击**发送端口**节点，右键单击您的发送端口，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="d6083-288">Click the **Send Ports** node, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a><span data-ttu-id="d6083-289">创建 Fabrikam 参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="d6083-289">To create a party and a business profile for Fabrikam</span></span>  
  
1. <span data-ttu-id="d6083-290">右键单击**参与方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="d6083-290">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2. <span data-ttu-id="d6083-291">输入中的参与方的名称**名称**文本框中，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d6083-291">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d6083-292">通过选择**本地 BizTalk 处理接收的来自此参与方发送消息的参与方或支持消息**复选框，可以指定要创建的参与方是为同一组织与托管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6083-292">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d6083-293">此基础，某些属性将启用，或禁用在创建协议时。</span><span class="sxs-lookup"><span data-stu-id="d6083-293">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="d6083-294">但是，对于此演练中，可以选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="d6083-294">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3. <span data-ttu-id="d6083-295">右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="d6083-295">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4. <span data-ttu-id="d6083-296">在中**配置文件属性**对话框中，在**常规**页上，输入**Fabrikam_Profile**中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="d6083-296">In the **Profile Properties** dialog box, on the **General** page, enter **Fabrikam_Profile** in the **Name** text box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d6083-297">创建一个参与方时，还创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="d6083-297">When you create a party, a profile is also created.</span></span> <span data-ttu-id="d6083-298">可以重命名，并使用该配置文件而不是创建一个新。</span><span class="sxs-lookup"><span data-stu-id="d6083-298">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="d6083-299">若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="d6083-299">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="d6083-300">在中**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d6083-300">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a><span data-ttu-id="d6083-301">为 Contoso 创建参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="d6083-301">To create a party and a business profile for Contoso</span></span>  
  
1. <span data-ttu-id="d6083-302">右键单击**参与方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="d6083-302">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2. <span data-ttu-id="d6083-303">输入中的参与方的名称**名称**文本框中，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d6083-303">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d6083-304">通过选择**本地 BizTalk 处理接收的来自此参与方发送消息的参与方或支持消息**复选框，可以指定要创建的参与方是为同一组织与托管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6083-304">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d6083-305">此基础，某些属性将启用，或禁用在创建协议时。</span><span class="sxs-lookup"><span data-stu-id="d6083-305">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="d6083-306">但是，对于此演练中，可以选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="d6083-306">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3. <span data-ttu-id="d6083-307">右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="d6083-307">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4. <span data-ttu-id="d6083-308">在中**配置文件属性**对话框中，在**常规**页上，输入**Contoso_Profile**中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="d6083-308">In the **Profile Properties** dialog box, on the **General** page, enter **Contoso_Profile** in the **Name** text box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d6083-309">创建一个参与方时，还创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="d6083-309">When you create a party, a profile is also created.</span></span> <span data-ttu-id="d6083-310">可以重命名，并使用该配置文件而不是创建一个新。</span><span class="sxs-lookup"><span data-stu-id="d6083-310">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="d6083-311">若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="d6083-311">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="d6083-312">在中**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d6083-312">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-an-as2-agreement-between-the-two-business-profiles"></a><span data-ttu-id="d6083-313">若要创建两个业务配置文件之间的 AS2 协议</span><span class="sxs-lookup"><span data-stu-id="d6083-313">To create an AS2 agreement between the two business profiles</span></span>  
  
1.  <span data-ttu-id="d6083-314">右键单击**Contoso_Profile**，依次指向**新建**，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="d6083-314">Right-click **Contoso_Profile**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="d6083-315">在**常规属性**页上，对于**名称**文字框中，输入协议的名称。</span><span class="sxs-lookup"><span data-stu-id="d6083-315">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  
  
3.  <span data-ttu-id="d6083-316">从**协议**下拉列表中，选择**AS2**。</span><span class="sxs-lookup"><span data-stu-id="d6083-316">From the **Protocol** drop-down list, select **AS2**.</span></span>  
  
4.  <span data-ttu-id="d6083-317">在中**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**Fabrikam**。</span><span class="sxs-lookup"><span data-stu-id="d6083-317">In the **Second Partner** section, from the **Name** drop-down list, select **Fabrikam**.</span></span>  
  
5.  <span data-ttu-id="d6083-318">在中**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**Fabrikam_Profile**。</span><span class="sxs-lookup"><span data-stu-id="d6083-318">In the **Second Partner** section, from the **Profile** drop-down list, select **Fabrikam_Profile**.</span></span>  
  
     <span data-ttu-id="d6083-319">你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡是用于配置一个单向 AS2 协议。</span><span class="sxs-lookup"><span data-stu-id="d6083-319">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way AS2 agreement.</span></span>  
  
6.  <span data-ttu-id="d6083-320">在执行以下任务**Contoso-> Fabrikam**选项卡。</span><span class="sxs-lookup"><span data-stu-id="d6083-320">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  
  
    1.  <span data-ttu-id="d6083-321">上**标识符**页上，输入值**AS2-从**并**AS2-到**。</span><span class="sxs-lookup"><span data-stu-id="d6083-321">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="d6083-322">有关**AS2-从**，输入`Contoso`。</span><span class="sxs-lookup"><span data-stu-id="d6083-322">For **AS2-From**, enter `Contoso`.</span></span> <span data-ttu-id="d6083-323">有关**AS2-To**，输入`Fabrikam`。</span><span class="sxs-lookup"><span data-stu-id="d6083-323">For **AS2- To**, enter `Fabrikam`.</span></span>  
  
    2.  <span data-ttu-id="d6083-324">在中**确认 (Mdn)** 页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d6083-324">In the **Acknowledgements (MDNs)** page, do the following:</span></span>  
  
        1.  <span data-ttu-id="d6083-325">选择**到 MessageBox 中处理入站的 MDN 以进行路由/传递**复选框。</span><span class="sxs-lookup"><span data-stu-id="d6083-325">Select the **Process inbound MDN into MessageBox for routing/delivery options** check box.</span></span>  
  
            > [!NOTE]
            >  <span data-ttu-id="d6083-326">检查**到 MessageBox 中处理入站的 MDN 以进行路由/传递**需要本演练中，测试，因为只有这样将返回的 MDN 才能放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="d6083-326">Checking the **Process inbound MDN into MessageBox for routing/delivery options** is required for the testing of this walkthrough, because only then will the returned MDN be dropped into the MessageBox.</span></span> <span data-ttu-id="d6083-327">这样，您可以创建一个发送端口订阅的 MDN，并将 MDN 发送到本地目录，以便可以验证 AS2 传输。</span><span class="sxs-lookup"><span data-stu-id="d6083-327">That enables you to create a send port to subscribe to the MDN, and to send the MDN to a local directory, so you can verify the AS2 transmission.</span></span>  
  
        2.  <span data-ttu-id="d6083-328">选择**请求 MDN**复选框。</span><span class="sxs-lookup"><span data-stu-id="d6083-328">Select the **Request MDN** check box.</span></span>  
  
        3.  <span data-ttu-id="d6083-329">请确保**请求经过签名的 MDN**清除复选框。</span><span class="sxs-lookup"><span data-stu-id="d6083-329">Make sure the **Request Signed MDN** check box is cleared.</span></span>  
  
        4.  <span data-ttu-id="d6083-330">将保留**请求异步 MDN**清除。</span><span class="sxs-lookup"><span data-stu-id="d6083-330">Leave **Request asynchronous MDN** cleared.</span></span>  
  
        5.  <span data-ttu-id="d6083-331">在中**处置-到通知**，输入任何值。</span><span class="sxs-lookup"><span data-stu-id="d6083-331">In **Disposition-Notification-To**, enter any value.</span></span> <span data-ttu-id="d6083-332">此字段的值不是在 AS2 处理过程中使用，但必须在字段中输入值。</span><span class="sxs-lookup"><span data-stu-id="d6083-332">The value of this field is not used during AS2 processing, but a value must be entered in the field.</span></span>  
  
    3.  <span data-ttu-id="d6083-333">上**发送端口**页上，将会将 EDI 交换发送到 Fabrikam 的双向发送端口相关联。</span><span class="sxs-lookup"><span data-stu-id="d6083-333">On the **Send Ports** page, associate the two-way send port that will be sending the EDI interchange to Fabrikam.</span></span> <span data-ttu-id="d6083-334">在中**发送端口**网格下**名称**列中，单击空单元格，并从下拉列表中，选择发送端口**SendToFab_RecvMDN**。</span><span class="sxs-lookup"><span data-stu-id="d6083-334">In the **Send ports** grid, under the **Name** column, click an empty cell, and from the drop-down list, select the send port **SendToFab_RecvMDN**.</span></span>  
  
7.  <span data-ttu-id="d6083-335">在执行以下任务**Fabrikam-> Contoso**选项卡。</span><span class="sxs-lookup"><span data-stu-id="d6083-335">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6083-336">在本演练中，我们指定的选项卡中所需的值，以便可以成功创建协议。</span><span class="sxs-lookup"><span data-stu-id="d6083-336">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="d6083-337">若要成功创建协议，两个单向协议选项卡必须具有定义为值**AS2_From**并**AS2-到**。</span><span class="sxs-lookup"><span data-stu-id="d6083-337">To successfully create an agreement, both one-way agreement tabs must have values defined for **AS2_From** and **AS2-To**.</span></span>  
  
    1.  <span data-ttu-id="d6083-338">上**标识符**页上，输入值**AS2-从**并**AS2-到**。</span><span class="sxs-lookup"><span data-stu-id="d6083-338">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="d6083-339">有关**AS2-从**，输入`Fabrikam`。</span><span class="sxs-lookup"><span data-stu-id="d6083-339">For **AS2-From**, enter `Fabrikam`.</span></span> <span data-ttu-id="d6083-340">有关**AS2-To**，输入`Contoso`。</span><span class="sxs-lookup"><span data-stu-id="d6083-340">For **AS2- To**, enter `Contoso`.</span></span>  
  
8.  <span data-ttu-id="d6083-341">单击 **“应用”** 。</span><span class="sxs-lookup"><span data-stu-id="d6083-341">Click **Apply**.</span></span>  
  
9. <span data-ttu-id="d6083-342">单击“确定”  。</span><span class="sxs-lookup"><span data-stu-id="d6083-342">Click **OK**.</span></span> <span data-ttu-id="d6083-343">中列出新添加的协议**协议**一部分**参与方和业务配置文件**窗格。</span><span class="sxs-lookup"><span data-stu-id="d6083-343">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="d6083-344">默认情况下启用新添加的协议。</span><span class="sxs-lookup"><span data-stu-id="d6083-344">The newly added agreement is enabled by default.</span></span>  
  
### <a name="testing-the-walkthrough"></a><span data-ttu-id="d6083-345">测试演练</span><span class="sxs-lookup"><span data-stu-id="d6083-345">Testing the Walkthrough</span></span>  
 <span data-ttu-id="d6083-346">本部分提供有关如何测试演练的信息。</span><span class="sxs-lookup"><span data-stu-id="d6083-346">This section provides information on how to test the walkthrough.</span></span>  
  
##### <a name="to-test-the-solution"></a><span data-ttu-id="d6083-347">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="d6083-347">To test the solution</span></span>  
  
1.  <span data-ttu-id="d6083-348">在 Windows 资源管理器，将 XML 测试文件粘贴到您创建的用于从 Contoso 接收测试消息的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="d6083-348">In Windows Explorer, paste your XML test file into the local folder that you created to receive the test message from Contoso.</span></span>  
  
2.  <span data-ttu-id="d6083-349">转到您创建的用于接收 XML 负载的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="d6083-349">Move to the local folder that you created to send the XML payload to.</span></span> <span data-ttu-id="d6083-350">确认该文件夹包含一个 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d6083-350">Confirm that the folder contains an XML file.</span></span> <span data-ttu-id="d6083-351">打开的文件和原始测试消息，并验证它们具有相同的内容。</span><span class="sxs-lookup"><span data-stu-id="d6083-351">Open the file and the original test message, and verify that they have the same content.</span></span>  
  
3.  <span data-ttu-id="d6083-352">转到你创建的用于接收生成的 MDN 的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="d6083-352">Move to the local folder that you created to send the resulting MDN to.</span></span> <span data-ttu-id="d6083-353">确认该文件夹包含一个文件;打开文件并确认它是一个 MDN 文件。</span><span class="sxs-lookup"><span data-stu-id="d6083-353">Confirm that the folder contains a file; open the file and confirm that it is an MDN file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6083-354">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6083-354">See Also</span></span>  
 <span data-ttu-id="d6083-355">[开发和配置 BizTalk Server AS2 解决方案](../core/developing-and-configuring-biztalk-server-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="d6083-355">[Developing and Configuring BizTalk Server AS2 Solutions](../core/developing-and-configuring-biztalk-server-as2-solutions.md) </span></span>  
 [<span data-ttu-id="d6083-356">通过 AS2 传出的非 EDI 消息的发送方处理</span><span class="sxs-lookup"><span data-stu-id="d6083-356">Send-Side Processing of an Outgoing Non-EDI Message over AS2</span></span>](../core/send-side-processing-of-an-outgoing-non-edi-message-over-as2.md)