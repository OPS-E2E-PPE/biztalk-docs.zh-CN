---
title: 如何配置传输高级选项的发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, transport options [send ports]
- configuring, send ports
- send ports, transport options
- managing [send ports], configuring
- managing [send ports], transport options
ms.assetid: b0033e09-3c18-4e53-a470-e12978e61ba1
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86c61a7d77b3fbb4ebda539863223fa4ae12ed51
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340157"
---
# <a name="how-to-configure-transport-advanced-options-for-a-send-port"></a><span data-ttu-id="35c93-102">如何配置传输高级选项的发送端口</span><span class="sxs-lookup"><span data-stu-id="35c93-102">How to Configure Transport Advanced Options for a Send Port</span></span>
<span data-ttu-id="35c93-103">使用 BizTalk Server 管理控制台来配置传输高级选项的发送端口。</span><span class="sxs-lookup"><span data-stu-id="35c93-103">Use the BizTalk Server Administration console to configure transport advanced options for a send port.</span></span> <span data-ttu-id="35c93-104">这些选项确定的发送端口，例如的次数重试发送消息失败的消息和端口的服务时段计划如何处理消息。</span><span class="sxs-lookup"><span data-stu-id="35c93-104">These options determine how messages are handled by the send port, such as the number of times to retry sending messages on message failure and the service window schedule for the port.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="35c93-105">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，可以启用按序的送达的动态发送端口，具体取决于相应适配器类型。</span><span class="sxs-lookup"><span data-stu-id="35c93-105">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, you can enable ordered delivery for dynamic send ports, depending on the adapter type.</span></span> <span data-ttu-id="35c93-106">此选项才可用的适配器类型对于静态发送端口，如文件适配器或 FTP 适配器能保证按序的送达的位置。</span><span class="sxs-lookup"><span data-stu-id="35c93-106">This option is only available for the adapter types where ordered delivery is guaranteed for static send ports, such as the File adapter, or the FTP adapter.</span></span>
> 
> <span data-ttu-id="35c93-107">六个消息，请考虑：M1、 M2、 M3，M4、 M5 和 M6。</span><span class="sxs-lookup"><span data-stu-id="35c93-107">Consider six messages: M1, M2, M3, M4, M5, and M6.</span></span> <span data-ttu-id="35c93-108">M1，M3，M5 意为文件位置。</span><span class="sxs-lookup"><span data-stu-id="35c93-108">M1, M3, M5 are meant for a file location.</span></span> <span data-ttu-id="35c93-109">M2、 M4 和 M6 用于 FTP。</span><span class="sxs-lookup"><span data-stu-id="35c93-109">M2, M4, and M6 are meant for FTP.</span></span> <span data-ttu-id="35c93-110">按序的送达动态发送端口可确保，M1、 M3 和 M5 进行排序;和 M2、 M4 和 M6 分别进行排序。</span><span class="sxs-lookup"><span data-stu-id="35c93-110">The ordered delivery dynamic send port makes sure that M1, M3, and M5 are ordered; and M2, M4, and M6 are ordered respectively.</span></span> 
> 
> <span data-ttu-id="35c93-111">对于这些不支持按序的送达的适配器类型，不存在任何可配置的动态发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="35c93-111">For those adapter types that don't support ordered delivery, there aren't any dynamic send port properties available to configure.</span></span> <span data-ttu-id="35c93-112">在运行时自动确定其传输选项。</span><span class="sxs-lookup"><span data-stu-id="35c93-112">Their transport options are automatically determined at run time.</span></span>  
> 
> <span data-ttu-id="35c93-113">**对于以前的 BizTalk 版本**使用动态端口，没有可用于配置，因为在运行时自动确定传输选项的任何属性。</span><span class="sxs-lookup"><span data-stu-id="35c93-113">**For previous BizTalk versions** that use dynamic ports, there aren't any properties available to configure because the transport options are automatically determined at run time.</span></span>

  
## <a name="prerequisites"></a><span data-ttu-id="35c93-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="35c93-114">Prerequisites</span></span>  
 <span data-ttu-id="35c93-115">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="35c93-115">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="35c93-116">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="35c93-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="controlling-send-port-priority"></a><span data-ttu-id="35c93-117">控制发送端口的优先级</span><span class="sxs-lookup"><span data-stu-id="35c93-117">Controlling Send Port Priority</span></span>  
 <span data-ttu-id="35c93-118">传输高级选项的优先级设置控制在其中可以从消息框中删除消息的顺序。</span><span class="sxs-lookup"><span data-stu-id="35c93-118">The Priority setting of the Transport Advanced Options controls the order in which messages are removed from the message box.</span></span> <span data-ttu-id="35c93-119">将具有较低的优先级，使较高优先级的端口更重要的相对于其他发送端口在单个主机端口更早处理具有较高优先级的端口。</span><span class="sxs-lookup"><span data-stu-id="35c93-119">Ports with a higher priority will be processed earlier than ports with a lower priority making the higher priority ports more important relative to other send ports within a single host.</span></span>  
  
 <span data-ttu-id="35c93-120">优先级是在需要低响应时间对于某些类型的请求方案中有用。</span><span class="sxs-lookup"><span data-stu-id="35c93-120">Priority is useful in scenarios requiring low response times for certain types of requests.</span></span> <span data-ttu-id="35c93-121">例如，如果有多个发送端口连接到不同的系统来处理正常请求和交互式请求。</span><span class="sxs-lookup"><span data-stu-id="35c93-121">For example, if there are multiple send ports that connect to different systems for processing normal requests and interactive requests.</span></span> <span data-ttu-id="35c93-122">交互式请求要求响应时间短，因此，当提交交互式请求时，你想要确保尽可能快地处理。</span><span class="sxs-lookup"><span data-stu-id="35c93-122">The interactive requests require a low response time, so when an interactive request is submitted, you want to ensure it is processed as soon as possible.</span></span>  
  
 <span data-ttu-id="35c93-123">BizTalk Server 不会尝试会公平对待各个消息的处理具有不同优先级的消息框中。</span><span class="sxs-lookup"><span data-stu-id="35c93-123">BizTalk Server does not attempt to be fair in the processing of messages with different priorities in the message box.</span></span> <span data-ttu-id="35c93-124">如果相等具有两个不同的优先级处理时在消息框中的项的数字开始，将项的较低优先级处理项都得到处理仅所有高优先级。</span><span class="sxs-lookup"><span data-stu-id="35c93-124">If there are equal numbers of items with two different priorities in the message box when processing begins, the lower priority items will be processed only after all high priority items have been processed.</span></span> <span data-ttu-id="35c93-125">如果高优先级的项量大，就可以永远不会处理优先级较低的项。</span><span class="sxs-lookup"><span data-stu-id="35c93-125">If the volume of high priority items is great, it is possible that items with a lower priority will never be processed.</span></span> <span data-ttu-id="35c93-126">换而言之，低优先级的项会出现资源不足。</span><span class="sxs-lookup"><span data-stu-id="35c93-126">In other words, the lower priority items will experience starvation.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="35c93-127">为了尽量降低消息资源不足的风险，全面测试实际负载下的应用程序，以确保所有消息进行都处理。</span><span class="sxs-lookup"><span data-stu-id="35c93-127">To minimize the risk of message starvation, thoroughly test your application under realistic loads to ensure all messages are processed.</span></span> <span data-ttu-id="35c93-128">故障来测试你的解决方案可能会导致未处理消息。</span><span class="sxs-lookup"><span data-stu-id="35c93-128">Failure to test your solution may result in unprocessed messages.</span></span>  
  
 <span data-ttu-id="35c93-129">在内部，BizTalk Server 将优先级分配给每个订阅。</span><span class="sxs-lookup"><span data-stu-id="35c93-129">Internally, BizTalk Server assigns a priority to every subscription.</span></span> <span data-ttu-id="35c93-130">优先级可以是从 1 （最高优先级） 到 10 （优先级最低） 任何数字。</span><span class="sxs-lookup"><span data-stu-id="35c93-130">Priority can be any number from 1 (highest priority) to 10 (lowest priority).</span></span> <span data-ttu-id="35c93-131">默认优先级为 7 来激活订阅和 5 相关订阅的因为关联消息将被传送早于激活订阅。</span><span class="sxs-lookup"><span data-stu-id="35c93-131">Because the default priority is 7 for activating subscriptions and 5 for correlating subscriptions, correlating messages will be delivered earlier than activating subscriptions.</span></span>  
  
