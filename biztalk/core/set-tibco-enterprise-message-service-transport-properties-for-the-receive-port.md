---
redirect_url: /biztalk/core/creating-tibco-enterprise-message-service-receive-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 856309a744d1874d336bb31840f193494858c81d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393298"
---
# <a name="setting-tibco-enterprise-message-service-transport-properties-for-the-receive-port"></a><span data-ttu-id="d97ab-101">设置 TIBCO Enterprise Message Service 传输属性的接收端口</span><span class="sxs-lookup"><span data-stu-id="d97ab-101">Setting TIBCO Enterprise Message Service Transport Properties for the Receive Port</span></span>
<span data-ttu-id="d97ab-102">用于 TIBCO Enterprise 消息系统 (EMS) 接收位置，则**URL**并**Target Namespace**到 TIBCO EMS 系统是所需的唯一配置值。</span><span class="sxs-lookup"><span data-stu-id="d97ab-102">For a TIBCO Enterprise Message System (EMS) receive location, the **URL** and **Target Namespace** to the TIBCO EMS System are the only configuration values required.</span></span>  
  
### <a name="to-specify-tibco-ems-transport-properties"></a><span data-ttu-id="d97ab-103">指定 TIBCO EMS 传输属性</span><span class="sxs-lookup"><span data-stu-id="d97ab-103">To specify TIBCO EMS transport properties</span></span>  
  
1.  <span data-ttu-id="d97ab-104">展开**系统定义**并输入所需的所有信息以连接到 TIBCO EMS 服务器。</span><span class="sxs-lookup"><span data-stu-id="d97ab-104">Expand the **System Definition** and enter all required information for connection to the TIBCO EMS server.</span></span>  
  
2.  <span data-ttu-id="d97ab-105">展开**消息处理**并输入所需的所有信息。</span><span class="sxs-lookup"><span data-stu-id="d97ab-105">Expand **Message Handling** and enter all required information.</span></span>  
  
    |<span data-ttu-id="d97ab-106">参数</span><span class="sxs-lookup"><span data-stu-id="d97ab-106">Parameter</span></span>|<span data-ttu-id="d97ab-107">Description</span><span class="sxs-lookup"><span data-stu-id="d97ab-107">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="d97ab-108">**消息选择器**</span><span class="sxs-lookup"><span data-stu-id="d97ab-108">**Message Selector**</span></span>|<span data-ttu-id="d97ab-109">此字符串的计算结果为与目标中的消息，则返回 True，才接收消息。</span><span class="sxs-lookup"><span data-stu-id="d97ab-109">Messages are received only if this string evaluates to True with the message in the destination.</span></span><br /><br /> <span data-ttu-id="d97ab-110">允许要检索包含在此字段中所述的表达式匹配的标头属性的消息的接收端口。</span><span class="sxs-lookup"><span data-stu-id="d97ab-110">Allows the receive port to retrieve only messages that contain header properties that match the expression described in this field.</span></span><br /><br /> <span data-ttu-id="d97ab-111">消息选择器的语法基于 SQL92 条件表达式语法的子集。</span><span class="sxs-lookup"><span data-stu-id="d97ab-111">The syntax of message selectors is based on a subset of the SQL92 conditional expression syntax.</span></span> <span data-ttu-id="d97ab-112">完全在 TIBCO EMS 用户指南中介绍的语法。</span><span class="sxs-lookup"><span data-stu-id="d97ab-112">The syntax is fully described in the TIBCO EMS users guide.</span></span><br /><br /> <span data-ttu-id="d97ab-113">例如，如果一条消息包含标头属性名称 NewsType，接收端口可以检索仅 Sports 或 Editorial 的类型。</span><span class="sxs-lookup"><span data-stu-id="d97ab-113">For example, if a message contains a header property name NewsType, a receive port can retrieve only those that are of type Sports or Editorial.</span></span>|  
    |<span data-ttu-id="d97ab-114">**重试次数**</span><span class="sxs-lookup"><span data-stu-id="d97ab-114">**Retry Count**</span></span>|<span data-ttu-id="d97ab-115">传输重试计数。</span><span class="sxs-lookup"><span data-stu-id="d97ab-115">The retry count for the transport.</span></span> <span data-ttu-id="d97ab-116">默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="d97ab-116">Default value is 0.</span></span>|  
    |<span data-ttu-id="d97ab-117">**重试间隔**</span><span class="sxs-lookup"><span data-stu-id="d97ab-117">**Retry Interval**</span></span>|<span data-ttu-id="d97ab-118">启动重试之前的时间段适配器的等待。</span><span class="sxs-lookup"><span data-stu-id="d97ab-118">The period of time the adapter waits before initiating a retry.</span></span> <span data-ttu-id="d97ab-119">默认值为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="d97ab-119">Default value is five minutes.</span></span>|  
  
