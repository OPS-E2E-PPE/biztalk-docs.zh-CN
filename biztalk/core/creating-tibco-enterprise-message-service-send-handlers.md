---
title: "创建 TIBCO EMS 发送项目 |Microsoft 文档"
description: "创建发送端口，并配置要在 BizTalk Server 中使用 TIBCO 企业消息服务适配器传输属性"
ms.custom: 
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f82609c-1847-4796-a24c-28cb350ec739
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 570693f4d5644f0ea850a53ec537ce30db5ca568
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="creating--tibco-enterprise-message-service-send-handlers"></a><span data-ttu-id="e17e4-103">创建 TIBCO Enterprise Message Service 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="e17e4-103">Creating  TIBCO Enterprise Message Service Send Handlers</span></span>
<span data-ttu-id="e17e4-104">本部分解释如何设置发送端口以连接到 TIBCO Enterprise Message Service (EMS) 以及如何将 XML 包括到业务流程中以在运行时与 TIBCO EMS 交互。</span><span class="sxs-lookup"><span data-stu-id="e17e4-104">This section explains how to set the send port to connect to TIBCO Enterprise Message Service (EMS) and how to include XML in your orchestration to interact with TIBCO EMS at run time.</span></span>  


## <a name="create-a-send-port"></a><span data-ttu-id="e17e4-105">创建发送端口</span><span class="sxs-lookup"><span data-stu-id="e17e4-105">Create a send port</span></span>  
  
1.  <span data-ttu-id="e17e4-106">在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e17e4-106">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then expand your application.</span></span>  
  
