---
title: 创建 TIBCO Rendezvous 适配器发送项目 |Microsoft Docs
description: 创建发送端口，配置将从 BizTalk 消息发送到 TIBCO Rendezvous 传输属性
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad996c4f-e6ed-4582-a768-0cb1ad25b1d8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a267b9deac31d729d580cde79c62be96a612b4c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353553"
---
# <a name="create-tibco-rendezvous-send-handlers"></a><span data-ttu-id="b8f34-103">创建 TIBCO Rendezvous 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="b8f34-103">Create TIBCO Rendezvous Send Handlers</span></span>
<span data-ttu-id="b8f34-104">本部分介绍如何创建用于在 BizTalk Server 业务流程中使用 TIBCO Rendezvous 的架构。</span><span class="sxs-lookup"><span data-stu-id="b8f34-104">This section explains how to create a schema to use TIBCO Rendezvous in a BizTalk Server orchestration.</span></span>  
  
## <a name="create-a-send-port"></a><span data-ttu-id="b8f34-105">创建发送端口</span><span class="sxs-lookup"><span data-stu-id="b8f34-105">Create a send port</span></span>
  
1.  <span data-ttu-id="b8f34-106">在中**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b8f34-106">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand your application.</span></span>  
  
2.  <span data-ttu-id="b8f34-107">右键单击**发送端口**，依次指向**新建**，然后单击**静态要求响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="b8f34-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="b8f34-108">在中**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b8f34-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="b8f34-109">例如，键入发送端口的名称`SendToTIBCORV`。</span><span class="sxs-lookup"><span data-stu-id="b8f34-109">Type a name for the send port, for example, `SendToTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="b8f34-110">从**类型**下拉列表中，选择**TIBCO Rendezvous**。</span><span class="sxs-lookup"><span data-stu-id="b8f34-110">From the **Type** drop-down list, select **TIBCO Rendezvous**.</span></span>  
  
    3.  <span data-ttu-id="b8f34-111">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="b8f34-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="b8f34-112">从发送管道下拉列表，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="b8f34-112">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  <span data-ttu-id="b8f34-113">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="b8f34-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  

        > [!NOTE]
        > <span data-ttu-id="b8f34-114">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器要求您选择 XMLTransmit 管道的发送和接收的 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="b8f34-114">Microsoft BizTalk Adapter for TIBCO Rendezvous requires that you select XMLTransmit pipeline for send, and XMLReceive pipeline for receive.</span></span>
        
    6.  <span data-ttu-id="b8f34-115">单击**配置**可配置的发送端口。</span><span class="sxs-lookup"><span data-stu-id="b8f34-115">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="b8f34-116">在中**TIBCO Rendezvous 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b8f34-116">In the **TIBCO Rendezvous Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="b8f34-117">输入的属性。</span><span class="sxs-lookup"><span data-stu-id="b8f34-117">Enter the properties.</span></span>  
  
         <span data-ttu-id="b8f34-118">不需要设置的登录信息。</span><span class="sxs-lookup"><span data-stu-id="b8f34-118">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="b8f34-119">在列表中，选择为表示 TIBCO Rendezvous 系统所创建的 SSO 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="b8f34-119">In the list, select the SSO affiliate application you created to represent the TIBCO Rendezvous system.</span></span>  
  
    3.  <span data-ttu-id="b8f34-120">有关**使用 SSO**，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="b8f34-120">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="b8f34-121">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="b8f34-121">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="b8f34-122">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="b8f34-122">Click **OK**.</span></span>  

