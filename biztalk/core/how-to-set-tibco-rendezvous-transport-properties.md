---
title: "如何设置 TIBCO 会合传输属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setting transport properties
- transport properties, setting
ms.assetid: db8e8a57-a942-44d7-a651-623aa614c6be
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c9ff40d5319daa0a71d67aa3fd132c3d115923e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-tibco-rendezvous-transport-properties"></a><span data-ttu-id="be4c4-102">如何设置 TIBCO Rendezvous 传输属性</span><span class="sxs-lookup"><span data-stu-id="be4c4-102">How to Set TIBCO Rendezvous Transport Properties</span></span>
<span data-ttu-id="be4c4-103">TIBCO Rendezvous 传输属性用于运行时。</span><span class="sxs-lookup"><span data-stu-id="be4c4-103">The TIBCO Rendezvous Transport property is used for run time.</span></span> <span data-ttu-id="be4c4-104">在**传输属性**屏幕上，你设置标识你想要将生成的消息发布 TIBCO 会合域的连接参数。</span><span class="sxs-lookup"><span data-stu-id="be4c4-104">In the **Transport Properties** screen, you set the connection parameters that identify the TIBCO Rendezvous domain where you want to publish the generated messages.</span></span>  
  
### <a name="to-specify-tibco-rendezvous-transport-properties"></a><span data-ttu-id="be4c4-105">指定 TIBCO Rendezvous 传输属性</span><span class="sxs-lookup"><span data-stu-id="be4c4-105">To specify TIBCO Rendezvous Transport properties</span></span>  
  
1.  <span data-ttu-id="be4c4-106">上**TIBCO 会合传输属性**屏幕中，展开**认证发件人属性**并输入以下信息。</span><span class="sxs-lookup"><span data-stu-id="be4c4-106">On the **TIBCO Rendezvous Transport Properties** screen, expand **Certified Sender Properties** and enter the following information.</span></span>  
  
     ![](../core/media/sadp-tibcoren-transs.gif "SAdp_TibcoRen_Transs")  
  
    |<span data-ttu-id="be4c4-107">使用此选项</span><span class="sxs-lookup"><span data-stu-id="be4c4-107">Use this</span></span>|<span data-ttu-id="be4c4-108">执行的操作</span><span class="sxs-lookup"><span data-stu-id="be4c4-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="be4c4-109">**分类帐名称**</span><span class="sxs-lookup"><span data-stu-id="be4c4-109">**Ledger name**</span></span>|<span data-ttu-id="be4c4-110">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="be4c4-110">Default value is blank.</span></span> <span data-ttu-id="be4c4-111">用于持久性认证消息传递的分类帐文件名。</span><span class="sxs-lookup"><span data-stu-id="be4c4-111">Ledger file name to use for persistent certified message delivery.</span></span> <span data-ttu-id="be4c4-112">仅限使用本地驱动器。</span><span class="sxs-lookup"><span data-stu-id="be4c4-112">Use local drives only.</span></span>|  
    |<span data-ttu-id="be4c4-113">**可重用的名称**</span><span class="sxs-lookup"><span data-stu-id="be4c4-113">**Reusable name**</span></span>|<span data-ttu-id="be4c4-114">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="be4c4-114">Default value is blank.</span></span> <span data-ttu-id="be4c4-115">用于已验证消息传递的可重用的通信名称。</span><span class="sxs-lookup"><span data-stu-id="be4c4-115">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="be4c4-116">在网络上所有已验证消息通信名称中，该名称必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="be4c4-116">The name must be unique among all certified message correspondent names on the network.</span></span>|  
  
