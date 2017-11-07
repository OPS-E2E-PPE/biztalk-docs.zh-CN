---
title: "创建 TIBCO 会合适配器发送项目 |Microsoft 文档"
description: "创建发送端口，配置要从 BizTalk 将消息发送到 TIBCO 会合的传输属性"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad996c4f-e6ed-4582-a768-0cb1ad25b1d8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed6d03885423582c2657c9cb624c63f26ce1c6f3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="create-tibco-rendezvous-send-handlers"></a><span data-ttu-id="e4ac9-103">创建 TIBCO 会合发送处理程序</span><span class="sxs-lookup"><span data-stu-id="e4ac9-103">Create TIBCO Rendezvous Send Handlers</span></span>
<span data-ttu-id="e4ac9-104">本部分介绍如何创建架构以在 BizTalk Server 业务流程中使用 TIBCO Rendezvous。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-104">This section explains how to create a schema to use TIBCO Rendezvous in a BizTalk Server orchestration.</span></span>  
  
## <a name="create-a-send-port"></a><span data-ttu-id="e4ac9-105">创建发送端口</span><span class="sxs-lookup"><span data-stu-id="e4ac9-105">Create a send port</span></span>
  
1.  <span data-ttu-id="e4ac9-106">在**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-106">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand your application.</span></span>  
  
2.  <span data-ttu-id="e4ac9-107">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="e4ac9-108">在**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e4ac9-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="e4ac9-109">例如，键入发送端口的名称`SendToTIBCORV`。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-109">Type a name for the send port, for example, `SendToTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="e4ac9-110">从**类型**下拉列表中，选择**TIBCO 会合**。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-110">From the **Type** drop-down list, select **TIBCO Rendezvous**.</span></span>  
  
    3.  <span data-ttu-id="e4ac9-111">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="e4ac9-112">从发送管道下拉列表中选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-112">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  <span data-ttu-id="e4ac9-113">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  

        > [!NOTE]
        > <span data-ttu-id="e4ac9-114">Microsoft BizTalk Adapter for TIBCO 会合要求你选择用于发送，XMLTransmit 管道和接收的 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-114">Microsoft BizTalk Adapter for TIBCO Rendezvous requires that you select XMLTransmit pipeline for send, and XMLReceive pipeline for receive.</span></span>
        
    6.  <span data-ttu-id="e4ac9-115">单击**配置**配置发送端口。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-115">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="e4ac9-116">在**TIBCO 会合传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e4ac9-116">In the **TIBCO Rendezvous Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="e4ac9-117">输入属性。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-117">Enter the properties.</span></span>  
  
         <span data-ttu-id="e4ac9-118">您不必设置登录信息。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-118">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="e4ac9-119">在列表中，选择 SSO 关联应用程序创建的用来表示 TIBCO 会合系统。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-119">In the list, select the SSO affiliate application you created to represent the TIBCO Rendezvous system.</span></span>  
  
    3.  <span data-ttu-id="e4ac9-120">有关**使用 SSO**，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-120">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="e4ac9-121">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-121">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="e4ac9-122">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-122">Click **OK**.</span></span>  