## <a name="set-the-transport-properties"></a><span data-ttu-id="b8f34-123">设置传输属性</span><span class="sxs-lookup"><span data-stu-id="b8f34-123">Set the transport properties</span></span>
<span data-ttu-id="b8f34-124">TIBCO Rendezvous 传输属性用于运行时。</span><span class="sxs-lookup"><span data-stu-id="b8f34-124">The TIBCO Rendezvous Transport property is used for run time.</span></span> <span data-ttu-id="b8f34-125">在中**传输属性**，设置标识你想要发布生成的消息的 TIBCO Rendezvous 域的连接参数。</span><span class="sxs-lookup"><span data-stu-id="b8f34-125">In the **Transport Properties**, you set the connection parameters that identify the TIBCO Rendezvous domain where you want to publish the generated messages.</span></span>  
  
 
1.  <span data-ttu-id="b8f34-126">上**TIBCO Rendezvous 传输属性**屏幕上，展开**已认证发送方属性**并输入以下信息。</span><span class="sxs-lookup"><span data-stu-id="b8f34-126">On the **TIBCO Rendezvous Transport Properties** screen, expand **Certified Sender Properties** and enter the following information.</span></span>  
  
     <span data-ttu-id="b8f34-127">![](../core/media/sadp-tibcoren-transs.gif "SAdp_TibcoRen_Transs")</span><span class="sxs-lookup"><span data-stu-id="b8f34-127">![](../core/media/sadp-tibcoren-transs.gif "SAdp_TibcoRen_Transs")</span></span>  
  
    |<span data-ttu-id="b8f34-128">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b8f34-128">Use this</span></span>|<span data-ttu-id="b8f34-129">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b8f34-129">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b8f34-130">**分类帐名称**</span><span class="sxs-lookup"><span data-stu-id="b8f34-130">**Ledger name**</span></span>|<span data-ttu-id="b8f34-131">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="b8f34-131">Default value is blank.</span></span> <span data-ttu-id="b8f34-132">要用于持久性认证的消息传递的分类帐文件名称。</span><span class="sxs-lookup"><span data-stu-id="b8f34-132">Ledger file name to use for persistent certified message delivery.</span></span> <span data-ttu-id="b8f34-133">使用仅限于本地驱动器。</span><span class="sxs-lookup"><span data-stu-id="b8f34-133">Use local drives only.</span></span>|  
    |<span data-ttu-id="b8f34-134">**可重复使用名称**</span><span class="sxs-lookup"><span data-stu-id="b8f34-134">**Reusable name**</span></span>|<span data-ttu-id="b8f34-135">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="b8f34-135">Default value is blank.</span></span> <span data-ttu-id="b8f34-136">若要使用认证的消息传递的可重用通信名称。</span><span class="sxs-lookup"><span data-stu-id="b8f34-136">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="b8f34-137">名称必须是唯一的而在网络上的所有认证的消息通信名称。</span><span class="sxs-lookup"><span data-stu-id="b8f34-137">The name must be unique among all certified message correspondent names on the network.</span></span>|  
  
2.  <span data-ttu-id="b8f34-138">展开**凭据**并输入以下信息以连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="b8f34-138">Expand **Credentials** and enter the following information for connection to the server.</span></span>  
  
    |<span data-ttu-id="b8f34-139">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b8f34-139">Use this</span></span>|<span data-ttu-id="b8f34-140">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b8f34-140">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b8f34-141">**密码**</span><span class="sxs-lookup"><span data-stu-id="b8f34-141">**Password**</span></span>|<span data-ttu-id="b8f34-142">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="b8f34-142">Default value is blank.</span></span> <span data-ttu-id="b8f34-143">登录到 Tibco Rendezvous 后台程序的密码。</span><span class="sxs-lookup"><span data-stu-id="b8f34-143">Password for login to a Tibco Rendezvous daemon.</span></span>|  
    |<span data-ttu-id="b8f34-144">**用户名**</span><span class="sxs-lookup"><span data-stu-id="b8f34-144">**User name**</span></span>|<span data-ttu-id="b8f34-145">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="b8f34-145">Default value is blank.</span></span> <span data-ttu-id="b8f34-146">Tibco Rendezvous 后台程序的用户名。</span><span class="sxs-lookup"><span data-stu-id="b8f34-146">User name for Tibco Rendezvous daemon.</span></span>|  
  
