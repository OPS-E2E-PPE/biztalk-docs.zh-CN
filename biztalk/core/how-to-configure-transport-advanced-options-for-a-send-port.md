---
title: "如何配置传输用于发送端口的高级选项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, transport options [send ports]
- configuring, send ports
- send ports, transport options
- managing [send ports], configuring
- managing [send ports], transport options
ms.assetid: b0033e09-3c18-4e53-a470-e12978e61ba1
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 320ed6c1caf288ac1bf9745a351bbd53a46f48db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-transport-advanced-options-for-a-send-port"></a><span data-ttu-id="294b9-102">如何为发送端口配置传输高级选项</span><span class="sxs-lookup"><span data-stu-id="294b9-102">How to Configure Transport Advanced Options for a Send Port</span></span>
<span data-ttu-id="294b9-103">使用 BizTalk Server 管理控制台来配置用于发送端口的高级选项的传输。</span><span class="sxs-lookup"><span data-stu-id="294b9-103">Use the BizTalk Server Administration console to configure transport advanced options for a send port.</span></span> <span data-ttu-id="294b9-104">这些选项决定发送端口处理消息的方式，如发送消息失败时的重试次数以及该端口的服务时段计划。</span><span class="sxs-lookup"><span data-stu-id="294b9-104">These options determine how messages are handled by the send port, such as the number of times to retry sending messages on message failure and the service window schedule for the port.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="294b9-105">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，你可以启用动态发送端口，具体取决于适配器类型的有序的传递。</span><span class="sxs-lookup"><span data-stu-id="294b9-105">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, you can enable ordered delivery for dynamic send ports, depending on the adapter type.</span></span> <span data-ttu-id="294b9-106">此选项才可用于适配器类型，将有序的传递保证为静态发送端口，如文件适配器中或 FTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="294b9-106">This option is only available for the adapter types where ordered delivery is guaranteed for static send ports, such as the File adapter, or the FTP adapter.</span></span>
> 
> <span data-ttu-id="294b9-107">请考虑六个消息： M1、 M2、 M3、 M4、 M5，和 M6。</span><span class="sxs-lookup"><span data-stu-id="294b9-107">Consider six messages: M1, M2, M3, M4, M5, and M6.</span></span> <span data-ttu-id="294b9-108">M1、 M3、 M5 的用途是提供文件位置。</span><span class="sxs-lookup"><span data-stu-id="294b9-108">M1, M3, M5 are meant for a file location.</span></span> <span data-ttu-id="294b9-109">M2、 M4 和 M6 用于 FTP。</span><span class="sxs-lookup"><span data-stu-id="294b9-109">M2, M4, and M6 are meant for FTP.</span></span> <span data-ttu-id="294b9-110">有序的传递动态发送端口可确保，排序 M1、 M3，而 M5;和 M2、 M4 和 M6 分别进行排序。</span><span class="sxs-lookup"><span data-stu-id="294b9-110">The ordered delivery dynamic send port makes sure that M1, M3, and M5 are ordered; and M2, M4, and M6 are ordered respectively.</span></span> 
> 
> <span data-ttu-id="294b9-111">对于不支持有序的传递这些适配器类型，不存在可用于配置任何动态发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="294b9-111">For those adapter types that don't support ordered delivery, there aren't any dynamic send port properties available to configure.</span></span> <span data-ttu-id="294b9-112">在运行时自动确定其传输选项。</span><span class="sxs-lookup"><span data-stu-id="294b9-112">Their transport options are automatically determined at run time.</span></span>  
>
> <span data-ttu-id="294b9-113">**对于以前的 BizTalk 版本**使用动态端口，没有可用于配置，因为在运行时自动确定的传输选项的任何属性。</span><span class="sxs-lookup"><span data-stu-id="294b9-113">**For previous BizTalk versions** that use dynamic ports, there aren't any properties available to configure because the transport options are automatically determined at run time.</span></span>

  
## <a name="prerequisites"></a><span data-ttu-id="294b9-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="294b9-114">Prerequisites</span></span>  
 <span data-ttu-id="294b9-115">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="294b9-115">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="294b9-116">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="294b9-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="controlling-send-port-priority"></a><span data-ttu-id="294b9-117">控制发送端口优先级</span><span class="sxs-lookup"><span data-stu-id="294b9-117">Controlling Send Port Priority</span></span>  
 <span data-ttu-id="294b9-118">“传输高级选项”的“优先级”设置控制从消息框中删除消息的顺序。</span><span class="sxs-lookup"><span data-stu-id="294b9-118">The Priority setting of the Transport Advanced Options controls the order in which messages are removed from the message box.</span></span> <span data-ttu-id="294b9-119">较高优先级的端口会比较低优先级的端口更早地得到处理，从而使较高优先级的端口比单一主机内的其他发送端口更为重要。</span><span class="sxs-lookup"><span data-stu-id="294b9-119">Ports with a higher priority will be processed earlier than ports with a lower priority making the higher priority ports more important relative to other send ports within a single host.</span></span>  
  
 <span data-ttu-id="294b9-120">当某些类型的请求要求响应时间较短时，优先级很有用。</span><span class="sxs-lookup"><span data-stu-id="294b9-120">Priority is useful in scenarios requiring low response times for certain types of requests.</span></span> <span data-ttu-id="294b9-121">例如，有多个发送端口连接到不同的系统，用于处理正常请求和交互式请求。</span><span class="sxs-lookup"><span data-stu-id="294b9-121">For example, if there are multiple send ports that connect to different systems for processing normal requests and interactive requests.</span></span> <span data-ttu-id="294b9-122">交互式请求要求响应时间短，因此，在提交交互式请求时，需确保尽快对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="294b9-122">The interactive requests require a low response time, so when an interactive request is submitted, you want to ensure it is processed as soon as possible.</span></span>  
  
 <span data-ttu-id="294b9-123">BizTalk Server 在处理 MessageBox 中具有不同优先级的消息时，不会公平对待各个消息。</span><span class="sxs-lookup"><span data-stu-id="294b9-123">BizTalk Server does not attempt to be fair in the processing of messages with different priorities in the message box.</span></span> <span data-ttu-id="294b9-124">如果处理开始时 MessageBox 中有数量相等但优先级不同的两种项目，则只有在处理完所有高优先级的项目后，才会处理较低优先级的项目。</span><span class="sxs-lookup"><span data-stu-id="294b9-124">If there are equal numbers of items with two different priorities in the message box when processing begins, the lower priority items will be processed only after all high priority items have been processed.</span></span> <span data-ttu-id="294b9-125">如果高优先级的项目数量巨大，则有可能永远也不会处理较低优先级的项目。</span><span class="sxs-lookup"><span data-stu-id="294b9-125">If the volume of high priority items is great, it is possible that items with a lower priority will never be processed.</span></span> <span data-ttu-id="294b9-126">换句话说，较低优先级的项目将会遇到资源不足的情况。</span><span class="sxs-lookup"><span data-stu-id="294b9-126">In other words, the lower priority items will experience starvation.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="294b9-127">为了尽量降低消息资源不足的危险，应在实际负载下彻底测试应用程序，以确保可以处理所有消息。</span><span class="sxs-lookup"><span data-stu-id="294b9-127">To minimize the risk of message starvation, thoroughly test your application under realistic loads to ensure all messages are processed.</span></span> <span data-ttu-id="294b9-128">如果不对解决方案进行测试，则有可能出现消息得不到处理的情况。</span><span class="sxs-lookup"><span data-stu-id="294b9-128">Failure to test your solution may result in unprocessed messages.</span></span>  
  
 <span data-ttu-id="294b9-129">BizTalk Server 会在内部为每个订阅分配一个优先级。</span><span class="sxs-lookup"><span data-stu-id="294b9-129">Internally, BizTalk Server assigns a priority to every subscription.</span></span> <span data-ttu-id="294b9-130">优先级可以是从 1（最高优先级）到 10（最低优先级）的任意数字。</span><span class="sxs-lookup"><span data-stu-id="294b9-130">Priority can be any number from 1 (highest priority) to 10 (lowest priority).</span></span> <span data-ttu-id="294b9-131">由于激活订阅的默认优先级为 7，而相关订阅的默认优先级为 5，因此，相关消息会比激活订阅更先传送。</span><span class="sxs-lookup"><span data-stu-id="294b9-131">Because the default priority is 7 for activating subscriptions and 5 for correlating subscriptions, correlating messages will be delivered earlier than activating subscriptions.</span></span>  
  