## <a name="set-the-transport-properties"></a><span data-ttu-id="e4ac9-123">设置传输属性</span><span class="sxs-lookup"><span data-stu-id="e4ac9-123">Set the transport properties</span></span>
<span data-ttu-id="e4ac9-124">TIBCO Rendezvous 传输属性用于运行时。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-124">The TIBCO Rendezvous Transport property is used for run time.</span></span> <span data-ttu-id="e4ac9-125">在**传输属性**，设置标识你想要将生成的消息发布 TIBCO 会合域的连接参数。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-125">In the **Transport Properties**, you set the connection parameters that identify the TIBCO Rendezvous domain where you want to publish the generated messages.</span></span>  
  
 
1.  <span data-ttu-id="e4ac9-126">上**TIBCO 会合传输属性**屏幕中，展开**认证发件人属性**并输入以下信息。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-126">On the **TIBCO Rendezvous Transport Properties** screen, expand **Certified Sender Properties** and enter the following information.</span></span>  
  
     ![](../core/media/sadp-tibcoren-transs.gif "SAdp_TibcoRen_Transs")  
  
    |<span data-ttu-id="e4ac9-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e4ac9-127">Use this</span></span>|<span data-ttu-id="e4ac9-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e4ac9-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e4ac9-129">**分类帐名称**</span><span class="sxs-lookup"><span data-stu-id="e4ac9-129">**Ledger name**</span></span>|<span data-ttu-id="e4ac9-130">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-130">Default value is blank.</span></span> <span data-ttu-id="e4ac9-131">用于持久性认证消息传递的分类帐文件名。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-131">Ledger file name to use for persistent certified message delivery.</span></span> <span data-ttu-id="e4ac9-132">仅限使用本地驱动器。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-132">Use local drives only.</span></span>|  
    |<span data-ttu-id="e4ac9-133">**可重用的名称**</span><span class="sxs-lookup"><span data-stu-id="e4ac9-133">**Reusable name**</span></span>|<span data-ttu-id="e4ac9-134">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-134">Default value is blank.</span></span> <span data-ttu-id="e4ac9-135">用于已验证消息传递的可重用的通信名称。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-135">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="e4ac9-136">在网络上所有已验证消息通信名称中，该名称必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-136">The name must be unique among all certified message correspondent names on the network.</span></span>|  
  
2.  <span data-ttu-id="e4ac9-137">展开**凭据**然后输入服务器连接的以下信息。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-137">Expand **Credentials** and enter the following information for connection to the server.</span></span>  
  
    |<span data-ttu-id="e4ac9-138">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e4ac9-138">Use this</span></span>|<span data-ttu-id="e4ac9-139">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e4ac9-139">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e4ac9-140">**密码**</span><span class="sxs-lookup"><span data-stu-id="e4ac9-140">**Password**</span></span>|<span data-ttu-id="e4ac9-141">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-141">Default value is blank.</span></span> <span data-ttu-id="e4ac9-142">登录到 Tibco Rendezvous 守护程序的密码。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-142">Password for login to a Tibco Rendezvous daemon.</span></span>|  
    |<span data-ttu-id="e4ac9-143">**用户名**</span><span class="sxs-lookup"><span data-stu-id="e4ac9-143">**User name**</span></span>|<span data-ttu-id="e4ac9-144">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-144">Default value is blank.</span></span> <span data-ttu-id="e4ac9-145">Tibco Rendezvous 守护程序的用户名称。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-145">User name for Tibco Rendezvous daemon.</span></span>|  
  
