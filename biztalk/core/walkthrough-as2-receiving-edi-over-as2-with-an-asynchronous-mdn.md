---
title: '演练 (AS2): 使用异步 MDN 通过 AS2 接收 EDI |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac3962e4-0525-4194-8cf1-b90664f1a139
caps.latest.revision: 40
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59fdb22b08a1855f1ba4d9cc433acb288132283a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003862"
---
# <a name="walkthrough-as2-receiving-edi-over-as2-with-an-asynchronous-mdn"></a><span data-ttu-id="99bf8-102">演练 (AS2)：使用异步 MDN 通过 AS2 接收 EDI</span><span class="sxs-lookup"><span data-stu-id="99bf8-102">Walkthrough (AS2): Receiving EDI over AS2 with an Asynchronous MDN</span></span>
<span data-ttu-id="99bf8-103">本演练将介绍创建一个通过 AS2 传输方法接收 EDI 消息并返回异步 MDN 的解决方案的分步操作过程。</span><span class="sxs-lookup"><span data-stu-id="99bf8-103">This walkthrough provides a set of step-by-step procedures that creates a solution for receiving EDI messages over AS2 transport, returning synchronous MDNs.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="99bf8-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="99bf8-104">Prerequisites</span></span>  
 <span data-ttu-id="99bf8-105">以下为执行本主题中的过程的前提条件：</span><span class="sxs-lookup"><span data-stu-id="99bf8-105">The following are prerequisites for performing the procedure in this topic:</span></span>  

- <span data-ttu-id="99bf8-106">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="99bf8-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  

- <span data-ttu-id="99bf8-107">运行演练的计算机必须安装了 Internet 信息服务 (IIS)。</span><span class="sxs-lookup"><span data-stu-id="99bf8-107">The computer that runs the walkthrough must have Internet Information Services (IIS) 7 installed.</span></span>  