3.  <span data-ttu-id="b8f34-147">展开**常规设置**并输入以下信息以连接到 TIBCO Rendezvous 服务器。</span><span class="sxs-lookup"><span data-stu-id="b8f34-147">Expand **General Settings** and enter the following information for connection to the TIBCO Rendezvous server.</span></span>  
  
    |<span data-ttu-id="b8f34-148">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b8f34-148">Use this</span></span>|<span data-ttu-id="b8f34-149">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b8f34-149">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b8f34-150">**代码页编号**</span><span class="sxs-lookup"><span data-stu-id="b8f34-150">**Code Page Number**</span></span>|<span data-ttu-id="b8f34-151">默认值是 65001 （代码页 utf-8 编码）。</span><span class="sxs-lookup"><span data-stu-id="b8f34-151">Default value is 65001 (code page for UTF-8 encoding).</span></span> <span data-ttu-id="b8f34-152">这是 TIBCO Rendezvous SDK 用于字符串编码的代码页。</span><span class="sxs-lookup"><span data-stu-id="b8f34-152">This is the code page that the TIBCO Rendezvous SDK uses for String encoding.</span></span>|  
    |<span data-ttu-id="b8f34-153">**默认使用者名称**</span><span class="sxs-lookup"><span data-stu-id="b8f34-153">**Default Subject Name**</span></span>|<span data-ttu-id="b8f34-154">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="b8f34-154">Default is empty.</span></span> <span data-ttu-id="b8f34-155">在业务流程中设置的使用者名称。</span><span class="sxs-lookup"><span data-stu-id="b8f34-155">The subject name is set in the orchestration.</span></span> <span data-ttu-id="b8f34-156">如果一个端口用于一种消息类型，您可以提供默认使用者名称，并通过删除需要设置 name 属性的使用者来简化业务流程。</span><span class="sxs-lookup"><span data-stu-id="b8f34-156">If a port is used for one message type, you can provide a default subject name, and you can simplify orchestrations by removing the need to set the Subject name property.</span></span>|  
    |<span data-ttu-id="b8f34-157">**启用时间批处理**</span><span class="sxs-lookup"><span data-stu-id="b8f34-157">**Enable Time Batch**</span></span>|<span data-ttu-id="b8f34-158">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="b8f34-158">Default value is False.</span></span> <span data-ttu-id="b8f34-159">启用/禁用 TIBCO Rendezvous 时间批处理功能。</span><span class="sxs-lookup"><span data-stu-id="b8f34-159">Enable/Disable TIBCO Rendezvous Time Batch feature.</span></span>|  
    |<span data-ttu-id="b8f34-160">**将不受支持的类型映射到字符串**</span><span class="sxs-lookup"><span data-stu-id="b8f34-160">**Map Unsupported types to string**</span></span>|<span data-ttu-id="b8f34-161">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="b8f34-161">Default value is True.</span></span> <span data-ttu-id="b8f34-162">如果为 true，它是否可以不受支持的类型将映射到字符串中。</span><span class="sxs-lookup"><span data-stu-id="b8f34-162">If true, unsupported types are mapped to string if it is possible.</span></span> <span data-ttu-id="b8f34-163">如果为 False，则会生成运行时错误。</span><span class="sxs-lookup"><span data-stu-id="b8f34-163">If False, a run-time error is generated.</span></span>|  
    |<span data-ttu-id="b8f34-164">**二进制文件，如 TIBCO Rendezvous 程序集路径**</span><span class="sxs-lookup"><span data-stu-id="b8f34-164">**Path to Binaries, such as TIBCO Rendezvous assemblies**</span></span>|<span data-ttu-id="b8f34-165">如果尚不在路径环境变量，提供此信息。</span><span class="sxs-lookup"><span data-stu-id="b8f34-165">Provide this information if it is not already in the PATH environment variable.</span></span>|  
    |<span data-ttu-id="b8f34-166">**保留订单**</span><span class="sxs-lookup"><span data-stu-id="b8f34-166">**Preserver Order**</span></span>|<span data-ttu-id="b8f34-167">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="b8f34-167">Default value is True.</span></span> <span data-ttu-id="b8f34-168">使逻辑将消息发送到 TIBCO Rendezvous 从 BizTalk Server 接收的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="b8f34-168">Enables logic to send messages to TIBCO Rendezvous in the same order they were received from BizTalk Server.</span></span> <span data-ttu-id="b8f34-169">此参数强制按相同顺序; 的发布它并不意味着订阅服务器的相同顺序接收它们。</span><span class="sxs-lookup"><span data-stu-id="b8f34-169">This parameter forces publishing in the same order; it does not mean that subscribers receive them in the same order.</span></span>|  
    |<span data-ttu-id="b8f34-170">**发送端口标识符**</span><span class="sxs-lookup"><span data-stu-id="b8f34-170">**Send Port Identifier**</span></span>|<span data-ttu-id="b8f34-171">此标识符出现在与此端口相关联的日志消息。</span><span class="sxs-lookup"><span data-stu-id="b8f34-171">This identifier appears in log messages associated with this port.</span></span> <span data-ttu-id="b8f34-172">它作为方便提供。</span><span class="sxs-lookup"><span data-stu-id="b8f34-172">It is provided as a convenience.</span></span>|  
  