## <a name="configure-the-transport-options"></a><span data-ttu-id="294b9-132">配置传输选项</span><span class="sxs-lookup"><span data-stu-id="294b9-132">Configure the transport options</span></span> 
  
1.  <span data-ttu-id="294b9-133">打开 **“BizTalk Server 管理”**。</span><span class="sxs-lookup"><span data-stu-id="294b9-133">Open **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="294b9-134">展开 BizTalk 组，然后展开你的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="294b9-134">Expand the BizTalk group, and then expand your BizTalk application.</span></span>  
  
3.  <span data-ttu-id="294b9-135">选择**发送端口**，右键单击要配置，，然后选择的发送端口**属性**。</span><span class="sxs-lookup"><span data-stu-id="294b9-135">Select **Send Ports**, right-click the send port to configure, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="294b9-136">在左窗格中，选择**传输高级选项**。</span><span class="sxs-lookup"><span data-stu-id="294b9-136">In the left pane, select **Transport Advanced Options**.</span></span>  
  
5.  <span data-ttu-id="294b9-137">下表中所述配置的传输选项，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="294b9-137">Configure the transport options as described in the following table, and then select **OK**.</span></span>  <span data-ttu-id="294b9-138">以下属性中仅有一些才可用于动态发送端口。</span><span class="sxs-lookup"><span data-stu-id="294b9-138">Only some of the following properties are available for dynamic send ports.</span></span>
  
    |<span data-ttu-id="294b9-139">使用此选项</span><span class="sxs-lookup"><span data-stu-id="294b9-139">Use this</span></span>|<span data-ttu-id="294b9-140">执行的操作</span><span class="sxs-lookup"><span data-stu-id="294b9-140">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="294b9-141">**重试计数**</span><span class="sxs-lookup"><span data-stu-id="294b9-141">**Retry count**</span></span>|<span data-ttu-id="294b9-142">指定在消息失败时发送端口重发消息的次数。</span><span class="sxs-lookup"><span data-stu-id="294b9-142">Specify the number of times for the send port to resend a message on message failure.</span></span> <span data-ttu-id="294b9-143">默认值为 3;允许的范围是从 0 到 1000。</span><span class="sxs-lookup"><span data-stu-id="294b9-143">The default is 3; the allowed range is from 0 through 1,000.</span></span>|  
    |<span data-ttu-id="294b9-144">**重试间隔**</span><span class="sxs-lookup"><span data-stu-id="294b9-144">**Retry interval**</span></span>|<span data-ttu-id="294b9-145">指定两次重发消息尝试之间的时间间隔（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="294b9-145">Specify the interval in minutes between message resend attempts.</span></span> <span data-ttu-id="294b9-146">默认值为 5;允许的范围是从 0 到 525600。</span><span class="sxs-lookup"><span data-stu-id="294b9-146">The default is 5; the allowed range is from 0 through 525,600.</span></span>|  
    |<span data-ttu-id="294b9-147">**Priority**</span><span class="sxs-lookup"><span data-stu-id="294b9-147">**Priority**</span></span>|<span data-ttu-id="294b9-148">设置重发尝试的优先级。</span><span class="sxs-lookup"><span data-stu-id="294b9-148">Set the priority of the resend attempt.</span></span>|  
    |<span data-ttu-id="294b9-149">**有序的传递**</span><span class="sxs-lookup"><span data-stu-id="294b9-149">**Ordered delivery**</span></span>|<span data-ttu-id="294b9-150">选中此复选框将按接收顺序发送消息。</span><span class="sxs-lookup"><span data-stu-id="294b9-150">Select this check box to send messages in order of receipt.</span></span>|  
    |<span data-ttu-id="294b9-151">**停止当前消息失败发送后续消息**</span><span class="sxs-lookup"><span data-stu-id="294b9-151">**Stop sending subsequent messages on current message failure**</span></span>|<span data-ttu-id="294b9-152">选中此复选框将停止发送失败消息后面的消息。</span><span class="sxs-lookup"><span data-stu-id="294b9-152">Select this check box to stop sending subsequent messages that follow a failed message.</span></span> <span data-ttu-id="294b9-153">此选项是时才可用**有序传送**选项。</span><span class="sxs-lookup"><span data-stu-id="294b9-153">This option is available only when the **Ordered delivery** option is selected.</span></span>|  
    |<span data-ttu-id="294b9-154">**启用路由失败消息**</span><span class="sxs-lookup"><span data-stu-id="294b9-154">**Enable routing for failed messages**</span></span>|<span data-ttu-id="294b9-155">选中此选项将为失败消息启用路由功能。</span><span class="sxs-lookup"><span data-stu-id="294b9-155">Select this option to enable routing for failed messages.</span></span>|  
    |<span data-ttu-id="294b9-156">**启用服务时段**</span><span class="sxs-lookup"><span data-stu-id="294b9-156">**Enable service window**</span></span>|<span data-ttu-id="294b9-157">选中此选项并指定开始时间和停止时间，即可指定发送端口每天运行的时间段。</span><span class="sxs-lookup"><span data-stu-id="294b9-157">Select this option to specify the time period each day during which the send port will be operational by specifying a start time and stop time.</span></span>|  
    |<span data-ttu-id="294b9-158">**开始时间**</span><span class="sxs-lookup"><span data-stu-id="294b9-158">**Start time**</span></span>|<span data-ttu-id="294b9-159">指定发送端口每天开始发送消息的时间。</span><span class="sxs-lookup"><span data-stu-id="294b9-159">Specify the time each day at which the send port starts sending messages.</span></span> <span data-ttu-id="294b9-160">此选项是时才可用**启用服务窗口**选项。</span><span class="sxs-lookup"><span data-stu-id="294b9-160">This option is available only when the **Enable service window** option is selected.</span></span>|  
    |<span data-ttu-id="294b9-161">**停止时间**</span><span class="sxs-lookup"><span data-stu-id="294b9-161">**Stop time**</span></span>|<span data-ttu-id="294b9-162">指定发送端口每天停止发送消息的时间。</span><span class="sxs-lookup"><span data-stu-id="294b9-162">Specify the time each day at which the send port stops sending messages.</span></span> <span data-ttu-id="294b9-163">此选项是时才可用**启用服务窗口**选项。</span><span class="sxs-lookup"><span data-stu-id="294b9-163">This option is available only when the **Enable service window** option is selected.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="294b9-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="294b9-164">See Also</span></span>  
[<span data-ttu-id="294b9-165">消息按序送达</span><span class="sxs-lookup"><span data-stu-id="294b9-165">Ordered Delivery of Messages</span></span>](../core/ordered-delivery-of-messages.md)  
 [<span data-ttu-id="294b9-166">创建和配置发送端口</span><span class="sxs-lookup"><span data-stu-id="294b9-166">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)