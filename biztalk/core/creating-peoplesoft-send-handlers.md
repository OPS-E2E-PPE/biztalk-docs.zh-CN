---
title: 创建 PeopleSoft 适配器发送项目 |Microsoft Docs
description: 创建发送端口、 发送传输属性和更新最大并发调用将消息发送到 PeopleSoft 在 BizTalk Server 中使用 PeopleSoft Enterprise 适配器
ms.custom: ''
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce67da59-26a6-44a2-929c-ed3acb21d407
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4857bf6444f30da0162cf7ffbeb8572042ba762
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390427"
---
# <a name="create-peoplesoft-send-artifacts"></a><span data-ttu-id="494c7-103">创建 PeopleSoft 发送项目</span><span class="sxs-lookup"><span data-stu-id="494c7-103">Create PeopleSoft send artifacts</span></span>
<span data-ttu-id="494c7-104">用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器访问 PeopleSoft 和浏览可用组件或处理 SOAP 请求。</span><span class="sxs-lookup"><span data-stu-id="494c7-104">Microsoft BizTalk Adapter for PeopleSoft Enterprise accesses PeopleSoft and explores available components or processes SOAP requests.</span></span> <span data-ttu-id="494c7-105">本主题演示如何在 BizTalk Server 管理为使用 PeopleSoft 适配器创建发送项目。</span><span class="sxs-lookup"><span data-stu-id="494c7-105">This topic shows you how to create the send artifacts in BizTalk Server Administration to use the PeopleSoft adapter.</span></span>


## <a name="create-the-send-port"></a><span data-ttu-id="494c7-106">创建发送端口</span><span class="sxs-lookup"><span data-stu-id="494c7-106">Create the send port</span></span>

