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
ms.openlocfilehash: 4e57efe686b72fa42a173eb4f28bb8fb92a899b9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012270"
---
# <a name="what-are-the-wcf-adapters"></a><span data-ttu-id="eb153-103">WCF 适配器有哪些？</span><span class="sxs-lookup"><span data-stu-id="eb153-103">What Are the WCF Adapters?</span></span>
<span data-ttu-id="eb153-104">共有两种 Windows Communication Foundation (WCF) 适配器：一个接收适配器和一个发送适配器。</span><span class="sxs-lookup"><span data-stu-id="eb153-104">There are two Windows Communication Foundation (WCF) adapters—a receive adapter and a send adapter.</span></span> <span data-ttu-id="eb153-105">使用 WCF 接收适配器可以接收 WCF 服务请求。</span><span class="sxs-lookup"><span data-stu-id="eb153-105">You use the WCF receive adapter to receive WCF service requests.</span></span> <span data-ttu-id="eb153-106">WCF 接收适配器接收一个请求、创建一个 BizTalk 消息对象，并将关联的属性升级到消息上下文中。</span><span class="sxs-lookup"><span data-stu-id="eb153-106">The WCF receive adapter receives a request, creates a BizTalk Message object, and promotes the associated properties to the message context.</span></span> <span data-ttu-id="eb153-107">使用 WCF 发送适配器可调用 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="eb153-107">You use the WCF send adapter to call a WCF service.</span></span> <span data-ttu-id="eb153-108">WCF 发送适配器通过无类型的协定调用 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="eb153-108">The WCF send adapter calls the WCF services through the typeless contracts.</span></span>  

> [!NOTE]
>  <span data-ttu-id="eb153-109">WCF 适配器不支持使用远程过程调用 (RPC) 型的 Web Services，因为 RPC 型 Web Services 中的消息部分引用消息类型而不是消息元素，WCF 适配器在其中使用消息部分的元素。</span><span class="sxs-lookup"><span data-stu-id="eb153-109">The WCF adapters do not support consuming Remote Procedure Call (RPC)-style Web services because the message parts in RPC-style Web services are referring to the message types rather than the message elements where WCF adapters are using elements for the message parts.</span></span> <span data-ttu-id="eb153-110">我们建议您通过“添加 Web 引用”向导添加 RPC 型 Web Services 以在 BizTalk 项目中使用 Web Services。</span><span class="sxs-lookup"><span data-stu-id="eb153-110">We recommend that you add the RPC-style Web services through Add Web Reference wizard for consuming the Web services in BizTalk projects.</span></span>  

