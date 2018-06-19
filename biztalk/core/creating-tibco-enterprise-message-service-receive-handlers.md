---
title: 创建 TIBCO EMS 接收项目 |Microsoft 文档
description: 创建接收端口，并设置要在 BizTalk Server 中使用 TIBCO 企业消息服务适配器传输属性
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1307e3c-0237-4f19-a642-58e694fe95d0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf5810dc012c7aa5dcc2fbdfcecd9d59d066ced7
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015372"
---
# <a name="create-tibco-ems-receive-artifacts"></a><span data-ttu-id="d0376-103">创建 TIBCO EMS 接收项目</span><span class="sxs-lookup"><span data-stu-id="d0376-103">Create TIBCO EMS receive artifacts</span></span>

## <a name="overview"></a><span data-ttu-id="d0376-104">概述</span><span class="sxs-lookup"><span data-stu-id="d0376-104">Overview</span></span>
<span data-ttu-id="d0376-105">TIBCO Enterprise Message Service 接收器是一种侦听服务，可以注册特殊的队列或主题，并接收相关消息。</span><span class="sxs-lookup"><span data-stu-id="d0376-105">TIBCO Enterprise Message Service receiver is a listener service that registers a particular Queue or Topic and receives the relative messages.</span></span> <span data-ttu-id="d0376-106">TIBCO Enterprise Message Service 的 BizTalk 适配器首先通过打开一个新会话向 TIBCO Enterprise Message Service 注册，然后继续轮询以接收消息。</span><span class="sxs-lookup"><span data-stu-id="d0376-106">BizTalk Adapter for TIBCO Enterprise Message Service first registers with TIBCO Enterprise Message Service by opening a new session, and then it continues polling to receive messages..</span></span> <span data-ttu-id="d0376-107">该部分介绍了如何设置接收端口以连接到 TIBCO Enterprise Message Service，如何在您的业务流程中加入 XML 以在运行时与 TIBCO EMS 进行交互。</span><span class="sxs-lookup"><span data-stu-id="d0376-107">This section explains how to set the receive port to connect to TIBCO Enterprise Message Service and how to include XML in your orchestration to interact with TIBCO EMS at run time.</span></span>  

## <a name="create-a-receive-port"></a><span data-ttu-id="d0376-108">创建接收端口</span><span class="sxs-lookup"><span data-stu-id="d0376-108">Create a receive port</span></span>  
  
1.  <span data-ttu-id="d0376-109">在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d0376-109">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then expand your application.</span></span>  
  
2.  <span data-ttu-id="d0376-110">右键单击**接收端口**，选择**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="d0376-110">Right-click **Receive Ports**, select **New**, and then click **One-way Receive Ports**.</span></span>  
  
3.  <span data-ttu-id="d0376-111">在**接收端口属性**窗口，请在**常规**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0376-111">In the **Receive Port Properties** window, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="d0376-112">在**名称**字段中，键入`ReceiveFromTIBCOEMS`。</span><span class="sxs-lookup"><span data-stu-id="d0376-112">In the **Name** field, type `ReceiveFromTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="d0376-113">在**身份验证**组框中，指定使用身份验证时处理消息的方式。</span><span class="sxs-lookup"><span data-stu-id="d0376-113">In the **Authentication** group box, specify how messages are handled when using authentication.</span></span>  
  
    3.  <span data-ttu-id="d0376-114">选择**启用路由失败消息**复选框。</span><span class="sxs-lookup"><span data-stu-id="d0376-114">Select the **Enable routing for failed messages** checkbox.</span></span>  
  
