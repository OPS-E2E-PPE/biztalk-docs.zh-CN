---
title: POP3 适配器是什么？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- POP3 adapters, availability
- authenticating, POP3 adapters
- POP3 adapters, data duplication
- data duplication
- POP3 adapters, receive adapters
- high availability, POP3 adapters
- POP3 adapters, supported platforms
- POP3 adapters, authenticating
- POP3 adapters, algorithims
- receive adapters, POP3 adapters
ms.assetid: 05e9598b-cdfe-4216-b6bf-1b84f8ddfeae
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c298af8c35aaea90c9f078dbf43d5ff8483bc742
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242813"
---
# <a name="what-is-the-pop3-adapter"></a><span data-ttu-id="89263-103">POP3 适配器是什么？</span><span class="sxs-lookup"><span data-stu-id="89263-103">What Is the POP3 Adapter?</span></span>
<span data-ttu-id="89263-104">本部分将介绍 POP3 接收适配器。</span><span class="sxs-lookup"><span data-stu-id="89263-104">This section describes the POP3 receive adapter.</span></span>  
  
## <a name="pop3-receive-adapter"></a><span data-ttu-id="89263-105">POP3 接收适配器</span><span class="sxs-lookup"><span data-stu-id="89263-105">POP3 Receive Adapter</span></span>  
 <span data-ttu-id="89263-106">POP3 接收适配器，可以将数据从启用 POP3 的邮箱移到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="89263-106">The POP3 receive adapter enables you to move data from a POP3-enabled mailbox to BizTalk Server.</span></span>  
  
 <span data-ttu-id="89263-107">主要功能的 POP3 接收适配器是：</span><span class="sxs-lookup"><span data-stu-id="89263-107">The key features of the POP3 receive adapter are:</span></span>  
  
-   <span data-ttu-id="89263-108">请求按需从 POP3 服务器邮箱的文件。</span><span class="sxs-lookup"><span data-stu-id="89263-108">Pulling files from the POP3 server mailbox on demand.</span></span>  
  
-   <span data-ttu-id="89263-109">基于可配置的计划运行轮询。</span><span class="sxs-lookup"><span data-stu-id="89263-109">Running polls based on a configurable schedule.</span></span>  
  
-   <span data-ttu-id="89263-110">轮询 POP3 服务器邮箱，并将数据发送到 BizTalk Server 直接。</span><span class="sxs-lookup"><span data-stu-id="89263-110">Polling the POP3 server mailbox and sending data directly to BizTalk Server.</span></span>  
  
-   <span data-ttu-id="89263-111">指定 POP3 服务器邮箱为 IP 地址或主机名、 端口、 用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="89263-111">Specifying the POP3 server mailbox as an IP address or host name, port, user name, and password.</span></span>  
  
-   <span data-ttu-id="89263-112">若要从需要安全套接字层 (SSL) 连接的邮件服务器下载电子邮件的功能。</span><span class="sxs-lookup"><span data-stu-id="89263-112">Ability to download e-mail from mail servers that require Secure Sockets Layer (SSL) connections.</span></span>  
  
-   <span data-ttu-id="89263-113">确保文件送达。</span><span class="sxs-lookup"><span data-stu-id="89263-113">Guaranteed file delivery.</span></span>  
  
-   <span data-ttu-id="89263-114">隐式 MIME 处理。</span><span class="sxs-lookup"><span data-stu-id="89263-114">Implicit MIME processing.</span></span> <span data-ttu-id="89263-115">不需要使用 POP3 适配器时，在接收管道中使用 MIME 解码器。</span><span class="sxs-lookup"><span data-stu-id="89263-115">It is not necessary to use a MIME decoder in a receive pipeline when using the POP3 adapter.</span></span>  
  
## <a name="pop3-adapter-supported-platforms"></a><span data-ttu-id="89263-116">POP3 适配器支持的平台</span><span class="sxs-lookup"><span data-stu-id="89263-116">POP3 Adapter Supported Platforms</span></span>  
 <span data-ttu-id="89263-117">POP3 适配器可使用任何符合以下 Rfc 的 POP3 服务器：</span><span class="sxs-lookup"><span data-stu-id="89263-117">The POP3 adapter is designed to work with any POP3 servers that conform to the following RFCs:</span></span>  
  