2.  <span data-ttu-id="be4c4-117">展开**凭据**然后输入服务器连接的以下信息。</span><span class="sxs-lookup"><span data-stu-id="be4c4-117">Expand **Credentials** and enter the following information for connection to the server.</span></span>  
  
    |<span data-ttu-id="be4c4-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="be4c4-118">Use this</span></span>|<span data-ttu-id="be4c4-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="be4c4-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="be4c4-120">**密码**</span><span class="sxs-lookup"><span data-stu-id="be4c4-120">**Password**</span></span>|<span data-ttu-id="be4c4-121">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="be4c4-121">Default value is blank.</span></span> <span data-ttu-id="be4c4-122">登录到 Tibco Rendezvous 守护程序的密码。</span><span class="sxs-lookup"><span data-stu-id="be4c4-122">Password for login to a Tibco Rendezvous daemon.</span></span>|  
    |<span data-ttu-id="be4c4-123">**用户名**</span><span class="sxs-lookup"><span data-stu-id="be4c4-123">**User name**</span></span>|<span data-ttu-id="be4c4-124">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="be4c4-124">Default value is blank.</span></span> <span data-ttu-id="be4c4-125">Tibco Rendezvous 守护程序的用户名称。</span><span class="sxs-lookup"><span data-stu-id="be4c4-125">User name for Tibco Rendezvous daemon.</span></span>|  
  
3.  <span data-ttu-id="be4c4-126">展开**常规设置**然后输入 TIBCO 会合服务器连接的以下信息。</span><span class="sxs-lookup"><span data-stu-id="be4c4-126">Expand **General Settings** and enter the following information for connection to the TIBCO Rendezvous server.</span></span>  
  
    |<span data-ttu-id="be4c4-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="be4c4-127">Use this</span></span>|<span data-ttu-id="be4c4-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="be4c4-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="be4c4-129">**代码页编号**</span><span class="sxs-lookup"><span data-stu-id="be4c4-129">**Code Page Number**</span></span>|<span data-ttu-id="be4c4-130">默认值是 65001（UTF-8 编码代码页）。</span><span class="sxs-lookup"><span data-stu-id="be4c4-130">Default value is 65001 (code page for UTF-8 encoding).</span></span> <span data-ttu-id="be4c4-131">这是 TIBCO Rendezvous SDK 用于字符串编码的代码页。</span><span class="sxs-lookup"><span data-stu-id="be4c4-131">This is the code page that the TIBCO Rendezvous SDK uses for String encoding.</span></span>|  
    |<span data-ttu-id="be4c4-132">**默认使用者名称**</span><span class="sxs-lookup"><span data-stu-id="be4c4-132">**Default Subject Name**</span></span>|<span data-ttu-id="be4c4-133">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="be4c4-133">Default is empty.</span></span> <span data-ttu-id="be4c4-134">使用者名称在业务流程中设置。</span><span class="sxs-lookup"><span data-stu-id="be4c4-134">The subject name is set in the orchestration.</span></span> <span data-ttu-id="be4c4-135">如果一个端口用于一种消息类型，您可以提供一个默认使用者名称，并通过删除设置使用者名称属性需求来简化业务流程。</span><span class="sxs-lookup"><span data-stu-id="be4c4-135">If a port is used for one message type, you can provide a default subject name, and you can simplify orchestrations by removing the need to set the Subject name property.</span></span>|  
    |<span data-ttu-id="be4c4-136">**启用时间批处理**</span><span class="sxs-lookup"><span data-stu-id="be4c4-136">**Enable Time Batch**</span></span>|<span data-ttu-id="be4c4-137">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="be4c4-137">Default value is False.</span></span> <span data-ttu-id="be4c4-138">启用/禁用 TIBCO Rendezvous 时间批处理功能。</span><span class="sxs-lookup"><span data-stu-id="be4c4-138">Enable/Disable TIBCO Rendezvous Time Batch feature.</span></span>|  
    |<span data-ttu-id="be4c4-139">**将不受支持的类型映射到字符串**</span><span class="sxs-lookup"><span data-stu-id="be4c4-139">**Map Unsupported types to string**</span></span>|<span data-ttu-id="be4c4-140">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="be4c4-140">Default value is True.</span></span> <span data-ttu-id="be4c4-141">如果为 True，在可能的情况将不受支持的类型映射到字符串。</span><span class="sxs-lookup"><span data-stu-id="be4c4-141">If true, unsupported types are mapped to string if it is possible.</span></span> <span data-ttu-id="be4c4-142">如果为 False，则生成运行时错误。</span><span class="sxs-lookup"><span data-stu-id="be4c4-142">If False, a run-time error is generated.</span></span>|  
    |<span data-ttu-id="be4c4-143">**对二进制文件，如 TIBCO 会合程序集的路径**</span><span class="sxs-lookup"><span data-stu-id="be4c4-143">**Path to Binaries, such as TIBCO Rendezvous assemblies**</span></span>|<span data-ttu-id="be4c4-144">如果此信息已不在该路径环境变量中，则提供此信息。</span><span class="sxs-lookup"><span data-stu-id="be4c4-144">Provide this information if it is not already in the PATH environment variable.</span></span>|  
    |<span data-ttu-id="be4c4-145">**意味着保留顺序**</span><span class="sxs-lookup"><span data-stu-id="be4c4-145">**Preserver Order**</span></span>|<span data-ttu-id="be4c4-146">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="be4c4-146">Default value is True.</span></span> <span data-ttu-id="be4c4-147">启用逻辑以按从 BizTalk Server 接收消息的相同顺序发送消息到 TIBCO Rendezvous。</span><span class="sxs-lookup"><span data-stu-id="be4c4-147">Enables logic to send messages to TIBCO Rendezvous in the same order they were received from BizTalk Server.</span></span> <span data-ttu-id="be4c4-148">此参数强制按相同顺序发布；但不表示订阅者按相同的顺序接收。</span><span class="sxs-lookup"><span data-stu-id="be4c4-148">This parameter forces publishing in the same order; it does not mean that subscribers receive them in the same order.</span></span>|  
    |<span data-ttu-id="be4c4-149">**发送端口标识符**</span><span class="sxs-lookup"><span data-stu-id="be4c4-149">**Send Port Identifier**</span></span>|<span data-ttu-id="be4c4-150">此标识符出现在与此端口关联的日志消息中。</span><span class="sxs-lookup"><span data-stu-id="be4c4-150">This identifier appears in log messages associated with this port.</span></span> <span data-ttu-id="be4c4-151">它作为方便提供。</span><span class="sxs-lookup"><span data-stu-id="be4c4-151">It is provided as a convenience.</span></span>|  
  
