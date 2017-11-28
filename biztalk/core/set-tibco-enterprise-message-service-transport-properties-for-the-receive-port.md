---
title: "设置 TIBCO 企业消息服务传输属性接收端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive ports, setting transport properties
- transport properties, setting for receive port
- setting transport properties, receive port
ms.assetid: bccddf84-d92e-469f-aa6f-4234c91a0be9
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d94229364e3bed8faaf1407603f17db76c70e6bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="setting-tibco-enterprise-message-service-transport-properties-for-the-receive-port"></a><span data-ttu-id="73713-102">设置 TIBCO 企业消息服务传输属性接收端口</span><span class="sxs-lookup"><span data-stu-id="73713-102">Setting TIBCO Enterprise Message Service Transport Properties for the Receive Port</span></span>
<span data-ttu-id="73713-103">TIBCO 企业消息系统 (EMS) 接收位置， **URL**和**目标 Namespace**到 TIBCO EMS 系统是所需的唯一配置值。</span><span class="sxs-lookup"><span data-stu-id="73713-103">For a TIBCO Enterprise Message System (EMS) receive location, the **URL** and **Target Namespace** to the TIBCO EMS System are the only configuration values required.</span></span>  
  
### <a name="to-specify-tibco-ems-transport-properties"></a><span data-ttu-id="73713-104">指定 TIBCO EMS 传输属性</span><span class="sxs-lookup"><span data-stu-id="73713-104">To specify TIBCO EMS transport properties</span></span>  
  
1.  <span data-ttu-id="73713-105">展开**系统定义**然后输入 TIBCO EMS 服务器连接的所有必要的信息。</span><span class="sxs-lookup"><span data-stu-id="73713-105">Expand the **System Definition** and enter all required information for connection to the TIBCO EMS server.</span></span>  
  
2.  <span data-ttu-id="73713-106">展开**消息处理**并输入所有所需的信息。</span><span class="sxs-lookup"><span data-stu-id="73713-106">Expand **Message Handling** and enter all required information.</span></span>  
  
    |<span data-ttu-id="73713-107">参数</span><span class="sxs-lookup"><span data-stu-id="73713-107">Parameter</span></span>|<span data-ttu-id="73713-108">Description</span><span class="sxs-lookup"><span data-stu-id="73713-108">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="73713-109">**消息选择器**</span><span class="sxs-lookup"><span data-stu-id="73713-109">**Message Selector**</span></span>|<span data-ttu-id="73713-110">仅当目标消息中的此字符串的评估结果为 True 时，才接收消息。</span><span class="sxs-lookup"><span data-stu-id="73713-110">Messages are received only if this string evaluates to True with the message in the destination.</span></span><br /><br /> <span data-ttu-id="73713-111">允许接收端口仅检索其包含的标头属性与本字段中介绍的表达式匹配的消息。</span><span class="sxs-lookup"><span data-stu-id="73713-111">Allows the receive port to retrieve only messages that contain header properties that match the expression described in this field.</span></span><br /><br /> <span data-ttu-id="73713-112">消息选择器的语法基于 SQL92 条件表达式语法的子集。</span><span class="sxs-lookup"><span data-stu-id="73713-112">The syntax of message selectors is based on a subset of the SQL92 conditional expression syntax.</span></span> <span data-ttu-id="73713-113">TIBCO EMS 用户指南中完整说明了该语法。</span><span class="sxs-lookup"><span data-stu-id="73713-113">The syntax is fully described in the TIBCO EMS users guide.</span></span><br /><br /> <span data-ttu-id="73713-114">例如，如果一个消息包含标头属性名称 NewsType，则接收端口将仅接收类型为 Sports 或 Editorial 的消息。</span><span class="sxs-lookup"><span data-stu-id="73713-114">For example, if a message contains a header property name NewsType, a receive port can retrieve only those that are of type Sports or Editorial.</span></span>|  
    |<span data-ttu-id="73713-115">**重试计数**</span><span class="sxs-lookup"><span data-stu-id="73713-115">**Retry Count**</span></span>|<span data-ttu-id="73713-116">传输重试计数。</span><span class="sxs-lookup"><span data-stu-id="73713-116">The retry count for the transport.</span></span> <span data-ttu-id="73713-117">默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="73713-117">Default value is 0.</span></span>|  
    |<span data-ttu-id="73713-118">**重试间隔**</span><span class="sxs-lookup"><span data-stu-id="73713-118">**Retry Interval**</span></span>|<span data-ttu-id="73713-119">适配器发起重试之前的等待时间。</span><span class="sxs-lookup"><span data-stu-id="73713-119">The period of time the adapter waits before initiating a retry.</span></span> <span data-ttu-id="73713-120">默认值为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="73713-120">Default value is five minutes.</span></span>|  
  
