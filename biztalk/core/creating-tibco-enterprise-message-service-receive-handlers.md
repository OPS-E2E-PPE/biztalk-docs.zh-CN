---
title: 创建 TIBCO EMS 接收项目 |Microsoft Docs
description: 创建接收端口，并设置要在 BizTalk Server 中使用 TIBCO Enterprise Message Service 适配器的传输属性
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
ms.openlocfilehash: 27dd4ff3e317f178c2b9085cf531a6b963aafc7f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390230"
---
# <a name="create-tibco-ems-receive-artifacts"></a><span data-ttu-id="49132-103">创建 TIBCO EMS 接收项目</span><span class="sxs-lookup"><span data-stu-id="49132-103">Create TIBCO EMS receive artifacts</span></span>

## <a name="overview"></a><span data-ttu-id="49132-104">概述</span><span class="sxs-lookup"><span data-stu-id="49132-104">Overview</span></span>
<span data-ttu-id="49132-105">TIBCO Enterprise Message Service 接收器是侦听器服务，注册特殊的队列或主题，并接收相关消息。</span><span class="sxs-lookup"><span data-stu-id="49132-105">TIBCO Enterprise Message Service receiver is a listener service that registers a particular Queue or Topic and receives the relative messages.</span></span> <span data-ttu-id="49132-106">用于 TIBCO Enterprise Message Service 的 BizTalk 适配器第一次注册与 TIBCO Enterprise Message Service 通过打开新的会话，，然后它会继续轮询以接收消息...</span><span class="sxs-lookup"><span data-stu-id="49132-106">BizTalk Adapter for TIBCO Enterprise Message Service first registers with TIBCO Enterprise Message Service by opening a new session, and then it continues polling to receive messages..</span></span> <span data-ttu-id="49132-107">本部分介绍如何设置要连接到 TIBCO Enterprise Message Service 的接收端口以及如何将 XML 包含在您的业务流程在运行时与 TIBCO EMS 交互。</span><span class="sxs-lookup"><span data-stu-id="49132-107">This section explains how to set the receive port to connect to TIBCO Enterprise Message Service and how to include XML in your orchestration to interact with TIBCO EMS at run time.</span></span>  

## <a name="create-a-receive-port"></a><span data-ttu-id="49132-108">创建接收端口</span><span class="sxs-lookup"><span data-stu-id="49132-108">Create a receive port</span></span>  
  
1.  <span data-ttu-id="49132-109">在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="49132-109">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then expand your application.</span></span>  
  
2.  <span data-ttu-id="49132-110">右键单击**接收端口**，选择**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="49132-110">Right-click **Receive Ports**, select **New**, and then click **One-way Receive Ports**.</span></span>  
  
