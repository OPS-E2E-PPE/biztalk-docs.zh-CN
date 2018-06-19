---
title: POP3 适配器概述 | Microsoft Docs
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
ms.openlocfilehash: 592e0475b607de3f9df528a4bab777aa0fb7635d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290621"
---
# <a name="what-is-the-pop3-adapter"></a><span data-ttu-id="fae30-103">POP3 适配器概述</span><span class="sxs-lookup"><span data-stu-id="fae30-103">What Is the POP3 Adapter?</span></span>
<span data-ttu-id="fae30-104">本部分将介绍 POP3 接收适配器。</span><span class="sxs-lookup"><span data-stu-id="fae30-104">This section describes the POP3 receive adapter.</span></span>  
  
## <a name="pop3-receive-adapter"></a><span data-ttu-id="fae30-105">POP3 接收适配器</span><span class="sxs-lookup"><span data-stu-id="fae30-105">POP3 Receive Adapter</span></span>  
 <span data-ttu-id="fae30-106">使用 POP3 接收适配器，可以将数据从启用 POP3 的邮箱移至 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="fae30-106">The POP3 receive adapter enables you to move data from a POP3-enabled mailbox to BizTalk Server.</span></span>  
  
 <span data-ttu-id="fae30-107">POP3 接收适配器的主要功能包括：</span><span class="sxs-lookup"><span data-stu-id="fae30-107">The key features of the POP3 receive adapter are:</span></span>  
  
-   <span data-ttu-id="fae30-108">根据需要从 POP3 服务器邮箱请求文件。</span><span class="sxs-lookup"><span data-stu-id="fae30-108">Pulling files from the POP3 server mailbox on demand.</span></span>  
  
-   <span data-ttu-id="fae30-109">根据可配置计划运行轮询。</span><span class="sxs-lookup"><span data-stu-id="fae30-109">Running polls based on a configurable schedule.</span></span>  
  
-   <span data-ttu-id="fae30-110">对 POP3 服务器邮箱进行轮询并将数据直接发送到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="fae30-110">Polling the POP3 server mailbox and sending data directly to BizTalk Server.</span></span>  
  
-   <span data-ttu-id="fae30-111">将 POP3 服务器邮箱指定为 IP 地址、主机名、端口、用户名或密码。</span><span class="sxs-lookup"><span data-stu-id="fae30-111">Specifying the POP3 server mailbox as an IP address or host name, port, user name, and password.</span></span>  
  
-   <span data-ttu-id="fae30-112">能够从需要安全套接字层 (SSL) 连接的邮件服务器中下载电子邮件。</span><span class="sxs-lookup"><span data-stu-id="fae30-112">Ability to download e-mail from mail servers that require Secure Sockets Layer (SSL) connections.</span></span>  
  
-   <span data-ttu-id="fae30-113">确保文件送达。</span><span class="sxs-lookup"><span data-stu-id="fae30-113">Guaranteed file delivery.</span></span>  
  
-   <span data-ttu-id="fae30-114">隐式 MIME 处理。</span><span class="sxs-lookup"><span data-stu-id="fae30-114">Implicit MIME processing.</span></span> <span data-ttu-id="fae30-115">使用 POP3 适配器时，无需在接收管道中使用 MIME 解码器。</span><span class="sxs-lookup"><span data-stu-id="fae30-115">It is not necessary to use a MIME decoder in a receive pipeline when using the POP3 adapter.</span></span>  
  
## <a name="pop3-adapter-supported-platforms"></a><span data-ttu-id="fae30-116">POP3 适配器支持的平台</span><span class="sxs-lookup"><span data-stu-id="fae30-116">POP3 Adapter Supported Platforms</span></span>  
 <span data-ttu-id="fae30-117">POP3 适配器设计为与符合以下 RFC 的任何 POP3 服务器协同工作：</span><span class="sxs-lookup"><span data-stu-id="fae30-117">The POP3 adapter is designed to work with any POP3 servers that conform to the following RFCs:</span></span>  
  
