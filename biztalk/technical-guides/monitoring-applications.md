---
title: 监视应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4be98ba2-6acd-4dee-b6ea-db71bbd368f0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67c937ae0edb1698991ad111622a582ebfc64d76
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008974"
---
# <a name="monitoring-applications"></a><span data-ttu-id="f1eaa-102">监视应用程序</span><span class="sxs-lookup"><span data-stu-id="f1eaa-102">Monitoring Applications</span></span>
<span data-ttu-id="f1eaa-103">设置 Microsoft System Center Operations Manager 来监视 BizTalk 应用程序通常可以分为渐进式四个步骤，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f1eaa-103">Setting up Microsoft System Center Operations Manager to monitor BizTalk applications typically can be broken down into a progressive four-step process as follows:</span></span>  
  
1.  <span data-ttu-id="f1eaa-104">**修改现有规则和/或复制到自定义管理包以监视自定义的 BizTalk 应用程序的规则**</span><span class="sxs-lookup"><span data-stu-id="f1eaa-104">**Modify existing rules and/or copy rules to a custom management pack to monitor a custom BizTalk application**</span></span>  
  
     <span data-ttu-id="f1eaa-105">你需要将许多这些规则复制多次。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-105">You will need to copy many of these rules multiple times.</span></span> <span data-ttu-id="f1eaa-106">如果监视大量的文件共享，例如，这是这种情况。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-106">This is the case if you are monitoring a number of file shares, for example.</span></span> <span data-ttu-id="f1eaa-107">在此方案中，将在说明字段中添加上的文件共享地址复制一次每个文件共享的基本规则**条件**规则选项卡。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-107">In this scenario, you would copy the base rule once for each file share with the file share address added in the description field on the **Criteria** tab of the rule.</span></span> <span data-ttu-id="f1eaa-108">通过添加地址，Operations Manager 将引发警报的每个单独的文件共享。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-108">By adding the address, Operations Manager will raise an alert for each individual file share.</span></span> <span data-ttu-id="f1eaa-109">复制现有规则时，确保选择**启用**规则禁用重写此规则，或者你将收到重复的警报。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-109">When you copy an existing rule, ensure that you select **Enable** rule-disable overrides for this rule or you will receive duplicate alerts.</span></span>  
  
     <span data-ttu-id="f1eaa-110">你应该添加到每个规则，你创建的另一项位于知识库信息**知识库**选项卡的规则属性。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-110">Another item that you should add to each rule that you create is Knowledge information on the **Knowledge Base** tab of the rule property.</span></span> <span data-ttu-id="f1eaa-111">此数据会附加到 Operations Manager 会发出警报时，会引发通知。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-111">This data is attached to the notification that is raised when Operations Manager sends out an alert.</span></span> <span data-ttu-id="f1eaa-112">包括可帮助解决该错误的步骤时，此功能的电源就变得清楚。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-112">The power of this feature becomes clear when you include steps that may help resolve the error.</span></span>  
  
2.  <span data-ttu-id="f1eaa-113">**创建每个定义的规则的操作**</span><span class="sxs-lookup"><span data-stu-id="f1eaa-113">**Create actions for each defined rule**</span></span>  
  
     <span data-ttu-id="f1eaa-114">创建或复制规则实际上是过程的第一步。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-114">Creating or copying a rule is really the first step in the process.</span></span> <span data-ttu-id="f1eaa-115">下一步是采取某项措施基于该规则。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-115">The next step is to take some action based on that rule.</span></span> <span data-ttu-id="f1eaa-116">如果没有任何操作根据规则则实际上并不重要事件不断监视。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-116">If there is no action based on a rule then it doesn’t really matter that the event was ever monitored.</span></span> <span data-ttu-id="f1eaa-117">最常执行的操作是警报的运算符或出现错误的管理员。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-117">The action most frequently taken is to alert an operator or administrator that an error has occurred.</span></span> <span data-ttu-id="f1eaa-118">Operations Manager 还提供了多个触发事件时，可以使用其他操作。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-118">Operations Manager also provides a number of other actions that can be used when an event is triggered.</span></span> <span data-ttu-id="f1eaa-119">这些操作包括：</span><span class="sxs-lookup"><span data-stu-id="f1eaa-119">These actions include:</span></span>  
  
    -   <span data-ttu-id="f1eaa-120">启动脚本</span><span class="sxs-lookup"><span data-stu-id="f1eaa-120">Starting a script</span></span>  
  
    -   <span data-ttu-id="f1eaa-121">发送的简单网络管理协议 (SNMP) 陷阱 （在 SNMP 代理监视的网络和网络控制台工作站的报表中的各种设备中的活动）</span><span class="sxs-lookup"><span data-stu-id="f1eaa-121">Sending a Simple Network Management Protocol (SNMP) trap (in SNMP, agents monitor the activity in the various devices on the network and report to the network console workstation)</span></span>  
  
    -   <span data-ttu-id="f1eaa-122">向通知组发送通知</span><span class="sxs-lookup"><span data-stu-id="f1eaa-122">Sending a notification to a Notification group</span></span>  
  
    -   <span data-ttu-id="f1eaa-123">执行的命令或批处理文件</span><span class="sxs-lookup"><span data-stu-id="f1eaa-123">Executing a command or batch file</span></span>  
  
    -   <span data-ttu-id="f1eaa-124">更新状态变量</span><span class="sxs-lookup"><span data-stu-id="f1eaa-124">Updating a state variable</span></span>  
  
    -   <span data-ttu-id="f1eaa-125">将文件传输</span><span class="sxs-lookup"><span data-stu-id="f1eaa-125">Transferring a file</span></span>  
  
    -   <span data-ttu-id="f1eaa-126">在托管的代码程序集上调用的方法</span><span class="sxs-lookup"><span data-stu-id="f1eaa-126">Calling a method on a managed code assembly</span></span>  
  