4.  <span data-ttu-id="b8f34-173">展开**Rendezvous 传输**并输入到 TIBCO Rendezvous 服务器的连接的信息，请单击**应用**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b8f34-173">Expand **Rendezvous Transport** and enter the information for connection to the TIBCO Rendezvous server, click **Apply**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="b8f34-174">必须设置为用于 TIBCO Rendezvous 以访问 TIBCO Rendezvous 的 Microsoft BizTalk 适配器的连接参数。</span><span class="sxs-lookup"><span data-stu-id="b8f34-174">You must set connection parameters for Microsoft BizTalk Adapter for TIBCO Rendezvous to access TIBCO Rendezvous.</span></span>  
  
    |<span data-ttu-id="b8f34-175">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b8f34-175">Use this</span></span>|<span data-ttu-id="b8f34-176">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b8f34-176">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b8f34-177">**守护程序**</span><span class="sxs-lookup"><span data-stu-id="b8f34-177">**Daemon**</span></span>|<span data-ttu-id="b8f34-178">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="b8f34-178">Default is empty.</span></span><br /><br /> <span data-ttu-id="b8f34-179">Rendezvous 传输后台程序参数。</span><span class="sxs-lookup"><span data-stu-id="b8f34-179">Rendezvous Transport Daemon parameter.</span></span>|  
    |<span data-ttu-id="b8f34-180">**Network**</span><span class="sxs-lookup"><span data-stu-id="b8f34-180">**Network**</span></span>|<span data-ttu-id="b8f34-181">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="b8f34-181">Default is empty.</span></span><br /><br /> <span data-ttu-id="b8f34-182">Rendezvous 传输网络参数。</span><span class="sxs-lookup"><span data-stu-id="b8f34-182">Rendezvous Transport Network parameter.</span></span>|  
    |<span data-ttu-id="b8f34-183">**服务**</span><span class="sxs-lookup"><span data-stu-id="b8f34-183">**Service**</span></span>|<span data-ttu-id="b8f34-184">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="b8f34-184">Default is empty.</span></span><br /><br /> <span data-ttu-id="b8f34-185">Rendezvous 传输服务参数。</span><span class="sxs-lookup"><span data-stu-id="b8f34-185">Rendezvous Transport Service parameter.</span></span>|  
  