3.  <span data-ttu-id="e4ac9-146">展开**常规设置**然后输入 TIBCO 会合服务器连接的以下信息。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-146">Expand **General Settings** and enter the following information for connection to the TIBCO Rendezvous server.</span></span>  
  
    |<span data-ttu-id="e4ac9-147">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e4ac9-147">Use this</span></span>|<span data-ttu-id="e4ac9-148">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e4ac9-148">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e4ac9-149">**代码页编号**</span><span class="sxs-lookup"><span data-stu-id="e4ac9-149">**Code Page Number**</span></span>|<span data-ttu-id="e4ac9-150">默认值是 65001（UTF-8 编码代码页）。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-150">Default value is 65001 (code page for UTF-8 encoding).</span></span> <span data-ttu-id="e4ac9-151">这是 TIBCO Rendezvous SDK 用于字符串编码的代码页。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-151">This is the code page that the TIBCO Rendezvous SDK uses for String encoding.</span></span>|  
    |<span data-ttu-id="e4ac9-152">**默认使用者名称**</span><span class="sxs-lookup"><span data-stu-id="e4ac9-152">**Default Subject Name**</span></span>|<span data-ttu-id="e4ac9-153">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-153">Default is empty.</span></span> <span data-ttu-id="e4ac9-154">使用者名称在业务流程中设置。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-154">The subject name is set in the orchestration.</span></span> <span data-ttu-id="e4ac9-155">如果一个端口用于一种消息类型，您可以提供一个默认使用者名称，并通过删除设置使用者名称属性需求来简化业务流程。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-155">If a port is used for one message type, you can provide a default subject name, and you can simplify orchestrations by removing the need to set the Subject name property.</span></span>|  
    |<span data-ttu-id="e4ac9-156">**启用时间批处理**</span><span class="sxs-lookup"><span data-stu-id="e4ac9-156">**Enable Time Batch**</span></span>|<span data-ttu-id="e4ac9-157">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-157">Default value is False.</span></span> <span data-ttu-id="e4ac9-158">启用/禁用 TIBCO Rendezvous 时间批处理功能。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-158">Enable/Disable TIBCO Rendezvous Time Batch feature.</span></span>|  
    |<span data-ttu-id="e4ac9-159">**将不受支持的类型映射到字符串**</span><span class="sxs-lookup"><span data-stu-id="e4ac9-159">**Map Unsupported types to string**</span></span>|<span data-ttu-id="e4ac9-160">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-160">Default value is True.</span></span> <span data-ttu-id="e4ac9-161">如果为 True，在可能的情况将不受支持的类型映射到字符串。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-161">If true, unsupported types are mapped to string if it is possible.</span></span> <span data-ttu-id="e4ac9-162">如果为 False，则生成运行时错误。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-162">If False, a run-time error is generated.</span></span>|  
    |<span data-ttu-id="e4ac9-163">**对二进制文件，如 TIBCO 会合程序集的路径**</span><span class="sxs-lookup"><span data-stu-id="e4ac9-163">**Path to Binaries, such as TIBCO Rendezvous assemblies**</span></span>|<span data-ttu-id="e4ac9-164">如果此信息已不在该路径环境变量中，则提供此信息。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-164">Provide this information if it is not already in the PATH environment variable.</span></span>|  
    |<span data-ttu-id="e4ac9-165">**意味着保留顺序**</span><span class="sxs-lookup"><span data-stu-id="e4ac9-165">**Preserver Order**</span></span>|<span data-ttu-id="e4ac9-166">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-166">Default value is True.</span></span> <span data-ttu-id="e4ac9-167">启用逻辑以按从 BizTalk Server 接收消息的相同顺序发送消息到 TIBCO Rendezvous。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-167">Enables logic to send messages to TIBCO Rendezvous in the same order they were received from BizTalk Server.</span></span> <span data-ttu-id="e4ac9-168">此参数强制按相同顺序发布；但不表示订阅者按相同的顺序接收。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-168">This parameter forces publishing in the same order; it does not mean that subscribers receive them in the same order.</span></span>|  
    |<span data-ttu-id="e4ac9-169">**发送端口标识符**</span><span class="sxs-lookup"><span data-stu-id="e4ac9-169">**Send Port Identifier**</span></span>|<span data-ttu-id="e4ac9-170">此标识符出现在与此端口关联的日志消息中。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-170">This identifier appears in log messages associated with this port.</span></span> <span data-ttu-id="e4ac9-171">它作为方便提供。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-171">It is provided as a convenience.</span></span>|  
  
4.  <span data-ttu-id="e4ac9-172">展开**会合传输**和输入 TIBCO 会合服务器连接的信息，请单击**应用**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-172">Expand **Rendezvous Transport** and enter the information for connection to the TIBCO Rendezvous server, click **Apply**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e4ac9-173">您必须为用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器设置连接参数以访问 TIBCO Rendezvous。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-173">You must set connection parameters for Microsoft BizTalk Adapter for TIBCO Rendezvous to access TIBCO Rendezvous.</span></span>  
  
    |<span data-ttu-id="e4ac9-174">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e4ac9-174">Use this</span></span>|<span data-ttu-id="e4ac9-175">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e4ac9-175">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e4ac9-176">**后台程序**</span><span class="sxs-lookup"><span data-stu-id="e4ac9-176">**Daemon**</span></span>|<span data-ttu-id="e4ac9-177">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-177">Default is empty.</span></span><br /><br /> <span data-ttu-id="e4ac9-178">Rendezvous 传输后台程序参数。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-178">Rendezvous Transport Daemon parameter.</span></span>|  
    |<span data-ttu-id="e4ac9-179">**网络**</span><span class="sxs-lookup"><span data-stu-id="e4ac9-179">**Network**</span></span>|<span data-ttu-id="e4ac9-180">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-180">Default is empty.</span></span><br /><br /> <span data-ttu-id="e4ac9-181">Rendezvous 传输网络参数。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-181">Rendezvous Transport Network parameter.</span></span>|  
    |<span data-ttu-id="e4ac9-182">**服务**</span><span class="sxs-lookup"><span data-stu-id="e4ac9-182">**Service**</span></span>|<span data-ttu-id="e4ac9-183">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-183">Default is empty.</span></span><br /><br /> <span data-ttu-id="e4ac9-184">Rendezvous 传输服务参数。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-184">Rendezvous Transport Service parameter.</span></span>|  
  