4.  <span data-ttu-id="be4c4-152">展开**会合传输**和输入 TIBCO 会合服务器连接的信息，请单击**应用**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="be4c4-152">Expand **Rendezvous Transport** and enter the information for connection to the TIBCO Rendezvous server, click **Apply**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="be4c4-153">您必须为用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器设置连接参数以访问 TIBCO Rendezvous。</span><span class="sxs-lookup"><span data-stu-id="be4c4-153">You must set connection parameters for Microsoft BizTalk Adapter for TIBCO Rendezvous to access TIBCO Rendezvous.</span></span>  
  
    |<span data-ttu-id="be4c4-154">使用此选项</span><span class="sxs-lookup"><span data-stu-id="be4c4-154">Use this</span></span>|<span data-ttu-id="be4c4-155">执行的操作</span><span class="sxs-lookup"><span data-stu-id="be4c4-155">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="be4c4-156">**后台程序**</span><span class="sxs-lookup"><span data-stu-id="be4c4-156">**Daemon**</span></span>|<span data-ttu-id="be4c4-157">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="be4c4-157">Default is empty.</span></span><br /><br /> <span data-ttu-id="be4c4-158">Rendezvous 传输后台程序参数。</span><span class="sxs-lookup"><span data-stu-id="be4c4-158">Rendezvous Transport Daemon parameter.</span></span>|  
    |<span data-ttu-id="be4c4-159">**网络**</span><span class="sxs-lookup"><span data-stu-id="be4c4-159">**Network**</span></span>|<span data-ttu-id="be4c4-160">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="be4c4-160">Default is empty.</span></span><br /><br /> <span data-ttu-id="be4c4-161">Rendezvous 传输网络参数。</span><span class="sxs-lookup"><span data-stu-id="be4c4-161">Rendezvous Transport Network parameter.</span></span>|  
    |<span data-ttu-id="be4c4-162">**服务**</span><span class="sxs-lookup"><span data-stu-id="be4c4-162">**Service**</span></span>|<span data-ttu-id="be4c4-163">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="be4c4-163">Default is empty.</span></span><br /><br /> <span data-ttu-id="be4c4-164">Rendezvous 传输服务参数。</span><span class="sxs-lookup"><span data-stu-id="be4c4-164">Rendezvous Transport Service parameter.</span></span>|  
  