## <a name="web-services-standards-support"></a><span data-ttu-id="eb153-111">Web Services 标准支持</span><span class="sxs-lookup"><span data-stu-id="eb153-111">Web Services Standards Support</span></span>  
 <span data-ttu-id="eb153-112">WCF 适配器支持 WS-\* 标准，比如 WS-Addressing、WS-Security 和 WS-AtomicTransaction。</span><span class="sxs-lookup"><span data-stu-id="eb153-112">WCF adapters provide the support for WS-\* standards such as WS-Addressing, WS-Security, and WS-AtomicTransaction.</span></span> <span data-ttu-id="eb153-113">此版本 WCF 适配器中不支持 WS-ReliableMessaging。</span><span class="sxs-lookup"><span data-stu-id="eb153-113">WS-ReliableMessaging is not supported in this release of the WCF adapters.</span></span> <span data-ttu-id="eb153-114">有关 WCF 支持的规范的列表，请参阅[ http://go.microsoft.com/fwlink/?LinkId=88314 ](http://go.microsoft.com/fwlink/?LinkId=88314)。</span><span class="sxs-lookup"><span data-stu-id="eb153-114">For a list of specifications supported by WCF, see [http://go.microsoft.com/fwlink/?LinkId=88314](http://go.microsoft.com/fwlink/?LinkId=88314).</span></span>  

### <a name="ws-addressing"></a><span data-ttu-id="eb153-115">WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="eb153-115">WS-Addressing</span></span>  
 <span data-ttu-id="eb153-116">WCF 适配器依赖 WCF 提供的 WS-Addressing 标准支持。</span><span class="sxs-lookup"><span data-stu-id="eb153-116">WCF adapters rely on the WS-Addressing standard support that is provided by WCF.</span></span> <span data-ttu-id="eb153-117">WCF 适配器具有下列功能：</span><span class="sxs-lookup"><span data-stu-id="eb153-117">The following features are available in WCF adapters:</span></span>  

-   <span data-ttu-id="eb153-118">配置在元数据交换请求过程中获得的发送端口终结点地址。</span><span class="sxs-lookup"><span data-stu-id="eb153-118">Configuration of the send port endpoint address obtained during the metadata exchange request.</span></span>  

-   <span data-ttu-id="eb153-119">配置发送端口终结点地址的寻址标头。</span><span class="sxs-lookup"><span data-stu-id="eb153-119">Configuration of the addressing headers for the send port endpoint address.</span></span>  

-   <span data-ttu-id="eb153-120">配置在 BizTalk 接收位置中公开的终结点的寻址标头。</span><span class="sxs-lookup"><span data-stu-id="eb153-120">Configuration of the addressing headers for the endpoint exposed in the BizTalk receive location.</span></span>  

### <a name="ws-security"></a><span data-ttu-id="eb153-121">WS-安全性</span><span class="sxs-lookup"><span data-stu-id="eb153-121">WS-Security</span></span>  
 <span data-ttu-id="eb153-122">WCF 适配器依赖 WCF 提供的安全标准支持。</span><span class="sxs-lookup"><span data-stu-id="eb153-122">WCF adapters rely on the security standards support that is provided by WCF.</span></span> <span data-ttu-id="eb153-123">WCF 适配器支持下列标准：</span><span class="sxs-lookup"><span data-stu-id="eb153-123">The following standards are supported in WCF adapters:</span></span>  

-   <span data-ttu-id="eb153-124">Web 服务安全： SOAP 消息安全性 (Ws-security) 1.0 和 1.1 版</span><span class="sxs-lookup"><span data-stu-id="eb153-124">Web Services Security: SOAP Message Security (WS-Security) 1.0 and 1.1</span></span>  

-   <span data-ttu-id="eb153-125">Web Services 安全对话语言 (WS-SecureConversation)</span><span class="sxs-lookup"><span data-stu-id="eb153-125">Web Services Secure Conversation Language (WS-SecureConversation)</span></span>  

-   <span data-ttu-id="eb153-126">Web Services 信任语言 (WS-Trust)</span><span class="sxs-lookup"><span data-stu-id="eb153-126">Web Services Trust Language (WS-Trust)</span></span>  

-   <span data-ttu-id="eb153-127">Web Services 安全 X.509 证书令牌配置文件</span><span class="sxs-lookup"><span data-stu-id="eb153-127">Web Services Security X.509 Certificate Token Profile</span></span>  

-   <span data-ttu-id="eb153-128">Web Services 安全用户名令牌配置文件 1.0</span><span class="sxs-lookup"><span data-stu-id="eb153-128">Web Services Security Username Token Profile 1.0</span></span>  

-   <span data-ttu-id="eb153-129">Web Services 安全 Kerberos 令牌配置文件 1.0</span><span class="sxs-lookup"><span data-stu-id="eb153-129">Web Services Security Kerberos Token Profile 1.0</span></span>  

#### <a name="service-authentication-types"></a><span data-ttu-id="eb153-130">服务验证类型</span><span class="sxs-lookup"><span data-stu-id="eb153-130">Service Authentication Types</span></span>  
 <span data-ttu-id="eb153-131">支持以下 WCF 服务验证类型：</span><span class="sxs-lookup"><span data-stu-id="eb153-131">The following WCF service authentication types are supported:</span></span>  

-   <span data-ttu-id="eb153-132">InclusionThresholdSetting</span><span class="sxs-lookup"><span data-stu-id="eb153-132">None</span></span>  

-   <span data-ttu-id="eb153-133">Windows</span><span class="sxs-lookup"><span data-stu-id="eb153-133">Windows</span></span>  

-   <span data-ttu-id="eb153-134">证书</span><span class="sxs-lookup"><span data-stu-id="eb153-134">Certificate</span></span>  

#### <a name="client-authentication-types"></a><span data-ttu-id="eb153-135">客户端身份验证类型</span><span class="sxs-lookup"><span data-stu-id="eb153-135">Client Authentication Types</span></span>  
 <span data-ttu-id="eb153-136">支持下列 WCF 客户端验证类型：</span><span class="sxs-lookup"><span data-stu-id="eb153-136">The following WCF client authentication types are supported:</span></span>  

-   <span data-ttu-id="eb153-137">匿名</span><span class="sxs-lookup"><span data-stu-id="eb153-137">Anonymous</span></span>  

-   <span data-ttu-id="eb153-138">UserName</span><span class="sxs-lookup"><span data-stu-id="eb153-138">UserName</span></span>  

-   <span data-ttu-id="eb153-139">Windows</span><span class="sxs-lookup"><span data-stu-id="eb153-139">Windows</span></span>  

-   <span data-ttu-id="eb153-140">证书</span><span class="sxs-lookup"><span data-stu-id="eb153-140">Certificate</span></span>  

#### <a name="security-modes"></a><span data-ttu-id="eb153-141">安全模式</span><span class="sxs-lookup"><span data-stu-id="eb153-141">Security Modes</span></span>  
 <span data-ttu-id="eb153-142">支持下列安全模式：</span><span class="sxs-lookup"><span data-stu-id="eb153-142">The following security modes are supported:</span></span>  

-   <span data-ttu-id="eb153-143">Transport</span><span class="sxs-lookup"><span data-stu-id="eb153-143">Transport</span></span>  

-   <span data-ttu-id="eb153-144">消息</span><span class="sxs-lookup"><span data-stu-id="eb153-144">Message</span></span>  

-   <span data-ttu-id="eb153-145">混合（传输级别安全性和消息级别验证）</span><span class="sxs-lookup"><span data-stu-id="eb153-145">Mixed (transport-level security and message-level authentication)</span></span>  

### <a name="ws-atomictransaction"></a><span data-ttu-id="eb153-146">WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="eb153-146">WS-AtomicTransaction</span></span>  
 <span data-ttu-id="eb153-147">WCF-WsHttp、WCF-NetTcp 和 WCF-NetMsmq 适配器支持 WS-AtomicTransaction 协议。</span><span class="sxs-lookup"><span data-stu-id="eb153-147">The WCF-WsHttp, WCF-NetTcp, and WCF-NetMsmq adapters support the WS-AtomicTransaction protocol.</span></span> <span data-ttu-id="eb153-148">此支持允许使用下列方案：</span><span class="sxs-lookup"><span data-stu-id="eb153-148">This support allows the following scenarios:</span></span>  

-   <span data-ttu-id="eb153-149">将消息事务性提交到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="eb153-149">Transactional submission of messages to the MessageBox database.</span></span>  

-   <span data-ttu-id="eb153-150">将来自 MessageBox 的消息事务性提交到事务性目标。</span><span class="sxs-lookup"><span data-stu-id="eb153-150">Transactional transmission of messages from the MessageBox to a transactional destination.</span></span>  

> [!NOTE]
>  <span data-ttu-id="eb153-151">事务作用域受 MessageBox 限制。</span><span class="sxs-lookup"><span data-stu-id="eb153-151">The transactional scope is limited by the MessageBox.</span></span> <span data-ttu-id="eb153-152">例如，一个 BizTalk 业务流程无法参与一个客户端的事务。</span><span class="sxs-lookup"><span data-stu-id="eb153-152">For example, a BizTalk orchestration cannot participate in a client’s transaction.</span></span> <span data-ttu-id="eb153-153">与此类似，一个目标终结点无法参与由 BizTalk 业务流程启动的事务。</span><span class="sxs-lookup"><span data-stu-id="eb153-153">Similarly, a destination endpoint cannot participate in a transaction that is initiated by a BizTalk orchestration.</span></span>  

#### <a name="transactional-submission"></a><span data-ttu-id="eb153-154">事务性提交</span><span class="sxs-lookup"><span data-stu-id="eb153-154">Transactional Submission</span></span>  
 <span data-ttu-id="eb153-155">对于 Wcf-wshttp 和 Wcf-nettcp 适配器，事务性提交到 BizTalk Server 选择启用**启用事务**接收位置传输属性对话框中的复选框。</span><span class="sxs-lookup"><span data-stu-id="eb153-155">For the WCF-WsHttp and WCF-NetTcp adapters, transactional submission to BizTalk Server is enabled by selecting the **Enable transactions** check box in the receive location transport properties dialog box.</span></span> <span data-ttu-id="eb153-156">Wcf-netmsmq 适配器**事务性**默认情况下选中复选框。</span><span class="sxs-lookup"><span data-stu-id="eb153-156">For the WCF-NetMsmq adapter, the **Transactional** check box is selected by default.</span></span> <span data-ttu-id="eb153-157">如果您正在请求消息的消息队列未标记为事务性，则需要清除此复选框；否则，将会接收到一个错误消息。</span><span class="sxs-lookup"><span data-stu-id="eb153-157">If the message queues from which you are pulling messages are not marked as transactional, you need to clear this check box; otherwise, you will receive an error message.</span></span>  

 <span data-ttu-id="eb153-158">如果已启用事务功能，则将使用客户端的事务将消息提交到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="eb153-158">If the transaction functionality is enabled, messages are submitted to the MessageBox database by using clients’ transactions.</span></span> <span data-ttu-id="eb153-159">如果客户端尝试提交事务作用域之外的消息，则适配器将向客户端返回一个异常。</span><span class="sxs-lookup"><span data-stu-id="eb153-159">If a client attempts to submit the messages outside the transactional scope, the adapter will return an exception back to the client.</span></span> <span data-ttu-id="eb153-160">但是，将不会挂起任何消息。</span><span class="sxs-lookup"><span data-stu-id="eb153-160">However, no messages will be suspended.</span></span> <span data-ttu-id="eb153-161">如果已禁用事务功能，则将不使用客户端的事务将消息提交到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="eb153-161">If the transaction functionality is disabled, messages are submitted to the MessageBox without using clients’ transactions.</span></span> <span data-ttu-id="eb153-162">如果客户端尝试提交事务作用域之内的消息，则适配器将向客户端返回一个异常，且不挂起任何消息。</span><span class="sxs-lookup"><span data-stu-id="eb153-162">If a client attempts to submit messages inside the transactional scope, the adapter will return an exception back to the client, and no messages will be suspended.</span></span>  

#### <a name="transactions-and-receive-location-type"></a><span data-ttu-id="eb153-163">事务和接收位置类型</span><span class="sxs-lookup"><span data-stu-id="eb153-163">Transactions and Receive Location Type</span></span>  
 <span data-ttu-id="eb153-164">事务性提交只可用于单向接收位置。</span><span class="sxs-lookup"><span data-stu-id="eb153-164">Transactional submission is available only for one-way receive locations.</span></span> <span data-ttu-id="eb153-165">如果客户端尝试为双向接收位置提交事务作用域之内的消息，则将向客户端返回一个异常，且不挂起任何消息。</span><span class="sxs-lookup"><span data-stu-id="eb153-165">If a client attempts to submit messages in a transactional scope for a two-way receive location, an exception will be returned back to the client, and no messages will be suspended.</span></span>  

#### <a name="transactional-transmission"></a><span data-ttu-id="eb153-166">事务性传输</span><span class="sxs-lookup"><span data-stu-id="eb153-166">Transactional Transmission</span></span>  
 <span data-ttu-id="eb153-167">对于 Wcf-wshttp 和 Wcf-nettcp 适配器，BizTalk Server 的事务性传输选择启用**启用事务**发送端口传输属性对话框中的复选框。</span><span class="sxs-lookup"><span data-stu-id="eb153-167">For the WCF-WsHttp and WCF-NetTcp adapters, transactional transmission from BizTalk Server is enabled by selecting the **Enable transactions** check box in the send port transport properties dialog box.</span></span> <span data-ttu-id="eb153-168">Wcf-netmsmq 适配器**事务性**默认情况下选中复选框。</span><span class="sxs-lookup"><span data-stu-id="eb153-168">For the WCF-NetMsmq adapter, the **Transactional** check box is selected by default.</span></span> <span data-ttu-id="eb153-169">如果您正在向其发送消息的消息队列未标记为事务性，则需要清除此复选框；否则，将会接收到一个错误消息。</span><span class="sxs-lookup"><span data-stu-id="eb153-169">If the message queues to which you are sending messages are not marked as transactional, you need to clear this check box; otherwise, you will receive an error message.</span></span>  

 <span data-ttu-id="eb153-170">如果已启用事务功能，则将使用事务从 MessageBox 数据库传输或删除消息。</span><span class="sxs-lookup"><span data-stu-id="eb153-170">If the transaction functionality is enabled, messages are transmitted and deleted from the MessageBox database under transaction.</span></span> <span data-ttu-id="eb153-171">如果目标服务在接收消息后执行了任何工作，则不会从 MessageBox 删除消息，但会在随后中止该事务并回滚该服务上的所有事务工作。</span><span class="sxs-lookup"><span data-stu-id="eb153-171">If the destination service has performed any work after receiving the message, and the message is not deleted from the MessageBox, then the transaction will be aborted and all transaction work on the service will be rolled back.</span></span> <span data-ttu-id="eb153-172">如果已禁用事务功能，则将不使用事务从 MessageBox 传输或删除消息。</span><span class="sxs-lookup"><span data-stu-id="eb153-172">If the transaction functionality is disabled, messages are transmitted and deleted from the MessageBox without using transactions.</span></span>  

## <a name="single-sign-on-support"></a><span data-ttu-id="eb153-173">单一登录支持</span><span class="sxs-lookup"><span data-stu-id="eb153-173">Single Sign-On Support</span></span>  
 <span data-ttu-id="eb153-174">您可模拟并获取企业单一登录 (SSO) 票证以将 SSO 与 WCF 适配器一起使用。</span><span class="sxs-lookup"><span data-stu-id="eb153-174">You can impersonate and acquire the Enterprise Single Sign-On (SSO) ticket for using SSO with WCF adapters.</span></span> <span data-ttu-id="eb153-175">有关如何通过 WCF 适配器使用 SSO 的详细信息，请参阅[WCF 适配器的单一登录支持](../core/single-sign-on-support-for-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="eb153-175">For more information about how to use SSO with WCF adapters, see [Single Sign-On Support for the WCF Adapters](../core/single-sign-on-support-for-the-wcf-adapters.md).</span></span>  

 <span data-ttu-id="eb153-176">下表总结了将 SSO 支持与 WCF 服务适配器一起使用时不支持的方案。</span><span class="sxs-lookup"><span data-stu-id="eb153-176">The following table summarizes the scenarios that are not supported when using SSO support with the WCF receive adapters.</span></span>  

|<span data-ttu-id="eb153-177">安全模式</span><span class="sxs-lookup"><span data-stu-id="eb153-177">Security mode</span></span>|<span data-ttu-id="eb153-178">凭据</span><span class="sxs-lookup"><span data-stu-id="eb153-178">Credential</span></span>|  
|-------------------|----------------|  
|<span data-ttu-id="eb153-179">InclusionThresholdSetting</span><span class="sxs-lookup"><span data-stu-id="eb153-179">None</span></span>|<span data-ttu-id="eb153-180">InclusionThresholdSetting</span><span class="sxs-lookup"><span data-stu-id="eb153-180">None</span></span>|  
|<span data-ttu-id="eb153-181">Transport</span><span class="sxs-lookup"><span data-stu-id="eb153-181">Transport</span></span>|<span data-ttu-id="eb153-182">InclusionThresholdSetting</span><span class="sxs-lookup"><span data-stu-id="eb153-182">None</span></span>|  
|<span data-ttu-id="eb153-183">消息</span><span class="sxs-lookup"><span data-stu-id="eb153-183">Message</span></span>|<span data-ttu-id="eb153-184">InclusionThresholdSetting</span><span class="sxs-lookup"><span data-stu-id="eb153-184">None</span></span>|  
|<span data-ttu-id="eb153-185">TransportWithMessageCredentials</span><span class="sxs-lookup"><span data-stu-id="eb153-185">TransportWithMessageCredentials</span></span>|<span data-ttu-id="eb153-186">InclusionThresholdSetting</span><span class="sxs-lookup"><span data-stu-id="eb153-186">None</span></span>|  
|<span data-ttu-id="eb153-187">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="eb153-187">TransportCredentialOnly</span></span>|<span data-ttu-id="eb153-188">InclusionThresholdSetting</span><span class="sxs-lookup"><span data-stu-id="eb153-188">None</span></span>|  

## <a name="wcf-extensibility"></a><span data-ttu-id="eb153-189">WCF 扩展性</span><span class="sxs-lookup"><span data-stu-id="eb153-189">WCF Extensibility</span></span>  
 <span data-ttu-id="eb153-190">您可扩展 WCF 的功能，方法是开发下列扩展功能并将它们与 WCF-Custom 和 WCF-CustomIsolated 适配器一起使用：</span><span class="sxs-lookup"><span data-stu-id="eb153-190">You can extend the functionality of WCF by developing the following extensions and using them with the WCF-Custom and WCF-CustomIsolated adapters:</span></span>  

-   <span data-ttu-id="eb153-191">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="eb153-191">Custom bindings</span></span>  

-   <span data-ttu-id="eb153-192">自定义绑定元素</span><span class="sxs-lookup"><span data-stu-id="eb153-192">Custom binding elements</span></span>  

### <a name="custom-bindings"></a><span data-ttu-id="eb153-193">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="eb153-193">Custom Bindings</span></span>  
 <span data-ttu-id="eb153-194">自定义绑定是将单个绑定元素打包到一个容器中来开发的，该容器为特定使用方案公开一个配置属性子集。</span><span class="sxs-lookup"><span data-stu-id="eb153-194">Custom bindings are developed by packaging individual binding elements into a container that exposes a subset of the configuration properties for a particular usage scenario.</span></span> <span data-ttu-id="eb153-195">您需要注册该绑定扩展，方法是将程序集安装到全局程序集缓存 (GAC) 然后将扩展元素添加到计算机配置文件中。</span><span class="sxs-lookup"><span data-stu-id="eb153-195">You need to register the binding extension by installing the assembly into the global assembly cache (GAC) and then adding the extension element to the machine configuration file.</span></span> <span data-ttu-id="eb153-196">若要使用自定义绑定，需要在 BizTalk 组中的每台服务器上设置绑定。</span><span class="sxs-lookup"><span data-stu-id="eb153-196">To use the custom bindings, you need to set up the binding on every server in the BizTalk group.</span></span> <span data-ttu-id="eb153-197">安装绑定后，WCF-Custom 和 WCF-CustomIsolated 适配器将可以看到该绑定。</span><span class="sxs-lookup"><span data-stu-id="eb153-197">After the binding is installed, it will be visible to the WCF-Custom and WCF-CustomIsolated adapters.</span></span> <span data-ttu-id="eb153-198">WCF-Custom 和 WCF-CustomIsolated 适配器将使用绑定配置元素上的反射来获取绑定配置属性。</span><span class="sxs-lookup"><span data-stu-id="eb153-198">The WCF-Custom and WCF-CustomIsolated adapters will get the binding configuration properties by using reflection on the binding configuration elements.</span></span>  

### <a name="custom-binding-elements"></a><span data-ttu-id="eb153-199">自定义绑定元素</span><span class="sxs-lookup"><span data-stu-id="eb153-199">Custom Binding Elements</span></span>  
 <span data-ttu-id="eb153-200">自定义绑定元素是通过添加或修改特定传输通道组件来开发的。</span><span class="sxs-lookup"><span data-stu-id="eb153-200">Custom binding elements are developed by adding or modifying certain transport channel components.</span></span> <span data-ttu-id="eb153-201">例如，自定义解压缩组件打包为绑定元素，或 UDP 传输表示为绑定元素。</span><span class="sxs-lookup"><span data-stu-id="eb153-201">For example, a custom decompression component is packaged as a binding element, or a UDP transport is represented as a binding element.</span></span> <span data-ttu-id="eb153-202">这些绑定元素可在 WCF 适配器内使用。</span><span class="sxs-lookup"><span data-stu-id="eb153-202">These binding elements can be used inside the WCF adapters.</span></span> <span data-ttu-id="eb153-203">您可定义一个通道堆栈以结合使用自定义绑定元素和其他预装或自定义绑定元素。</span><span class="sxs-lookup"><span data-stu-id="eb153-203">You can define a channel stack that uses the custom binding element in combination with other out-of-box or custom binding elements.</span></span> <span data-ttu-id="eb153-204">您需要注册该绑定元素扩展，方法是将程序集安装到 GAC 然后将扩展元素添加到计算机配置文件中。</span><span class="sxs-lookup"><span data-stu-id="eb153-204">You need to register the binding element extension by installing the assembly into the GAC and then adding the extension element to the machine configuration file.</span></span> <span data-ttu-id="eb153-205">若要使用自定义绑定，需要在 BizTalk 组中的每台服务器上设置绑定。</span><span class="sxs-lookup"><span data-stu-id="eb153-205">To use the custom bindings, you need to set up the binding on every server in the BizTalk group.</span></span> <span data-ttu-id="eb153-206">若要使用自定义绑定元素，可以选择**CustomBinding**绑定类型然后添加、 修改或重新排列顺序所需的绑定元素。</span><span class="sxs-lookup"><span data-stu-id="eb153-206">To use the custom binding elements, you can select the **CustomBinding** binding type and then add, modify, or rearrange the binding elements in a desired order.</span></span>  

## <a name="in-this-section"></a><span data-ttu-id="eb153-207">本节内容</span><span class="sxs-lookup"><span data-stu-id="eb153-207">In This Section</span></span>  

-   [<span data-ttu-id="eb153-208">WCF 接收适配器</span><span class="sxs-lookup"><span data-stu-id="eb153-208">WCF Receive Adapter</span></span>](../core/wcf-receive-adapter.md)  

-   [<span data-ttu-id="eb153-209">WCF 发送适配器</span><span class="sxs-lookup"><span data-stu-id="eb153-209">WCF Send Adapter</span></span>](../core/wcf-send-adapter.md)  

## <a name="see-also"></a><span data-ttu-id="eb153-210">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb153-210">See Also</span></span>  
- [<span data-ttu-id="eb153-211">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="eb153-211">WCF Adapters</span></span>](../core/wcf-adapters.md)   
- <span data-ttu-id="eb153-212">**WCF 适配器服务协定引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="eb153-212">**WCF Adapters Service Contract Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