## <a name="configure-the-transport-options"></a><span data-ttu-id="35c93-132">配置传输选项</span><span class="sxs-lookup"><span data-stu-id="35c93-132">Configure the transport options</span></span> 
  
1.  <span data-ttu-id="35c93-133">打开 **“BizTalk Server 管理”**。</span><span class="sxs-lookup"><span data-stu-id="35c93-133">Open **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="35c93-134">展开 BizTalk 组，然后展开 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="35c93-134">Expand the BizTalk group, and then expand your BizTalk application.</span></span>  
  
3.  <span data-ttu-id="35c93-135">选择**发送端口**，右键单击发送端口以配置，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="35c93-135">Select **Send Ports**, right-click the send port to configure, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="35c93-136">在左窗格中，选择**传输高级选项**。</span><span class="sxs-lookup"><span data-stu-id="35c93-136">In the left pane, select **Transport Advanced Options**.</span></span>  
  
5.  <span data-ttu-id="35c93-137">下表中所述配置传输选项，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="35c93-137">Configure the transport options as described in the following table, and then select **OK**.</span></span>  <span data-ttu-id="35c93-138">仅以下属性中的一些适用于动态发送端口。</span><span class="sxs-lookup"><span data-stu-id="35c93-138">Only some of the following properties are available for dynamic send ports.</span></span>
  
    |<span data-ttu-id="35c93-139">使用此选项</span><span class="sxs-lookup"><span data-stu-id="35c93-139">Use this</span></span>|<span data-ttu-id="35c93-140">执行的操作</span><span class="sxs-lookup"><span data-stu-id="35c93-140">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="35c93-141">**重试次数**</span><span class="sxs-lookup"><span data-stu-id="35c93-141">**Retry count**</span></span>|<span data-ttu-id="35c93-142">指定的发送端口以重新发送消息失败的消息的次数。</span><span class="sxs-lookup"><span data-stu-id="35c93-142">Specify the number of times for the send port to resend a message on message failure.</span></span> <span data-ttu-id="35c93-143">默认值为 3;允许的范围是从 0 到 1000。</span><span class="sxs-lookup"><span data-stu-id="35c93-143">The default is 3; the allowed range is from 0 through 1,000.</span></span>|  
    |<span data-ttu-id="35c93-144">**重试间隔**</span><span class="sxs-lookup"><span data-stu-id="35c93-144">**Retry interval**</span></span>|<span data-ttu-id="35c93-145">指定以分钟为单位次重发消息尝试之间的间隔。</span><span class="sxs-lookup"><span data-stu-id="35c93-145">Specify the interval in minutes between message resend attempts.</span></span> <span data-ttu-id="35c93-146">默认值为 5;允许的范围是从 0 到 525600。</span><span class="sxs-lookup"><span data-stu-id="35c93-146">The default is 5; the allowed range is from 0 through 525,600.</span></span>|  
    |<span data-ttu-id="35c93-147">**Priority**</span><span class="sxs-lookup"><span data-stu-id="35c93-147">**Priority**</span></span>|<span data-ttu-id="35c93-148">设置重发尝试的优先级。</span><span class="sxs-lookup"><span data-stu-id="35c93-148">Set the priority of the resend attempt.</span></span>|  
    |<span data-ttu-id="35c93-149">**按序的送达**</span><span class="sxs-lookup"><span data-stu-id="35c93-149">**Ordered delivery**</span></span>|<span data-ttu-id="35c93-150">选择此复选框可按接收顺序发送消息。</span><span class="sxs-lookup"><span data-stu-id="35c93-150">Select this check box to send messages in order of receipt.</span></span>|  
    |<span data-ttu-id="35c93-151">**停止发送随后的消息当前消息失败**</span><span class="sxs-lookup"><span data-stu-id="35c93-151">**Stop sending subsequent messages on current message failure**</span></span>|<span data-ttu-id="35c93-152">选择此复选框可以停止发送随后失败消息的消息。</span><span class="sxs-lookup"><span data-stu-id="35c93-152">Select this check box to stop sending subsequent messages that follow a failed message.</span></span> <span data-ttu-id="35c93-153">此选项是时才可用**按序送达**选择选项。</span><span class="sxs-lookup"><span data-stu-id="35c93-153">This option is available only when the **Ordered delivery** option is selected.</span></span>|  
    |<span data-ttu-id="35c93-154">**为失败消息启用路由功能**</span><span class="sxs-lookup"><span data-stu-id="35c93-154">**Enable routing for failed messages**</span></span>|<span data-ttu-id="35c93-155">选择此选项可为失败消息启用路由功能。</span><span class="sxs-lookup"><span data-stu-id="35c93-155">Select this option to enable routing for failed messages.</span></span>|  
    |<span data-ttu-id="35c93-156">**启用服务时段**</span><span class="sxs-lookup"><span data-stu-id="35c93-156">**Enable service window**</span></span>|<span data-ttu-id="35c93-157">选择此选项可指定在此期间发送端口将操作通过指定开始时间和停止时间每一天的时间段。</span><span class="sxs-lookup"><span data-stu-id="35c93-157">Select this option to specify the time period each day during which the send port will be operational by specifying a start time and stop time.</span></span>|  
    |<span data-ttu-id="35c93-158">**开始时间**</span><span class="sxs-lookup"><span data-stu-id="35c93-158">**Start time**</span></span>|<span data-ttu-id="35c93-159">指定发送端口开始发送消息的每一天的时间。</span><span class="sxs-lookup"><span data-stu-id="35c93-159">Specify the time each day at which the send port starts sending messages.</span></span> <span data-ttu-id="35c93-160">此选项是时才可用**启用服务时段**选择选项。</span><span class="sxs-lookup"><span data-stu-id="35c93-160">This option is available only when the **Enable service window** option is selected.</span></span>|  
    |<span data-ttu-id="35c93-161">**停止时间**</span><span class="sxs-lookup"><span data-stu-id="35c93-161">**Stop time**</span></span>|<span data-ttu-id="35c93-162">指定发送端口停止发送消息的每一天的时间。</span><span class="sxs-lookup"><span data-stu-id="35c93-162">Specify the time each day at which the send port stops sending messages.</span></span> <span data-ttu-id="35c93-163">此选项是时才可用**启用服务时段**选择选项。</span><span class="sxs-lookup"><span data-stu-id="35c93-163">This option is available only when the **Enable service window** option is selected.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35c93-164">请参阅</span><span class="sxs-lookup"><span data-stu-id="35c93-164">See Also</span></span>  
[<span data-ttu-id="35c93-165">按序送达消息</span><span class="sxs-lookup"><span data-stu-id="35c93-165">Ordered Delivery of Messages</span></span>](../core/ordered-delivery-of-messages.md)  
 [<span data-ttu-id="35c93-166">创建和配置发送端口</span><span class="sxs-lookup"><span data-stu-id="35c93-166">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)