4.  <span data-ttu-id="d0376-115">上**接收位置**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0376-115">On the **Receive Locations** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="d0376-116">单击 **“新建”**。</span><span class="sxs-lookup"><span data-stu-id="d0376-116">Click **New**.</span></span>  
  
    2.  <span data-ttu-id="d0376-117">在**接收位置**窗口，请在**常规**页上，键入**名称**的接收位置。</span><span class="sxs-lookup"><span data-stu-id="d0376-117">In the **Receive Locations** window, on the **General** page, type the **Name** of the receive location.</span></span>  
  
    3.  <span data-ttu-id="d0376-118">从**类型**下拉列表中，选择传输类型，并从**接收处理程序**下拉列表中，选择的传输地址。</span><span class="sxs-lookup"><span data-stu-id="d0376-118">From the **Type** drop-down list, select the transport type, and from the **Receive handler** drop-down list, select the transport address.</span></span>  
  
    4.  <span data-ttu-id="d0376-119">从**接收管道**下拉列表中，选择接收管道。</span><span class="sxs-lookup"><span data-stu-id="d0376-119">From the **Receive pipeline** drop-down list, select the receive pipeline.</span></span>  
  
    5.  <span data-ttu-id="d0376-120">上**计划**页上，选择**开始日期**和**结束日期**限制接收的文档。</span><span class="sxs-lookup"><span data-stu-id="d0376-120">On the **Schedule** page, select the **Start date** and the **End date** to restrict receiving documents.</span></span>  
  
    6.  <span data-ttu-id="d0376-121">选择**启用服务窗口**复选框。</span><span class="sxs-lookup"><span data-stu-id="d0376-121">Select the **Enable service window** checkbox.</span></span>  
  
    7.  <span data-ttu-id="d0376-122">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d0376-122">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="d0376-123">上**入站映射**页上，选择转换所选的端口上的文档的入站的映射。</span><span class="sxs-lookup"><span data-stu-id="d0376-123">On the **Inbound Maps** page, select the inbound maps for transforming documents on the selected port.</span></span>  
  
6.  <span data-ttu-id="d0376-124">上**跟踪**页上，选择所需的跟踪消息正文和跟踪消息属性。</span><span class="sxs-lookup"><span data-stu-id="d0376-124">On the **Tracking** page, select the desired tracking message bodies and tracking message properties.</span></span>  
  
7.  <span data-ttu-id="d0376-125">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d0376-125">Click **OK**.</span></span>  

## <a name="set-the-receive-port-transport-properties"></a><span data-ttu-id="d0376-126">设置接收端口传输属性</span><span class="sxs-lookup"><span data-stu-id="d0376-126">Set the receive port transport properties</span></span>
<span data-ttu-id="d0376-127">TIBCO 企业消息系统 (EMS) 接收位置， **URL**和**目标 Namespace**到 TIBCO EMS 系统是所需的唯一配置值。</span><span class="sxs-lookup"><span data-stu-id="d0376-127">For a TIBCO Enterprise Message System (EMS) receive location, the **URL** and **Target Namespace** to the TIBCO EMS System are the only configuration values required.</span></span>    
 
1.  <span data-ttu-id="d0376-128">展开**系统定义**然后输入 TIBCO EMS 服务器连接的所有必要的信息。</span><span class="sxs-lookup"><span data-stu-id="d0376-128">Expand the **System Definition** and enter all required information for connection to the TIBCO EMS server.</span></span>  
  