2.  <span data-ttu-id="e17e4-107">右键单击**发送端口**，选择**新建**，然后选择**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="e17e4-107">Right-click **Send Ports**, select **New**, and then select **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="e17e4-108">在**发送端口属性**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e17e4-108">In the **Send Port Properties**, do the following:</span></span>  
  
    1.  <span data-ttu-id="e17e4-109">例如，键入发送端口的名称`SendToTIBCOEMS`。</span><span class="sxs-lookup"><span data-stu-id="e17e4-109">Type a name for the send port, for example, `SendToTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="e17e4-110">从**类型**下拉列表中，选择**TIBCO EMS**。</span><span class="sxs-lookup"><span data-stu-id="e17e4-110">From the **Type** drop-down list, select **TIBCO EMS**.</span></span>  
  
    3.  <span data-ttu-id="e17e4-111">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="e17e4-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="e17e4-112">从**发送管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="e17e4-112">From the **Send Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span> <span data-ttu-id="e17e4-113">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="e17e4-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  

        > [!NOTE]
        > <span data-ttu-id="e17e4-114">TIBCO 企业消息服务 BizTalk 适配器需要用于接收 XMLTransmit 为发送和 XMLReceive 选择。</span><span class="sxs-lookup"><span data-stu-id="e17e4-114">The BizTalk Adapter for TIBCO Enterprise Message Service requires that you select XMLTransmit for send, and XMLReceive for receive.</span></span>  
  
    6.  <span data-ttu-id="e17e4-115">选择**配置**配置发送端口。</span><span class="sxs-lookup"><span data-stu-id="e17e4-115">Select **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="e17e4-116">在**TIBCO EMS 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e17e4-116">In the **TIBCO EMS Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="e17e4-117">输入**消息处理**，**服务器连接定义**，**事务支持**，**用户名**，和**密码**。</span><span class="sxs-lookup"><span data-stu-id="e17e4-117">Enter **Message Handling**, **Server Connection Definition**, **Transaction Support**, **Username**, and the **password**.</span></span>  
  
         <span data-ttu-id="e17e4-118">您不必设置登录信息。</span><span class="sxs-lookup"><span data-stu-id="e17e4-118">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="e17e4-119">在列表中选择为表示 TIBCO EMS 系统所创建的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="e17e4-119">In the list, select the affiliate application you created to represent the TIBCO EMS system.</span></span>  
  
    3.  <span data-ttu-id="e17e4-120">有关**使用 SSO**，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="e17e4-120">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="e17e4-121">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="e17e4-121">Select **OK**.</span></span>  
  
5.  <span data-ttu-id="e17e4-122">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="e17e4-122">Select **OK**.</span></span> 

## <a name="set-send-port-transport-properties"></a><span data-ttu-id="e17e4-123">设置发送端口传输属性</span><span class="sxs-lookup"><span data-stu-id="e17e4-123">Set send port transport properties</span></span>
<span data-ttu-id="e17e4-124">TIBCO Enterprise Message Service 传输属性在设计时配置，在运行时使用。</span><span class="sxs-lookup"><span data-stu-id="e17e4-124">The TIBCO Enterprise Message Service transport properties are configured in design time and used in run time.</span></span> <span data-ttu-id="e17e4-125">在**传输属性**，设置的连接和凭据参数特定于服务器系统和你尝试访问的对象。</span><span class="sxs-lookup"><span data-stu-id="e17e4-125">In the **Transport Properties**, you set the connection and credential parameters specific to the server system and the objects you are trying to access.</span></span>  
  
 ![](../core/media/tib-tibcoemssendtransportpropertiess.gif "TIB_TIBCOEMSSendTransportPropertiess")  
  
  
1.  <span data-ttu-id="e17e4-126">在**传输属性**，展开**系统定义**，然后输入 TIBCO EMS 服务器连接的所有必要的信息。</span><span class="sxs-lookup"><span data-stu-id="e17e4-126">In the **Transport Properties**, expand **System Definition**, and enter all required information for connection to the TIBCO EMS server.</span></span>  
  
     <span data-ttu-id="e17e4-127">您必须设置配置参数才能将用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器连接到 TIBCO EMS。</span><span class="sxs-lookup"><span data-stu-id="e17e4-127">You must set configuration parameters to connect Microsoft BizTalk Adapter for TIBCO Enterprise Message Service to TIBCO EMS.</span></span> <span data-ttu-id="e17e4-128">**此数据是区分大小写。**</span><span class="sxs-lookup"><span data-stu-id="e17e4-128">**This data is case sensitive.**</span></span>  
  
2.  <span data-ttu-id="e17e4-129">展开**消息处理**，并输入所有所需的信息。</span><span class="sxs-lookup"><span data-stu-id="e17e4-129">Expand **Message Handling**, and enter all required information.</span></span>  
  
    |<span data-ttu-id="e17e4-130">参数</span><span class="sxs-lookup"><span data-stu-id="e17e4-130">Parameter</span></span>|<span data-ttu-id="e17e4-131">Description</span><span class="sxs-lookup"><span data-stu-id="e17e4-131">Description</span></span>|  
    |---------------|-----------------|  
    |`Message Expiration Time`|<span data-ttu-id="e17e4-132">描述消息保留在队列或主题中的时间长度的整数；该时间到期后，消息将被 TIBCO EMS 服务器删除。</span><span class="sxs-lookup"><span data-stu-id="e17e4-132">An integer that describes the length of time the message stays on the queue or topic; after the time expires, the message is deleted by the TIBCO EMS server.</span></span><br /><br /> <span data-ttu-id="e17e4-133">它与 EMS.Expiration 消息属性标头同义。</span><span class="sxs-lookup"><span data-stu-id="e17e4-133">It is synonymous to the EMS.Expiration message property header.</span></span> <span data-ttu-id="e17e4-134">业务流程可以将其覆盖。</span><span class="sxs-lookup"><span data-stu-id="e17e4-134">It can be overridden with the orchestration.</span></span><br /><br /> <span data-ttu-id="e17e4-135">默认值为 0 毫秒，这意味着消息在目标中将不会过期。</span><span class="sxs-lookup"><span data-stu-id="e17e4-135">Default value is 0 milliseconds, which means that the message will not expire from the destination.</span></span>|  
    |`Message is Persistent`|<span data-ttu-id="e17e4-136">在确认消息之前，TIBCO EMS 服务器已将其写入磁盘。</span><span class="sxs-lookup"><span data-stu-id="e17e4-136">Messages are written to disk by the TIBCO EMS server before they are acknowledged.</span></span><br /><br /> <span data-ttu-id="e17e4-137">这是 TibcoEMS.DeliveryMode 标头属性。</span><span class="sxs-lookup"><span data-stu-id="e17e4-137">This is the TibcoEMS.DeliveryMode header property.</span></span> <span data-ttu-id="e17e4-138">它指示在向适配器确认接收消息之前，服务器已将发送的消息保留在队列中。</span><span class="sxs-lookup"><span data-stu-id="e17e4-138">It instructs sent messages to be persisted in the queue by the server before acknowledging reception of the message to the adapter.</span></span><br /><br /> <span data-ttu-id="e17e4-139">默认值为 **True**。</span><span class="sxs-lookup"><span data-stu-id="e17e4-139">Default value is **True**.</span></span>|  
    |`Message Priority`|<span data-ttu-id="e17e4-140">0 到 9 之间的数字，用于定义消息的优先级；该值越大，优先级就越高。</span><span class="sxs-lookup"><span data-stu-id="e17e4-140">Numeric ranking from 0 to 9, which defines the priority of the message; the larger the value, the higher the priority.</span></span><br /><br /> <span data-ttu-id="e17e4-141">优先级影响服务器向使用者传递消息的顺序（较大的值优先）。</span><span class="sxs-lookup"><span data-stu-id="e17e4-141">Priority affects the order in which the server delivers messages to consumers (higher values first).</span></span><br /><br /> <span data-ttu-id="e17e4-142">JMS 规范定义了十个级别的优先级值，从 0（最低优先级）到 9（最高优先级）。</span><span class="sxs-lookup"><span data-stu-id="e17e4-142">The JMS specification defines ten levels of priority value, from zero (lowest priority) to 9 (highest priority).</span></span> <span data-ttu-id="e17e4-143">该规范建议客户端将 0–4 视为正常优先级层次，将优先级 5–9 视为加急优先级层次。</span><span class="sxs-lookup"><span data-stu-id="e17e4-143">The specification suggests that clients consider 0–4 as gradations of normal priority, and priorities 5–9 as gradations of expedited priority.</span></span><br /><br /> <span data-ttu-id="e17e4-144">默认值是**4**。</span><span class="sxs-lookup"><span data-stu-id="e17e4-144">Default value is **4**.</span></span>|  
  
3.  <span data-ttu-id="e17e4-145">展开**服务器连接定义**并输入所有所需的信息。</span><span class="sxs-lookup"><span data-stu-id="e17e4-145">Expand **Server Connection Definition** and enter all required information.</span></span>  
  
    |<span data-ttu-id="e17e4-146">参数</span><span class="sxs-lookup"><span data-stu-id="e17e4-146">Parameter</span></span>|<span data-ttu-id="e17e4-147">Description</span><span class="sxs-lookup"><span data-stu-id="e17e4-147">Description</span></span>|  
    |---------------|-----------------|  
    |`Destination`|<span data-ttu-id="e17e4-148">强制设置。</span><span class="sxs-lookup"><span data-stu-id="e17e4-148">Mandatory setting.</span></span> <span data-ttu-id="e17e4-149">定义目标名称和类型。</span><span class="sxs-lookup"><span data-stu-id="e17e4-149">Defines the name and type of the destination.</span></span> <span data-ttu-id="e17e4-150">例如： staticqueue [Q1]。</span><span class="sxs-lookup"><span data-stu-id="e17e4-150">For example: staticqueue[Q1].</span></span><br /><br /> <span data-ttu-id="e17e4-151">定义的队列或主题具有以下格式: {静态} {动态] 队列 [queuename] 或 {静态} {动态] 主题 [topicname]。</span><span class="sxs-lookup"><span data-stu-id="e17e4-151">Defines the queue or topic with the following format: {static}{dynamic]Queue[queuename] or {static}{dynamic]Topic[topicname].</span></span> <span data-ttu-id="e17e4-152">**注意：**可以将消息发送到的目标，不存在。</span><span class="sxs-lookup"><span data-stu-id="e17e4-152">**Note:**  You can send a message to a destination that does not exist.</span></span> <span data-ttu-id="e17e4-153">在这种情况下，TIBCO 企业消息服务创建目标;这称为*动态目标*。</span><span class="sxs-lookup"><span data-stu-id="e17e4-153">In such a case, TIBCO Enterprise Message Service creates the destination; this is referred to as a *Dynamic Destination*.</span></span> <span data-ttu-id="e17e4-154">这是在使用消息时由生成者创建的目标，当生成者断开连接时，此目标会被删除。</span><span class="sxs-lookup"><span data-stu-id="e17e4-154">This is a destination created by a producer and deleted when the message is consumed and the producer disconnects.</span></span> <span data-ttu-id="e17e4-155">A*静态目标*是目标仅可以创建由 TIBCO 企业消息服务管理员。</span><span class="sxs-lookup"><span data-stu-id="e17e4-155">A *static destination* is a destination which can only created by a TIBCO Enterprise Message Service Administrator.</span></span> <span data-ttu-id="e17e4-156">在您打开与目标的连接时无法连接到动态端口，因为用于 TIBCO Enterprise Message Service 的 BizTalk 适配器在服务器上使用名称查找机制。</span><span class="sxs-lookup"><span data-stu-id="e17e4-156">You cannot connect to a dynamic port when you open a connection to a destination because BizTalk Adapter for TIBCO Enterprise Message Service uses a name lookup mechanism on the server.</span></span> <span data-ttu-id="e17e4-157">当您使用名称查找时，只有静态端口是可见的。</span><span class="sxs-lookup"><span data-stu-id="e17e4-157">Only static ports are visible when you are using the name lookup.</span></span> <span data-ttu-id="e17e4-158">在连接到动态端口时，可以使用静态目标；但是，如果不存在具有该名称的目标，则会创建一个目标。</span><span class="sxs-lookup"><span data-stu-id="e17e4-158">When connecting to a dynamic port, you can use static destinations; however, if no destination by that name exists, a destination is created.</span></span> <span data-ttu-id="e17e4-159">目标可让您在定义端口时显式指定要使用的目标类型。</span><span class="sxs-lookup"><span data-stu-id="e17e4-159">Destination lets you explicitly specify the type of destination to use when defining the port.</span></span> <span data-ttu-id="e17e4-160">目标的语法不区分大小写： staticqueue [queue_name]、 statictopic [topic_name]、 dynamicqueue [queue_name];dynamictopic [topic_name]。</span><span class="sxs-lookup"><span data-stu-id="e17e4-160">The syntax for the Destination is not case sensitive: staticqueue[queue_name], statictopic[topic_name], dynamicqueue[queue_name]; dynamictopic[topic_name].</span></span>|  
    |`Port Number`|<span data-ttu-id="e17e4-161">TIBCO EMS 服务器侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="e17e4-161">Port on which the TIBCO EMS server listens.</span></span>|  
    |`Server Name`|<span data-ttu-id="e17e4-162">强制设置。</span><span class="sxs-lookup"><span data-stu-id="e17e4-162">Mandatory setting.</span></span> <span data-ttu-id="e17e4-163">托管 TIBCO EMS 服务器的系统的名称。</span><span class="sxs-lookup"><span data-stu-id="e17e4-163">Name of the system hosting the TIBCO EMS server.</span></span>|  
  
4.  <span data-ttu-id="e17e4-164">使用单一登录 (SSO) 提供凭据。</span><span class="sxs-lookup"><span data-stu-id="e17e4-164">Provide credentials using Single Sign-On (SSO).</span></span>  
  
     <span data-ttu-id="e17e4-165">可以使用两种方法来访问 TIBCO EMS 系统。</span><span class="sxs-lookup"><span data-stu-id="e17e4-165">You can use two methods to access the TIBCO EMS system.</span></span> <span data-ttu-id="e17e4-166">您可以使用凭据（用户名和密码参数）或单一登录。</span><span class="sxs-lookup"><span data-stu-id="e17e4-166">You can use Credentials (User Name and Password parameters) or Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="e17e4-167">选择**是**中**使用 SSO**用于单一登录。</span><span class="sxs-lookup"><span data-stu-id="e17e4-167">Select **Yes** in the **Use SSO** to use Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="e17e4-168">从列表中选择一个关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="e17e4-168">Select an affiliate application from the list.</span></span>  
  
         <span data-ttu-id="e17e4-169">企业单一登录工具创建的关联应用程序代表诸如 TIBCO EMS 之类的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e17e4-169">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as TIBCO EMS.</span></span> <span data-ttu-id="e17e4-170">用于 TIBCO EMS 的 BizTalk 适配器使用应用程序用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="e17e4-170">BizTalk Adapter for TIBCO EMS uses the credentials of an application user.</span></span> <span data-ttu-id="e17e4-171">这些凭据是从服务器系统的 SSO 数据库中为指定关联应用程序检索的。</span><span class="sxs-lookup"><span data-stu-id="e17e4-171">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span>  
  
         <span data-ttu-id="e17e4-172">有关如何创建关联应用程序的详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications5.md)。</span><span class="sxs-lookup"><span data-stu-id="e17e4-172">For more information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
5.  <span data-ttu-id="e17e4-173">在**事务支持**，选择**是**如果此发送端口将支持事务。</span><span class="sxs-lookup"><span data-stu-id="e17e4-173">In **Transaction Support**, select **Yes** if this send port will support transactions.</span></span>  
  
     <span data-ttu-id="e17e4-174">如果在端口上启用事务支持，则使用此端口的所有业务流程都必须是事务性的；否则，所有调用都会回滚（例如不提交）。</span><span class="sxs-lookup"><span data-stu-id="e17e4-174">If you enable transaction support on the port, all orchestrations using this port must be transactional; otherwise, all calls are rolled back (for example, are not committed).</span></span> <span data-ttu-id="e17e4-175">添加到业务流程中的作用域对象控制事务的生命周期。</span><span class="sxs-lookup"><span data-stu-id="e17e4-175">The scope object added to the orchestration controls the transaction life-cycle.</span></span>  
  
6.  <span data-ttu-id="e17e4-176">展开**用户凭据**并输入**用户名**和**密码**访问 TIBCO EMS 服务器。</span><span class="sxs-lookup"><span data-stu-id="e17e4-176">Expand **User Credentials** and enter the **User Name** and **Password** to access the TIBCO EMS server.</span></span>  
  
    |<span data-ttu-id="e17e4-177">参数</span><span class="sxs-lookup"><span data-stu-id="e17e4-177">Parameter</span></span>|<span data-ttu-id="e17e4-178">Description</span><span class="sxs-lookup"><span data-stu-id="e17e4-178">Description</span></span>|  
    |---------------|-----------------|  
    |`Password`|<span data-ttu-id="e17e4-179">用于与 TIBCO EMS 守护程序进行通信的用户的密码。</span><span class="sxs-lookup"><span data-stu-id="e17e4-179">The user’s Password used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="e17e4-180">如果你未选择**使用 SSO**，你必须设置为 BizTalk 适配器 TIBCO EMS 与 TIBCO EMS 后台程序进行通信的凭据参数。</span><span class="sxs-lookup"><span data-stu-id="e17e4-180">If you did not select **Use SSO**, you must set credential parameters for the BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
    |`User Name`|<span data-ttu-id="e17e4-181">用来与 TIBCO EMS 守护程序进行通信的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="e17e4-181">Name of a user used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="e17e4-182">如果你未选择**使用 SSO**，你必须设置为 BizTalk 适配器 TIBCO EMS 与 TIBCO EMS 后台程序进行通信的凭据参数。</span><span class="sxs-lookup"><span data-stu-id="e17e4-182">If you did not select **Use SSO**, you must set credential parameters for the BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
  
7.  <span data-ttu-id="e17e4-183">单击**应用**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e17e4-183">Click **Apply**, and then click **OK**.</span></span>  

   
## <a name="next-steps"></a><span data-ttu-id="e17e4-184">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e17e4-184">Next steps</span></span>
[<span data-ttu-id="e17e4-185">创建接收项目</span><span class="sxs-lookup"><span data-stu-id="e17e4-185">Create receive artifacts</span></span>](../core/creating-tibco-enterprise-message-service-receive-handlers.md)  
[<span data-ttu-id="e17e4-186">TIBCO EMS 消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="e17e4-186">TIBCO EMS message context properties</span></span>](../core/message-context-properties-in-biztalk-server.md)