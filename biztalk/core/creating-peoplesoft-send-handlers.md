---
title: "创建 PeopleSoft 适配器发送项目 |Microsoft 文档"
description: "创建发送端口、 发送传输属性和更新最大并发调用，以将消息发送到 BizTalk Server 中使用 PeopleSoft Enterprise 适配器 PeopleSoft"
ms.custom: 
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce67da59-26a6-44a2-929c-ed3acb21d407
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31889aa0c4f13826758547fb5e8e7acdf061239b
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="create-peoplesoft-send-artifacts"></a><span data-ttu-id="a9533-103">创建 PeopleSoft 发送项目</span><span class="sxs-lookup"><span data-stu-id="a9533-103">Create PeopleSoft send artifacts</span></span>
<span data-ttu-id="a9533-104">适用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器用于访问 PeopleSoft，以及浏览可用组件或处理 SOAP 请求。</span><span class="sxs-lookup"><span data-stu-id="a9533-104">Microsoft BizTalk Adapter for PeopleSoft Enterprise accesses PeopleSoft and explores available components or processes SOAP requests.</span></span> <span data-ttu-id="a9533-105">本主题演示如何在 BizTalk Server 管理来使用 PeopleSoft 适配器中创建的发送项目。</span><span class="sxs-lookup"><span data-stu-id="a9533-105">This topic shows you how to create the send artifacts in BizTalk Server Administration to use the PeopleSoft adapter.</span></span>


## <a name="create-the-send-port"></a><span data-ttu-id="a9533-106">创建发送端口</span><span class="sxs-lookup"><span data-stu-id="a9533-106">Create the send port</span></span>