2.  <span data-ttu-id="d0376-129">展开**消息处理**并输入所有所需的信息。</span><span class="sxs-lookup"><span data-stu-id="d0376-129">Expand **Message Handling** and enter all required information.</span></span>  
  
    |<span data-ttu-id="d0376-130">参数</span><span class="sxs-lookup"><span data-stu-id="d0376-130">Parameter</span></span>|<span data-ttu-id="d0376-131">Description</span><span class="sxs-lookup"><span data-stu-id="d0376-131">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="d0376-132">**消息选择器**</span><span class="sxs-lookup"><span data-stu-id="d0376-132">**Message Selector**</span></span>|<span data-ttu-id="d0376-133">仅当目标消息中的此字符串的评估结果为 True 时，才接收消息。</span><span class="sxs-lookup"><span data-stu-id="d0376-133">Messages are received only if this string evaluates to True with the message in the destination.</span></span><br /><br /> <span data-ttu-id="d0376-134">允许接收端口仅检索其包含的标头属性与本字段中介绍的表达式匹配的消息。</span><span class="sxs-lookup"><span data-stu-id="d0376-134">Allows the receive port to retrieve only messages that contain header properties that match the expression described in this field.</span></span><br /><br /> <span data-ttu-id="d0376-135">消息选择器的语法基于 SQL92 条件表达式语法的子集。</span><span class="sxs-lookup"><span data-stu-id="d0376-135">The syntax of message selectors is based on a subset of the SQL92 conditional expression syntax.</span></span> <span data-ttu-id="d0376-136">TIBCO EMS 用户指南中完整说明了该语法。</span><span class="sxs-lookup"><span data-stu-id="d0376-136">The syntax is fully described in the TIBCO EMS users guide.</span></span><br /><br /> <span data-ttu-id="d0376-137">例如，如果一个消息包含标头属性名称 NewsType，则接收端口将仅接收类型为 Sports 或 Editorial 的消息。</span><span class="sxs-lookup"><span data-stu-id="d0376-137">For example, if a message contains a header property name NewsType, a receive port can retrieve only those that are of type Sports or Editorial.</span></span>|  
    |<span data-ttu-id="d0376-138">**重试计数**</span><span class="sxs-lookup"><span data-stu-id="d0376-138">**Retry Count**</span></span>|<span data-ttu-id="d0376-139">传输重试计数。</span><span class="sxs-lookup"><span data-stu-id="d0376-139">The retry count for the transport.</span></span> <span data-ttu-id="d0376-140">默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="d0376-140">Default value is 0.</span></span>|  
    |<span data-ttu-id="d0376-141">**重试间隔**</span><span class="sxs-lookup"><span data-stu-id="d0376-141">**Retry Interval**</span></span>|<span data-ttu-id="d0376-142">适配器发起重试之前的等待时间。</span><span class="sxs-lookup"><span data-stu-id="d0376-142">The period of time the adapter waits before initiating a retry.</span></span> <span data-ttu-id="d0376-143">默认值为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="d0376-143">Default value is five minutes.</span></span>|  
  
3.  <span data-ttu-id="d0376-144">展开**服务器连接定义**并输入所有所需的信息。</span><span class="sxs-lookup"><span data-stu-id="d0376-144">Expand the **Server Connection Definition** and enter all required information.</span></span>  
  
    |<span data-ttu-id="d0376-145">参数</span><span class="sxs-lookup"><span data-stu-id="d0376-145">Parameter</span></span>|<span data-ttu-id="d0376-146">Description</span><span class="sxs-lookup"><span data-stu-id="d0376-146">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="d0376-147">**目标**</span><span class="sxs-lookup"><span data-stu-id="d0376-147">**Destination**</span></span>|<span data-ttu-id="d0376-148">强制设置。</span><span class="sxs-lookup"><span data-stu-id="d0376-148">Mandatory setting.</span></span> <span data-ttu-id="d0376-149">定义目标名称和类型。</span><span class="sxs-lookup"><span data-stu-id="d0376-149">Defines the name and type of the destination.</span></span> <span data-ttu-id="d0376-150">使用以下格式定义队列或主题：Queue[queue.name] 或 Topic[topic.name]。</span><span class="sxs-lookup"><span data-stu-id="d0376-150">Defines the queue or topic with the following format: Queue[queue.name] or Topic[topic.name].</span></span>|  
    |<span data-ttu-id="d0376-151">**端口号**</span><span class="sxs-lookup"><span data-stu-id="d0376-151">**Port Number**</span></span>|<span data-ttu-id="d0376-152">TIBCO EMS 服务器侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="d0376-152">Port on which the TIBCO EMS server listens.</span></span>|  
    |<span data-ttu-id="d0376-153">**服务器名称**</span><span class="sxs-lookup"><span data-stu-id="d0376-153">**Server Name**</span></span>|<span data-ttu-id="d0376-154">强制设置。</span><span class="sxs-lookup"><span data-stu-id="d0376-154">Mandatory setting.</span></span> <span data-ttu-id="d0376-155">托管 TIBCO EMS 服务器的系统的名称。</span><span class="sxs-lookup"><span data-stu-id="d0376-155">Name of the system hosting the TIBCO EMS server.</span></span>|  
  