-   <span data-ttu-id="fae30-118">**RFC 1939。**</span><span class="sxs-lookup"><span data-stu-id="fae30-118">**RFC 1939.**</span></span> <span data-ttu-id="fae30-119">邮局协议版本 3 (请参阅[http://go.microsoft.com/fwlink/?LinkId=58808](http://go.microsoft.com/fwlink/?LinkId=58808))</span><span class="sxs-lookup"><span data-stu-id="fae30-119">Post Office Protocol Version 3 (see [http://go.microsoft.com/fwlink/?LinkId=58808](http://go.microsoft.com/fwlink/?LinkId=58808))</span></span>  
  
-   <span data-ttu-id="fae30-120">**RFC 1734。**</span><span class="sxs-lookup"><span data-stu-id="fae30-120">**RFC 1734.**</span></span> <span data-ttu-id="fae30-121">POP3 身份验证命令 (请参阅[http://go.microsoft.com/fwlink/?LinkId=58809](http://go.microsoft.com/fwlink/?LinkId=58809))</span><span class="sxs-lookup"><span data-stu-id="fae30-121">POP3 AUTHentication command (see [http://go.microsoft.com/fwlink/?LinkId=58809](http://go.microsoft.com/fwlink/?LinkId=58809))</span></span>  
  
-   <span data-ttu-id="fae30-122">**RFC 2045。**</span><span class="sxs-lookup"><span data-stu-id="fae30-122">**RFC 2045.**</span></span> <span data-ttu-id="fae30-123">多用途 Internet 邮件扩展 (MIME) 一部分一个： Internet 消息正文格式 (请参阅[http://go.microsoft.com/fwlink/?LinkId=58810](http://go.microsoft.com/fwlink/?LinkId=58810))</span><span class="sxs-lookup"><span data-stu-id="fae30-123">Multipurpose Internet Mail Extensions (MIME) Part One: Format of Internet Message Bodies (see [http://go.microsoft.com/fwlink/?LinkId=58810](http://go.microsoft.com/fwlink/?LinkId=58810))</span></span>  
  
-   <span data-ttu-id="fae30-124">**RFC 2046。**</span><span class="sxs-lookup"><span data-stu-id="fae30-124">**RFC 2046.**</span></span> <span data-ttu-id="fae30-125">多用途 Internet 邮件扩展 (MIME) 一部分两种： 媒体类型 (请参阅[http://go.microsoft.com/fwlink/?LinkId=58811](http://go.microsoft.com/fwlink/?LinkId=58811))</span><span class="sxs-lookup"><span data-stu-id="fae30-125">Multipurpose Internet Mail Extensions (MIME) Part Two: Media Types (see [http://go.microsoft.com/fwlink/?LinkId=58811](http://go.microsoft.com/fwlink/?LinkId=58811))</span></span>  
  
-   <span data-ttu-id="fae30-126">**RFC 2047。**</span><span class="sxs-lookup"><span data-stu-id="fae30-126">**RFC 2047.**</span></span> <span data-ttu-id="fae30-127">非 ASCII 文本的 MIME （多用途 Internet 邮件扩展） 第三部分： 消息标头扩展 (请参阅[http://go.microsoft.com/fwlink/?LinkId=58812](http://go.microsoft.com/fwlink/?LinkId=58812))</span><span class="sxs-lookup"><span data-stu-id="fae30-127">MIME (Multipurpose Internet Mail Extensions) Part Three: Message Header Extensions for Non-ASCII Text (see [http://go.microsoft.com/fwlink/?LinkId=58812](http://go.microsoft.com/fwlink/?LinkId=58812))</span></span>  
  
 <span data-ttu-id="fae30-128">根据 Microsoft Exchange Server 2003 对 POP3 适配器进行了大量的测试。</span><span class="sxs-lookup"><span data-stu-id="fae30-128">The POP3 adapter was tested extensively against Microsoft Exchange Server 2003.</span></span>  
  
## <a name="considerations-for-preventing-data-duplication-when-using-the-pop3-adapter"></a><span data-ttu-id="fae30-129">使用 POP3 适配器时防止数据重复的注意事项</span><span class="sxs-lookup"><span data-stu-id="fae30-129">Considerations for Preventing Data Duplication When Using the POP3 Adapter</span></span>  
 <span data-ttu-id="fae30-130">POP3 适配器不是事务性适配器，因此可能出现处理同一消息的多个副本的情况，这可能导致数据重复。</span><span class="sxs-lookup"><span data-stu-id="fae30-130">The POP3 adapter is not a transactional adapter and therefore is subject to processing multiple copies of the same message, potentially causing data duplication.</span></span> <span data-ttu-id="fae30-131">在以下情况中，POP3 适配器可能会传送消息的重复副本：</span><span class="sxs-lookup"><span data-stu-id="fae30-131">It is possible that the POP3 adapter will deliver duplicate copies of a message in the following scenarios:</span></span>  
  
-   <span data-ttu-id="fae30-132">在电子邮件已成功提交到 BizTalk Server 以进行处理后，POP3 适配器将始终从配置为要监视的邮箱中删除电子邮件。</span><span class="sxs-lookup"><span data-stu-id="fae30-132">The POP3 adapter always deletes e-mails from the mailbox that it is configured to monitor after the e-mail has been successfully submitted to BizTalk Server for processing.</span></span> <span data-ttu-id="fae30-133">如果 POP3 适配器从邮箱中检索到电子邮件并将其提交给 BizTalk Server 以便进行处理，但未能从邮箱中删除该电子邮件，那么，在 POP3 适配器下一次轮询该邮箱时，会将该电子邮件重新提交给 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="fae30-133">If the POP3 adapter retrieves an e-mail from a mailbox, submits the e-mail to BizTalk Server for processing, and fails to delete the e-mail from the mailbox, the e-mail will be resubmitted to BizTalk Server the next time that the POP3 adapter polls the mailbox.</span></span>  
  
-   <span data-ttu-id="fae30-134">如果位于单独 BizTalk 主机实例中的多个 POP3 适配器实例正在同时监视同一个邮箱，并且 POP3 服务器允许与其邮箱进行多个并行连接，则该适配器可能传送消息的重复副本。</span><span class="sxs-lookup"><span data-stu-id="fae30-134">If multiple instances of the POP3 adapter in separate BizTalk Host instances are monitoring the same mailbox simultaneously and the POP3 server allows multiple concurrent connections to its mailboxes, then the adapter may deliver duplicate copies of messages.</span></span>  
  
## <a name="high-availability-for-the-pop3-adapter"></a><span data-ttu-id="fae30-135">POP3 适配器的高可用性</span><span class="sxs-lookup"><span data-stu-id="fae30-135">High Availability for the POP3 Adapter</span></span>  
 <span data-ttu-id="fae30-136">某些 POP3 服务器允许与给定邮箱进行多个并行连接。</span><span class="sxs-lookup"><span data-stu-id="fae30-136">Some POP3 servers permit multiple concurrent connections to a given mailbox.</span></span> <span data-ttu-id="fae30-137">如果将多个 POP3 适配器实例配置为从此类 POP3 服务器上的邮箱中检索邮件，则可能出现数据重复。</span><span class="sxs-lookup"><span data-stu-id="fae30-137">If more than one instance of the POP3 adapter is configured to retrieve mail from a mailbox on such a POP3 server then data duplication can occur.</span></span> <span data-ttu-id="fae30-138">因此，应当只将一个 POP3 适配器实例配置为从允许多个并行连接的邮箱中检索邮件。</span><span class="sxs-lookup"><span data-stu-id="fae30-138">Therefore you should configure only one instance of the POP3 adapter to retrieve mail from a mailbox that permits multiple concurrent connections.</span></span>  
  
 <span data-ttu-id="fae30-139">若要为此方案中的 POP3 适配器提供容错功能，则应将单个 POP3 适配器接收处理程序配置为在群集 BizTalk 主机中运行。</span><span class="sxs-lookup"><span data-stu-id="fae30-139">To provide fault tolerance for the POP3 adapter in this scenario, a single POP3 adapter receive handler should be configured to run in a clustered BizTalk Host.</span></span> <span data-ttu-id="fae30-140">有关详细信息请参阅[在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。</span><span class="sxs-lookup"><span data-stu-id="fae30-140">For more information see [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span></span>  
  
## <a name="authentication-warnings-when-multiple-instances-of-the-pop3-adapter-connect-to-the-same-mailbox"></a><span data-ttu-id="fae30-141">多个 POP3 适配器实例连接到同一邮箱时的验证警告</span><span class="sxs-lookup"><span data-stu-id="fae30-141">Authentication Warnings When Multiple Instances of the POP3 Adapter Connect to the Same Mailbox</span></span>  
 <span data-ttu-id="fae30-142">可以将 BizTalk Server 配置为允许多个 POP3 适配器实例从同一邮箱中检索邮件。</span><span class="sxs-lookup"><span data-stu-id="fae30-142">BizTalk Server may be configured to have more than one instance of the POP3 adapter retrieve mail from the same mailbox.</span></span> <span data-ttu-id="fae30-143">在这种情况下，由于某些 POP3 服务器采用了锁定机制，因此在 BizTalk Server 应用程序日志中可能生成验证警告。</span><span class="sxs-lookup"><span data-stu-id="fae30-143">In such a case, it is possible that authentication warnings may be generated in the BizTalk Server Application log because of the locking mechanism employed by some POP3 servers.</span></span> <span data-ttu-id="fae30-144">这些警告对于 POP3 适配器功能没有影响，因而在此方案中可以安全地将其忽略。</span><span class="sxs-lookup"><span data-stu-id="fae30-144">These warnings will have no impact on the POP3 adapter functionality and can be safely ignored in this scenario.</span></span>  
  
## <a name="encrypted-messages-received-by-the-pop3-adapter-that-are-sent-to-the-suspended-queue-may-be-viewable-in-clear-text"></a><span data-ttu-id="fae30-145">由 POP3 适配器接收的加密消息（发送到挂起队列）的明文形式可能允许查看</span><span class="sxs-lookup"><span data-stu-id="fae30-145">Encrypted Messages Received by the POP3 Adapter that are sent to the Suspended Queue may be Viewable in Clear Text</span></span>  
 <span data-ttu-id="fae30-146">您可以对 POP3 适配器进行配置，对经数字加密的电子邮件进行解密。</span><span class="sxs-lookup"><span data-stu-id="fae30-146">You can configure the POP3 adapter to decrypt digitally encrypted e-mails.</span></span> <span data-ttu-id="fae30-147">这可通过设置**应用 MIME 解码**属性**True**为接收位置该使用 POP3 适配器。</span><span class="sxs-lookup"><span data-stu-id="fae30-147">This is done by setting the **Apply MIME Decoding** property to **True** for receive locations that use the POP3 adapter.</span></span> <span data-ttu-id="fae30-148">如果 POP3 适配器收到进行数字加密电子邮件和**应用 MIME 解码**接收位置的属性设置为**True**然后 POP3 适配器尝试解密电子邮件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fae30-148">If the POP3 Adapter receives a digitally encrypted e-mail and the **Apply MIME Decoding** property for the receive location is set to **True** then the POP3 adapter attempts to decrypt the e-mail as follows:</span></span>  
  
-   <span data-ttu-id="fae30-149">该 POP3 适配器将搜索与用来加密电子邮件的公钥证书相匹配的私钥证书。</span><span class="sxs-lookup"><span data-stu-id="fae30-149">The POP3 Adapter searches for a private certificate that matches the public certificate used to encrypt the e-mail.</span></span> <span data-ttu-id="fae30-150">该私钥证书必须位于运行指定主机实例（与 POP3 接收处理程序绑定）的服务器的个人证书存储区中。</span><span class="sxs-lookup"><span data-stu-id="fae30-150">The private certificate must be in the Personal certificate store of the server that is running the host instance that the POP3 receive handler is bound to.</span></span>  
  
-   <span data-ttu-id="fae30-151">如果 POP3 适配器找到相应的私钥证书，它将使用该私钥证书解密电子邮件。</span><span class="sxs-lookup"><span data-stu-id="fae30-151">If the POP3 Adapter locates a corresponding private certificate, it uses the private certificate to decrypt the e-mail message.</span></span>  
  
-   <span data-ttu-id="fae30-152">该电子邮件将被解密并保存到 BizTalk MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="fae30-152">The e-mail is decrypted and persisted to the BizTalk MessageBox.</span></span>  
  
 <span data-ttu-id="fae30-153">如果一个消息经过解密并保存到 BizTalk MessageBox 中后被挂起，则在 BizTalk 挂起队列中，消息内容的明文形式将是可见的。</span><span class="sxs-lookup"><span data-stu-id="fae30-153">If a message is suspended after being decrypted and persisted to the BizTalk MessageBox, the contents of the message will be visible in clear text in the BizTalk suspended queue.</span></span>  
  
 <span data-ttu-id="fae30-154">如果要阻止安全消息文本显示在挂起队列中，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="fae30-154">If you need to prevent the display of secure message text in the suspended queue, follow these steps:</span></span>  
  
-   <span data-ttu-id="fae30-155">设置**应用 MIME 解码**属性**False**为接收该使用 POP3 适配器的位置和解密与 SMIME 管道组件的管道中的消息。</span><span class="sxs-lookup"><span data-stu-id="fae30-155">Set the **Apply MIME Decoding** property to **False** for receive locations that use the POP3 adapter and decrypt the message in a pipeline with the SMIME pipeline component.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fae30-156">此方法将阻止您将特定于电子邮件的属性升级到消息上下文中。</span><span class="sxs-lookup"><span data-stu-id="fae30-156">This approach will prevent you from being able to promote e-mail specific properties to the message context.</span></span>  
  
-   <span data-ttu-id="fae30-157">如果要将特定于电子邮件的属性应用到消息的上下文中，并要确保加密消息被路由到挂起队列时仍处于加密状态，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="fae30-157">If you need to promote e-mail specific properties to the message context and ensure that encrypted messages remain encrypted if they are routed to the suspended queue, follow these steps:</span></span>  
  
    -   <span data-ttu-id="fae30-158">检查选项**启用路由失败消息**保存使用 POP3 适配器的接收位置接收端口上。</span><span class="sxs-lookup"><span data-stu-id="fae30-158">Check the option to **Enable routing for failed messages** on the receive port that houses the receive location(s) that use the POP3 adapter.</span></span>  
  
    -   <span data-ttu-id="fae30-159">创建一个业务流程，以订阅在传输到使用 POP3 适配器的接收位置所在接收端口时失败的消息。</span><span class="sxs-lookup"><span data-stu-id="fae30-159">Create an orchestration to subscribe to messages that fail delivery to the receive port that houses the receive location(s) that use the POP3 adapter.</span></span>  
  
    -   <span data-ttu-id="fae30-160">为该业务流程配置一个可使用 SMIME 管道组件在管道中加密消息的发送端口。</span><span class="sxs-lookup"><span data-stu-id="fae30-160">Configure the orchestration with a send port that encrypts the message in a pipeline using the SMIME pipeline component.</span></span>  
  
    -   <span data-ttu-id="fae30-161">为该业务流程配置一个挂起形状，以挂起业务流程实例和消息。</span><span class="sxs-lookup"><span data-stu-id="fae30-161">Configure the orchestration with a suspend shape to suspend the orchestration instance and the message.</span></span>  
  
    -   <span data-ttu-id="fae30-162">生成并部署该业务流程，然后将已部署的业务流程绑定到适当的接收端口。</span><span class="sxs-lookup"><span data-stu-id="fae30-162">Build and deploy the orchestration, bind the deployed orchestration to the appropriate receive port.</span></span>  
  
## <a name="maximum-message-size-supported-by-the-pop3-adapter"></a><span data-ttu-id="fae30-163">POP3 适配器支持的最大消息大小</span><span class="sxs-lookup"><span data-stu-id="fae30-163">Maximum Message Size Supported by the POP3 Adapter</span></span>  
 <span data-ttu-id="fae30-164">经测试，POP3 适配器支持接收大小不超过 50 MB 的消息。</span><span class="sxs-lookup"><span data-stu-id="fae30-164">The POP3 adapter has been tested with and supports receiving messages up to 50 MB in size.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fae30-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fae30-165">See Also</span></span>  
 [<span data-ttu-id="fae30-166">POP3 适配器</span><span class="sxs-lookup"><span data-stu-id="fae30-166">POP3 Adapter</span></span>](../core/pop3-adapter.md)