5.  <span data-ttu-id="e4ac9-185">使用单一登录 (SSO) 提供凭据。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-185">Provide credentials using Single Sign-On (SSO).</span></span>  
  
     <span data-ttu-id="e4ac9-186">有两种方法可用于访问 TIBCO Rendezvous 系统。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-186">There are two methods that you can use to access the TIBCO Rendezvous system.</span></span> <span data-ttu-id="e4ac9-187">您可以使用凭据（用户名和密码参数）或单一登录。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-187">You can use Credentials (User Name and Password parameters) or Single Sign-On.</span></span>  
  
    1.  <span data-ttu-id="e4ac9-188">选择**是**中**使用 SSO**用于单一登录。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-188">Select **Yes** in the **Use SSO** to use Single Sign-On.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="e4ac9-189">请参阅[安全](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)有关如何设置 SSO 信息。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-189">See [Security](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md) for information about how to set up SSO.</span></span>  
  
    2.  <span data-ttu-id="e4ac9-190">从列表中选择一个关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-190">Select an affiliate application from the list.</span></span>  
  
         <span data-ttu-id="e4ac9-191">一个由企业单一登录工具创建的关联应用程序表示一个应用程序（如 TIBCO Rendezvous）。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-191">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as TIBCO Rendezvous.</span></span> <span data-ttu-id="e4ac9-192">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-192">Microsoft BizTalk Adapter for TIBCO Rendezvous uses the credentials of an application user.</span></span> <span data-ttu-id="e4ac9-193">这些凭据是从服务器系统的 SSO 数据库中为指定关联应用程序检索的。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-193">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="e4ac9-194">有关如何创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications1.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-194">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications1.md).</span></span>  
  
6.  <span data-ttu-id="e4ac9-195">单击**应用**，然后单击**确定**后提供所有必要的信息，以接受连接信息。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-195">Click **Apply**, and then click **OK** after providing all required information to accept the connection information.</span></span>  
  
     <span data-ttu-id="e4ac9-196">你必须设置为 TIBCO 会合访问 TIBCO 会合的 BizTalk 适配器的连接参数。</span><span class="sxs-lookup"><span data-stu-id="e4ac9-196">You must set connection parameters for BizTalk Adapter for TIBCO Rendezvous to access TIBCO Rendezvous .</span></span>  


## <a name="next-steps"></a><span data-ttu-id="e4ac9-197">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e4ac9-197">Next steps</span></span>
  
-   [<span data-ttu-id="e4ac9-198">从 BizTalk Server 中使用 TIBCO Rendezvous 发送端口</span><span class="sxs-lookup"><span data-stu-id="e4ac9-198">Using TIBCO Rendezvous Send Ports from BizTalk Server</span></span>](../core/using-tibco-rendezvous-send-ports-from-biztalk-server.md)  
  
-   [<span data-ttu-id="e4ac9-199">TIBCO Rendezvous 中用于发送处理程序的数据类型映射</span><span class="sxs-lookup"><span data-stu-id="e4ac9-199">Data Type Mapping for Send Handlers in TIBCO Rendezvous</span></span>](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md)  
  
-   [<span data-ttu-id="e4ac9-200">BizTalk Server 消息上下文属性（发送处理程序）</span><span class="sxs-lookup"><span data-stu-id="e4ac9-200">BizTalk Server Message Context Properties (Send Handlers)</span></span>](../core/biztalk-server-message-context-properties-send-handlers.md)