1.  <span data-ttu-id="a9533-107">在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="a9533-107">In the BizTalk Server Administration Console,expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="a9533-108">右键单击**发送端口**，选择**新建**，然后选择**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="a9533-108">Right-click **Send Ports**, select **New**, and then select **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="a9533-109">在**发送端口属性**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a9533-109">In the **Send Port Properties**, do the following:</span></span>  
  
    1.  <span data-ttu-id="a9533-110">输入发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="a9533-110">Enter a name for the send port.</span></span> <span data-ttu-id="a9533-111">例如，输入`SSOSendToPeopleSoft`。</span><span class="sxs-lookup"><span data-stu-id="a9533-111">For example, enter `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="a9533-112">从**类型**下拉列表中，选择**PeopleSoft**。</span><span class="sxs-lookup"><span data-stu-id="a9533-112">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="a9533-113">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="a9533-113">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="a9533-114">从发送管道下拉列表中选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="a9533-114">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="a9533-115">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="a9533-115">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="a9533-116">选择**配置**配置发送端口。</span><span class="sxs-lookup"><span data-stu-id="a9533-116">Select **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="a9533-117">在**PeopleSoft 传输属性**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a9533-117">In the **PeopleSoft Transport Properties**, do the following:</span></span>  
  
    1.  <span data-ttu-id="a9533-118">展开**适配器所需属性**，并输入**应用程序服务器路径**， **JAVA_HOME**，**用户名**， **密码**，和连接到 Peoplesoft 系统的 Jar 文件。</span><span class="sxs-lookup"><span data-stu-id="a9533-118">Expand **Adapter Required Properties**, and enter **Application Server Path**, **JAVA_HOME**, **user name**, **password**, and the Jar file for connecting into the Peoplesoft system.</span></span>  
  
         <span data-ttu-id="a9533-119">您不必设置登录信息。</span><span class="sxs-lookup"><span data-stu-id="a9533-119">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="a9533-120">在列表中选择为表示 PeopleSoft 系统所创建的 SSO 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="a9533-120">In the list, select the SSO affiliate application you created to represent the PeopleSoft system.</span></span>  
  
    3.  <span data-ttu-id="a9533-121">有关**使用 SSO**，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="a9533-121">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="a9533-122">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="a9533-122">Select **OK**.</span></span>  
  
5.  <span data-ttu-id="a9533-123">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="a9533-123">Select **OK**.</span></span>

## <a name="set-the-transport-properties"></a><span data-ttu-id="a9533-124">设置传输属性</span><span class="sxs-lookup"><span data-stu-id="a9533-124">Set the transport properties</span></span>
<span data-ttu-id="a9533-125">PeopleSoft 传输属性用于运行时和设计时。</span><span class="sxs-lookup"><span data-stu-id="a9533-125">The PeopleSoft transport properties are used for design and run time.</span></span> <span data-ttu-id="a9533-126">在**传输属性**对话框中，你设置的连接和凭据参数特定于服务器系统和你尝试访问的对象。</span><span class="sxs-lookup"><span data-stu-id="a9533-126">In the **Transport Properties** dialog box, you set the connection and credential parameters specific to the server system and the objects you are trying to access.</span></span>  
  
 ![](../core/media/peop-peoplesofttransportpropertiess.gif "Peop_PeopleSoftTransportPropertiess")  
  
1.  <span data-ttu-id="a9533-127">展开“适配器必需属性”，然后填写连接到 PeopleSoft 服务器所需的各项信息。</span><span class="sxs-lookup"><span data-stu-id="a9533-127">Expand the Adapter Required Properties and fill in all required information for connection to the PeopleSoft server.</span></span>  
  
     <span data-ttu-id="a9533-128">必须设置配置参数才能将适用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器连接到 PeopleSoft Enterprise。</span><span class="sxs-lookup"><span data-stu-id="a9533-128">You must set configuration parameters to connect Microsoft BizTalk Adapter for PeopleSoft Enterprise to PeopleSoft Enterprise.</span></span> <span data-ttu-id="a9533-129">此数据是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="a9533-129">This data is case sensitive.</span></span>  
  
    |<span data-ttu-id="a9533-130">参数</span><span class="sxs-lookup"><span data-stu-id="a9533-130">Parameter</span></span>|<span data-ttu-id="a9533-131">Description</span><span class="sxs-lookup"><span data-stu-id="a9533-131">Description</span></span>|  
    |---------------|-----------------|  
    |`Application Server Path`|<span data-ttu-id="a9533-132">此字符串代表 PeopleSoft 应用程序服务器运行的计算机和侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="a9533-132">A string representing the computer and port on which the PeopleSoft Application Server is running and listening.</span></span> <span data-ttu-id="a9533-133">PeopleSoft 8 应用程序的 URL 路径的语法是 / / < 计算机名 >:\<端口 >。</span><span class="sxs-lookup"><span data-stu-id="a9533-133">The syntax of the URL path to the PeopleSoft 8 Application is //<computer_name>:\<port>.</span></span> <span data-ttu-id="a9533-134">向你 PeopleSoft 管理员请求\<端口 > 值。</span><span class="sxs-lookup"><span data-stu-id="a9533-134">Ask your PeopleSoft administrator for the \<port> value.</span></span> <span data-ttu-id="a9533-135">\<端口 > 值是震动协议侦听器端口，不是应用程序服务器端口。</span><span class="sxs-lookup"><span data-stu-id="a9533-135">The \<port> value is the JOLT protocol listener port, not the App Server port.</span></span> <span data-ttu-id="a9533-136">默认 JOLT 端口为 9000。</span><span class="sxs-lookup"><span data-stu-id="a9533-136">The default JOLT port is 9000.</span></span>|  
    |`JAVA_HOME`|<span data-ttu-id="a9533-137">设置 JAVA_HOME 变量以指向你 JDK 的安装，例如： **C:\j2sdk1.4.2_08**。</span><span class="sxs-lookup"><span data-stu-id="a9533-137">Set the JAVA_HOME variable to point to your JDK installation, for example: **C:\j2sdk1.4.2_08**.</span></span>|  
    |`Password`|<span data-ttu-id="a9533-138">如果你未选择**使用 SSO**，必须设置为 BizTalk 适配器 PeopleSoft 企业访问服务器系统的凭据参数。</span><span class="sxs-lookup"><span data-stu-id="a9533-138">If you did not select **Use SSO**, you must set credential parameters for the BizTalk Adapter for PeopleSoft Enterprise to access the server system.</span></span><br /><br /> <span data-ttu-id="a9533-139">表示用户密码的字符串，用于登录到 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="a9533-139">A string representing the user's password for logon to a PeopleSoft system.</span></span> <span data-ttu-id="a9533-140">不会显示密码中的字符，而是以星号 (*) 表示这些字符。</span><span class="sxs-lookup"><span data-stu-id="a9533-140">The characters do not appear but are represented by asterisks (*).</span></span>|  
    |`PeopleSoft 8.x Jar Files`|<span data-ttu-id="a9533-141">若要使用组件接口（仅限 PeopleSoft 8），则必须更新 CLASSPATH 以包含 PeopleSoft 组件接口 jar 文件。</span><span class="sxs-lookup"><span data-stu-id="a9533-141">To use Ccmponent interfaces (PeopleSoft 8 only) you must update your CLASSPATH to include the PeopleSoft Component Interface jar file.</span></span> <span data-ttu-id="a9533-142">例如： **< PeopleSoft_Home > \web\PSJOA\psjoa.jar**。</span><span class="sxs-lookup"><span data-stu-id="a9533-142">For example: **<PeopleSoft_Home>\web\PSJOA\psjoa.jar**.</span></span>|  
    |`User Name`|<span data-ttu-id="a9533-143">如果你未选择**使用 SSO**，必须设置为 BizTalk 适配器 PeopleSoft 企业访问服务器系统的凭据参数。</span><span class="sxs-lookup"><span data-stu-id="a9533-143">If you did not select **Use SSO**, you must set credential parameters for the BizTalk Adapter for PeopleSoft Enterprise to access the server system.</span></span><br /><br /> <span data-ttu-id="a9533-144">表示用户名的字符串，用于登录到 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="a9533-144">A string representing a user name required for logon to a PeopleSoft system.</span></span>|  
  
2.  <span data-ttu-id="a9533-145">输入**其他参数**时日期用作键的值; 它具有不同的格式。</span><span class="sxs-lookup"><span data-stu-id="a9533-145">Enter an **Additional parameters** value when a date is used as a key; it has a different format.</span></span> <span data-ttu-id="a9533-146">YYYY-月-日是默认格式。</span><span class="sxs-lookup"><span data-stu-id="a9533-146">YYYY-MM-DD is the default format.</span></span>  
  
3.  <span data-ttu-id="a9533-147">输入**并发控制**值在表示的调用，例如 200、 数**最大并发调用**如有必要。</span><span class="sxs-lookup"><span data-stu-id="a9533-147">Enter a **Concurrency control** value representing the number of calls, for example 200, in **Max Concurrent Calls** if it is required.</span></span>  
  
     <span data-ttu-id="a9533-148">**最大并发调用**参数激活过载保护，如果后端服务器无法处理的数据量。</span><span class="sxs-lookup"><span data-stu-id="a9533-148">The **Max Concurrent Calls** parameter activates an overload protection if the back-end server cannot process the amount of data.</span></span> <span data-ttu-id="a9533-149">并行调用是适配器尚未进行回复的请求。</span><span class="sxs-lookup"><span data-stu-id="a9533-149">A concurrent call is a request for which the adapter does not yet have a reply.</span></span> <span data-ttu-id="a9533-150">设置**最大并发调用**其中吞吐量超过后端处理功能的实例中。</span><span class="sxs-lookup"><span data-stu-id="a9533-150">Set **Max Concurrent Calls** in instances where the throughput exceeds back-end processing capabilities.</span></span>  
  
     <span data-ttu-id="a9533-151">此字段的默认值为 -1，意味着未进行任何保护。</span><span class="sxs-lookup"><span data-stu-id="a9533-151">The default value for this field is -1, meaning no protection occurs.</span></span>  
  
     <span data-ttu-id="a9533-152">如果 BizTalk Server 将请求提交到传输适配器，并且调用等于或超过为设置的值的并发数**最大并发调用**，提交请求被保存，直到并发调用数量的线程为降低到低于设置的值。</span><span class="sxs-lookup"><span data-stu-id="a9533-152">If BizTalk Server submits a request to the Transmit adapter, and the number of concurrent calls equals or exceeds the value set for **Max Concurrent Calls**, the thread submitting the request is saved until the concurrent calls number decreases to below the set value.</span></span>  

## <a name="update-max-concurrent-calls"></a><span data-ttu-id="a9533-153">更新最大并发调用</span><span class="sxs-lookup"><span data-stu-id="a9533-153">Update Max Concurrent Calls</span></span>

<span data-ttu-id="a9533-154">`Max Concurrent Calls` 参数是一种用来优化配置的功能。</span><span class="sxs-lookup"><span data-stu-id="a9533-154">The `Max Concurrent Calls` parameter is a feature that enables you to optimize your configuration.</span></span> <span data-ttu-id="a9533-155">在吞吐量超过了后端处理能力的情况下，可以使用此参数。</span><span class="sxs-lookup"><span data-stu-id="a9533-155">You use this parameter in instances where the throughput exceeds back-end processing capabilities.</span></span> <span data-ttu-id="a9533-156">你可以将参数添加到中的适配器**发送端口传输属性**对话框中，若要激活消息重载保护。</span><span class="sxs-lookup"><span data-stu-id="a9533-156">You can add the parameter to the adapters in the **Send Port Transport Properties** dialog box to activate message overload protection.</span></span> <span data-ttu-id="a9533-157">默认值为 -1，表示不限制调用数量。</span><span class="sxs-lookup"><span data-stu-id="a9533-157">The default is -1, meaning the calls are unlimited.</span></span>  
  
<span data-ttu-id="a9533-158">当 BizTalk Server 将消息提交到传输适配器时，它首先接收来自适配器的一个批并对批调用 `TransmitMessage()` 以传输每个消息。</span><span class="sxs-lookup"><span data-stu-id="a9533-158">When BizTalk Server submits messages to the transmit adapter, it first receives a batch from the adapter and invokes `TransmitMessage()` on the batch to transmit each message.</span></span> <span data-ttu-id="a9533-159">完成上述操作后，BizTalk Server 对批调用 `Done()`，然后适配器开始将消息传输到后端。</span><span class="sxs-lookup"><span data-stu-id="a9533-159">When done, BizTalk Server invokes `Done()` on the batch, and the adapter starts transmitting the messages to the back-end.</span></span> <span data-ttu-id="a9533-160">如果 BizTalk Server 在调用 `Done` 之前获得了多个批，`Done` 命令可能永远不会发生。</span><span class="sxs-lookup"><span data-stu-id="a9533-160">If BizTalk Server obtains multiple batches before `Done` is invoked, the `Done` command might never occur.</span></span> <span data-ttu-id="a9533-161">通过设置批中的最大消息数量，可以控制传输到后端的消息。</span><span class="sxs-lookup"><span data-stu-id="a9533-161">By setting the maximum number of messages in a batch, you can control messages to the back-end.</span></span> <span data-ttu-id="a9533-162">对此参数的更改会在一分钟后生效。</span><span class="sxs-lookup"><span data-stu-id="a9533-162">Changing this parameter takes effect in a minute.</span></span> <span data-ttu-id="a9533-163">BizTalk Server 必须检索保存在 SQL 数据库中的适配器配置的更改。</span><span class="sxs-lookup"><span data-stu-id="a9533-163">BizTalk Server must retrieve the changes to the adapter configuration that is saved in the SQL database.</span></span>  
  
### <a name="change-the-max-concurrent-calls-parameter"></a><span data-ttu-id="a9533-164">更改最大并发调用参数</span><span class="sxs-lookup"><span data-stu-id="a9533-164">Change the Max Concurrent Calls parameter</span></span>  
  
1.  <span data-ttu-id="a9533-165">在**发送端口传输属性**对话框框中，输入**连接**值。</span><span class="sxs-lookup"><span data-stu-id="a9533-165">In the **Send Port Transport Properties** dialog box, enter a **Connection** value.</span></span>  
  
     <span data-ttu-id="a9533-166">默认值为 40 个会话。</span><span class="sxs-lookup"><span data-stu-id="a9533-166">The default value is 40 sessions.</span></span> <span data-ttu-id="a9533-167">如果您使用一个较小的值，可能会出现运行时性能下降。</span><span class="sxs-lookup"><span data-stu-id="a9533-167">If you use a smaller value, you might experience degradation in run-time performance.</span></span> <span data-ttu-id="a9533-168">反之亦然，使用较大的值，则会超出服务器的能力并导致运行时错误。</span><span class="sxs-lookup"><span data-stu-id="a9533-168">The opposite is also true; a bigger value could exceed the ability of the server and result in run-time errors.</span></span>  
  
2.  <span data-ttu-id="a9533-169">选择**是**为**刷新代理**强制 runtimeagent.exe 以及要在需要时自动重新启动 browsingagent.exe 过程。</span><span class="sxs-lookup"><span data-stu-id="a9533-169">Select **Yes** for **Refresh Agent** to force the runtimeagent.exe and the browsingagent.exe processes to restart automatically when required.</span></span>  
  
     <span data-ttu-id="a9533-170">例如，您希望进程在出现以下情况时自动重新启动：丢失了与服务器的连接；或者向服务器中添加了内容，但是由于它没有显示在 Microsoft 适配器向导中而无法选择它。</span><span class="sxs-lookup"><span data-stu-id="a9533-170">For example, you want the process to restart automatically if it loses connection with the server, or if you add something to the server and it does not appear in the Microsoft Adapter Wizard for selection.</span></span>  
  
     <span data-ttu-id="a9533-171">**刷新代理**参数刷新浏览和运行时代理。</span><span class="sxs-lookup"><span data-stu-id="a9533-171">The **Refresh Agent** parameter refreshes both the browsing and the run-time agents.</span></span> <span data-ttu-id="a9533-172">runtimeagent.exe 在一分钟延迟后或在下一次发送呼叫时更新。</span><span class="sxs-lookup"><span data-stu-id="a9533-172">The runtimeagent.exe updates after a delay of one minute or at the next send call.</span></span>  
  
3.  <span data-ttu-id="a9533-173">提供凭据以访问 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="a9533-173">Provide credentials to access the PeopleSoft system.</span></span>  
  
     <span data-ttu-id="a9533-174">您可以使用两种方法来访问系统：</span><span class="sxs-lookup"><span data-stu-id="a9533-174">You can use two methods to access the system:</span></span>  
  
    -   <span data-ttu-id="a9533-175">登录凭据（传输属性登录参数）</span><span class="sxs-lookup"><span data-stu-id="a9533-175">Login Credentials (Transport Properties Login parameters)</span></span>  
  
    -   <span data-ttu-id="a9533-176">单一登录</span><span class="sxs-lookup"><span data-stu-id="a9533-176">Single Sign-On</span></span>  
  
4.  <span data-ttu-id="a9533-177">选择**是**为**使用 SSO**用于单一登录。</span><span class="sxs-lookup"><span data-stu-id="a9533-177">Select **Yes** for **Use SSO** to use Single Sign-On.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a9533-178">有关详细信息，请参阅[安全适配器](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="a9533-178">For more information, see [Secure the adapter](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md).</span></span> 
  
5.  <span data-ttu-id="a9533-179">在列表中选择一个关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="a9533-179">Select an affiliate application in the list.</span></span>  
  
     <span data-ttu-id="a9533-180">由企业单一登录工具创建的关联应用程序，表示一个应用程序，如 PeopleSoft。</span><span class="sxs-lookup"><span data-stu-id="a9533-180">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as PeopleSoft.</span></span> <span data-ttu-id="a9533-181">适用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="a9533-181">Microsoft BizTalk Adapter for PeopleSoft Enterprise uses the credentials of an application user.</span></span> <span data-ttu-id="a9533-182">这些凭据是从服务器系统的 SSO 数据库中为指定关联应用程序检索的。</span><span class="sxs-lookup"><span data-stu-id="a9533-182">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span> <span data-ttu-id="a9533-183">凭据是启动 BizTalk 项目的用户（应用程序用户）的凭据。</span><span class="sxs-lookup"><span data-stu-id="a9533-183">The credentials are those of the user (the application user) who launched the BizTalk project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a9533-184">有关如何创建关联应用程序的详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications2.md)，或 Microsoft BizTalk Server 联机帮助。</span><span class="sxs-lookup"><span data-stu-id="a9533-184">For more information about how to create affiliate applications, see [Creating Affiliate Applications](../core/creating-affiliate-applications2.md), or the Microsoft BizTalk Server online Help.</span></span>  
  
6.  <span data-ttu-id="a9533-185">提供所有所需的信息，以接受连接信息后，单击**应用**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a9533-185">After providing all required information to accept the connection information, click **Apply**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="a9533-186">您必须为适用于 PeopleSoft Enterprise 的 BizTalk 适配器设置连接参数，以访问 PeopleSoft。</span><span class="sxs-lookup"><span data-stu-id="a9533-186">You must set connection parameters for the BizTalk Adapter for PeopleSoft Enterprise to access PeopleSoft.</span></span>  
  

## <a name="next"></a><span data-ttu-id="a9533-187">Next</span><span class="sxs-lookup"><span data-stu-id="a9533-187">Next</span></span>
  
[<span data-ttu-id="a9533-188">将 PeopleSoft 架构导入到 BizTalk Server 项目</span><span class="sxs-lookup"><span data-stu-id="a9533-188">Import PeopleSoft Schemas into BizTalk Server Projects</span></span>](../core/importing-peoplesoft-schemas-into-biztalk-server-projects.md)  
[<span data-ttu-id="a9533-189">接收来自 PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="a9533-189">Receive from PeopleSoft</span></span>](../core/receiving-from-peoplesoft.md)