5.  <span data-ttu-id="be4c4-165">使用单一登录 (SSO) 提供凭据。</span><span class="sxs-lookup"><span data-stu-id="be4c4-165">Provide credentials using Single Sign-On (SSO).</span></span>  
  
     <span data-ttu-id="be4c4-166">有两种方法可用于访问 TIBCO Rendezvous 系统。</span><span class="sxs-lookup"><span data-stu-id="be4c4-166">There are two methods that you can use to access the TIBCO Rendezvous system.</span></span> <span data-ttu-id="be4c4-167">您可以使用凭据（用户名和密码参数）或单一登录。</span><span class="sxs-lookup"><span data-stu-id="be4c4-167">You can use Credentials (User Name and Password parameters) or Single Sign-On.</span></span>  
  
    1.  <span data-ttu-id="be4c4-168">选择**是**中**使用 SSO**用于单一登录。</span><span class="sxs-lookup"><span data-stu-id="be4c4-168">Select **Yes** in the **Use SSO** to use Single Sign-On.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="be4c4-169">请参阅[使用单一登录](../core/using-single-sign-on5.md)有关如何设置 SSO 信息。</span><span class="sxs-lookup"><span data-stu-id="be4c4-169">See [Using Single Sign-On](../core/using-single-sign-on5.md) for information about how to set up SSO.</span></span>  
  
    2.  <span data-ttu-id="be4c4-170">从列表中选择一个关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="be4c4-170">Select an affiliate application from the list.</span></span>  
  
         <span data-ttu-id="be4c4-171">一个由企业单一登录工具创建的关联应用程序表示一个应用程序（如 TIBCO Rendezvous）。</span><span class="sxs-lookup"><span data-stu-id="be4c4-171">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as TIBCO Rendezvous.</span></span> <span data-ttu-id="be4c4-172">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="be4c4-172">Microsoft BizTalk Adapter for TIBCO Rendezvous uses the credentials of an application user.</span></span> <span data-ttu-id="be4c4-173">这些凭据是从服务器系统的 SSO 数据库中为指定关联应用程序检索的。</span><span class="sxs-lookup"><span data-stu-id="be4c4-173">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="be4c4-174">有关如何创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications1.md)。</span><span class="sxs-lookup"><span data-stu-id="be4c4-174">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications1.md).</span></span>  
  
6.  <span data-ttu-id="be4c4-175">单击**应用**，然后单击**确定**后提供所有必要的信息，以接受连接信息。</span><span class="sxs-lookup"><span data-stu-id="be4c4-175">Click **Apply**, and then click **OK** after providing all required information to accept the connection information.</span></span>  
  
     <span data-ttu-id="be4c4-176">你必须设置为 TIBCO 会合访问 TIBCO 会合的 BizTalk 适配器的连接参数。</span><span class="sxs-lookup"><span data-stu-id="be4c4-176">You must set connection parameters for BizTalk Adapter for TIBCO Rendezvous to access TIBCO Rendezvous .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be4c4-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be4c4-177">See Also</span></span>  
 [<span data-ttu-id="be4c4-178">创建 TIBCO 会合发送处理程序</span><span class="sxs-lookup"><span data-stu-id="be4c4-178">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)