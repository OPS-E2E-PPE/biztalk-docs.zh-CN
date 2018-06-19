---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 2b0a1aa81971e3e086881e23bcfd6d7ba5d5799d
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24012876"
---
# <a name="optimize-configuration"></a><span data-ttu-id="74734-101">优化配置</span><span class="sxs-lookup"><span data-stu-id="74734-101">Optimize configuration</span></span>
<span data-ttu-id="74734-102">本部分介绍如何优化适用于 PeopleSoft Enterprise 的 BizTalk 适配器的配置，并且包括了用于设置适配器的参数说明。</span><span class="sxs-lookup"><span data-stu-id="74734-102">This section contains information about how to optimize your configuration of BizTalk Adapter for PeopleSoft Enterprise and includes parameter descriptions for setting up the adapter.</span></span>  
  
## <a name="message-overload-protection"></a><span data-ttu-id="74734-103">消息重载保护</span><span class="sxs-lookup"><span data-stu-id="74734-103">Message Overload Protection</span></span>  
 <span data-ttu-id="74734-104">`Max Concurrent Calls` 参数是一种用来优化配置的功能。</span><span class="sxs-lookup"><span data-stu-id="74734-104">The `Max Concurrent Calls` parameter is a feature that enables you to optimize your configuration.</span></span> <span data-ttu-id="74734-105">在吞吐量超过了后端处理能力的情况下，可以使用此参数。</span><span class="sxs-lookup"><span data-stu-id="74734-105">You use this parameter in instances where the throughput exceeds back-end processing capabilities.</span></span> <span data-ttu-id="74734-106">你可以将参数添加到中的适配器**发送端口传输属性**对话框中，若要激活消息重载保护。</span><span class="sxs-lookup"><span data-stu-id="74734-106">You can add the parameter to the adapters in the **Send Port Transport Properties** dialog box to activate message overload protection.</span></span> <span data-ttu-id="74734-107">默认值为 -1，表示不限制调用数量。</span><span class="sxs-lookup"><span data-stu-id="74734-107">The default is -1, meaning the calls are unlimited.</span></span>  
  
 <span data-ttu-id="74734-108">当 BizTalk Server 将消息提交到传输适配器时，它首先接收来自适配器的一个批并对批调用 `TransmitMessage()` 以传输每个消息。</span><span class="sxs-lookup"><span data-stu-id="74734-108">When BizTalk Server submits messages to the transmit adapter, it first receives a batch from the adapter and invokes `TransmitMessage()` on the batch to transmit each message.</span></span> <span data-ttu-id="74734-109">完成上述操作后，BizTalk Server 对批调用 `Done()`，然后适配器开始将消息传输到后端。</span><span class="sxs-lookup"><span data-stu-id="74734-109">When done, BizTalk Server invokes `Done()` on the batch, and the adapter starts transmitting the messages to the back-end.</span></span> <span data-ttu-id="74734-110">如果 BizTalk Server 在调用 `Done` 之前获得了多个批，`Done` 命令可能永远不会发生。</span><span class="sxs-lookup"><span data-stu-id="74734-110">If BizTalk Server obtains multiple batches before `Done` is invoked, the `Done` command might never occur.</span></span> <span data-ttu-id="74734-111">通过设置批中的最大消息数量，可以控制传输到后端的消息。</span><span class="sxs-lookup"><span data-stu-id="74734-111">By setting the maximum number of messages in a batch, you can control messages to the back-end.</span></span> <span data-ttu-id="74734-112">对此参数的更改会在一分钟后生效。</span><span class="sxs-lookup"><span data-stu-id="74734-112">Changing this parameter takes effect in a minute.</span></span> <span data-ttu-id="74734-113">BizTalk Server 必须检索保存在 SQL 数据库中的适配器配置的更改。</span><span class="sxs-lookup"><span data-stu-id="74734-113">BizTalk Server must retrieve the changes to the adapter configuration that is saved in the SQL database.</span></span>  
  
## <a name="change-the-max-concurrent-calls-parameter"></a><span data-ttu-id="74734-114">更改最大并发调用参数</span><span class="sxs-lookup"><span data-stu-id="74734-114">Change the Max Concurrent Calls parameter</span></span>  
  
1.  <span data-ttu-id="74734-115">在**发送端口传输属性**对话框框中，输入**连接**值。</span><span class="sxs-lookup"><span data-stu-id="74734-115">In the **Send Port Transport Properties** dialog box, enter a **Connection** value.</span></span>  
  
     <span data-ttu-id="74734-116">默认值为 40 个会话。</span><span class="sxs-lookup"><span data-stu-id="74734-116">The default value is 40 sessions.</span></span> <span data-ttu-id="74734-117">如果您使用一个较小的值，可能会出现运行时性能下降。</span><span class="sxs-lookup"><span data-stu-id="74734-117">If you use a smaller value, you might experience degradation in run-time performance.</span></span> <span data-ttu-id="74734-118">反之亦然，使用较大的值，则会超出服务器的能力并导致运行时错误。</span><span class="sxs-lookup"><span data-stu-id="74734-118">The opposite is also true; a bigger value could exceed the ability of the server and result in run-time errors.</span></span>  
  
