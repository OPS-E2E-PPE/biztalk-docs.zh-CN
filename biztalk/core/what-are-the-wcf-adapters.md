---
title: WCF 适配器有哪些？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18ca8535-3386-4018-8b5b-d32bdb9ebf70
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f82973bce0ae79a151d0336d788c07fa99b7e8d4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244078"
---
# <a name="what-are-the-wcf-adapters"></a><span data-ttu-id="da647-103">WCF 适配器有哪些？</span><span class="sxs-lookup"><span data-stu-id="da647-103">What Are the WCF Adapters?</span></span>
<span data-ttu-id="da647-104">有两个 Windows Communication Foundation (WCF) 适配器，接收适配器和一个发送适配器。</span><span class="sxs-lookup"><span data-stu-id="da647-104">There are two Windows Communication Foundation (WCF) adapters—a receive adapter and a send adapter.</span></span> <span data-ttu-id="da647-105">使用 WCF 接收适配器接收 WCF 服务请求。</span><span class="sxs-lookup"><span data-stu-id="da647-105">You use the WCF receive adapter to receive WCF service requests.</span></span> <span data-ttu-id="da647-106">WCF 接收适配器收到的请求，创建一个 BizTalk 消息对象，并升级到消息上下文关联的属性。</span><span class="sxs-lookup"><span data-stu-id="da647-106">The WCF receive adapter receives a request, creates a BizTalk Message object, and promotes the associated properties to the message context.</span></span> <span data-ttu-id="da647-107">使用 WCF 发送适配器来调用 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="da647-107">You use the WCF send adapter to call a WCF service.</span></span> <span data-ttu-id="da647-108">WCF 发送适配器调用通过无类型协定的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="da647-108">The WCF send adapter calls the WCF services through the typeless contracts.</span></span>  

> [!NOTE]
>  <span data-ttu-id="da647-109">WCF 适配器不支持使用远程过程调用 (RPC) 的 Web services，因为 RPC 型 Web services 中的消息部分引用消息类型而不是在 WCF 适配器有使用元素的消息的消息元素部分。</span><span class="sxs-lookup"><span data-stu-id="da647-109">The WCF adapters do not support consuming Remote Procedure Call (RPC)-style Web services because the message parts in RPC-style Web services are referring to the message types rather than the message elements where WCF adapters are using elements for the message parts.</span></span> <span data-ttu-id="da647-110">我们建议使用 BizTalk 项目中的 Web 服务添加通过添加 Web 引用向导的 RPC 样式的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="da647-110">We recommend that you add the RPC-style Web services through Add Web Reference wizard for consuming the Web services in BizTalk projects.</span></span>  