4.  <span data-ttu-id="d0376-156">使用单一登录 (SSO) 提供凭据。</span><span class="sxs-lookup"><span data-stu-id="d0376-156">Provide credentials using Single Sign-On (SSO).</span></span>  
  
     <span data-ttu-id="d0376-157">有两种方法可用于访问 TIBCO EMS 系统。</span><span class="sxs-lookup"><span data-stu-id="d0376-157">There are two methods that you can use to access the TIBCO EMS system.</span></span> <span data-ttu-id="d0376-158">你可以使用凭据 （用户名称和密码参数） 或上单一登录。</span><span class="sxs-lookup"><span data-stu-id="d0376-158">You can use Credentials (user name and password parameters) or Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="d0376-159">选择**是**中**使用 SSO**用于单一登录。</span><span class="sxs-lookup"><span data-stu-id="d0376-159">Select **Yes** in **Use SSO** to use Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="d0376-160">在列表中选择一个关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="d0376-160">Select an affiliate application in the list.</span></span>  
  
         <span data-ttu-id="d0376-161">企业单一登录工具创建的关联应用程序代表诸如 TIBCO EMS 之类的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d0376-161">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as TIBCO EMS.</span></span> <span data-ttu-id="d0376-162">用于 TIBCO EMS 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="d0376-162">Microsoft BizTalk Adapter for TIBCO EMS uses the credentials of an application user.</span></span> <span data-ttu-id="d0376-163">这些凭据是从服务器系统的 SSO 数据库中为指定关联应用程序检索的。</span><span class="sxs-lookup"><span data-stu-id="d0376-163">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span>  
  
         <span data-ttu-id="d0376-164">有关如何创建关联应用程序的详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications5.md)。</span><span class="sxs-lookup"><span data-stu-id="d0376-164">For more information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
5.  <span data-ttu-id="d0376-165">展开**用户凭据**并输入**用户名**和**密码**访问 TIBCO EMS 服务器。</span><span class="sxs-lookup"><span data-stu-id="d0376-165">Expand **User Credentials** and enter the **User Name** and **Password** to access the TIBCO EMS server.</span></span>  
  
    |<span data-ttu-id="d0376-166">参数</span><span class="sxs-lookup"><span data-stu-id="d0376-166">Parameter</span></span>|<span data-ttu-id="d0376-167">Description</span><span class="sxs-lookup"><span data-stu-id="d0376-167">Description</span></span>|  
    |---------------|-----------------|  
    |`Password`|<span data-ttu-id="d0376-168">用于与 TIBCO EMS 后台程序通信的用户的密码。</span><span class="sxs-lookup"><span data-stu-id="d0376-168">The user’s password that is used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="d0376-169">如果你未选择**使用 SSO**，你必须设置为 BizTalk 适配器 TIBCO EMS 与 TIBCO EMS 后台程序进行通信的凭据参数。</span><span class="sxs-lookup"><span data-stu-id="d0376-169">If you did not select **Use SSO**, you must set credential parameters for BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
    |`User Name`|<span data-ttu-id="d0376-170">用于与 TIBCO EMS 后台程序进行通信的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="d0376-170">Name of a user that is used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="d0376-171">如果你未选择**使用 SSO**，你必须设置为 BizTalk 适配器 TIBCO EMS 与 TIBCO EMS 后台程序进行通信的凭据参数。</span><span class="sxs-lookup"><span data-stu-id="d0376-171">If you did not select **Use SSO**, you must set credential parameters for BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
  
6.  <span data-ttu-id="d0376-172">单击**应用**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d0376-172">Click **Apply**, and then click **OK**.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="d0376-173">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d0376-173">Next steps</span></span>
[<span data-ttu-id="d0376-174">TIBCO EMS 消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="d0376-174">TIBCO EMS message context properties</span></span>](../core/message-context-properties-in-biztalk-server.md)