5.  <span data-ttu-id="b8f34-186">提供使用单一登录 (SSO) 的凭据。</span><span class="sxs-lookup"><span data-stu-id="b8f34-186">Provide credentials using Single Sign-On (SSO).</span></span>  
  
     <span data-ttu-id="b8f34-187">有两种方法可用于访问 TIBCO Rendezvous 系统。</span><span class="sxs-lookup"><span data-stu-id="b8f34-187">There are two methods that you can use to access the TIBCO Rendezvous system.</span></span> <span data-ttu-id="b8f34-188">您可以使用凭据 （用户名和密码参数） 或单一登录。</span><span class="sxs-lookup"><span data-stu-id="b8f34-188">You can use Credentials (User Name and Password parameters) or Single Sign-On.</span></span>  
  
    1.  <span data-ttu-id="b8f34-189">选择**是**中**使用 SSO**若要使用单一登录。</span><span class="sxs-lookup"><span data-stu-id="b8f34-189">Select **Yes** in the **Use SSO** to use Single Sign-On.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="b8f34-190">请参阅[安全](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)了解如何设置 SSO。</span><span class="sxs-lookup"><span data-stu-id="b8f34-190">See [Security](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md) for information about how to set up SSO.</span></span>  
  
    2.  <span data-ttu-id="b8f34-191">从列表中选择关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="b8f34-191">Select an affiliate application from the list.</span></span>  
  
         <span data-ttu-id="b8f34-192">企业单一登录工具创建的关联应用程序表示诸如 TIBCO Rendezvous 等的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b8f34-192">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as TIBCO Rendezvous.</span></span> <span data-ttu-id="b8f34-193">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="b8f34-193">Microsoft BizTalk Adapter for TIBCO Rendezvous uses the credentials of an application user.</span></span> <span data-ttu-id="b8f34-194">从指定的关联应用程序的服务器系统的 SSO 数据库检索这些凭据。</span><span class="sxs-lookup"><span data-stu-id="b8f34-194">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="b8f34-195">有关如何创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications1.md)。</span><span class="sxs-lookup"><span data-stu-id="b8f34-195">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications1.md).</span></span>  
  
6.  <span data-ttu-id="b8f34-196">单击**Apply**，然后单击**确定**提供接受连接信息所需的所有信息后。</span><span class="sxs-lookup"><span data-stu-id="b8f34-196">Click **Apply**, and then click **OK** after providing all required information to accept the connection information.</span></span>  
  
     <span data-ttu-id="b8f34-197">必须设置为用于 TIBCO Rendezvous 以访问 TIBCO Rendezvous 的 BizTalk 适配器的连接参数。</span><span class="sxs-lookup"><span data-stu-id="b8f34-197">You must set connection parameters for BizTalk Adapter for TIBCO Rendezvous to access TIBCO Rendezvous .</span></span>  


## <a name="next-steps"></a><span data-ttu-id="b8f34-198">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b8f34-198">Next steps</span></span>
  
-   [<span data-ttu-id="b8f34-199">从 BizTalk Server 中使用 TIBCO Rendezvous 发送端口</span><span class="sxs-lookup"><span data-stu-id="b8f34-199">Using TIBCO Rendezvous Send Ports from BizTalk Server</span></span>](../core/using-tibco-rendezvous-send-ports-from-biztalk-server.md)  
  
-   [<span data-ttu-id="b8f34-200">TIBCO Rendezvous 中用于发送处理程序的数据类型映射</span><span class="sxs-lookup"><span data-stu-id="b8f34-200">Data Type Mapping for Send Handlers in TIBCO Rendezvous</span></span>](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md)  
  
-   [<span data-ttu-id="b8f34-201">BizTalk Server 消息上下文属性（发送处理程序）</span><span class="sxs-lookup"><span data-stu-id="b8f34-201">BizTalk Server Message Context Properties (Send Handlers)</span></span>](../core/biztalk-server-message-context-properties-send-handlers.md)