## <a name="web-services-standards-support"></a><span data-ttu-id="da647-111">Web Services 标准支持</span><span class="sxs-lookup"><span data-stu-id="da647-111">Web Services Standards Support</span></span>  
 <span data-ttu-id="da647-112">WCF 适配器支持 WS-\* 标准如 Ws-addressing、 Ws-security 和 WS-AtomicTransaction。</span><span class="sxs-lookup"><span data-stu-id="da647-112">WCF adapters provide the support for WS-\* standards such as WS-Addressing, WS-Security, and WS-AtomicTransaction.</span></span> <span data-ttu-id="da647-113">在此版本的 WCF 适配器不支持 WS-ReliableMessaging。</span><span class="sxs-lookup"><span data-stu-id="da647-113">WS-ReliableMessaging is not supported in this release of the WCF adapters.</span></span> <span data-ttu-id="da647-114">有关 WCF 支持的规范的列表，请参阅[ http://go.microsoft.com/fwlink/?LinkId=88314 ](http://go.microsoft.com/fwlink/?LinkId=88314)。</span><span class="sxs-lookup"><span data-stu-id="da647-114">For a list of specifications supported by WCF, see [http://go.microsoft.com/fwlink/?LinkId=88314](http://go.microsoft.com/fwlink/?LinkId=88314).</span></span>  

### <a name="ws-addressing"></a><span data-ttu-id="da647-115">WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="da647-115">WS-Addressing</span></span>  
 <span data-ttu-id="da647-116">WCF 适配器依赖 WCF 提供的 Ws-addressing 的标准支持。</span><span class="sxs-lookup"><span data-stu-id="da647-116">WCF adapters rely on the WS-Addressing standard support that is provided by WCF.</span></span> <span data-ttu-id="da647-117">WCF 适配器中提供了以下功能：</span><span class="sxs-lookup"><span data-stu-id="da647-117">The following features are available in WCF adapters:</span></span>  

-   <span data-ttu-id="da647-118">在元数据交换请求过程中获取的发送端口终结点地址的配置。</span><span class="sxs-lookup"><span data-stu-id="da647-118">Configuration of the send port endpoint address obtained during the metadata exchange request.</span></span>  

-   <span data-ttu-id="da647-119">发送端口终结点地址的寻址标头的配置。</span><span class="sxs-lookup"><span data-stu-id="da647-119">Configuration of the addressing headers for the send port endpoint address.</span></span>  

-   <span data-ttu-id="da647-120">在 BizTalk 中公开的终结点的寻址标头的配置接收位置。</span><span class="sxs-lookup"><span data-stu-id="da647-120">Configuration of the addressing headers for the endpoint exposed in the BizTalk receive location.</span></span>  

### <a name="ws-security"></a><span data-ttu-id="da647-121">WS-Security</span><span class="sxs-lookup"><span data-stu-id="da647-121">WS-Security</span></span>  
 <span data-ttu-id="da647-122">WCF 适配器依赖 WCF 提供的安全标准支持。</span><span class="sxs-lookup"><span data-stu-id="da647-122">WCF adapters rely on the security standards support that is provided by WCF.</span></span> <span data-ttu-id="da647-123">WCF 适配器支持以下标准：</span><span class="sxs-lookup"><span data-stu-id="da647-123">The following standards are supported in WCF adapters:</span></span>  

-   <span data-ttu-id="da647-124">Web 服务安全：SOAP 消息安全性 (Ws-security) 1.0 和 1.1 版</span><span class="sxs-lookup"><span data-stu-id="da647-124">Web Services Security: SOAP Message Security (WS-Security) 1.0 and 1.1</span></span>  

-   <span data-ttu-id="da647-125">Web 服务安全对话语言 (Ws-secureconversation)</span><span class="sxs-lookup"><span data-stu-id="da647-125">Web Services Secure Conversation Language (WS-SecureConversation)</span></span>  

-   <span data-ttu-id="da647-126">Web 服务信任语言 （WS 信任）</span><span class="sxs-lookup"><span data-stu-id="da647-126">Web Services Trust Language (WS-Trust)</span></span>  

-   <span data-ttu-id="da647-127">Web 服务安全 X.509 证书令牌配置文件</span><span class="sxs-lookup"><span data-stu-id="da647-127">Web Services Security X.509 Certificate Token Profile</span></span>  

-   <span data-ttu-id="da647-128">Web 服务安全用户名令牌配置文件 1.0</span><span class="sxs-lookup"><span data-stu-id="da647-128">Web Services Security Username Token Profile 1.0</span></span>  

-   <span data-ttu-id="da647-129">Web 服务安全 Kerberos 令牌配置文件 1.0</span><span class="sxs-lookup"><span data-stu-id="da647-129">Web Services Security Kerberos Token Profile 1.0</span></span>  

#### <a name="service-authentication-types"></a><span data-ttu-id="da647-130">服务身份验证类型</span><span class="sxs-lookup"><span data-stu-id="da647-130">Service Authentication Types</span></span>  
 <span data-ttu-id="da647-131">支持以下 WCF 服务身份验证类型：</span><span class="sxs-lookup"><span data-stu-id="da647-131">The following WCF service authentication types are supported:</span></span>  

-   <span data-ttu-id="da647-132">None</span><span class="sxs-lookup"><span data-stu-id="da647-132">None</span></span>  

-   <span data-ttu-id="da647-133">Windows</span><span class="sxs-lookup"><span data-stu-id="da647-133">Windows</span></span>  

-   <span data-ttu-id="da647-134">证书</span><span class="sxs-lookup"><span data-stu-id="da647-134">Certificate</span></span>  

#### <a name="client-authentication-types"></a><span data-ttu-id="da647-135">客户端身份验证类型</span><span class="sxs-lookup"><span data-stu-id="da647-135">Client Authentication Types</span></span>  
 <span data-ttu-id="da647-136">支持以下 WCF 客户端身份验证类型：</span><span class="sxs-lookup"><span data-stu-id="da647-136">The following WCF client authentication types are supported:</span></span>  

-   <span data-ttu-id="da647-137">匿名</span><span class="sxs-lookup"><span data-stu-id="da647-137">Anonymous</span></span>  

-   <span data-ttu-id="da647-138">UserName</span><span class="sxs-lookup"><span data-stu-id="da647-138">UserName</span></span>  

-   <span data-ttu-id="da647-139">Windows</span><span class="sxs-lookup"><span data-stu-id="da647-139">Windows</span></span>  

-   <span data-ttu-id="da647-140">证书</span><span class="sxs-lookup"><span data-stu-id="da647-140">Certificate</span></span>  

#### <a name="security-modes"></a><span data-ttu-id="da647-141">安全模式</span><span class="sxs-lookup"><span data-stu-id="da647-141">Security Modes</span></span>  
 <span data-ttu-id="da647-142">支持以下安全模式：</span><span class="sxs-lookup"><span data-stu-id="da647-142">The following security modes are supported:</span></span>  

-   <span data-ttu-id="da647-143">Transport</span><span class="sxs-lookup"><span data-stu-id="da647-143">Transport</span></span>  

-   <span data-ttu-id="da647-144">消息</span><span class="sxs-lookup"><span data-stu-id="da647-144">Message</span></span>  

-   <span data-ttu-id="da647-145">混合 （传输级安全和消息级别的身份验证）</span><span class="sxs-lookup"><span data-stu-id="da647-145">Mixed (transport-level security and message-level authentication)</span></span>  

### <a name="ws-atomictransaction"></a><span data-ttu-id="da647-146">WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="da647-146">WS-AtomicTransaction</span></span>  
 <span data-ttu-id="da647-147">Wcf-wshttp、 Wcf-nettcp 和 Wcf-netmsmq 适配器支持 WS-AtomicTransaction 协议。</span><span class="sxs-lookup"><span data-stu-id="da647-147">The WCF-WsHttp, WCF-NetTcp, and WCF-NetMsmq adapters support the WS-AtomicTransaction protocol.</span></span> <span data-ttu-id="da647-148">此支持允许使用下列方案：</span><span class="sxs-lookup"><span data-stu-id="da647-148">This support allows the following scenarios:</span></span>  

-   <span data-ttu-id="da647-149">到 MessageBox 数据库的消息事务性提交。</span><span class="sxs-lookup"><span data-stu-id="da647-149">Transactional submission of messages to the MessageBox database.</span></span>  

-   <span data-ttu-id="da647-150">事务方式传输消息从 MessageBox 到事务性目标。</span><span class="sxs-lookup"><span data-stu-id="da647-150">Transactional transmission of messages from the MessageBox to a transactional destination.</span></span>  

> [!NOTE]
>  <span data-ttu-id="da647-151">事务作用域受 MessageBox 限制。</span><span class="sxs-lookup"><span data-stu-id="da647-151">The transactional scope is limited by the MessageBox.</span></span> <span data-ttu-id="da647-152">例如，BizTalk 业务流程不能参与客户端的事务。</span><span class="sxs-lookup"><span data-stu-id="da647-152">For example, a BizTalk orchestration cannot participate in a client’s transaction.</span></span> <span data-ttu-id="da647-153">同样，目标终结点不能参与由 BizTalk 业务流程启动的事务。</span><span class="sxs-lookup"><span data-stu-id="da647-153">Similarly, a destination endpoint cannot participate in a transaction that is initiated by a BizTalk orchestration.</span></span>  

#### <a name="transactional-submission"></a><span data-ttu-id="da647-154">事务性提交</span><span class="sxs-lookup"><span data-stu-id="da647-154">Transactional Submission</span></span>  
 <span data-ttu-id="da647-155">对于 Wcf-wshttp 和 Wcf-nettcp 适配器，事务性提交到 BizTalk Server 选择启用**启用事务**接收位置传输属性对话框中的复选框。</span><span class="sxs-lookup"><span data-stu-id="da647-155">For the WCF-WsHttp and WCF-NetTcp adapters, transactional submission to BizTalk Server is enabled by selecting the **Enable transactions** check box in the receive location transport properties dialog box.</span></span> <span data-ttu-id="da647-156">Wcf-netmsmq 适配器**事务性**默认情况下选中复选框。</span><span class="sxs-lookup"><span data-stu-id="da647-156">For the WCF-NetMsmq adapter, the **Transactional** check box is selected by default.</span></span> <span data-ttu-id="da647-157">如果您正在从其请求消息的消息队列未标记为事务性，则需要清除此复选框;否则，将收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="da647-157">If the message queues from which you are pulling messages are not marked as transactional, you need to clear this check box; otherwise, you will receive an error message.</span></span>  

 <span data-ttu-id="da647-158">如果启用事务功能，则消息通过使用客户端的事务提交到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="da647-158">If the transaction functionality is enabled, messages are submitted to the MessageBox database by using clients’ transactions.</span></span> <span data-ttu-id="da647-159">如果客户端尝试提交事务作用域之外的消息，适配器将向客户端返回一个异常。</span><span class="sxs-lookup"><span data-stu-id="da647-159">If a client attempts to submit the messages outside the transactional scope, the adapter will return an exception back to the client.</span></span> <span data-ttu-id="da647-160">但是，将不挂起任何消息。</span><span class="sxs-lookup"><span data-stu-id="da647-160">However, no messages will be suspended.</span></span> <span data-ttu-id="da647-161">如果禁用事务功能，则将消息提交到 MessageBox 不使用客户端的事务。</span><span class="sxs-lookup"><span data-stu-id="da647-161">If the transaction functionality is disabled, messages are submitted to the MessageBox without using clients’ transactions.</span></span> <span data-ttu-id="da647-162">如果客户端尝试提交事务作用域内的消息，适配器将返回一个异常返回给客户端，并将挂起任何消息。</span><span class="sxs-lookup"><span data-stu-id="da647-162">If a client attempts to submit messages inside the transactional scope, the adapter will return an exception back to the client, and no messages will be suspended.</span></span>  

#### <a name="transactions-and-receive-location-type"></a><span data-ttu-id="da647-163">事务和接收位置类型</span><span class="sxs-lookup"><span data-stu-id="da647-163">Transactions and Receive Location Type</span></span>  
 <span data-ttu-id="da647-164">事务提交是仅适用于单向接收位置。</span><span class="sxs-lookup"><span data-stu-id="da647-164">Transactional submission is available only for one-way receive locations.</span></span> <span data-ttu-id="da647-165">如果客户端尝试提交事务作用域中的双向消息的接收位置，将返回异常返回给客户端，并将挂起任何消息。</span><span class="sxs-lookup"><span data-stu-id="da647-165">If a client attempts to submit messages in a transactional scope for a two-way receive location, an exception will be returned back to the client, and no messages will be suspended.</span></span>  

#### <a name="transactional-transmission"></a><span data-ttu-id="da647-166">事务性传输</span><span class="sxs-lookup"><span data-stu-id="da647-166">Transactional Transmission</span></span>  
 <span data-ttu-id="da647-167">对于 Wcf-wshttp 和 Wcf-nettcp 适配器，BizTalk Server 的事务性传输选择启用**启用事务**发送端口传输属性对话框中的复选框。</span><span class="sxs-lookup"><span data-stu-id="da647-167">For the WCF-WsHttp and WCF-NetTcp adapters, transactional transmission from BizTalk Server is enabled by selecting the **Enable transactions** check box in the send port transport properties dialog box.</span></span> <span data-ttu-id="da647-168">Wcf-netmsmq 适配器**事务性**默认情况下选中复选框。</span><span class="sxs-lookup"><span data-stu-id="da647-168">For the WCF-NetMsmq adapter, the **Transactional** check box is selected by default.</span></span> <span data-ttu-id="da647-169">如果向其发送消息的消息队列未标记为事务性，则需要清除此复选框;否则，将收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="da647-169">If the message queues to which you are sending messages are not marked as transactional, you need to clear this check box; otherwise, you will receive an error message.</span></span>  

 <span data-ttu-id="da647-170">如果启用事务功能，则消息传输并从 MessageBox 数据库在事务中删除。</span><span class="sxs-lookup"><span data-stu-id="da647-170">If the transaction functionality is enabled, messages are transmitted and deleted from the MessageBox database under transaction.</span></span> <span data-ttu-id="da647-171">如果目标服务执行了任何工作之后接收的消息和从 MessageBox 未删除该消息，然后将中止事务并在服务上的所有事务都工作将回滚。</span><span class="sxs-lookup"><span data-stu-id="da647-171">If the destination service has performed any work after receiving the message, and the message is not deleted from the MessageBox, then the transaction will be aborted and all transaction work on the service will be rolled back.</span></span> <span data-ttu-id="da647-172">如果禁用事务功能，则消息传送并不使用事务从 MessageBox 中删除。</span><span class="sxs-lookup"><span data-stu-id="da647-172">If the transaction functionality is disabled, messages are transmitted and deleted from the MessageBox without using transactions.</span></span>  

## <a name="single-sign-on-support"></a><span data-ttu-id="da647-173">单一登录支持</span><span class="sxs-lookup"><span data-stu-id="da647-173">Single Sign-On Support</span></span>  
 <span data-ttu-id="da647-174">您可以模拟并获取使用 SSO 与 WCF 适配器的企业单一登录 (SSO) 票证。</span><span class="sxs-lookup"><span data-stu-id="da647-174">You can impersonate and acquire the Enterprise Single Sign-On (SSO) ticket for using SSO with WCF adapters.</span></span> <span data-ttu-id="da647-175">有关如何通过 WCF 适配器使用 SSO 的详细信息，请参阅[WCF 适配器的单一登录支持](../core/single-sign-on-support-for-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="da647-175">For more information about how to use SSO with WCF adapters, see [Single Sign-On Support for the WCF Adapters](../core/single-sign-on-support-for-the-wcf-adapters.md).</span></span>  

 <span data-ttu-id="da647-176">下表汇总了不受支持的方案使用 SSO 支持与 WCF 接收适配器时。</span><span class="sxs-lookup"><span data-stu-id="da647-176">The following table summarizes the scenarios that are not supported when using SSO support with the WCF receive adapters.</span></span>  

|<span data-ttu-id="da647-177">安全模式</span><span class="sxs-lookup"><span data-stu-id="da647-177">Security mode</span></span>|<span data-ttu-id="da647-178">凭据</span><span class="sxs-lookup"><span data-stu-id="da647-178">Credential</span></span>|  
|-------------------|----------------|  
|<span data-ttu-id="da647-179">None</span><span class="sxs-lookup"><span data-stu-id="da647-179">None</span></span>|<span data-ttu-id="da647-180">None</span><span class="sxs-lookup"><span data-stu-id="da647-180">None</span></span>|  
|<span data-ttu-id="da647-181">Transport</span><span class="sxs-lookup"><span data-stu-id="da647-181">Transport</span></span>|<span data-ttu-id="da647-182">None</span><span class="sxs-lookup"><span data-stu-id="da647-182">None</span></span>|  
|<span data-ttu-id="da647-183">消息</span><span class="sxs-lookup"><span data-stu-id="da647-183">Message</span></span>|<span data-ttu-id="da647-184">None</span><span class="sxs-lookup"><span data-stu-id="da647-184">None</span></span>|  
|<span data-ttu-id="da647-185">TransportWithMessageCredentials</span><span class="sxs-lookup"><span data-stu-id="da647-185">TransportWithMessageCredentials</span></span>|<span data-ttu-id="da647-186">None</span><span class="sxs-lookup"><span data-stu-id="da647-186">None</span></span>|  
|<span data-ttu-id="da647-187">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="da647-187">TransportCredentialOnly</span></span>|<span data-ttu-id="da647-188">None</span><span class="sxs-lookup"><span data-stu-id="da647-188">None</span></span>|  

## <a name="wcf-extensibility"></a><span data-ttu-id="da647-189">WCF 扩展性</span><span class="sxs-lookup"><span data-stu-id="da647-189">WCF Extensibility</span></span>  
 <span data-ttu-id="da647-190">通过开发下列扩展并使用通过 Wcf-custom 和 Wcf-customisolated 适配器，可以扩展 WCF 的功能：</span><span class="sxs-lookup"><span data-stu-id="da647-190">You can extend the functionality of WCF by developing the following extensions and using them with the WCF-Custom and WCF-CustomIsolated adapters:</span></span>  

-   <span data-ttu-id="da647-191">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="da647-191">Custom bindings</span></span>  

-   <span data-ttu-id="da647-192">自定义绑定元素</span><span class="sxs-lookup"><span data-stu-id="da647-192">Custom binding elements</span></span>  

### <a name="custom-bindings"></a><span data-ttu-id="da647-193">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="da647-193">Custom Bindings</span></span>  
 <span data-ttu-id="da647-194">自定义绑定到容器中公开的特定使用方案的配置属性的一部分开发的打包各个绑定元素。</span><span class="sxs-lookup"><span data-stu-id="da647-194">Custom bindings are developed by packaging individual binding elements into a container that exposes a subset of the configuration properties for a particular usage scenario.</span></span> <span data-ttu-id="da647-195">需要注册绑定扩展，通过该程序集安装到全局程序集缓存 (GAC) 然后将扩展元素添加到计算机配置文件。</span><span class="sxs-lookup"><span data-stu-id="da647-195">You need to register the binding extension by installing the assembly into the global assembly cache (GAC) and then adding the extension element to the machine configuration file.</span></span> <span data-ttu-id="da647-196">若要使用自定义绑定，需要设置 BizTalk 组中的每个服务器上的绑定。</span><span class="sxs-lookup"><span data-stu-id="da647-196">To use the custom bindings, you need to set up the binding on every server in the BizTalk group.</span></span> <span data-ttu-id="da647-197">安装绑定后，将会显示为 Wcf-custom 和 Wcf-customisolated 适配器。</span><span class="sxs-lookup"><span data-stu-id="da647-197">After the binding is installed, it will be visible to the WCF-Custom and WCF-CustomIsolated adapters.</span></span> <span data-ttu-id="da647-198">Wcf-custom 和 Wcf-customisolated 适配器将通过绑定配置元素上使用反射获取的绑定配置属性。</span><span class="sxs-lookup"><span data-stu-id="da647-198">The WCF-Custom and WCF-CustomIsolated adapters will get the binding configuration properties by using reflection on the binding configuration elements.</span></span>  

### <a name="custom-binding-elements"></a><span data-ttu-id="da647-199">自定义绑定元素</span><span class="sxs-lookup"><span data-stu-id="da647-199">Custom Binding Elements</span></span>  
 <span data-ttu-id="da647-200">通过添加或修改特定传输通道组件来开发自定义绑定元素。</span><span class="sxs-lookup"><span data-stu-id="da647-200">Custom binding elements are developed by adding or modifying certain transport channel components.</span></span> <span data-ttu-id="da647-201">例如，自定义解压缩组件打包为绑定元素，或 UDP 传输表示为绑定元素。</span><span class="sxs-lookup"><span data-stu-id="da647-201">For example, a custom decompression component is packaged as a binding element, or a UDP transport is represented as a binding element.</span></span> <span data-ttu-id="da647-202">可以在 WCF 适配器内使用这些绑定元素。</span><span class="sxs-lookup"><span data-stu-id="da647-202">These binding elements can be used inside the WCF adapters.</span></span> <span data-ttu-id="da647-203">您可以定义与其他全新的或自定义绑定元素结合使用自定义绑定元素的通道堆栈。</span><span class="sxs-lookup"><span data-stu-id="da647-203">You can define a channel stack that uses the custom binding element in combination with other out-of-box or custom binding elements.</span></span> <span data-ttu-id="da647-204">您需要通过将程序集安装到 GAC 然后将扩展元素添加到计算机配置文件注册的绑定元素扩展。</span><span class="sxs-lookup"><span data-stu-id="da647-204">You need to register the binding element extension by installing the assembly into the GAC and then adding the extension element to the machine configuration file.</span></span> <span data-ttu-id="da647-205">若要使用自定义绑定，需要设置 BizTalk 组中的每个服务器上的绑定。</span><span class="sxs-lookup"><span data-stu-id="da647-205">To use the custom bindings, you need to set up the binding on every server in the BizTalk group.</span></span> <span data-ttu-id="da647-206">若要使用自定义绑定元素，可以选择**CustomBinding**绑定类型然后添加、 修改或重新排列顺序所需的绑定元素。</span><span class="sxs-lookup"><span data-stu-id="da647-206">To use the custom binding elements, you can select the **CustomBinding** binding type and then add, modify, or rearrange the binding elements in a desired order.</span></span>  

## <a name="in-this-section"></a><span data-ttu-id="da647-207">本节内容</span><span class="sxs-lookup"><span data-stu-id="da647-207">In This Section</span></span>  

-   [<span data-ttu-id="da647-208">WCF 接收适配器</span><span class="sxs-lookup"><span data-stu-id="da647-208">WCF Receive Adapter</span></span>](../core/wcf-receive-adapter.md)  

-   [<span data-ttu-id="da647-209">WCF 发送适配器</span><span class="sxs-lookup"><span data-stu-id="da647-209">WCF Send Adapter</span></span>](../core/wcf-send-adapter.md)  

## <a name="see-also"></a><span data-ttu-id="da647-210">请参阅</span><span class="sxs-lookup"><span data-stu-id="da647-210">See Also</span></span>  
- [<span data-ttu-id="da647-211">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="da647-211">WCF Adapters</span></span>](../core/wcf-adapters.md)   
- <span data-ttu-id="da647-212">**WCF 适配器服务协定引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="da647-212">**WCF Adapters Service Contract Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