2.  <span data-ttu-id="74734-119">选择**是**为**刷新代理**强制 runtimeagent.exe 以及要在需要时自动重新启动 browsingagent.exe 过程。</span><span class="sxs-lookup"><span data-stu-id="74734-119">Select **Yes** for **Refresh Agent** to force the runtimeagent.exe and the browsingagent.exe processes to restart automatically when required.</span></span>  
  
     <span data-ttu-id="74734-120">例如，您希望进程在出现以下情况时自动重新启动：丢失了与服务器的连接；或者向服务器中添加了内容，但是由于它没有显示在 Microsoft 适配器向导中而无法选择它。</span><span class="sxs-lookup"><span data-stu-id="74734-120">For example, you want the process to restart automatically if it loses connection with the server, or if you add something to the server and it does not appear in the Microsoft Adapter Wizard for selection.</span></span>  
  
     <span data-ttu-id="74734-121">**刷新代理**参数刷新浏览和运行时代理。</span><span class="sxs-lookup"><span data-stu-id="74734-121">The **Refresh Agent** parameter refreshes both the browsing and the run-time agents.</span></span> <span data-ttu-id="74734-122">runtimeagent.exe 在一分钟延迟后或在下一次发送呼叫时更新。</span><span class="sxs-lookup"><span data-stu-id="74734-122">The runtimeagent.exe updates after a delay of one minute or at the next send call.</span></span>  
  
3.  <span data-ttu-id="74734-123">提供凭据以访问 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="74734-123">Provide credentials to access the PeopleSoft system.</span></span>  
  
     <span data-ttu-id="74734-124">您可以使用两种方法来访问系统：</span><span class="sxs-lookup"><span data-stu-id="74734-124">You can use two methods to access the system:</span></span>  
  
    -   <span data-ttu-id="74734-125">登录凭据（传输属性登录参数）</span><span class="sxs-lookup"><span data-stu-id="74734-125">Login Credentials (Transport Properties Login parameters)</span></span>  
  
    -   <span data-ttu-id="74734-126">单一登录</span><span class="sxs-lookup"><span data-stu-id="74734-126">Single Sign-On</span></span>  
  
4.  <span data-ttu-id="74734-127">选择**是**为**使用 SSO**用于单一登录。</span><span class="sxs-lookup"><span data-stu-id="74734-127">Select **Yes** for **Use SSO** to use Single Sign-On.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="74734-128">有关详细信息，请参阅[安全适配器](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="74734-128">For more information, see [Secure the adapter](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md).</span></span> 
  
5.  <span data-ttu-id="74734-129">在列表中选择一个关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="74734-129">Select an affiliate application in the list.</span></span>  
  
     <span data-ttu-id="74734-130">由企业单一登录工具创建的关联应用程序，表示一个应用程序，如 PeopleSoft。</span><span class="sxs-lookup"><span data-stu-id="74734-130">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as PeopleSoft.</span></span> <span data-ttu-id="74734-131">适用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="74734-131">Microsoft BizTalk Adapter for PeopleSoft Enterprise uses the credentials of an application user.</span></span> <span data-ttu-id="74734-132">这些凭据是从服务器系统的 SSO 数据库中为指定关联应用程序检索的。</span><span class="sxs-lookup"><span data-stu-id="74734-132">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span> <span data-ttu-id="74734-133">凭据是启动 BizTalk 项目的用户（应用程序用户）的凭据。</span><span class="sxs-lookup"><span data-stu-id="74734-133">The credentials are those of the user (the application user) who launched the BizTalk project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="74734-134">有关如何创建关联应用程序的详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications2.md)，或 Microsoft BizTalk Server 联机帮助。</span><span class="sxs-lookup"><span data-stu-id="74734-134">For more information about how to create affiliate applications, see [Creating Affiliate Applications](../core/creating-affiliate-applications2.md), or the Microsoft BizTalk Server online Help.</span></span>  
  
6.  <span data-ttu-id="74734-135">提供所有所需的信息，以接受连接信息后，单击**应用**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="74734-135">After providing all required information to accept the connection information, click **Apply**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="74734-136">您必须为适用于 PeopleSoft Enterprise 的 BizTalk 适配器设置连接参数，以访问 PeopleSoft。</span><span class="sxs-lookup"><span data-stu-id="74734-136">You must set connection parameters for the BizTalk Adapter for PeopleSoft Enterprise to access PeopleSoft.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74734-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74734-137">See Also</span></span>  
 [<span data-ttu-id="74734-138">创建 PeopleSoft 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="74734-138">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)