3.  <span data-ttu-id="f1eaa-127">**创建迭代进程来自动执行手动任务**</span><span class="sxs-lookup"><span data-stu-id="f1eaa-127">**Create iterative processes to automate manual tasks**</span></span>  
  
     <span data-ttu-id="f1eaa-128">下一步是一个迭代过程，并将移动超出基本警报机制。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-128">The next step is an iterative process and moves beyond the basic alerting mechanism.</span></span> <span data-ttu-id="f1eaa-129">借助 Operations Manager 能够调用脚本和.NET 代码，自动执行基于引发的事件的手动任务的过程是一种功能强大和时间的保存功能。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-129">With Operations Manager able to invoke both script and .NET code, the process of automating manual tasks based on raised events is a powerful and time saving feature.</span></span> <span data-ttu-id="f1eaa-130">此示例是运行一个脚本来自动启动一个端口，如果记录已禁用 / 停止事件消息。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-130">An example of this is to run a script to automatically start a port if a disabled /stopped event message is logged.</span></span> <span data-ttu-id="f1eaa-131">由于可以自动执行的许多过程，此过程是迭代。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-131">This process is iterative since many processes can be automated.</span></span>  
  
4.  <span data-ttu-id="f1eaa-132">**阈值规则用于自动执行手动任务**</span><span class="sxs-lookup"><span data-stu-id="f1eaa-132">**Use threshold rules to automate manual tasks**</span></span>  
  
     <span data-ttu-id="f1eaa-133">处理的下一步是超越反应警报并可以使用阈值规则。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-133">The next step in processing is to move beyond the reactive alerting and use threshold rules.</span></span> <span data-ttu-id="f1eaa-134">默认情况下，BizTalk Server 管理包不包含任何阈值规则。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-134">The BizTalk Server Management Pack does not contain any threshold rules by default.</span></span> <span data-ttu-id="f1eaa-135">这是因为此类规则通常特定于自定义应用程序，并且对于每个应用程序都有所不同。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-135">This is because such rules are typically specific to the custom application and are different for every application.</span></span> <span data-ttu-id="f1eaa-136">阈值它包含有关自定义应用程序的业务规则，并提供一种监视系统的主动方法。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-136">A threshold embodies a business rule regarding the custom application and provides a proactive means of monitoring a system.</span></span> <span data-ttu-id="f1eaa-137">你可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供使用性能分析的日志 (PAL) 工具来定义规则的阈值模板。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-137">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] threshold templates provided with the Performance Analysis of Logs (PAL) tool to define rules.</span></span>  
  
     <span data-ttu-id="f1eaa-138">此类阈值规则的示例是度量值在服务器上的 Cpu 一致地运行时 75%以上指定的时间段。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-138">An example of such a threshold rule is to measure when the CPUs on a server consistently run above 75 percent for a specific time period.</span></span> <span data-ttu-id="f1eaa-139">这可能表明需要横向扩展系统。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-139">This could indicate that you need to scale out the system.</span></span> <span data-ttu-id="f1eaa-140">还有另一个示例是在其中创建监视一组唯一的计数器的阈值规则。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-140">Yet another example is where you create a threshold rule that monitors a unique set of counters.</span></span> <span data-ttu-id="f1eaa-141">然后，此规则就会调用代码以在需求较高的时间段期间初始化以前配置的备份服务器上的 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="f1eaa-141">This rule could then invoke code to initialize BizTalk host instances on a previously configured backup server during periods of high demand.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1eaa-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1eaa-142">See Also</span></span>  
 [<span data-ttu-id="f1eaa-143">使用 System Center Operations Manager 2007 监视 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f1eaa-143">Monitoring BizTalk Server with System Center Operations Manager 2007</span></span>](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)