3.  <span data-ttu-id="49132-111">在中**接收端口属性**窗口，然后在**常规**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="49132-111">In the **Receive Port Properties** window, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="49132-112">在中**名称**字段中，键入`ReceiveFromTIBCOEMS`。</span><span class="sxs-lookup"><span data-stu-id="49132-112">In the **Name** field, type `ReceiveFromTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="49132-113">在中**身份验证**组框中，指定如何处理消息时使用身份验证。</span><span class="sxs-lookup"><span data-stu-id="49132-113">In the **Authentication** group box, specify how messages are handled when using authentication.</span></span>  
  
    3.  <span data-ttu-id="49132-114">选择**失败消息启用路由功能**复选框。</span><span class="sxs-lookup"><span data-stu-id="49132-114">Select the **Enable routing for failed messages** checkbox.</span></span>  
  
4.  <span data-ttu-id="49132-115">上**接收位置**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="49132-115">On the **Receive Locations** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="49132-116">单击 **“新建”**。</span><span class="sxs-lookup"><span data-stu-id="49132-116">Click **New**.</span></span>  
  
    2.  <span data-ttu-id="49132-117">在中**接收位置**窗口，然后在**常规**页上，键入**名称**的接收位置。</span><span class="sxs-lookup"><span data-stu-id="49132-117">In the **Receive Locations** window, on the **General** page, type the **Name** of the receive location.</span></span>  
  
    3.  <span data-ttu-id="49132-118">从**类型**下拉列表中，选择传输类型和从**接收处理程序**下拉列表中，选择的传输地址。</span><span class="sxs-lookup"><span data-stu-id="49132-118">From the **Type** drop-down list, select the transport type, and from the **Receive handler** drop-down list, select the transport address.</span></span>  
  
    4.  <span data-ttu-id="49132-119">从**接收管道**下拉列表中，选择接收管道。</span><span class="sxs-lookup"><span data-stu-id="49132-119">From the **Receive pipeline** drop-down list, select the receive pipeline.</span></span>  
  
    5.  <span data-ttu-id="49132-120">上**计划**页上，选择**开始日期**并**结束日期**以限制接收文档。</span><span class="sxs-lookup"><span data-stu-id="49132-120">On the **Schedule** page, select the **Start date** and the **End date** to restrict receiving documents.</span></span>  
  
    6.  <span data-ttu-id="49132-121">选择**启用服务时段**复选框。</span><span class="sxs-lookup"><span data-stu-id="49132-121">Select the **Enable service window** checkbox.</span></span>  
  
    7.  <span data-ttu-id="49132-122">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="49132-122">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="49132-123">上**入站映射**页上，选择用于转换所选端口上的文档的入站的映射。</span><span class="sxs-lookup"><span data-stu-id="49132-123">On the **Inbound Maps** page, select the inbound maps for transforming documents on the selected port.</span></span>  
  
6.  <span data-ttu-id="49132-124">上**跟踪**页上，选择所需的跟踪消息正文和跟踪消息属性。</span><span class="sxs-lookup"><span data-stu-id="49132-124">On the **Tracking** page, select the desired tracking message bodies and tracking message properties.</span></span>  
  
7.  <span data-ttu-id="49132-125">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="49132-125">Click **OK**.</span></span>  

## <a name="set-the-receive-port-transport-properties"></a><span data-ttu-id="49132-126">设置接收端口传输属性</span><span class="sxs-lookup"><span data-stu-id="49132-126">Set the receive port transport properties</span></span>
<span data-ttu-id="49132-127">用于 TIBCO Enterprise 消息系统 (EMS) 接收位置，则**URL**并**Target Namespace**到 TIBCO EMS 系统是所需的唯一配置值。</span><span class="sxs-lookup"><span data-stu-id="49132-127">For a TIBCO Enterprise Message System (EMS) receive location, the **URL** and **Target Namespace** to the TIBCO EMS System are the only configuration values required.</span></span>    
 
1.  <span data-ttu-id="49132-128">展开**系统定义**并输入所需的所有信息以连接到 TIBCO EMS 服务器。</span><span class="sxs-lookup"><span data-stu-id="49132-128">Expand the **System Definition** and enter all required information for connection to the TIBCO EMS server.</span></span>  
  
2.  <span data-ttu-id="49132-129">展开**消息处理**并输入所需的所有信息。</span><span class="sxs-lookup"><span data-stu-id="49132-129">Expand **Message Handling** and enter all required information.</span></span>  
  
    |<span data-ttu-id="49132-130">参数</span><span class="sxs-lookup"><span data-stu-id="49132-130">Parameter</span></span>|<span data-ttu-id="49132-131">Description</span><span class="sxs-lookup"><span data-stu-id="49132-131">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="49132-132">**消息选择器**</span><span class="sxs-lookup"><span data-stu-id="49132-132">**Message Selector**</span></span>|<span data-ttu-id="49132-133">此字符串的计算结果为与目标中的消息，则返回 True，才接收消息。</span><span class="sxs-lookup"><span data-stu-id="49132-133">Messages are received only if this string evaluates to True with the message in the destination.</span></span><br /><br /> <span data-ttu-id="49132-134">允许要检索包含在此字段中所述的表达式匹配的标头属性的消息的接收端口。</span><span class="sxs-lookup"><span data-stu-id="49132-134">Allows the receive port to retrieve only messages that contain header properties that match the expression described in this field.</span></span><br /><br /> <span data-ttu-id="49132-135">消息选择器的语法基于 SQL92 条件表达式语法的子集。</span><span class="sxs-lookup"><span data-stu-id="49132-135">The syntax of message selectors is based on a subset of the SQL92 conditional expression syntax.</span></span> <span data-ttu-id="49132-136">完全在 TIBCO EMS 用户指南中介绍的语法。</span><span class="sxs-lookup"><span data-stu-id="49132-136">The syntax is fully described in the TIBCO EMS users guide.</span></span><br /><br /> <span data-ttu-id="49132-137">例如，如果一条消息包含标头属性名称 NewsType，接收端口可以检索仅 Sports 或 Editorial 的类型。</span><span class="sxs-lookup"><span data-stu-id="49132-137">For example, if a message contains a header property name NewsType, a receive port can retrieve only those that are of type Sports or Editorial.</span></span>|  
    |<span data-ttu-id="49132-138">**重试次数**</span><span class="sxs-lookup"><span data-stu-id="49132-138">**Retry Count**</span></span>|<span data-ttu-id="49132-139">传输重试计数。</span><span class="sxs-lookup"><span data-stu-id="49132-139">The retry count for the transport.</span></span> <span data-ttu-id="49132-140">默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="49132-140">Default value is 0.</span></span>|  
    |<span data-ttu-id="49132-141">**重试间隔**</span><span class="sxs-lookup"><span data-stu-id="49132-141">**Retry Interval**</span></span>|<span data-ttu-id="49132-142">启动重试之前的时间段适配器的等待。</span><span class="sxs-lookup"><span data-stu-id="49132-142">The period of time the adapter waits before initiating a retry.</span></span> <span data-ttu-id="49132-143">默认值为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="49132-143">Default value is five minutes.</span></span>|  
  
3.  <span data-ttu-id="49132-144">展开**服务器连接定义**并输入所需的所有信息。</span><span class="sxs-lookup"><span data-stu-id="49132-144">Expand the **Server Connection Definition** and enter all required information.</span></span>  
  
    |<span data-ttu-id="49132-145">参数</span><span class="sxs-lookup"><span data-stu-id="49132-145">Parameter</span></span>|<span data-ttu-id="49132-146">Description</span><span class="sxs-lookup"><span data-stu-id="49132-146">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="49132-147">**目标**</span><span class="sxs-lookup"><span data-stu-id="49132-147">**Destination**</span></span>|<span data-ttu-id="49132-148">强制设置。</span><span class="sxs-lookup"><span data-stu-id="49132-148">Mandatory setting.</span></span> <span data-ttu-id="49132-149">定义名称和目标的类型。</span><span class="sxs-lookup"><span data-stu-id="49132-149">Defines the name and type of the destination.</span></span> <span data-ttu-id="49132-150">定义队列或主题具有以下格式：Queue [queue.name] 或 topic [topic.name]。</span><span class="sxs-lookup"><span data-stu-id="49132-150">Defines the queue or topic with the following format: Queue[queue.name] or Topic[topic.name].</span></span>|  
    |<span data-ttu-id="49132-151">**端口号**</span><span class="sxs-lookup"><span data-stu-id="49132-151">**Port Number**</span></span>|<span data-ttu-id="49132-152">TIBCO EMS 服务器在其侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="49132-152">Port on which the TIBCO EMS server listens.</span></span>|  
    |<span data-ttu-id="49132-153">**服务器名称**</span><span class="sxs-lookup"><span data-stu-id="49132-153">**Server Name**</span></span>|<span data-ttu-id="49132-154">强制设置。</span><span class="sxs-lookup"><span data-stu-id="49132-154">Mandatory setting.</span></span> <span data-ttu-id="49132-155">托管 TIBCO EMS 服务器的系统的名称。</span><span class="sxs-lookup"><span data-stu-id="49132-155">Name of the system hosting the TIBCO EMS server.</span></span>|  
  
4.  <span data-ttu-id="49132-156">提供使用单一登录 (SSO) 的凭据。</span><span class="sxs-lookup"><span data-stu-id="49132-156">Provide credentials using Single Sign-On (SSO).</span></span>  
  
     <span data-ttu-id="49132-157">有两种方法可用于访问 TIBCO EMS 系统。</span><span class="sxs-lookup"><span data-stu-id="49132-157">There are two methods that you can use to access the TIBCO EMS system.</span></span> <span data-ttu-id="49132-158">可以使用凭据 （用户名称和密码参数） 或单一登录。</span><span class="sxs-lookup"><span data-stu-id="49132-158">You can use Credentials (user name and password parameters) or Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="49132-159">选择**是**中**使用 SSO**若要使用单一登录。</span><span class="sxs-lookup"><span data-stu-id="49132-159">Select **Yes** in **Use SSO** to use Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="49132-160">在列表中选择关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="49132-160">Select an affiliate application in the list.</span></span>  
  
         <span data-ttu-id="49132-161">企业单一登录工具创建的关联应用程序表示诸如 TIBCO EMS 之类的应用程序。</span><span class="sxs-lookup"><span data-stu-id="49132-161">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as TIBCO EMS.</span></span> <span data-ttu-id="49132-162">用于 TIBCO EMS 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="49132-162">Microsoft BizTalk Adapter for TIBCO EMS uses the credentials of an application user.</span></span> <span data-ttu-id="49132-163">从指定的关联应用程序的服务器系统的 SSO 数据库检索这些凭据。</span><span class="sxs-lookup"><span data-stu-id="49132-163">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span>  
  
         <span data-ttu-id="49132-164">有关如何创建关联应用程序的详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications5.md)。</span><span class="sxs-lookup"><span data-stu-id="49132-164">For more information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
5.  <span data-ttu-id="49132-165">展开**用户凭据**并输入**用户名**并**密码**访问 TIBCO EMS 服务器。</span><span class="sxs-lookup"><span data-stu-id="49132-165">Expand **User Credentials** and enter the **User Name** and **Password** to access the TIBCO EMS server.</span></span>  
  
    |<span data-ttu-id="49132-166">参数</span><span class="sxs-lookup"><span data-stu-id="49132-166">Parameter</span></span>|<span data-ttu-id="49132-167">Description</span><span class="sxs-lookup"><span data-stu-id="49132-167">Description</span></span>|  
    |---------------|-----------------|  
    |`Password`|<span data-ttu-id="49132-168">用于与 TIBCO EMS 守护程序通信的用户的密码。</span><span class="sxs-lookup"><span data-stu-id="49132-168">The user’s password that is used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="49132-169">如果未选中**使用 SSO**，则必须设置凭据参数，用于与 TIBCO EMS 守护程序通信的 TIBCO EMS 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="49132-169">If you did not select **Use SSO**, you must set credential parameters for BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
    |`User Name`|<span data-ttu-id="49132-170">用于与 TIBCO EMS 守护程序通信的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="49132-170">Name of a user that is used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="49132-171">如果未选中**使用 SSO**，则必须设置凭据参数，用于与 TIBCO EMS 守护程序通信的 TIBCO EMS 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="49132-171">If you did not select **Use SSO**, you must set credential parameters for BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
  
6.  <span data-ttu-id="49132-172">单击**Apply**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="49132-172">Click **Apply**, and then click **OK**.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="49132-173">后续步骤</span><span class="sxs-lookup"><span data-stu-id="49132-173">Next steps</span></span>
[<span data-ttu-id="49132-174">TIBCO EMS 消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="49132-174">TIBCO EMS message context properties</span></span>](../core/message-context-properties-in-biztalk-server.md)