3.  <span data-ttu-id="73713-121">展开**服务器连接定义**并输入所有所需的信息。</span><span class="sxs-lookup"><span data-stu-id="73713-121">Expand the **Server Connection Definition** and enter all required information.</span></span>  
  
    |<span data-ttu-id="73713-122">参数</span><span class="sxs-lookup"><span data-stu-id="73713-122">Parameter</span></span>|<span data-ttu-id="73713-123">Description</span><span class="sxs-lookup"><span data-stu-id="73713-123">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="73713-124">**目标**</span><span class="sxs-lookup"><span data-stu-id="73713-124">**Destination**</span></span>|<span data-ttu-id="73713-125">强制设置。</span><span class="sxs-lookup"><span data-stu-id="73713-125">Mandatory setting.</span></span> <span data-ttu-id="73713-126">定义目标名称和类型。</span><span class="sxs-lookup"><span data-stu-id="73713-126">Defines the name and type of the destination.</span></span> <span data-ttu-id="73713-127">使用以下格式定义队列或主题：Queue[queue.name] 或 Topic[topic.name]。</span><span class="sxs-lookup"><span data-stu-id="73713-127">Defines the queue or topic with the following format: Queue[queue.name] or Topic[topic.name].</span></span>|  
    |<span data-ttu-id="73713-128">**端口号**</span><span class="sxs-lookup"><span data-stu-id="73713-128">**Port Number**</span></span>|<span data-ttu-id="73713-129">TIBCO EMS 服务器侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="73713-129">Port on which the TIBCO EMS server listens.</span></span>|  
    |<span data-ttu-id="73713-130">**服务器名称**</span><span class="sxs-lookup"><span data-stu-id="73713-130">**Server Name**</span></span>|<span data-ttu-id="73713-131">强制设置。</span><span class="sxs-lookup"><span data-stu-id="73713-131">Mandatory setting.</span></span> <span data-ttu-id="73713-132">托管 TIBCO EMS 服务器的系统的名称。</span><span class="sxs-lookup"><span data-stu-id="73713-132">Name of the system hosting the TIBCO EMS server.</span></span>|  
  
4.  <span data-ttu-id="73713-133">使用单一登录 (SSO) 提供凭据。</span><span class="sxs-lookup"><span data-stu-id="73713-133">Provide credentials using Single Sign-On (SSO).</span></span>  
  
     <span data-ttu-id="73713-134">有两种方法可用于访问 TIBCO EMS 系统。</span><span class="sxs-lookup"><span data-stu-id="73713-134">There are two methods that you can use to access the TIBCO EMS system.</span></span> <span data-ttu-id="73713-135">你可以使用凭据 （用户名称和密码参数） 或上单一登录。</span><span class="sxs-lookup"><span data-stu-id="73713-135">You can use Credentials (user name and password parameters) or Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="73713-136">选择**是**中**使用 SSO**用于单一登录。</span><span class="sxs-lookup"><span data-stu-id="73713-136">Select **Yes** in **Use SSO** to use Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="73713-137">在列表中选择一个关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="73713-137">Select an affiliate application in the list.</span></span>  
  
         <span data-ttu-id="73713-138">企业单一登录工具创建的关联应用程序代表诸如 TIBCO EMS 之类的应用程序。</span><span class="sxs-lookup"><span data-stu-id="73713-138">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as TIBCO EMS.</span></span> <span data-ttu-id="73713-139">用于 TIBCO EMS 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="73713-139">Microsoft BizTalk Adapter for TIBCO EMS uses the credentials of an application user.</span></span> <span data-ttu-id="73713-140">这些凭据是从服务器系统的 SSO 数据库中为指定关联应用程序检索的。</span><span class="sxs-lookup"><span data-stu-id="73713-140">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span>  
  
         <span data-ttu-id="73713-141">有关如何创建关联应用程序的详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications5.md)。</span><span class="sxs-lookup"><span data-stu-id="73713-141">For more information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
5.  <span data-ttu-id="73713-142">展开**用户凭据**并输入**用户名**和**密码**访问 TIBCO EMS 服务器。</span><span class="sxs-lookup"><span data-stu-id="73713-142">Expand **User Credentials** and enter the **User Name** and **Password** to access the TIBCO EMS server.</span></span>  
  
    |<span data-ttu-id="73713-143">参数</span><span class="sxs-lookup"><span data-stu-id="73713-143">Parameter</span></span>|<span data-ttu-id="73713-144">Description</span><span class="sxs-lookup"><span data-stu-id="73713-144">Description</span></span>|  
    |---------------|-----------------|  
    |`Password`|<span data-ttu-id="73713-145">用于与 TIBCO EMS 后台程序通信的用户的密码。</span><span class="sxs-lookup"><span data-stu-id="73713-145">The user’s password that is used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="73713-146">如果你未选择**使用 SSO**，你必须设置为 BizTalk 适配器 TIBCO EMS 与 TIBCO EMS 后台程序进行通信的凭据参数。</span><span class="sxs-lookup"><span data-stu-id="73713-146">If you did not select **Use SSO**, you must set credential parameters for BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
    |`User Name`|<span data-ttu-id="73713-147">用于与 TIBCO EMS 后台程序进行通信的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="73713-147">Name of a user that is used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="73713-148">如果你未选择**使用 SSO**，你必须设置为 BizTalk 适配器 TIBCO EMS 与 TIBCO EMS 后台程序进行通信的凭据参数。</span><span class="sxs-lookup"><span data-stu-id="73713-148">If you did not select **Use SSO**, you must set credential parameters for BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
  
6.  <span data-ttu-id="73713-149">单击**应用**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="73713-149">Click **Apply**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73713-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73713-150">See Also</span></span>  
 <span data-ttu-id="73713-151">[创建发送端口](../core/creating-send-ports1.md) </span><span class="sxs-lookup"><span data-stu-id="73713-151">[Creating Send Ports](../core/creating-send-ports1.md) </span></span>  
 [<span data-ttu-id="73713-152">创建 TIBCO 企业消息服务接收处理程序</span><span class="sxs-lookup"><span data-stu-id="73713-152">Creating TIBCO Enterprise Message Service Receive Handlers</span></span>](../core/creating-tibco-enterprise-message-service-receive-handlers.md)