- <span data-ttu-id="89263-118">**RFC 1939。**</span><span class="sxs-lookup"><span data-stu-id="89263-118">**RFC 1939.**</span></span> <span data-ttu-id="89263-119">邮局协议版本 3 (请参阅[ http://go.microsoft.com/fwlink/?LinkId=58808 ](http://go.microsoft.com/fwlink/?LinkId=58808))</span><span class="sxs-lookup"><span data-stu-id="89263-119">Post Office Protocol Version 3 (see [http://go.microsoft.com/fwlink/?LinkId=58808](http://go.microsoft.com/fwlink/?LinkId=58808))</span></span>  
  
- <span data-ttu-id="89263-120">**RFC 1734。**</span><span class="sxs-lookup"><span data-stu-id="89263-120">**RFC 1734.**</span></span> <span data-ttu-id="89263-121">POP3 身份验证命令 (请参阅[ http://go.microsoft.com/fwlink/?LinkId=58809 ](http://go.microsoft.com/fwlink/?LinkId=58809))</span><span class="sxs-lookup"><span data-stu-id="89263-121">POP3 AUTHentication command (see [http://go.microsoft.com/fwlink/?LinkId=58809](http://go.microsoft.com/fwlink/?LinkId=58809))</span></span>  
  
- <span data-ttu-id="89263-122">**RFC 2045。**</span><span class="sxs-lookup"><span data-stu-id="89263-122">**RFC 2045.**</span></span> <span data-ttu-id="89263-123">多用途 Internet 邮件扩展 (MIME) 第 1 部分：Internet 消息正文的格式 (请参阅[ http://go.microsoft.com/fwlink/?LinkId=58810 ](http://go.microsoft.com/fwlink/?LinkId=58810))</span><span class="sxs-lookup"><span data-stu-id="89263-123">Multipurpose Internet Mail Extensions (MIME) Part One: Format of Internet Message Bodies (see [http://go.microsoft.com/fwlink/?LinkId=58810](http://go.microsoft.com/fwlink/?LinkId=58810))</span></span>  
  
- <span data-ttu-id="89263-124">**RFC 2046。**</span><span class="sxs-lookup"><span data-stu-id="89263-124">**RFC 2046.**</span></span> <span data-ttu-id="89263-125">多用途 Internet 邮件扩展 (MIME) 第二部分：媒体类型 (请参阅[ http://go.microsoft.com/fwlink/?LinkId=58811 ](http://go.microsoft.com/fwlink/?LinkId=58811))</span><span class="sxs-lookup"><span data-stu-id="89263-125">Multipurpose Internet Mail Extensions (MIME) Part Two: Media Types (see [http://go.microsoft.com/fwlink/?LinkId=58811](http://go.microsoft.com/fwlink/?LinkId=58811))</span></span>  
  
- <span data-ttu-id="89263-126">**RFC 最多允许 2047年。**</span><span class="sxs-lookup"><span data-stu-id="89263-126">**RFC 2047.**</span></span> <span data-ttu-id="89263-127">MIME （多用途 Internet 邮件扩展） 第 3 部分：为非 ASCII 文本消息标头扩展 (请参阅[ http://go.microsoft.com/fwlink/?LinkId=58812 ](http://go.microsoft.com/fwlink/?LinkId=58812))</span><span class="sxs-lookup"><span data-stu-id="89263-127">MIME (Multipurpose Internet Mail Extensions) Part Three: Message Header Extensions for Non-ASCII Text (see [http://go.microsoft.com/fwlink/?LinkId=58812](http://go.microsoft.com/fwlink/?LinkId=58812))</span></span>  
  
  <span data-ttu-id="89263-128">针对 Microsoft Exchange Server 2003，POP3 适配器已进行广泛测试。</span><span class="sxs-lookup"><span data-stu-id="89263-128">The POP3 adapter was tested extensively against Microsoft Exchange Server 2003.</span></span>  
  
## <a name="considerations-for-preventing-data-duplication-when-using-the-pop3-adapter"></a><span data-ttu-id="89263-129">使用 POP3 适配器时防止数据重复的注意事项</span><span class="sxs-lookup"><span data-stu-id="89263-129">Considerations for Preventing Data Duplication When Using the POP3 Adapter</span></span>  
 <span data-ttu-id="89263-130">POP3 适配器不是事务性适配器，因此可能出现处理同一消息的多个副本可能会导致数据重复。</span><span class="sxs-lookup"><span data-stu-id="89263-130">The POP3 adapter is not a transactional adapter and therefore is subject to processing multiple copies of the same message, potentially causing data duplication.</span></span> <span data-ttu-id="89263-131">此外，可以 POP3 适配器将在以下方案中提供的一条消息的重复副本：</span><span class="sxs-lookup"><span data-stu-id="89263-131">It is possible that the POP3 adapter will deliver duplicate copies of a message in the following scenarios:</span></span>  
  
-   <span data-ttu-id="89263-132">POP3 适配器从邮箱配置来监视电子邮件已成功提交到 BizTalk Server 进行处理后始终删除电子邮件。</span><span class="sxs-lookup"><span data-stu-id="89263-132">The POP3 adapter always deletes e-mails from the mailbox that it is configured to monitor after the e-mail has been successfully submitted to BizTalk Server for processing.</span></span> <span data-ttu-id="89263-133">如果 POP3 适配器从邮箱中检索电子邮件、 将电子邮件发送至 BizTalk Server 提交进行处理，并且无法删除邮箱中的电子邮件，电子邮件将重新提交到 BizTalk Server 的下一步时间 POP3 适配器轮询该邮箱。</span><span class="sxs-lookup"><span data-stu-id="89263-133">If the POP3 adapter retrieves an e-mail from a mailbox, submits the e-mail to BizTalk Server for processing, and fails to delete the e-mail from the mailbox, the e-mail will be resubmitted to BizTalk Server the next time that the POP3 adapter polls the mailbox.</span></span>  
  
-   <span data-ttu-id="89263-134">如果 POP3 适配器在单独的 BizTalk 主机实例中的多个实例正在同时监视同一个邮箱，并且 POP3 服务器允许对其邮箱进行多个并发连接，该适配器可能传送消息的重复副本。</span><span class="sxs-lookup"><span data-stu-id="89263-134">If multiple instances of the POP3 adapter in separate BizTalk Host instances are monitoring the same mailbox simultaneously and the POP3 server allows multiple concurrent connections to its mailboxes, then the adapter may deliver duplicate copies of messages.</span></span>  
  
## <a name="high-availability-for-the-pop3-adapter"></a><span data-ttu-id="89263-135">POP3 适配器的高可用性</span><span class="sxs-lookup"><span data-stu-id="89263-135">High Availability for the POP3 Adapter</span></span>  
 <span data-ttu-id="89263-136">某些 POP3 服务器允许与给定邮箱的多个并发连接。</span><span class="sxs-lookup"><span data-stu-id="89263-136">Some POP3 servers permit multiple concurrent connections to a given mailbox.</span></span> <span data-ttu-id="89263-137">如果 POP3 适配器的多个实例配置为从 POP3 服务器上的邮箱中检索邮件可能出现数据重复。</span><span class="sxs-lookup"><span data-stu-id="89263-137">If more than one instance of the POP3 adapter is configured to retrieve mail from a mailbox on such a POP3 server then data duplication can occur.</span></span> <span data-ttu-id="89263-138">因此应配置 POP3 适配器从允许多个并发连接的邮箱中检索邮件的一个实例。</span><span class="sxs-lookup"><span data-stu-id="89263-138">Therefore you should configure only one instance of the POP3 adapter to retrieve mail from a mailbox that permits multiple concurrent connections.</span></span>  
  
 <span data-ttu-id="89263-139">若要为此方案中的 POP3 适配器提供容错，单个 POP3 适配器接收处理程序应配置为在群集 BizTalk 主机中运行。</span><span class="sxs-lookup"><span data-stu-id="89263-139">To provide fault tolerance for the POP3 adapter in this scenario, a single POP3 adapter receive handler should be configured to run in a clustered BizTalk Host.</span></span> <span data-ttu-id="89263-140">有关详细信息请参阅[群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。</span><span class="sxs-lookup"><span data-stu-id="89263-140">For more information see [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span></span>  
  
## <a name="authentication-warnings-when-multiple-instances-of-the-pop3-adapter-connect-to-the-same-mailbox"></a><span data-ttu-id="89263-141">POP3 适配器的多个实例连接到同一邮箱时的验证警告</span><span class="sxs-lookup"><span data-stu-id="89263-141">Authentication Warnings When Multiple Instances of the POP3 Adapter Connect to the Same Mailbox</span></span>  
 <span data-ttu-id="89263-142">BizTalk Server 可能配置为具有从同一邮箱中检索邮件的 POP3 适配器的多个实例。</span><span class="sxs-lookup"><span data-stu-id="89263-142">BizTalk Server may be configured to have more than one instance of the POP3 adapter retrieve mail from the same mailbox.</span></span> <span data-ttu-id="89263-143">在这种情况下，很可能身份验证警告，可能会由于某些 POP3 服务器采用了锁定机制在 BizTalk Server 应用程序日志中进行生成。</span><span class="sxs-lookup"><span data-stu-id="89263-143">In such a case, it is possible that authentication warnings may be generated in the BizTalk Server Application log because of the locking mechanism employed by some POP3 servers.</span></span> <span data-ttu-id="89263-144">这些警告将对 POP3 适配器功能没有任何影响，可以在此方案中安全地忽略。</span><span class="sxs-lookup"><span data-stu-id="89263-144">These warnings will have no impact on the POP3 adapter functionality and can be safely ignored in this scenario.</span></span>  
  
## <a name="encrypted-messages-received-by-the-pop3-adapter-that-are-sent-to-the-suspended-queue-may-be-viewable-in-clear-text"></a><span data-ttu-id="89263-145">发送到挂起队列 POP3 适配器接收加密消息可能会以明文形式的可视区域大小</span><span class="sxs-lookup"><span data-stu-id="89263-145">Encrypted Messages Received by the POP3 Adapter that are sent to the Suspended Queue may be Viewable in Clear Text</span></span>  
 <span data-ttu-id="89263-146">可以配置 POP3 适配器进行解密进行数字加密的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="89263-146">You can configure the POP3 adapter to decrypt digitally encrypted e-mails.</span></span> <span data-ttu-id="89263-147">这是通过设置**应用 MIME 解码**属性设置为**True**的接收位置，使用 POP3 适配器。</span><span class="sxs-lookup"><span data-stu-id="89263-147">This is done by setting the **Apply MIME Decoding** property to **True** for receive locations that use the POP3 adapter.</span></span> <span data-ttu-id="89263-148">如果 POP3 适配器收到经数字加密的电子邮件并**应用 MIME 解码**接收位置属性设置为**True** POP3 适配器尝试解密该电子邮件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="89263-148">If the POP3 Adapter receives a digitally encrypted e-mail and the **Apply MIME Decoding** property for the receive location is set to **True** then the POP3 adapter attempts to decrypt the e-mail as follows:</span></span>  
  
- <span data-ttu-id="89263-149">POP3 适配器搜索匹配用来加密电子邮件的公用证书的私钥证书。</span><span class="sxs-lookup"><span data-stu-id="89263-149">The POP3 Adapter searches for a private certificate that matches the public certificate used to encrypt the e-mail.</span></span> <span data-ttu-id="89263-150">私钥证书必须在运行 POP3 接收主机实例的服务器的个人证书存储中处理程序绑定到。</span><span class="sxs-lookup"><span data-stu-id="89263-150">The private certificate must be in the Personal certificate store of the server that is running the host instance that the POP3 receive handler is bound to.</span></span>  
  
- <span data-ttu-id="89263-151">如果 POP3 适配器找到相应的私钥证书，则使用该私钥证书对电子邮件消息进行解密。</span><span class="sxs-lookup"><span data-stu-id="89263-151">If the POP3 Adapter locates a corresponding private certificate, it uses the private certificate to decrypt the e-mail message.</span></span>  
  
- <span data-ttu-id="89263-152">电子邮件是解密，并保存到 BizTalk MessageBox。</span><span class="sxs-lookup"><span data-stu-id="89263-152">The e-mail is decrypted and persisted to the BizTalk MessageBox.</span></span>  
  
  <span data-ttu-id="89263-153">如果经过解密并保存到 BizTalk MessageBox 中后被挂起一条消息，消息的内容将以明文形式在 BizTalk 挂起队列中可见。</span><span class="sxs-lookup"><span data-stu-id="89263-153">If a message is suspended after being decrypted and persisted to the BizTalk MessageBox, the contents of the message will be visible in clear text in the BizTalk suspended queue.</span></span>  
  
  <span data-ttu-id="89263-154">如果需要阻止的挂起队列中的安全消息中文本的显示，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="89263-154">If you need to prevent the display of secure message text in the suspended queue, follow these steps:</span></span>  
  
- <span data-ttu-id="89263-155">设置**应用 MIME 解码**属性设置为**False**为该使用 POP3 适配器接收位置和解密使用 SMIME 管道组件的管道中的消息。</span><span class="sxs-lookup"><span data-stu-id="89263-155">Set the **Apply MIME Decoding** property to **False** for receive locations that use the POP3 adapter and decrypt the message in a pipeline with the SMIME pipeline component.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="89263-156">此方法将阻止你无法升级到消息上下文的电子邮件特定属性。</span><span class="sxs-lookup"><span data-stu-id="89263-156">This approach will prevent you from being able to promote e-mail specific properties to the message context.</span></span>  
  
- <span data-ttu-id="89263-157">如果你需要升级到消息上下文的电子邮件特定属性，并确保其路由到挂起队列加密的消息保持加密，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="89263-157">If you need to promote e-mail specific properties to the message context and ensure that encrypted messages remain encrypted if they are routed to the suspended queue, follow these steps:</span></span>  
  
  -   <span data-ttu-id="89263-158">选中选项**失败消息启用路由功能**使用 POP3 适配器的接收位置所在接收端口上。</span><span class="sxs-lookup"><span data-stu-id="89263-158">Check the option to **Enable routing for failed messages** on the receive port that houses the receive location(s) that use the POP3 adapter.</span></span>  
  
  -   <span data-ttu-id="89263-159">创建一个业务流程订阅到使用 POP3 适配器的接收位置所在接收端口传递失败的消息。</span><span class="sxs-lookup"><span data-stu-id="89263-159">Create an orchestration to subscribe to messages that fail delivery to the receive port that houses the receive location(s) that use the POP3 adapter.</span></span>  
  
  -   <span data-ttu-id="89263-160">配置加密使用 SMIME 管道组件的管道中的消息的发送端口业务流程。</span><span class="sxs-lookup"><span data-stu-id="89263-160">Configure the orchestration with a send port that encrypts the message in a pipeline using the SMIME pipeline component.</span></span>  
  
  -   <span data-ttu-id="89263-161">使用挂起形状，以挂起业务流程实例和消息配置业务流程。</span><span class="sxs-lookup"><span data-stu-id="89263-161">Configure the orchestration with a suspend shape to suspend the orchestration instance and the message.</span></span>  
  
  -   <span data-ttu-id="89263-162">生成和部署业务流程、 接收端口绑定到相应部署的业务流程。</span><span class="sxs-lookup"><span data-stu-id="89263-162">Build and deploy the orchestration, bind the deployed orchestration to the appropriate receive port.</span></span>  
  
## <a name="maximum-message-size-supported-by-the-pop3-adapter"></a><span data-ttu-id="89263-163">POP3 适配器支持的最大消息大小</span><span class="sxs-lookup"><span data-stu-id="89263-163">Maximum Message Size Supported by the POP3 Adapter</span></span>  
 <span data-ttu-id="89263-164">POP3 适配器进行了测试和支持接收消息最多为 50 MB 的大小。</span><span class="sxs-lookup"><span data-stu-id="89263-164">The POP3 adapter has been tested with and supports receiving messages up to 50 MB in size.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89263-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="89263-165">See Also</span></span>  
 [<span data-ttu-id="89263-166">POP3 适配器</span><span class="sxs-lookup"><span data-stu-id="89263-166">POP3 Adapter</span></span>](../core/pop3-adapter.md)