3.  <span data-ttu-id="d97ab-120">展开**服务器连接定义**并输入所需的所有信息。</span><span class="sxs-lookup"><span data-stu-id="d97ab-120">Expand the **Server Connection Definition** and enter all required information.</span></span>  
  
    |<span data-ttu-id="d97ab-121">参数</span><span class="sxs-lookup"><span data-stu-id="d97ab-121">Parameter</span></span>|<span data-ttu-id="d97ab-122">Description</span><span class="sxs-lookup"><span data-stu-id="d97ab-122">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="d97ab-123">**目标**</span><span class="sxs-lookup"><span data-stu-id="d97ab-123">**Destination**</span></span>|<span data-ttu-id="d97ab-124">强制设置。</span><span class="sxs-lookup"><span data-stu-id="d97ab-124">Mandatory setting.</span></span> <span data-ttu-id="d97ab-125">定义名称和目标的类型。</span><span class="sxs-lookup"><span data-stu-id="d97ab-125">Defines the name and type of the destination.</span></span> <span data-ttu-id="d97ab-126">定义队列或主题具有以下格式：Queue [queue.name] 或 topic [topic.name]。</span><span class="sxs-lookup"><span data-stu-id="d97ab-126">Defines the queue or topic with the following format: Queue[queue.name] or Topic[topic.name].</span></span>|  
    |<span data-ttu-id="d97ab-127">**端口号**</span><span class="sxs-lookup"><span data-stu-id="d97ab-127">**Port Number**</span></span>|<span data-ttu-id="d97ab-128">TIBCO EMS 服务器在其侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="d97ab-128">Port on which the TIBCO EMS server listens.</span></span>|  
    |<span data-ttu-id="d97ab-129">**服务器名称**</span><span class="sxs-lookup"><span data-stu-id="d97ab-129">**Server Name**</span></span>|<span data-ttu-id="d97ab-130">强制设置。</span><span class="sxs-lookup"><span data-stu-id="d97ab-130">Mandatory setting.</span></span> <span data-ttu-id="d97ab-131">托管 TIBCO EMS 服务器的系统的名称。</span><span class="sxs-lookup"><span data-stu-id="d97ab-131">Name of the system hosting the TIBCO EMS server.</span></span>|  
  
4.  <span data-ttu-id="d97ab-132">提供使用单一登录 (SSO) 的凭据。</span><span class="sxs-lookup"><span data-stu-id="d97ab-132">Provide credentials using Single Sign-On (SSO).</span></span>  
  
     <span data-ttu-id="d97ab-133">有两种方法可用于访问 TIBCO EMS 系统。</span><span class="sxs-lookup"><span data-stu-id="d97ab-133">There are two methods that you can use to access the TIBCO EMS system.</span></span> <span data-ttu-id="d97ab-134">可以使用凭据 （用户名称和密码参数） 或单一登录。</span><span class="sxs-lookup"><span data-stu-id="d97ab-134">You can use Credentials (user name and password parameters) or Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="d97ab-135">选择**是**中**使用 SSO**若要使用单一登录。</span><span class="sxs-lookup"><span data-stu-id="d97ab-135">Select **Yes** in **Use SSO** to use Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="d97ab-136">在列表中选择关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="d97ab-136">Select an affiliate application in the list.</span></span>  
  
         <span data-ttu-id="d97ab-137">企业单一登录工具创建的关联应用程序表示诸如 TIBCO EMS 之类的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d97ab-137">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as TIBCO EMS.</span></span> <span data-ttu-id="d97ab-138">用于 TIBCO EMS 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="d97ab-138">Microsoft BizTalk Adapter for TIBCO EMS uses the credentials of an application user.</span></span> <span data-ttu-id="d97ab-139">从指定的关联应用程序的服务器系统的 SSO 数据库检索这些凭据。</span><span class="sxs-lookup"><span data-stu-id="d97ab-139">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span>  
  
         <span data-ttu-id="d97ab-140">有关如何创建关联应用程序的详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications5.md)。</span><span class="sxs-lookup"><span data-stu-id="d97ab-140">For more information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
5.  <span data-ttu-id="d97ab-141">展开**用户凭据**并输入**用户名**并**密码**访问 TIBCO EMS 服务器。</span><span class="sxs-lookup"><span data-stu-id="d97ab-141">Expand **User Credentials** and enter the **User Name** and **Password** to access the TIBCO EMS server.</span></span>  
  
    |<span data-ttu-id="d97ab-142">参数</span><span class="sxs-lookup"><span data-stu-id="d97ab-142">Parameter</span></span>|<span data-ttu-id="d97ab-143">Description</span><span class="sxs-lookup"><span data-stu-id="d97ab-143">Description</span></span>|  
    |---------------|-----------------|  
    |`Password`|<span data-ttu-id="d97ab-144">用于与 TIBCO EMS 守护程序通信的用户的密码。</span><span class="sxs-lookup"><span data-stu-id="d97ab-144">The user’s password that is used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="d97ab-145">如果未选中**使用 SSO**，则必须设置凭据参数，用于与 TIBCO EMS 守护程序通信的 TIBCO EMS 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="d97ab-145">If you did not select **Use SSO**, you must set credential parameters for BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
    |`User Name`|<span data-ttu-id="d97ab-146">用于与 TIBCO EMS 守护程序通信的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="d97ab-146">Name of a user that is used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="d97ab-147">如果未选中**使用 SSO**，则必须设置凭据参数，用于与 TIBCO EMS 守护程序通信的 TIBCO EMS 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="d97ab-147">If you did not select **Use SSO**, you must set credential parameters for BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
  
6.  <span data-ttu-id="d97ab-148">单击**Apply**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d97ab-148">Click **Apply**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d97ab-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="d97ab-149">See Also</span></span>  
  [<span data-ttu-id="d97ab-150">创建 TIBCO Enterprise Message Service 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="d97ab-150">Creating TIBCO Enterprise Message Service Receive Handlers</span></span>](../core/creating-tibco-enterprise-message-service-receive-handlers.md)