- <span data-ttu-id="99bf8-108">如果运行此演练的计算机安装了 64 位版本的 Windows，则您必须确保 BizTalk 主机标记只能为 32 位。</span><span class="sxs-lookup"><span data-stu-id="99bf8-108">If the computer that runs the walkthrough is installed with a 64-bit version of Windows, you must ensure that the BizTalk hosts are marked as 32-bit only.</span></span> <span data-ttu-id="99bf8-109">您还必须确保 IIS 已将“为应用程序池启用 32 位应用程序设置”设置为 True。 </span><span class="sxs-lookup"><span data-stu-id="99bf8-109">You must also ensure IIS has the Enable 32-Bit Application Setting for the Application Pools set to True.</span></span> <span data-ttu-id="99bf8-110">有关详细信息，请参阅[教程 3: AS2 教程](../core/tutorial-3-as2-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="99bf8-110">For more information, see [Tutorial 3: AS2 Tutorial](../core/tutorial-3-as2-tutorial.md).</span></span>  

## <a name="how-the-solution-receives-an-edi-interchange-and-returns-an-asynchronous-mdn"></a><span data-ttu-id="99bf8-111">解决方案如何接收 EDI 交换并返回异步 MDN</span><span class="sxs-lookup"><span data-stu-id="99bf8-111">How the Solution Receives an EDI Interchange and Returns an Asynchronous MDN</span></span>  
 <span data-ttu-id="99bf8-112">该解决方案将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="99bf8-112">The solution will do the following:</span></span>  

1. <span data-ttu-id="99bf8-113">从贸易合作伙伴通过 HTTP 接收包含有 EDI 交换的 AS2 消息，并对来自 EDIINT/AS2 的交换进行解码。</span><span class="sxs-lookup"><span data-stu-id="99bf8-113">Receive an AS2 message containing an EDI interchange over HTTP from the trading partner, and decode the interchange from EDIINT/AS2.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="99bf8-114">此列表中的事件可能不会按所示顺序发生。</span><span class="sxs-lookup"><span data-stu-id="99bf8-114">The events in this list may not occur in the order shown.</span></span>  

2. <span data-ttu-id="99bf8-115">生成 MDN 响应，并将其放置到 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="99bf8-115">Generate an MDN response, and drop it in the MessageBox.</span></span>  

3. <span data-ttu-id="99bf8-116">通过动态发送端口提取消息 MDN。</span><span class="sxs-lookup"><span data-stu-id="99bf8-116">Pick up the message MDN by a dynamic send port.</span></span>  

4. <span data-ttu-id="99bf8-117">将异步消息 MDN 返回到贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="99bf8-117">Return the asynchronous message MDN to the trading partner.</span></span>  

5. <span data-ttu-id="99bf8-118">将 EDI 格式的交换转换为内部 XML 格式，并将其放在 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="99bf8-118">Convert the EDI format of the interchange to internal XML format, and drop it in the MessageBox.</span></span>  

6. <span data-ttu-id="99bf8-119">具有 PassThruTransmit 管道的发送端口将从 MessageBox 提取消息 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="99bf8-119">A send port with a PassThruTransmit pipeline picks up the message XML file from the MessageBox.</span></span>  

7. <span data-ttu-id="99bf8-120">该发送端口将 EDI 交换 XML 文件发送到 Contoso 参与方的某一文件夹。</span><span class="sxs-lookup"><span data-stu-id="99bf8-120">The send port sends EDI interchange XML file to a folder at the Contoso party.</span></span>  

   <span data-ttu-id="99bf8-121">下图显示出此解决方案的结构。</span><span class="sxs-lookup"><span data-stu-id="99bf8-121">The following figure shows the architecture for this solution.</span></span>  

   <span data-ttu-id="99bf8-122">![使用异步 MDN 的 AS2 接收](../core/media/bts-configuring-the-receiving-of-edi-over-as2-with-an-asynchronous-mdnc.gif "bts_Configuring_the_Receiving_of_EDI_Over_AS2_with_an_Asynchronous_MDNc")</span><span class="sxs-lookup"><span data-stu-id="99bf8-122">![AS2 receiving with an asynchronous MDN](../core/media/bts-configuring-the-receiving-of-edi-over-as2-with-an-asynchronous-mdnc.gif "bts_Configuring_the_Receiving_of_EDI_Over_AS2_with_an_Asynchronous_MDNc")</span></span>  

## <a name="the-functionality-in-this-solution"></a><span data-ttu-id="99bf8-123">此解决方案中的功能</span><span class="sxs-lookup"><span data-stu-id="99bf8-123">The Functionality in this Solution</span></span>  
 <span data-ttu-id="99bf8-124">本演练的功能具有以下特点：</span><span class="sxs-lookup"><span data-stu-id="99bf8-124">The following applies to the functionality of this walkthrough:</span></span>  

-   <span data-ttu-id="99bf8-125">不会生成 EDI 确认。</span><span class="sxs-lookup"><span data-stu-id="99bf8-125">An EDI acknowledgment is not generated.</span></span> <span data-ttu-id="99bf8-126">生成 EDI 确认进行了演示[演练 (X12)： 接收 EDI 交换并发送回确认信息](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)。</span><span class="sxs-lookup"><span data-stu-id="99bf8-126">Generating an EDI acknowledgment is demonstrated in [Walkthrough (X12): Receiving EDI Interchanges and Sending Back an Acknowledgement](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md).</span></span> <span data-ttu-id="99bf8-127">通过 AS2 传输发送 EDI 确认中所述[演练 (AS2): 使用异步 MDN 通过 AS2 发送 EDI](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md)。</span><span class="sxs-lookup"><span data-stu-id="99bf8-127">Sending an EDI acknowledgment over AS2 transport is described in [Walkthrough (AS2): Sending EDI over AS2 with an Asynchronous MDN](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md).</span></span>  

-   <span data-ttu-id="99bf8-128">该解决方案专用于使用 X12 编码而不是 EDIFACT 编码的交换。</span><span class="sxs-lookup"><span data-stu-id="99bf8-128">The solution is designed for interchanges using X12 encoding, not EDIFACT encoding.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="99bf8-129">用于 EDIFACT 编码的配置与用于 X12 编码的配置几近相同。</span><span class="sxs-lookup"><span data-stu-id="99bf8-129">The configuration used for EDIFACT encoding is closely parallel to that used for X12 encoding.</span></span>  

-   <span data-ttu-id="99bf8-130">EDI 类型和扩展的验证将在传入交换上执行。</span><span class="sxs-lookup"><span data-stu-id="99bf8-130">EDI type and extended validation will be performed on the incoming interchange.</span></span>  

-   <span data-ttu-id="99bf8-131">系统将启用 AS2 和 EDI 报告功能，并保存事务集以从交换状态报告进行查看。</span><span class="sxs-lookup"><span data-stu-id="99bf8-131">AS2 and EDI reporting will be enabled, and transaction sets will be saved for viewing from the interchange status report.</span></span>  

-   <span data-ttu-id="99bf8-132">此解决方案不在不可否认数据库中配置签名、压缩、加密或消息存储。</span><span class="sxs-lookup"><span data-stu-id="99bf8-132">This solution does not configure signing, compression, encryption, or message storage in the non-repudiation database.</span></span> <span data-ttu-id="99bf8-133">有关配置这些属性的过程，请参阅[配置 AS2 属性](../core/configuring-as2-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="99bf8-133">For procedures on configuring those properties, see [Configuring AS2 Properties](../core/configuring-as2-properties.md).</span></span>  

## <a name="configuring-and-testing-the-walkthrough"></a><span data-ttu-id="99bf8-134">配置和测试演练</span><span class="sxs-lookup"><span data-stu-id="99bf8-134">Configuring and Testing the Walkthrough</span></span>  
 <span data-ttu-id="99bf8-135">该解决方案所需的过程包括：</span><span class="sxs-lookup"><span data-stu-id="99bf8-135">The procedures required for this solution include the following:</span></span>  

- <span data-ttu-id="99bf8-136">使用所需的消息架构生成并部署 BizTalk 项目，并将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 设置为在处理接收的交换时使用这些架构。</span><span class="sxs-lookup"><span data-stu-id="99bf8-136">Build and deploy a BizTalk project with the required message schema, making the schema available for use by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in processing the received interchange.</span></span>  

- <span data-ttu-id="99bf8-137">启用接收 AS2 消息时使用的 BTS ISAPI 筛选器。</span><span class="sxs-lookup"><span data-stu-id="99bf8-137">Enable the BTS ISAPI filter used in receiving the AS2 message.</span></span>  

- <span data-ttu-id="99bf8-138">按照接收位置中的配置，创建一个用于从 Fabrikam 接收 AS2 消息的 Contoso 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="99bf8-138">Create a Contoso virtual directory that receives the AS2 message from Fabrikam, as configured in the receive location.</span></span>  

- <span data-ttu-id="99bf8-139">创建一个用于从 Contoso 接收 MDN 的 Fabrikam 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="99bf8-139">Create a Fabrikam virtual directory that receives the MDN from Contoso.</span></span>  

- <span data-ttu-id="99bf8-140">指定 Windows SharePoint Services 不管理 Contoso 和 Fabrikam 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="99bf8-140">Specify that the Contoso and Fabrikam virtual directories are not managed by Windows SharePoint Services.</span></span>  

- <span data-ttu-id="99bf8-141">为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建一个静态单向 HTTP 接收端口以从贸易合作伙伴接收包含 EDI 业务文档的 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="99bf8-141">Create a static one-way HTTP receive port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive the AS2 message containing the EDI business document from the trading partner.</span></span> <span data-ttu-id="99bf8-142">将接收管道配置为 AS2EDIReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="99bf8-142">Configure the receive pipeline to be the AS2EDIReceive pipeline.</span></span>  

- <span data-ttu-id="99bf8-143">为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建一个动态单向 HTTP 发送端口以发送对应于所接收 AS2 消息的 MDN。</span><span class="sxs-lookup"><span data-stu-id="99bf8-143">Create a dynamic one-way HTTP send port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send the MDN responding to the received AS2 message.</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="99bf8-144">此发送端口基于 EdiIntAS.IsAS2AsynchronousMDN 属性（由 AS2EdiReceive 管道设置为 True）和相关标记订阅 MDN。</span><span class="sxs-lookup"><span data-stu-id="99bf8-144">This send port subscribes to the MDN based on the EdiIntAS.IsAS2AsynchronousMDN property (which was set to True by the AS2EdiReceive pipeline) and correlation tokens.</span></span> <span data-ttu-id="99bf8-145">发送端口必须是动态的，因此它将向消息标头的 Receipt-Delivery-Notification 行中的地址发送该 MDN。</span><span class="sxs-lookup"><span data-stu-id="99bf8-145">The send port must be dynamic, so it will send the MDN to the address in the Receipt-Delivery-Notification line in the header of the message.</span></span>  

- <span data-ttu-id="99bf8-146">创建静态单向 FILE 发送端口以将 EDI 负载（XML 格式）发送到本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="99bf8-146">Create a static one-way FILE send port to route the EDI payload (in XML format) to a local folder.</span></span> <span data-ttu-id="99bf8-147">创建本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="99bf8-147">Create the local folder.</span></span>  

- <span data-ttu-id="99bf8-148">为 Fabrikam 和 Contoso 创建参与方（贸易合作伙伴）。</span><span class="sxs-lookup"><span data-stu-id="99bf8-148">Create a party (trading partner) for both Fabrikam and Contoso.</span></span>  

- <span data-ttu-id="99bf8-149">为这两个贸易参与方创建业务配置文件每个。</span><span class="sxs-lookup"><span data-stu-id="99bf8-149">Create a business profile each for both the trading parties.</span></span>  

- <span data-ttu-id="99bf8-150">在 Fabrikam 和 Contoso 的业务配置文件之间创建一个 AS2 协议。</span><span class="sxs-lookup"><span data-stu-id="99bf8-150">Create an AS2 agreement between the business profiles for Fabrikam and Contoso.</span></span> <span data-ttu-id="99bf8-151">AS2 协议中将包含发送 AS2 消息并接收返回的异步 MDN 的属性。</span><span class="sxs-lookup"><span data-stu-id="99bf8-151">The AS2 agreement would contain properties to send an AS2 message and receive an asynchronous MDN in return.</span></span>  

- <span data-ttu-id="99bf8-152">创建 X12 协议的业务配置文件，Fabrikam 和 Contoso 之间接收 X12 消息。</span><span class="sxs-lookup"><span data-stu-id="99bf8-152">Create an X12 agreement between the business profiles for Fabrikam and Contoso to receive X12 messages.</span></span>  

- <span data-ttu-id="99bf8-153">AS2 教程文件中通过附带的 HTTP 发送方实用工具中测试解决方案。</span><span class="sxs-lookup"><span data-stu-id="99bf8-153">Test the solution by using the HTTP Sender utility that is shipped as part of the AS2 tutorial files.</span></span> <span data-ttu-id="99bf8-154">该实用工具将通过 AS2 传输类型发送一条包含 EDI 交换的测试 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="99bf8-154">This utility sends a test AS2 message containing an EDI interchange over AS2 transport.</span></span> <span data-ttu-id="99bf8-155">该实用工具通过 AS2 传输方法发送一条包含有 EDI 交换的测试 AS2 消息（X12_00401_864.edi，也包括在 AS2 教程中）。</span><span class="sxs-lookup"><span data-stu-id="99bf8-155">This utility sends a test AS2 message containing an EDI interchange over AS2 transport (X12_00401_864.edi, also shipped with the AS2 tutorial).</span></span> <span data-ttu-id="99bf8-156">在此演练中使用的 HTTP 发送实用工具和测试消息与交付用于本教程的版本相同。</span><span class="sxs-lookup"><span data-stu-id="99bf8-156">The HTTP Sender and the test message that you use for this walkthrough are the same as the versions that shipped for the tutorial.</span></span>  

### <a name="configuring-the-walkthrough"></a><span data-ttu-id="99bf8-157">配置演练</span><span class="sxs-lookup"><span data-stu-id="99bf8-157">Configuring the Walkthrough</span></span>  
 <span data-ttu-id="99bf8-158">本部分介绍配置本演练的步骤。</span><span class="sxs-lookup"><span data-stu-id="99bf8-158">This section describes the procedures to configure the walkthrough.</span></span>  

##### <a name="to-deploy-the-message-schema"></a><span data-ttu-id="99bf8-159">部署消息架构</span><span class="sxs-lookup"><span data-stu-id="99bf8-159">To deploy the message schema</span></span>  

1. <span data-ttu-id="99bf8-160">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开项目 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas\Schemas.btproj。</span><span class="sxs-lookup"><span data-stu-id="99bf8-160">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the project [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas\Schemas.btproj.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="99bf8-161">此项目随 AS2 教程一起提供，其中包括一个 864 架构以与测试消息一起使用。</span><span class="sxs-lookup"><span data-stu-id="99bf8-161">This project, which is shipped for the AS2 tutorial, includes an 864 schema for use with the test message.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="99bf8-162">本主题假定你已从你的应用程序添加了对包含 EDI 架构、管道和业务流程的 BizTalk EDI 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="99bf8-162">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="99bf8-163">如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。</span><span class="sxs-lookup"><span data-stu-id="99bf8-163">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  

2. <span data-ttu-id="99bf8-164">右键单击**架构**项目在解决方案资源管理器，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-164">Right-click the **Schemas** project in the Solution Explorer, and then click **Properties**.</span></span> <span data-ttu-id="99bf8-165">单击**签名**选项卡在项目设计器中，检查**程序集签名**复选框，并从下拉列表中选择**新建**并提供所需的值来创建强名称密钥文件。</span><span class="sxs-lookup"><span data-stu-id="99bf8-165">Click the **Signing** tab in the project designer, check the **Sign the Assembly** checkbox, and from the drop-down, select **New** and provide the necessary values to create a strong name key file.</span></span> <span data-ttu-id="99bf8-166">保存所做的更改并关闭项目属性窗口。</span><span class="sxs-lookup"><span data-stu-id="99bf8-166">Save the changes and close the project properties window.</span></span>  

3. <span data-ttu-id="99bf8-167">生成并部署 Schemas.btproj。</span><span class="sxs-lookup"><span data-stu-id="99bf8-167">Build and deploy Schemas.btproj.</span></span>  

##### <a name="to-enable-the-bts-isapi-filter"></a><span data-ttu-id="99bf8-168">启用 BTS ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="99bf8-168">To enable the BTS ISAPI Filter</span></span>  

1. <span data-ttu-id="99bf8-169">单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="99bf8-169">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  

   > [!TIP]
   >  <span data-ttu-id="99bf8-170">根据操作系统，管理工具启动菜单选项可能不可用。</span><span class="sxs-lookup"><span data-stu-id="99bf8-170">Depending on the operating system, the Administrative Tools start menu option may not be available.</span></span> <span data-ttu-id="99bf8-171">在这种情况下，单击**启动**，单击**运行**，然后输入`inetmgr`打开 Internet 信息服务 (IIS) 管理器。</span><span class="sxs-lookup"><span data-stu-id="99bf8-171">In such cases, click **Start**, click **Run**, and enter `inetmgr` to open Internet Information Services (IIS) Manager.</span></span>  

2. <span data-ttu-id="99bf8-172">选择根 Web 服务器条目并在**功能视图**，双击**处理程序映射**，然后在操作窗格中的单击**添加脚本映射**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-172">Select the root Web Server entry and in the **Features View**, double click **Handler Mappings** and then in the Actions pane click **Add Script Map**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="99bf8-173">在 Web 服务器级别配置的脚本映射将导致此映射应用于所有子网站。</span><span class="sxs-lookup"><span data-stu-id="99bf8-173">Configuring the script mapping at the Web Server level will cause this mapping to apply to all child Web Sites.</span></span> <span data-ttu-id="99bf8-174">如果你想要将映射限制到特定的网站或虚拟文件夹，选择文件夹而不是 Web 服务器的目标站点。</span><span class="sxs-lookup"><span data-stu-id="99bf8-174">If you wish to restrict the mapping to a specific Web Site or Virtual Folder, select the target site or folder instead of the Web Server.</span></span>  

3. <span data-ttu-id="99bf8-175">在中**添加脚本映射**对话框框中，输入`BtsHttpReceive.dll`中**请求路径**字段。</span><span class="sxs-lookup"><span data-stu-id="99bf8-175">In the **Add Script Map** dialog box, enter `BtsHttpReceive.dll` in the **Request path** field.</span></span>  

4. <span data-ttu-id="99bf8-176">在中**可执行文件**字段中，单击**省略号 （...）** 按钮并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive。</span><span class="sxs-lookup"><span data-stu-id="99bf8-176">In the **Executable** field, click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive.</span></span> <span data-ttu-id="99bf8-177">选择 BtsHttpReceive.dll，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-177">Select BtsHttpReceive.dll and click **OK**.</span></span>  

5. <span data-ttu-id="99bf8-178">输入`BizTalk HTTP Receive`中`Name`字段中，然后依次**请求限制**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-178">Enter `BizTalk HTTP Receive` in the `Name` field, and then click **Request Restrictions**.</span></span>  

6. <span data-ttu-id="99bf8-179">在请求限制对话框中，选择**谓词**选项卡，然后选择**以下谓词之一**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-179">In the Request Restrictions dialog box, select the **Verbs** tab and then select **One of the following verbs**.</span></span> <span data-ttu-id="99bf8-180">输入`POST`作为谓词。</span><span class="sxs-lookup"><span data-stu-id="99bf8-180">Enter `POST` as the verb .</span></span>  

7. <span data-ttu-id="99bf8-181">上**访问**选项卡上，选择**脚本**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-181">On the **Access** tab, select **Script** and then click **OK**.</span></span>  

8. <span data-ttu-id="99bf8-182">单击**确定**并在提示是否允许 ISAPI 扩展，请单击**是**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-182">Click **OK** and when prompted to allow the ISAPI extension, click **Yes**.</span></span>  

##### <a name="to-configure-the-contoso-web-page"></a><span data-ttu-id="99bf8-183">配置 Contoso 网页</span><span class="sxs-lookup"><span data-stu-id="99bf8-183">To configure the Contoso Web page</span></span>  

1. <span data-ttu-id="99bf8-184">在 IIS 管理器中，右键单击**应用程序池**，然后选择**添加应用程序池**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-184">In IIS Manager, right-click **Application Pools** and select **Add Application Pool**.</span></span>  

2. <span data-ttu-id="99bf8-185">在中**添加应用程序池**对话框框中，输入**BizTalkAppPool**中**名称**，然后选择 **.NET Framework V4.0.30210**中 **.NET framework 版本**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="99bf8-185">In the **Add Application Pool** dialog box, enter **BizTalkAppPool** in **Name**, and then select **.NET Framework V4.0.30210** in the **.NET Framework version** drop-down list.</span></span> <span data-ttu-id="99bf8-186">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="99bf8-186">Click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="99bf8-187">根据计算机上安装的 [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] 版本，.NET Framework 的版本可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="99bf8-187">The version number may vary depending on the version of [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] installed on the machine.</span></span>  

3. <span data-ttu-id="99bf8-188">选择**应用程序池**，在功能视图中，选择**BizTalkAppPool**，然后单击**高级设置**中**操作**窗格。</span><span class="sxs-lookup"><span data-stu-id="99bf8-188">Select **Application Pools**, in the Features View select **BizTalkAppPool**, and then click **Advanced Settings** in the **Actions** pane.</span></span>  

4. <span data-ttu-id="99bf8-189">在中**高级设置**对话框中，选择**标识**，然后单击**省略号 （...）** 按钮。</span><span class="sxs-lookup"><span data-stu-id="99bf8-189">In the **Advanced Settings** dialog box, select **Identity** and then click the **ellipsis (…)** button.</span></span>  

5. <span data-ttu-id="99bf8-190">在中**应用程序池标识**对话框中，选择**自定义帐户**，然后单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-190">In the **Application Pool Identity** dialog box, select **Custom account** and then click **Set**.</span></span>  

6. <span data-ttu-id="99bf8-191">输入**用户名**并**密码**是 administrators 组的成员的用户帐户，请输入中的密码**确认密码**，然后单击**确定**三次以返回到 IIS 管理器。</span><span class="sxs-lookup"><span data-stu-id="99bf8-191">Enter the **User name** and **Password** for a user account that is a member of the administrators group, enter the password in **Confirm password** and then click **OK** three times to return to the IIS Manager.</span></span>  

7. <span data-ttu-id="99bf8-192">在 IIS 管理器中，打开**站点**文件夹。</span><span class="sxs-lookup"><span data-stu-id="99bf8-192">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="99bf8-193">右键单击**Default Web Site**节点，并选择**添加应用程序**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-193">Right-click the **Default Web Site** node, and then select **Add Application**.</span></span>  

8. <span data-ttu-id="99bf8-194">在中**添加应用程序**对话框框中，输入**Contoso**中**别名**文本框中，，然后单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-194">In the **Add Application** dialog box, enter **Contoso** in the **Alias** text box, and then click **Select**.</span></span>  

9. <span data-ttu-id="99bf8-195">在中**选择应用程序池**对话框中，选择**BizTalkAppPool**然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-195">In the **Select Application Pool** dialog box, select **BizTalkAppPool** and click **OK**.</span></span>  

10. <span data-ttu-id="99bf8-196">有关**物理路径**，单击**省略号 （...）** 按钮并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive。</span><span class="sxs-lookup"><span data-stu-id="99bf8-196">For the **Physical Path**, click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive.</span></span>  

11. <span data-ttu-id="99bf8-197">单击**测试设置**并验证是否没有显示在错误**测试连接**对话框。</span><span class="sxs-lookup"><span data-stu-id="99bf8-197">Click **Test Settings** and verify that there are no errors displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="99bf8-198">单击 **“关闭”**，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-198">Click **Close**, and then click **OK**.</span></span>  

12. <span data-ttu-id="99bf8-199">在 IIS 管理器中，选择 Contoso 虚拟目录并在**功能视图**，双击**身份验证**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-199">In IIS Manager, select the Contoso virtual directory and in the **Features View**, double-click **Authentication**.</span></span>  

13. <span data-ttu-id="99bf8-200">在中**身份验证**页上，选择**匿名身份验证**，并验证**状态**是**已启用**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-200">In the **Authentication** page, select **Anonymous Authentication** and verify that the **Status** is **Enabled**.</span></span> <span data-ttu-id="99bf8-201">如果**状态**是**禁用**，单击**启用**中**操作**窗格。</span><span class="sxs-lookup"><span data-stu-id="99bf8-201">If the **Status** is **Disabled**, click **Enable** in the **Actions** pane.</span></span>  

##### <a name="to-configure-the-fabrikam-web-page"></a><span data-ttu-id="99bf8-202">配置 Fabrikam 网页</span><span class="sxs-lookup"><span data-stu-id="99bf8-202">To configure the Fabrikam Web page</span></span>  

1. <span data-ttu-id="99bf8-203">在 IIS 管理器中，打开**站点**文件夹。</span><span class="sxs-lookup"><span data-stu-id="99bf8-203">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="99bf8-204">右键单击**Default Web Site**节点，并选择**添加应用程序**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-204">Right-click the **Default Web Site** node, and then select **Add Application**.</span></span>  

2. <span data-ttu-id="99bf8-205">在中**添加应用程序**对话框框中，输入**Fabrikam**中**别名**，然后单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-205">In the **Add Application** dialog box, enter **Fabrikam** in **Alias**, and then click **Select**.</span></span>  

3. <span data-ttu-id="99bf8-206">在中**选择应用程序池**对话框中，选择**BizTalkAppPool**然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-206">In the **Select Application Pool** dialog box, select **BizTalkAppPool** and click **OK**.</span></span>  

4. <span data-ttu-id="99bf8-207">有关**物理路径**，单击**省略号 （...）** 按钮并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Fabrikam。</span><span class="sxs-lookup"><span data-stu-id="99bf8-207">For the **Physical Path**, click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Fabrikam.</span></span>  

5. <span data-ttu-id="99bf8-208">单击**测试设置**并验证是否没有显示在错误**测试连接**对话框。</span><span class="sxs-lookup"><span data-stu-id="99bf8-208">Click **Test Settings** and verify that there are no errors displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="99bf8-209">单击 **“关闭”**，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-209">Click **Close**, and then click **OK**.</span></span>  

6. <span data-ttu-id="99bf8-210">在 IIS 管理器中，选择 Contoso 虚拟目录并在**功能视图**，双击**身份验证**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-210">In IIS Manager, select the Contoso virtual directory and in the **Features View**, double-click **Authentication**.</span></span>  

7. <span data-ttu-id="99bf8-211">在中**身份验证**页上，选择**匿名身份验证**，并验证**状态**是**已启用**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-211">In the **Authentication** page, select **Anonymous Authentication** and verify that the **Status** is **Enabled**.</span></span> <span data-ttu-id="99bf8-212">如果**状态**是**禁用**，单击**启用**中**操作**窗格。</span><span class="sxs-lookup"><span data-stu-id="99bf8-212">If the **Status** is **Disabled**, click **Enable** in the **Actions** pane.</span></span>  

##### <a name="to-specify-that-your-virtual-directory-is-not-managed-by-windows-sharepoint-services"></a><span data-ttu-id="99bf8-213">指定虚拟目录不由 Windows SharePoint Services 托管</span><span class="sxs-lookup"><span data-stu-id="99bf8-213">To specify that your virtual directory is not managed by Windows SharePoint Services</span></span>  

1.  <span data-ttu-id="99bf8-214">如果您的计算机上安装 Windows SharePoint Services，请单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**SharePoint 3.0 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-214">If Windows SharePoint Services is installed on your computer, click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint 3.0 Central Administration**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="99bf8-215">如果用于设置演练的同一计算机上还安装了 Windows SharePoint Server，则此过程是必需的。</span><span class="sxs-lookup"><span data-stu-id="99bf8-215">This procedure is required if Windows SharePoint Server is installed on the same computer that you are setting the walkthrough up on.</span></span> <span data-ttu-id="99bf8-216">在该情况下，您必须指定 IIS 虚拟目录不由 Windows SharePoint Server 托管。</span><span class="sxs-lookup"><span data-stu-id="99bf8-216">In that case, you must specify that your IIS virtual directory is not being managed by Windows SharePoint Server.</span></span>  

2.  <span data-ttu-id="99bf8-217">上**Central Administration**页面上，在**管理中心**，单击**应用程序管理**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-217">On the **Central Administration** page, under **Central Administration**, click **Application Management**.</span></span>  

3.  <span data-ttu-id="99bf8-218">上**应用程序管理**页上，单击**定义管理路径**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-218">On the **Application Management** page, click **Define managed paths**.</span></span>  

4.  <span data-ttu-id="99bf8-219">中**定义管理路径**页面上，在**添加新路径**，在**路径**文字框中，输入**Contoso**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-219">In the **Define Managed Paths** page, under **Add a New Path**, in the **Path** text box, enter **Contoso**.</span></span> <span data-ttu-id="99bf8-220">下**类型**，单击**排除的路径**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-220">Under **Type**, click **Excluded Path**, and then click **OK**.</span></span>  

5.  <span data-ttu-id="99bf8-221">请为 Fabrikam 虚拟目录重复步骤 4。</span><span class="sxs-lookup"><span data-stu-id="99bf8-221">Repeat step 4 for the Fabrikam virtual directory.</span></span>  

##### <a name="to-create-a-receive-port-to-receive-the-edi-interchange-over-as2-from-fabrikam"></a><span data-ttu-id="99bf8-222">创建接收端口以通过 AS2 从 Fabrikam 接收 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="99bf8-222">To create a receive port to receive the EDI interchange Over AS2 from Fabrikam</span></span>  

1. <span data-ttu-id="99bf8-223">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-223">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the **Receive Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **One-way Receive Port**.</span></span>  

2. <span data-ttu-id="99bf8-224">接收端口的名称，然后单击**接收位置**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="99bf8-224">Name the receive port, and then click **Receive Locations** in the console tree.</span></span>  

3. <span data-ttu-id="99bf8-225">单击 **“新建”**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-225">Click **New**.</span></span>  

4. <span data-ttu-id="99bf8-226">名称的接收位置，选择**HTTP**有关**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-226">Name the receive location, select **HTTP** for **Type**, and then click **Configure**.</span></span>  

5. <span data-ttu-id="99bf8-227">有关**虚拟目录和 ISAPI 扩展**，输入`/Contoso/BTSHTTPReceive.dll`。</span><span class="sxs-lookup"><span data-stu-id="99bf8-227">For **Virtual directory plus ISAPI extension**, enter `/Contoso/BTSHTTPReceive.dll`.</span></span>  

6. <span data-ttu-id="99bf8-228">选择**挂起失败的请求**复选框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-228">Select the **Suspend failed requests** check box, and click **OK**.</span></span>  

7. <span data-ttu-id="99bf8-229">有关**接收管道**，选择**AS2EDIReceive**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-229">For **Receive pipeline**, select **AS2EDIReceive**.</span></span>  

8. <span data-ttu-id="99bf8-230">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="99bf8-230">Click **OK**, and then click **OK** again.</span></span>  

9. <span data-ttu-id="99bf8-231">在中**接收位置**窗格[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击该接收位置，然后依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-231">In the **Receive Locations** pane of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the receive location, and then click **Enable**.</span></span>  

##### <a name="to-create-a-dynamic-send-port-to-send-the-mdn-to-fabrikam"></a><span data-ttu-id="99bf8-232">创建动态发送端口将 MDN 发送至 Fabrikam</span><span class="sxs-lookup"><span data-stu-id="99bf8-232">To create a dynamic send port to send the MDN to Fabrikam</span></span>  

1. <span data-ttu-id="99bf8-233">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**动态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-233">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Dynamic One-way Send Port**.</span></span>  

2. <span data-ttu-id="99bf8-234">在中**发送端口属性**对话框中，发送端口名称。</span><span class="sxs-lookup"><span data-stu-id="99bf8-234">In the **Send Port Properties** dialog box, name the send port.</span></span>  

3. <span data-ttu-id="99bf8-235">有关**发送管道**，选择**AS2Send**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-235">For **Send Pipeline**, select **AS2Send**.</span></span>  

4. <span data-ttu-id="99bf8-236">在控制台树中，选择**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-236">In the console tree, select **Filters**.</span></span> <span data-ttu-id="99bf8-237">有关**属性**，输入**EdiIntAS.IsAS2AsynchronousMDN**; 对于**运算符**，输入**==**; 以及**值**，输入 **，则返回 True**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-237">For **Property**, enter **EdiIntAS.IsAS2AsynchronousMDN**; for **Operator**, enter **==**; and for **Value** , enter **True**.</span></span>  

5. <span data-ttu-id="99bf8-238">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="99bf8-238">Click **OK**.</span></span>  

##### <a name="to-create-a-send-port-to-send-the-edi-payload-to-a-local-folder"></a><span data-ttu-id="99bf8-239">创建用于将 EDI 负载发送到本地文件夹的发送端口</span><span class="sxs-lookup"><span data-stu-id="99bf8-239">To create a send port to send the EDI payload to a local folder</span></span>  

1. <span data-ttu-id="99bf8-240">在 Windows 资源管理器，创建一个名为 Contoso 本地文件夹**EDI_to_Contoso**用于接收 EDI 负载。</span><span class="sxs-lookup"><span data-stu-id="99bf8-240">In Windows Explorer, create a Contoso local folder named **EDI_to_Contoso** to send the EDI payload to.</span></span>  

2. <span data-ttu-id="99bf8-241">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-241">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  

3. <span data-ttu-id="99bf8-242">在中**发送端口属性**对话框框中，将发送端口，例如， **Send_Payload**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-242">In the **Send Port Properties** dialog box, name your send port, for example, **Send_Payload**.</span></span> <span data-ttu-id="99bf8-243">选择**文件**有关**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-243">Select **FILE** for **Type**, and then click **Configure**.</span></span>  

4. <span data-ttu-id="99bf8-244">在中**FILE 传输属性**对话框中，对于**目标文件夹**，浏览到并选择**EDI_to_Contoso**步骤 1 中创建的文件夹。</span><span class="sxs-lookup"><span data-stu-id="99bf8-244">In the **FILE Transport Properties** dialog box, for **Destination folder**, browse to and select the **EDI_to_Contoso** folder that you created in step 1.</span></span> <span data-ttu-id="99bf8-245">将保留**文件名**作为 **%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-245">Leave **File name** as **%MessageID%.xml**.</span></span> <span data-ttu-id="99bf8-246">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="99bf8-246">Click **OK**.</span></span>  

5. <span data-ttu-id="99bf8-247">接受默认值为**PassThruTransmit**有关**发送管道**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-247">Accept the default of **PassThruTransmit** for **Send Pipeline**.</span></span>  

6. <span data-ttu-id="99bf8-248">单击**筛选器**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="99bf8-248">Click **Filters** in the console tree.</span></span> <span data-ttu-id="99bf8-249">有关**属性**，输入**BTS。MessageType**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-249">For **Property**, enter **BTS.MessageType**.</span></span> <span data-ttu-id="99bf8-250">有关**运算符**，输入**==**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-250">For **Operator**, enter **==**.</span></span> <span data-ttu-id="99bf8-251">有关**值**，输入您的消息，消息类型`http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`。</span><span class="sxs-lookup"><span data-stu-id="99bf8-251">For **Value**, enter the message type for your message, `http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`.</span></span>  

7. <span data-ttu-id="99bf8-252">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="99bf8-252">Click **OK**.</span></span>  

8. <span data-ttu-id="99bf8-253">在中**发送端口**窗格[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击该发送端口，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-253">In the **Send Ports** pane of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the send port, and then click **Start**.</span></span>  

##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a><span data-ttu-id="99bf8-254">创建 Fabrikam 参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="99bf8-254">To create a party and a business profile for Fabrikam</span></span>  

1. <span data-ttu-id="99bf8-255">右键单击**参与方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-255">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  

2. <span data-ttu-id="99bf8-256">输入中的参与方的名称**名称**文本框中，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-256">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="99bf8-257">通过选择**本地 BizTalk 处理接收的来自此参与方发送消息的参与方或支持消息**复选框，可以指定要创建的参与方是为同一组织与托管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99bf8-257">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="99bf8-258">此基础，某些属性将启用，或禁用在创建协议时。</span><span class="sxs-lookup"><span data-stu-id="99bf8-258">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="99bf8-259">但是，对于此演练中，可以选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="99bf8-259">However, for this walkthrough, you can leave this check box selected.</span></span>  

3. <span data-ttu-id="99bf8-260">右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-260">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  

4. <span data-ttu-id="99bf8-261">在中**配置文件属性**对话框中，在**常规**页上，输入**Fabrikam_Profile**中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="99bf8-261">In the **Profile Properties** dialog box, on the **General** page, enter **Fabrikam_Profile** in the **Name** text box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="99bf8-262">创建一个参与方时，还创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="99bf8-262">When you create a party, a profile is also created.</span></span> <span data-ttu-id="99bf8-263">可以重命名，并使用该配置文件而不是创建一个新。</span><span class="sxs-lookup"><span data-stu-id="99bf8-263">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="99bf8-264">若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-264">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="99bf8-265">在中**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="99bf8-265">In the **General** page, specify a name for the profile.</span></span>  

##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a><span data-ttu-id="99bf8-266">为 Contoso 创建参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="99bf8-266">To create a party and a business profile for Contoso</span></span>  

1. <span data-ttu-id="99bf8-267">右键单击**参与方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-267">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  

2. <span data-ttu-id="99bf8-268">输入中的参与方的名称**名称**文本框中，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-268">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="99bf8-269">通过选择**本地 BizTalk 处理接收的来自此参与方发送消息的参与方或支持消息**复选框，可以指定要创建的参与方是为同一组织与托管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99bf8-269">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="99bf8-270">此基础，某些属性将启用，或禁用在创建协议时。</span><span class="sxs-lookup"><span data-stu-id="99bf8-270">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="99bf8-271">但是，对于此演练中，可以选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="99bf8-271">However, for this walkthrough, you can leave this check box selected.</span></span>  

3. <span data-ttu-id="99bf8-272">右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-272">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  

4. <span data-ttu-id="99bf8-273">在中**配置文件属性**对话框中，在**常规**页上，输入**Contoso_Profile**中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="99bf8-273">In the **Profile Properties** dialog box, on the **General** page, enter **Contoso_Profile** in the **Name** text box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="99bf8-274">创建一个参与方时，还创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="99bf8-274">When you create a party, a profile is also created.</span></span> <span data-ttu-id="99bf8-275">可以重命名，并使用该配置文件而不是创建一个新。</span><span class="sxs-lookup"><span data-stu-id="99bf8-275">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="99bf8-276">若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-276">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="99bf8-277">在中**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="99bf8-277">In the **General** page, specify a name for the profile.</span></span>  

##### <a name="to-create-an-as2-agreement-between-the-two-business-profiles"></a><span data-ttu-id="99bf8-278">在两个业务配置文件之间创建 AS2 协议</span><span class="sxs-lookup"><span data-stu-id="99bf8-278">To create an AS2 agreement between the two business profiles</span></span>  

1.  <span data-ttu-id="99bf8-279">右键单击**Fabrikam_Profile**，依次指向**新建**，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-279">Right-click **Fabrikam_Profile**, point to **New**, and then click **Agreement**.</span></span>  

2.  <span data-ttu-id="99bf8-280">在**常规属性**页上，对于**名称**文字框中，输入协议的名称。</span><span class="sxs-lookup"><span data-stu-id="99bf8-280">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  

3.  <span data-ttu-id="99bf8-281">从**协议**下拉列表中，选择**AS2**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-281">From the **Protocol** drop-down list, select **AS2**.</span></span>  

4.  <span data-ttu-id="99bf8-282">在中**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**Contoso**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-282">In the **Second Partner** section, from the **Name** drop-down list, select **Contoso**.</span></span>  

5.  <span data-ttu-id="99bf8-283">在中**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**Contoso_Profile**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-283">In the **Second Partner** section, from the **Profile** drop-down list, select **Contoso_Profile**.</span></span>  

     <span data-ttu-id="99bf8-284">你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡用于配置一个单向 AS2 协议。</span><span class="sxs-lookup"><span data-stu-id="99bf8-284">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way AS2 agreement.</span></span>  

6.  <span data-ttu-id="99bf8-285">在中**常规**选项卡中，**常规属性**页上，在**公用主机设置**部分中，选择**打开报告**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-285">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**.</span></span>  

7.  <span data-ttu-id="99bf8-286">在执行以下任务**Fabrikam-> Contoso**选项卡。</span><span class="sxs-lookup"><span data-stu-id="99bf8-286">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  

    1.  <span data-ttu-id="99bf8-287">上**标识符**页上，输入值**AS2-从**并**AS2-到**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-287">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="99bf8-288">有关**AS2-从**，输入`Fabrikam`。</span><span class="sxs-lookup"><span data-stu-id="99bf8-288">For **AS2-From**, enter `Fabrikam`.</span></span> <span data-ttu-id="99bf8-289">有关**AS2-To**，输入`Contoso`。</span><span class="sxs-lookup"><span data-stu-id="99bf8-289">For **AS2- To**, enter `Contoso`.</span></span>  

    2.  <span data-ttu-id="99bf8-290">上**验证**页上，选择**使用的验证和 MDN 的协议设置而非消息标头**复选框</span><span class="sxs-lookup"><span data-stu-id="99bf8-290">On the **Validation** page, select the **Use agreement settings for validation and MDN instead of message header** check box</span></span>  

    3.  <span data-ttu-id="99bf8-291">在中**确认 (Mdn)** 页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="99bf8-291">In the **Acknowledgements (MDNs)** page, do the following:</span></span>  

        1.  <span data-ttu-id="99bf8-292">选择**请求 MDN**复选框。</span><span class="sxs-lookup"><span data-stu-id="99bf8-292">Select the **Request MDN** check box.</span></span>  

        2.  <span data-ttu-id="99bf8-293">请确保**请求经过签名的 MDN**清除复选框。</span><span class="sxs-lookup"><span data-stu-id="99bf8-293">Make sure the **Request Signed MDN** check box is cleared.</span></span>  

        3.  <span data-ttu-id="99bf8-294">选择**请求异步 MDN**复选框。</span><span class="sxs-lookup"><span data-stu-id="99bf8-294">Select the **Request asynchronous MDN** check box.</span></span>  

        4.  <span data-ttu-id="99bf8-295">在中**回执送达选项 (URL)** 文字框中，输入`http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam`。</span><span class="sxs-lookup"><span data-stu-id="99bf8-295">In the **Receipt-Delivery-Option (URL)** text box, enter `http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam`.</span></span>  

8.  <span data-ttu-id="99bf8-296">在执行以下任务**Contoso-> Fabrikam**选项卡。</span><span class="sxs-lookup"><span data-stu-id="99bf8-296">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="99bf8-297">在本演练中，我们指定的选项卡中所需的值，以便可以成功创建协议。</span><span class="sxs-lookup"><span data-stu-id="99bf8-297">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="99bf8-298">若要成功创建协议，两个单向协议选项卡必须具有定义为值**AS2-从**并**AS2-到**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-298">To successfully create an agreement, both one-way agreement tabs must have values defined for **AS2-From** and **AS2-To**.</span></span>  

    1.  <span data-ttu-id="99bf8-299">上**标识符**页上，输入值**AS2-从**并**AS2-到**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-299">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="99bf8-300">有关**AS2-从**，输入`Contoso`。</span><span class="sxs-lookup"><span data-stu-id="99bf8-300">For **AS2-From**, enter `Contoso`.</span></span> <span data-ttu-id="99bf8-301">有关**AS2-To**，输入`Fabrikam`。</span><span class="sxs-lookup"><span data-stu-id="99bf8-301">For **AS2- To**, enter `Fabrikam`.</span></span>  

9. <span data-ttu-id="99bf8-302">单击 **“应用”**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-302">Click **Apply**.</span></span>  

10. <span data-ttu-id="99bf8-303">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="99bf8-303">Click **OK**.</span></span> <span data-ttu-id="99bf8-304">中列出新添加的协议**协议**一部分**参与方和业务配置文件**窗格。</span><span class="sxs-lookup"><span data-stu-id="99bf8-304">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="99bf8-305">默认情况下，启用新添加的协议。</span><span class="sxs-lookup"><span data-stu-id="99bf8-305">The newly added agreement is enabled by default.</span></span>  

##### <a name="to-create-an-x12-agreement-between-the-two-business-profiles"></a><span data-ttu-id="99bf8-306">在两个业务配置文件之间创建 X12 协议</span><span class="sxs-lookup"><span data-stu-id="99bf8-306">To create an X12 agreement between the two business profiles</span></span>  

1. <span data-ttu-id="99bf8-307">右键单击**Fabrikam_Profile**，依次指向**新建**，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-307">Right-click **Fabrikam_Profile**, point to **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="99bf8-308">在**常规属性**页上，对于**名称**文字框中，输入协议的名称。</span><span class="sxs-lookup"><span data-stu-id="99bf8-308">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  

3. <span data-ttu-id="99bf8-309">从**协议**下拉列表中，选择**X12**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-309">From the **Protocol** drop-down list, select **X12**.</span></span>  

4. <span data-ttu-id="99bf8-310">在中**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**Contoso**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-310">In the **Second Partner** section, from the **Name** drop-down list, select **Contoso**.</span></span>  

5. <span data-ttu-id="99bf8-311">在中**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**Contoso_Profile**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-311">In the **Second Partner** section, from the **Profile** drop-down list, select **Contoso_Profile**.</span></span>  

    <span data-ttu-id="99bf8-312">你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡可用于配置一个单向 X12 协议。</span><span class="sxs-lookup"><span data-stu-id="99bf8-312">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way X12 agreement.</span></span>  

6. <span data-ttu-id="99bf8-313">在中**常规**选项卡中，**常规属性**页上，在**公用主机设置**部分中，选择**打开报告**，，然后选择**存储消息负载以用于报告**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-313">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**, and then select **Store message payload for reporting**.</span></span>  

7. <span data-ttu-id="99bf8-314">在执行以下任务**Fabrikam-> Contoso**选项卡。</span><span class="sxs-lookup"><span data-stu-id="99bf8-314">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  

   1. <span data-ttu-id="99bf8-315">上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，并**ISA8**) 的测试消息中这些标头字段的值相对应。</span><span class="sxs-lookup"><span data-stu-id="99bf8-315">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="99bf8-316"> 要求为发送方和接收方的限定符和标识符字段输入值才能执行协议解析。</span><span class="sxs-lookup"><span data-stu-id="99bf8-316"> requires the qualifier and identifier fields for sender and receiver in order to perform agreement resolution.</span></span> <span data-ttu-id="99bf8-317">它将匹配的值**ISA5**， **ISA6**， **ISA7**，以及**ISA8**与协议属性中的交换标头中。</span><span class="sxs-lookup"><span data-stu-id="99bf8-317">It will match the values of **ISA5**, **ISA6**, **ISA7**, and **ISA8** in the interchange header with those in the properties of an agreement.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="99bf8-318"> 此外将通过匹配发送方限定符和标识符 （不接收方限定符和标识符） 来解析协议。</span><span class="sxs-lookup"><span data-stu-id="99bf8-318"> will also resolve the agreement by matching the sender qualifier and identifier (without the receiver qualifier and identifier).</span></span> <span data-ttu-id="99bf8-319">如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法解析协议，则将使用后备协议属性。</span><span class="sxs-lookup"><span data-stu-id="99bf8-319">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot resolve the agreement, it will use the fallback agreement properties.</span></span>  
      > 
      > [!NOTE]
      >  <span data-ttu-id="99bf8-320">对于本演练中，设置**ISA5**到**ZZ**， **ISA6**到**7654321**， **ISA7**到**ZZ**，并**ISA8**到**1234567**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-320">For this walkthrough, set **ISA5** to **ZZ**, **ISA6** to **7654321**, **ISA7** to **ZZ**, and **ISA8** to **1234567**.</span></span>  

   2. <span data-ttu-id="99bf8-321">上**验证**页**交换设置**部分中，请确保**检查重复的 isa13**选项处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="99bf8-321">On the **Validation** page under the **Interchange Settings** section, make sure **Check for duplicate ISA13** option is unchecked.</span></span>  

      > [!NOTE]
      >  <span data-ttu-id="99bf8-322">清除**检查重复的 isa13**属性使您能够接收同一消息的多个实例。</span><span class="sxs-lookup"><span data-stu-id="99bf8-322">Clearing the **Check for duplicate ISA13** property enables you to receive multiple instances of the same message.</span></span>  

   3. <span data-ttu-id="99bf8-323">如果你使用附带的标准架构之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后在**本地主机设置**页下**事务集设置**部分中，选择要使用的架构的命名空间处理传入的交换。</span><span class="sxs-lookup"><span data-stu-id="99bf8-323">If you are using one of the standard schemas shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], on the **Local Host Settings** page under the **Transaction Set Settings** section, select the namespace for the schema to be used to process the incoming interchange.</span></span>  

      |<span data-ttu-id="99bf8-324">使用此选项</span><span class="sxs-lookup"><span data-stu-id="99bf8-324">Use this</span></span>|<span data-ttu-id="99bf8-325">执行的操作</span><span class="sxs-lookup"><span data-stu-id="99bf8-325">To do this</span></span>|  
      |--------------|----------------|  
      |<span data-ttu-id="99bf8-326">**Default**</span><span class="sxs-lookup"><span data-stu-id="99bf8-326">**Default**</span></span>|<span data-ttu-id="99bf8-327">选中列中的复选框</span><span class="sxs-lookup"><span data-stu-id="99bf8-327">Select the checkbox in the column</span></span>|  
      |<span data-ttu-id="99bf8-328">**目标 Namespace**</span><span class="sxs-lookup"><span data-stu-id="99bf8-328">**Target Namespace**</span></span>|<span data-ttu-id="99bf8-329">选择 `http://schemas.microsoft.com/BizTalk/EDI/X12/2006`。</span><span class="sxs-lookup"><span data-stu-id="99bf8-329">Select `http://schemas.microsoft.com/BizTalk/EDI/X12/2006`.</span></span>|  

      > [!NOTE]
      >  <span data-ttu-id="99bf8-330">设置属性可以使 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 确定处理传入 850 交换时使用的架构。</span><span class="sxs-lookup"><span data-stu-id="99bf8-330">Setting the properties enables [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to determine the schema to be used in processing the incoming 850 interchange.</span></span> <span data-ttu-id="99bf8-331">如果某一交换的 GS02 和 ST01 的值是在网格行上输入的，则将使用同一行的目标命名空间来确定要使用的架构。</span><span class="sxs-lookup"><span data-stu-id="99bf8-331">If an interchange has the values of GS02 and ST01 that are entered on a line of the grid, then the target namespace for the same line will be used to determine the schema to be used.</span></span>  

   4. <span data-ttu-id="99bf8-332">上**信封**页**事务集设置**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="99bf8-332">On the **Envelopes** page under the **Transaction Set Settings** section, do the following:</span></span>  


      |       <span data-ttu-id="99bf8-333">使用此选项</span><span class="sxs-lookup"><span data-stu-id="99bf8-333">Use this</span></span>       |                                                                                                                                              <span data-ttu-id="99bf8-334">执行的操作</span><span class="sxs-lookup"><span data-stu-id="99bf8-334">To do this</span></span>                                                                                                                                               |
      |----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |     <span data-ttu-id="99bf8-335">**Default**</span><span class="sxs-lookup"><span data-stu-id="99bf8-335">**Default**</span></span>      |              <span data-ttu-id="99bf8-336">选择**默认**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-336">Select **Default**.</span></span> <span data-ttu-id="99bf8-337">**注意：** 选择此行作为默认值的值**GS1**， **GS2**， **GS3**， **GS7**，和**GS8**使用即使的值**事务类型**，**版本/发行版**，并且**目标命名空间**不是消息的匹配项。</span><span class="sxs-lookup"><span data-stu-id="99bf8-337">**Note:**  When you select this row as the default, the values for **GS1**, **GS2**, **GS3**, **GS7**, and **GS8** are used even if the values for **Transaction Type**, **Version/Release**, and **Target namespace** are not a match for the message.</span></span>              |
      | <span data-ttu-id="99bf8-338">**事务类型**</span><span class="sxs-lookup"><span data-stu-id="99bf8-338">**Transaction Type**</span></span> |                                                                                                          <span data-ttu-id="99bf8-339">例如，选择你的测试消息的消息类型**864 – 文本消息**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-339">Select the message type of your test message, for example, **864 – Text Message**.</span></span>                                                                                                           |
      | <span data-ttu-id="99bf8-340">**版本/发行版**</span><span class="sxs-lookup"><span data-stu-id="99bf8-340">**Version/Release**</span></span>  |                                                                                                                                           <span data-ttu-id="99bf8-341">输入**00401**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-341">Enter **00401**.</span></span>                                                                                                                                            |
      | <span data-ttu-id="99bf8-342">**目标命名空间**</span><span class="sxs-lookup"><span data-stu-id="99bf8-342">**Target namespace**</span></span> |                                                                                                                    <span data-ttu-id="99bf8-343">选择**<http://schemas.microsoft.com/BizTalk/EDI/X12/2006>**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-343">Select **<http://schemas.microsoft.com/BizTalk/EDI/X12/2006>**.</span></span>                                                                                                                    |
      |       <span data-ttu-id="99bf8-344">**GS1**</span><span class="sxs-lookup"><span data-stu-id="99bf8-344">**GS1**</span></span>        |                                                                                                <span data-ttu-id="99bf8-345">验证是否选择测试消息的消息类型，例如， **TX-文本消息 (864)**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-345">Verify that the message type of the test message is selected, for example, **TX - Text Message (864)**.</span></span>                                                                                                |
      |       <span data-ttu-id="99bf8-346">**GS2**</span><span class="sxs-lookup"><span data-stu-id="99bf8-346">**GS2**</span></span>        |                                                                                                                                             <span data-ttu-id="99bf8-347">输入**01**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-347">Enter **01**.</span></span>                                                                                                                                             |
      |       <span data-ttu-id="99bf8-348">**GS3**</span><span class="sxs-lookup"><span data-stu-id="99bf8-348">**GS3**</span></span>        |                                                                                                                                          <span data-ttu-id="99bf8-349">输入**7654321**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-349">Enter **7654321**.</span></span>                                                                                                                                           |
      |       <span data-ttu-id="99bf8-350">**GS4**</span><span class="sxs-lookup"><span data-stu-id="99bf8-350">**GS4**</span></span>        | <span data-ttu-id="99bf8-351">选择所需的日期格式。</span><span class="sxs-lookup"><span data-stu-id="99bf8-351">Select the date format that you want.</span></span> <span data-ttu-id="99bf8-352">选择**CCYYMMDD**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-352">Select **CCYYMMDD**.</span></span> <span data-ttu-id="99bf8-353">**注意：** 需要下拉列表中选择一个值，而不仅仅是单击该字段以显示默认值。</span><span class="sxs-lookup"><span data-stu-id="99bf8-353">**Note:**  You have to select the value in the drop-down list, not just click in the field to display the default.</span></span> <span data-ttu-id="99bf8-354">如果你仅单击字段，而没有从下拉列表中选择值，则实际上并未选择值。</span><span class="sxs-lookup"><span data-stu-id="99bf8-354">If you click in the field without selecting the value from the drop-down list, the value will not actually be selected.</span></span> |
      |       <span data-ttu-id="99bf8-355">**GS5**</span><span class="sxs-lookup"><span data-stu-id="99bf8-355">**GS5**</span></span>        |                                                                                                                      <span data-ttu-id="99bf8-356">选择所需的时间格式。</span><span class="sxs-lookup"><span data-stu-id="99bf8-356">Select the time format that you want.</span></span> <span data-ttu-id="99bf8-357">选择**HHMMSSdd**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-357">Select **HHMMSSdd**.</span></span>                                                                                                                       |
      |       <span data-ttu-id="99bf8-358">**GS7**</span><span class="sxs-lookup"><span data-stu-id="99bf8-358">**GS7**</span></span>        |                                                                                                                   <span data-ttu-id="99bf8-359">选择**揟-运输数据协调委员会 (TDCC)**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-359">Select **T - Transportation Data Coordinating Committee (TDCC)**.</span></span>                                                                                                                   |
      |       <span data-ttu-id="99bf8-360">**GS8**</span><span class="sxs-lookup"><span data-stu-id="99bf8-360">**GS8**</span></span>        |                                                                                                                      <span data-ttu-id="99bf8-361">验证是否已作为输入 EDI 版本**00401**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-361">Verify that the EDI version has been entered as **00401**.</span></span>                                                                                                                       |


8. <span data-ttu-id="99bf8-362">在执行以下任务**Contoso-> Fabrikam**选项卡。</span><span class="sxs-lookup"><span data-stu-id="99bf8-362">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="99bf8-363">在本演练中，我们指定的选项卡中所需的值，以便可以成功创建协议。</span><span class="sxs-lookup"><span data-stu-id="99bf8-363">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="99bf8-364">若要成功创建协议，两个单向协议选项卡必须具有定义为值**ISA5**， **ISA6**， **ISA7**，以及**ISA8**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-364">To successfully create an agreement, both one-way agreement tabs must have values defined for **ISA5**, **ISA6**, **ISA7**, and **ISA8**.</span></span>  

   1.  <span data-ttu-id="99bf8-365">上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，并**ISA8**) 的测试消息中这些标头字段的值相对应。</span><span class="sxs-lookup"><span data-stu-id="99bf8-365">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  

       > [!NOTE]
       >  <span data-ttu-id="99bf8-366">对于本演练中，设置**ISA5**到**ZZ**， **ISA6**到**1234567**， **ISA7**到**ZZ**，并**ISA8**到**7654321**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-366">For this walkthrough, set **ISA5** to **ZZ**, **ISA6** to **1234567**, **ISA7** to **ZZ**, and **ISA8** to **7654321**.</span></span>  

9. <span data-ttu-id="99bf8-367">单击 **“应用”**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-367">Click **Apply**.</span></span>  

10. <span data-ttu-id="99bf8-368">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="99bf8-368">Click **OK**.</span></span> <span data-ttu-id="99bf8-369">中列出新添加的协议**协议**一部分**参与方和业务配置文件**窗格。</span><span class="sxs-lookup"><span data-stu-id="99bf8-369">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="99bf8-370">默认情况下，启用新添加的协议。</span><span class="sxs-lookup"><span data-stu-id="99bf8-370">The newly added agreement is enabled by default.</span></span>  

### <a name="testing-the-walkthrough"></a><span data-ttu-id="99bf8-371">测试演练</span><span class="sxs-lookup"><span data-stu-id="99bf8-371">Testing the Walkthrough</span></span>  
 <span data-ttu-id="99bf8-372">本部分提供有关如何测试演练的信息。</span><span class="sxs-lookup"><span data-stu-id="99bf8-372">This section provides information on how to test the walkthrough.</span></span>  

##### <a name="to-test-the-solution"></a><span data-ttu-id="99bf8-373">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="99bf8-373">To test the solution</span></span>  

1. <span data-ttu-id="99bf8-374">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender 文件夹中的 Sender.csproj 项目。</span><span class="sxs-lookup"><span data-stu-id="99bf8-374">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the Sender.csproj project in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender folder.</span></span>  

2. <span data-ttu-id="99bf8-375">在 HttpSender.cs 中，确保未注释以下行（紧接在 //Request Asynchronous MDN 注释行下面）：</span><span class="sxs-lookup"><span data-stu-id="99bf8-375">In HttpSender.cs, make sure that the following line is not commented out (immediately below the //Request Asynchronous MDN comment line):</span></span>  

   ```  
   Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864.edi", FileMode.Open, FileAccess.Read);  
   ```  

3. <span data-ttu-id="99bf8-376">确保未注释以下行（紧接在 //Request Synchronous MDN 注释行下面）：</span><span class="sxs-lookup"><span data-stu-id="99bf8-376">Make sure that the following line is commented out (immediately below the //Request Synchronous MDN comment line):</span></span>  

   ```  
   Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864-Sync.edi", FileMode.Open, FileAccess.Read);  
   ```  

4. <span data-ttu-id="99bf8-377">生成此项目。</span><span class="sxs-lookup"><span data-stu-id="99bf8-377">Build this project.</span></span>  

5. <span data-ttu-id="99bf8-378">在 Windows 资源管理器中，移至 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\AS2 Tutorial。</span><span class="sxs-lookup"><span data-stu-id="99bf8-378">In Windows Explorer, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial.</span></span> <span data-ttu-id="99bf8-379">在记事本中打开 X12_00401_864.edi。</span><span class="sxs-lookup"><span data-stu-id="99bf8-379">Open X12_00401_864.edi in Notepad.</span></span> <span data-ttu-id="99bf8-380">删除用于定义 Disposition-Notification-Options 头的行，然后保存该文件。</span><span class="sxs-lookup"><span data-stu-id="99bf8-380">Delete the line defining the Disposition-Notification-Options header, and then save the file.</span></span>  

6. <span data-ttu-id="99bf8-381">在 Windows 资源管理器，转至[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug 并执行**Sender.exe**。</span><span class="sxs-lookup"><span data-stu-id="99bf8-381">In Windows Explorer, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug and execute **Sender.exe**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="99bf8-382">在此实例中运行 Sender.exe 将把消息 X12_00401_864.edi 发送到 Contoso 虚拟目录（BTS http 接收位置）。</span><span class="sxs-lookup"><span data-stu-id="99bf8-382">Running Sender.exe in this instance posts the message X12_00401_864.edi to the Contoso virtual directory (the BTS http receive location).</span></span>  

7. <span data-ttu-id="99bf8-383">打开您创建的用于将 EDI 负载发送到 (\EDI_to_Contoso) 的 Contoso 本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="99bf8-383">Open the Contoso local folder that you created to send the EDI payload to (\EDI_to_Contoso).</span></span> <span data-ttu-id="99bf8-384">验证该文件夹中有一个 .XML 文件。</span><span class="sxs-lookup"><span data-stu-id="99bf8-384">Verify that there is a .XML file in the folder.</span></span> <span data-ttu-id="99bf8-385">打开该 XML 文件并验证它包含有一个 864 事务集。</span><span class="sxs-lookup"><span data-stu-id="99bf8-385">Open the XML file and verify that it contains an 864 transaction set.</span></span>  

8. <span data-ttu-id="99bf8-386">打开 MDN 要返回的 Fabrikam 本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="99bf8-386">Open the Fabrikam local folder to which the MDN is returned.</span></span> <span data-ttu-id="99bf8-387">在 Windows 资源管理器，转至[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_MDNToFabrikam。</span><span class="sxs-lookup"><span data-stu-id="99bf8-387">In Windows Explorer, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_MDNToFabrikam.</span></span> <span data-ttu-id="99bf8-388">打开记事本中的消息文件，并验证该 MDN。</span><span class="sxs-lookup"><span data-stu-id="99bf8-388">Open the message file in a notepad and verify the MDN.</span></span> <span data-ttu-id="99bf8-389">验证在 MDN 中，AS2-From 是 Contoso，AS2-To 是 Fabrikam。</span><span class="sxs-lookup"><span data-stu-id="99bf8-389">Verify that in the MDN AS2-From is Contoso and AS2-To is Fabrikam.</span></span>  

9. <span data-ttu-id="99bf8-390">在记事本中打开测试消息 X12_00401_864.edi，验证 \EDI_to_Contoso 本地文件夹的输出消息中的事务集与 X12_00401_864.edi 输入消息中的事务集相对应。</span><span class="sxs-lookup"><span data-stu-id="99bf8-390">Open the test message X12_00401_864.edi in Notepad, and verify that the transaction set in the output message in the \EDI_to_Contoso local folder corresponds to the transaction set in the X12_00401_864.edi input message.</span></span>  

## <a name="see-also"></a><span data-ttu-id="99bf8-391">请参阅</span><span class="sxs-lookup"><span data-stu-id="99bf8-391">See Also</span></span>  
 [<span data-ttu-id="99bf8-392">开发和配置 BizTalk Server AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="99bf8-392">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)