1.  <span data-ttu-id="494c7-107">在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开所需的应用程序。</span><span class="sxs-lookup"><span data-stu-id="494c7-107">In the BizTalk Server Administration Console,expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="494c7-108">右键单击**发送端口**，选择**新建**，然后选择**静态要求响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="494c7-108">Right-click **Send Ports**, select **New**, and then select **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="494c7-109">在中**发送端口属性**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="494c7-109">In the **Send Port Properties**, do the following:</span></span>  
  
    1.  <span data-ttu-id="494c7-110">输入发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="494c7-110">Enter a name for the send port.</span></span> <span data-ttu-id="494c7-111">例如，输入 `SSOSendToPeopleSoft`。</span><span class="sxs-lookup"><span data-stu-id="494c7-111">For example, enter `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="494c7-112">从**类型**下拉列表中，选择**PeopleSoft**。</span><span class="sxs-lookup"><span data-stu-id="494c7-112">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="494c7-113">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="494c7-113">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="494c7-114">从发送管道下拉列表，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="494c7-114">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="494c7-115">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="494c7-115">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="494c7-116">选择**配置**可配置的发送端口。</span><span class="sxs-lookup"><span data-stu-id="494c7-116">Select **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="494c7-117">在中**PeopleSoft 传输属性**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="494c7-117">In the **PeopleSoft Transport Properties**, do the following:</span></span>  
  
    1.  <span data-ttu-id="494c7-118">展开**适配器所需的属性**，并输入**应用程序服务器路径**， **JAVA_HOME**，**用户名**， **密码**，和用于连接到 Peoplesoft 系统的 Jar 文件。</span><span class="sxs-lookup"><span data-stu-id="494c7-118">Expand **Adapter Required Properties**, and enter **Application Server Path**, **JAVA_HOME**, **user name**, **password**, and the Jar file for connecting into the Peoplesoft system.</span></span>  
  
         <span data-ttu-id="494c7-119">不需要设置的登录信息。</span><span class="sxs-lookup"><span data-stu-id="494c7-119">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="494c7-120">在列表中，选择创建为表示 PeopleSoft 系统的 SSO 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="494c7-120">In the list, select the SSO affiliate application you created to represent the PeopleSoft system.</span></span>  
  
    3.  <span data-ttu-id="494c7-121">有关**使用 SSO**，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="494c7-121">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="494c7-122">选择 **确定**。</span><span class="sxs-lookup"><span data-stu-id="494c7-122">Select **OK**.</span></span>  
  
5.  <span data-ttu-id="494c7-123">选择 **确定**。</span><span class="sxs-lookup"><span data-stu-id="494c7-123">Select **OK**.</span></span>

## <a name="set-the-transport-properties"></a><span data-ttu-id="494c7-124">设置传输属性</span><span class="sxs-lookup"><span data-stu-id="494c7-124">Set the transport properties</span></span>
<span data-ttu-id="494c7-125">PeopleSoft 传输属性用于设计和运行时。</span><span class="sxs-lookup"><span data-stu-id="494c7-125">The PeopleSoft transport properties are used for design and run time.</span></span> <span data-ttu-id="494c7-126">在中**传输属性**对话框中，您设置的连接和凭据参数特定于服务器系统和你尝试访问的对象。</span><span class="sxs-lookup"><span data-stu-id="494c7-126">In the **Transport Properties** dialog box, you set the connection and credential parameters specific to the server system and the objects you are trying to access.</span></span>  
  
 <span data-ttu-id="494c7-127">![](../core/media/peop-peoplesofttransportpropertiess.gif "Peop_PeopleSoftTransportPropertiess")</span><span class="sxs-lookup"><span data-stu-id="494c7-127">![](../core/media/peop-peoplesofttransportpropertiess.gif "Peop_PeopleSoftTransportPropertiess")</span></span>  
  
1.  <span data-ttu-id="494c7-128">展开适配器必需属性，填写连接到 PeopleSoft 服务器的所有所需信息。</span><span class="sxs-lookup"><span data-stu-id="494c7-128">Expand the Adapter Required Properties and fill in all required information for connection to the PeopleSoft server.</span></span>  
  
     <span data-ttu-id="494c7-129">必须设置连接到 PeopleSoft Enterprise 的 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器的配置参数。</span><span class="sxs-lookup"><span data-stu-id="494c7-129">You must set configuration parameters to connect Microsoft BizTalk Adapter for PeopleSoft Enterprise to PeopleSoft Enterprise.</span></span> <span data-ttu-id="494c7-130">此数据是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="494c7-130">This data is case sensitive.</span></span>  
  
    |<span data-ttu-id="494c7-131">参数</span><span class="sxs-lookup"><span data-stu-id="494c7-131">Parameter</span></span>|<span data-ttu-id="494c7-132">Description</span><span class="sxs-lookup"><span data-stu-id="494c7-132">Description</span></span>|  
    |---------------|-----------------|  
    |`Application Server Path`|<span data-ttu-id="494c7-133">表示的计算机和 PeopleSoft 应用程序服务器是运行和侦听的端口的字符串。</span><span class="sxs-lookup"><span data-stu-id="494c7-133">A string representing the computer and port on which the PeopleSoft Application Server is running and listening.</span></span> <span data-ttu-id="494c7-134">PeopleSoft 8 应用程序的 URL 路径的语法是 / / < 计算机名 >:\<端口\>。</span><span class="sxs-lookup"><span data-stu-id="494c7-134">The syntax of the URL path to the PeopleSoft 8 Application is //<computer_name>:\<port\>.</span></span> <span data-ttu-id="494c7-135">询问有关 PeopleSoft 管理员\<端口\>值。</span><span class="sxs-lookup"><span data-stu-id="494c7-135">Ask your PeopleSoft administrator for the \<port\> value.</span></span> <span data-ttu-id="494c7-136">\<端口\>值指的是 JOLT 协议侦听程序端口，不是应用程序服务器端口。</span><span class="sxs-lookup"><span data-stu-id="494c7-136">The \<port\> value is the JOLT protocol listener port, not the App Server port.</span></span> <span data-ttu-id="494c7-137">默认 JOLT 端口为 9000。</span><span class="sxs-lookup"><span data-stu-id="494c7-137">The default JOLT port is 9000.</span></span>|  
    |`JAVA_HOME`|<span data-ttu-id="494c7-138">设置 JAVA_HOME 变量以指向您的 JDK 安装，例如：**C:\j2sdk1.4.2_08**.</span><span class="sxs-lookup"><span data-stu-id="494c7-138">Set the JAVA_HOME variable to point to your JDK installation, for example: **C:\j2sdk1.4.2_08**.</span></span>|  
    |`Password`|<span data-ttu-id="494c7-139">如果未选中**使用 SSO**，必须设置凭据参数以便用于访问服务器系统的 PeopleSoft Enterprise 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="494c7-139">If you did not select **Use SSO**, you must set credential parameters for the BizTalk Adapter for PeopleSoft Enterprise to access the server system.</span></span><br /><br /> <span data-ttu-id="494c7-140">表示用户的密码登录到 PeopleSoft 系统的字符串。</span><span class="sxs-lookup"><span data-stu-id="494c7-140">A string representing the user's password for logon to a PeopleSoft system.</span></span> <span data-ttu-id="494c7-141">字符不会出现，但由星号 （\*） 表示。</span><span class="sxs-lookup"><span data-stu-id="494c7-141">The characters do not appear but are represented by asterisks (\*).</span></span>|  
    |`PeopleSoft 8.x Jar Files`|<span data-ttu-id="494c7-142">若要使用组件接口 (仅适用于 PeopleSoft 8)，则必须更新 CLASSPATH 以包含 PeopleSoft 组件接口 jar 文件。</span><span class="sxs-lookup"><span data-stu-id="494c7-142">To use Ccmponent interfaces (PeopleSoft 8 only) you must update your CLASSPATH to include the PeopleSoft Component Interface jar file.</span></span> <span data-ttu-id="494c7-143">例如： **< PeopleSoft_Home > \web\PSJOA\psjoa.jar**。</span><span class="sxs-lookup"><span data-stu-id="494c7-143">For example: **<PeopleSoft_Home>\web\PSJOA\psjoa.jar**.</span></span>|  
    |`User Name`|<span data-ttu-id="494c7-144">如果未选中**使用 SSO**，必须设置凭据参数以便用于访问服务器系统的 PeopleSoft Enterprise 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="494c7-144">If you did not select **Use SSO**, you must set credential parameters for the BizTalk Adapter for PeopleSoft Enterprise to access the server system.</span></span><br /><br /> <span data-ttu-id="494c7-145">表示用于登录到 PeopleSoft 系统的用户名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="494c7-145">A string representing a user name required for logon to a PeopleSoft system.</span></span>|  
  
2.  <span data-ttu-id="494c7-146">输入**其他参数**时日期用作键的值; 它具有不同的格式。</span><span class="sxs-lookup"><span data-stu-id="494c7-146">Enter an **Additional parameters** value when a date is used as a key; it has a different format.</span></span> <span data-ttu-id="494c7-147">年-月-日是默认格式。</span><span class="sxs-lookup"><span data-stu-id="494c7-147">YYYY-MM-DD is the default format.</span></span>  
  
3.  <span data-ttu-id="494c7-148">输入**并发控制**值，该值表示在调用，例如 200 数**最大并发调用**如有必要。</span><span class="sxs-lookup"><span data-stu-id="494c7-148">Enter a **Concurrency control** value representing the number of calls, for example 200, in **Max Concurrent Calls** if it is required.</span></span>  
  
     <span data-ttu-id="494c7-149">**最大并发调用**参数激活过载保护，如果后端服务器无法处理的数据量。</span><span class="sxs-lookup"><span data-stu-id="494c7-149">The **Max Concurrent Calls** parameter activates an overload protection if the back-end server cannot process the amount of data.</span></span> <span data-ttu-id="494c7-150">并行调用是为其适配器还没有回复的请求。</span><span class="sxs-lookup"><span data-stu-id="494c7-150">A concurrent call is a request for which the adapter does not yet have a reply.</span></span> <span data-ttu-id="494c7-151">设置**最大并发调用**中在吞吐量超过了后端处理能力。</span><span class="sxs-lookup"><span data-stu-id="494c7-151">Set **Max Concurrent Calls** in instances where the throughput exceeds back-end processing capabilities.</span></span>  
  
     <span data-ttu-id="494c7-152">默认值为此字段为-1，这意味着无保护时发生。</span><span class="sxs-lookup"><span data-stu-id="494c7-152">The default value for this field is -1, meaning no protection occurs.</span></span>  
  
     <span data-ttu-id="494c7-153">如果 BizTalk Server 将提交到传输适配器的请求和调用等于或超过设置的值的并发数**最大并发调用**、 提交直到并发调用数，已保存请求的线程为降低到低于设置的值。</span><span class="sxs-lookup"><span data-stu-id="494c7-153">If BizTalk Server submits a request to the Transmit adapter, and the number of concurrent calls equals or exceeds the value set for **Max Concurrent Calls**, the thread submitting the request is saved until the concurrent calls number decreases to below the set value.</span></span>  

## <a name="update-max-concurrent-calls"></a><span data-ttu-id="494c7-154">更新最大并发调用数</span><span class="sxs-lookup"><span data-stu-id="494c7-154">Update Max Concurrent Calls</span></span>

<span data-ttu-id="494c7-155">`Max Concurrent Calls`参数是一项功能，可用于优化您的配置。</span><span class="sxs-lookup"><span data-stu-id="494c7-155">The `Max Concurrent Calls` parameter is a feature that enables you to optimize your configuration.</span></span> <span data-ttu-id="494c7-156">在吞吐量超过了后端处理能力的实例中使用此参数。</span><span class="sxs-lookup"><span data-stu-id="494c7-156">You use this parameter in instances where the throughput exceeds back-end processing capabilities.</span></span> <span data-ttu-id="494c7-157">可以将参数添加到中的适配器**发送端口传输属性**对话框以激活消息重载保护。</span><span class="sxs-lookup"><span data-stu-id="494c7-157">You can add the parameter to the adapters in the **Send Port Transport Properties** dialog box to activate message overload protection.</span></span> <span data-ttu-id="494c7-158">默认值为-1，这意味着不限制调用数量。</span><span class="sxs-lookup"><span data-stu-id="494c7-158">The default is -1, meaning the calls are unlimited.</span></span>  
  
<span data-ttu-id="494c7-159">当 BizTalk Server 将消息提交到传输适配器时，它首先接收来自适配器的批处理并调用`TransmitMessage()`对批，将每个消息传送。</span><span class="sxs-lookup"><span data-stu-id="494c7-159">When BizTalk Server submits messages to the transmit adapter, it first receives a batch from the adapter and invokes `TransmitMessage()` on the batch to transmit each message.</span></span> <span data-ttu-id="494c7-160">完成后，BizTalk Server 调用`Done()`批处理，然后适配器开始将消息传输到后端上。</span><span class="sxs-lookup"><span data-stu-id="494c7-160">When done, BizTalk Server invokes `Done()` on the batch, and the adapter starts transmitting the messages to the back-end.</span></span> <span data-ttu-id="494c7-161">如果 BizTalk Server 之前获得了多个批`Done`调用时，`Done`命令可能永远不会发生。</span><span class="sxs-lookup"><span data-stu-id="494c7-161">If BizTalk Server obtains multiple batches before `Done` is invoked, the `Done` command might never occur.</span></span> <span data-ttu-id="494c7-162">通过在批处理中设置的最大消息数，可以控制到后端的消息。</span><span class="sxs-lookup"><span data-stu-id="494c7-162">By setting the maximum number of messages in a batch, you can control messages to the back-end.</span></span> <span data-ttu-id="494c7-163">更改此参数在一分钟内将生效。</span><span class="sxs-lookup"><span data-stu-id="494c7-163">Changing this parameter takes effect in a minute.</span></span> <span data-ttu-id="494c7-164">BizTalk Server 必须检索保存在 SQL 数据库中的适配器配置的更改。</span><span class="sxs-lookup"><span data-stu-id="494c7-164">BizTalk Server must retrieve the changes to the adapter configuration that is saved in the SQL database.</span></span>  
  
### <a name="change-the-max-concurrent-calls-parameter"></a><span data-ttu-id="494c7-165">更改最大并发调用参数</span><span class="sxs-lookup"><span data-stu-id="494c7-165">Change the Max Concurrent Calls parameter</span></span>  
  
1.  <span data-ttu-id="494c7-166">在中**发送端口传输属性**对话框框中，输入**连接**值。</span><span class="sxs-lookup"><span data-stu-id="494c7-166">In the **Send Port Transport Properties** dialog box, enter a **Connection** value.</span></span>  
  
     <span data-ttu-id="494c7-167">默认值为 40 个会话。</span><span class="sxs-lookup"><span data-stu-id="494c7-167">The default value is 40 sessions.</span></span> <span data-ttu-id="494c7-168">如果使用较小的值，可能会遇到运行时性能下降。</span><span class="sxs-lookup"><span data-stu-id="494c7-168">If you use a smaller value, you might experience degradation in run-time performance.</span></span> <span data-ttu-id="494c7-169">相反也是如此;较大的值可能会超过服务器和在运行时错误的结果的能力。</span><span class="sxs-lookup"><span data-stu-id="494c7-169">The opposite is also true; a bigger value could exceed the ability of the server and result in run-time errors.</span></span>  
  
2.  <span data-ttu-id="494c7-170">选择**是**有关**刷新代理**以强迫 runtimeagent.exe 和 browsingagent.exe 进程在需要时自动重新启动。</span><span class="sxs-lookup"><span data-stu-id="494c7-170">Select **Yes** for **Refresh Agent** to force the runtimeagent.exe and the browsingagent.exe processes to restart automatically when required.</span></span>  
  
     <span data-ttu-id="494c7-171">例如，您希望自动重新启动它将失去与服务器的连接，或者如果将内容添加到服务器并且不会出现在 Microsoft 适配器向导中选择的过程。</span><span class="sxs-lookup"><span data-stu-id="494c7-171">For example, you want the process to restart automatically if it loses connection with the server, or if you add something to the server and it does not appear in the Microsoft Adapter Wizard for selection.</span></span>  
  
     <span data-ttu-id="494c7-172">**刷新代理**参数刷新浏览和运行时代理。</span><span class="sxs-lookup"><span data-stu-id="494c7-172">The **Refresh Agent** parameter refreshes both the browsing and the run-time agents.</span></span> <span data-ttu-id="494c7-173">Runtimeagent.exe 在延迟一分钟或在下一步后的更新发送调用。</span><span class="sxs-lookup"><span data-stu-id="494c7-173">The runtimeagent.exe updates after a delay of one minute or at the next send call.</span></span>  
  
3.  <span data-ttu-id="494c7-174">提供凭据以访问 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="494c7-174">Provide credentials to access the PeopleSoft system.</span></span>  
  
     <span data-ttu-id="494c7-175">可以使用两种方法来访问系统：</span><span class="sxs-lookup"><span data-stu-id="494c7-175">You can use two methods to access the system:</span></span>  
  
    -   <span data-ttu-id="494c7-176">登录凭据 （传输属性登录参数）</span><span class="sxs-lookup"><span data-stu-id="494c7-176">Login Credentials (Transport Properties Login parameters)</span></span>  
  
    -   <span data-ttu-id="494c7-177">单一登录</span><span class="sxs-lookup"><span data-stu-id="494c7-177">Single Sign-On</span></span>  
  
4.  <span data-ttu-id="494c7-178">选择**是**有关**使用 SSO**若要使用单一登录。</span><span class="sxs-lookup"><span data-stu-id="494c7-178">Select **Yes** for **Use SSO** to use Single Sign-On.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="494c7-179">有关详细信息，请参阅[保护适配器](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="494c7-179">For more information, see [Secure the adapter](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md).</span></span> 
  
5.  <span data-ttu-id="494c7-180">在列表中选择关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="494c7-180">Select an affiliate application in the list.</span></span>  
  
     <span data-ttu-id="494c7-181">企业单一登录工具创建的关联应用程序代表诸如 PeopleSoft 之类的应用程序。</span><span class="sxs-lookup"><span data-stu-id="494c7-181">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as PeopleSoft.</span></span> <span data-ttu-id="494c7-182">用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="494c7-182">Microsoft BizTalk Adapter for PeopleSoft Enterprise uses the credentials of an application user.</span></span> <span data-ttu-id="494c7-183">从指定的关联应用程序的服务器系统的 SSO 数据库检索这些凭据。</span><span class="sxs-lookup"><span data-stu-id="494c7-183">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span> <span data-ttu-id="494c7-184">凭据是启动 BizTalk 项目的用户 （应用程序用户）。</span><span class="sxs-lookup"><span data-stu-id="494c7-184">The credentials are those of the user (the application user) who launched the BizTalk project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="494c7-185">有关如何创建关联应用程序的详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications2.md)，或 Microsoft BizTalk Server 联机帮助。</span><span class="sxs-lookup"><span data-stu-id="494c7-185">For more information about how to create affiliate applications, see [Creating Affiliate Applications](../core/creating-affiliate-applications2.md), or the Microsoft BizTalk Server online Help.</span></span>  
  
6.  <span data-ttu-id="494c7-186">提供所需的所有信息，以接受连接信息后，单击**Apply**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="494c7-186">After providing all required information to accept the connection information, click **Apply**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="494c7-187">必须设置用于访问 PeopleSoft 的 PeopleSoft Enterprise 的 BizTalk 适配器的连接参数。</span><span class="sxs-lookup"><span data-stu-id="494c7-187">You must set connection parameters for the BizTalk Adapter for PeopleSoft Enterprise to access PeopleSoft.</span></span>  
  

## <a name="next"></a><span data-ttu-id="494c7-188">Next</span><span class="sxs-lookup"><span data-stu-id="494c7-188">Next</span></span>
  
[<span data-ttu-id="494c7-189">PeopleSoft 架构导入到 BizTalk Server 项目</span><span class="sxs-lookup"><span data-stu-id="494c7-189">Import PeopleSoft Schemas into BizTalk Server Projects</span></span>](../core/importing-peoplesoft-schemas-into-biztalk-server-projects.md)  
[<span data-ttu-id="494c7-190">从 PeopleSoft 接收</span><span class="sxs-lookup"><span data-stu-id="494c7-190">Receive from PeopleSoft</span></span>](../core/receiving-from-peoplesoft.md)