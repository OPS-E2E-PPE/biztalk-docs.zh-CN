---
title: 消息队列队列 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [MSMQ adapters], queue paths
- naming conventions, MSMQ adapters
- configuring [MSMQ adapters], naming conventions
- messages, queuing
- MSMQ adapters, troubleshooting
- MSMQ adapters, message queues
- configuring [MSMQ adapters], troubleshooting
- troubleshooting, queue paths [MSMQ adapters]
- naming conventions, queue paths [MSMQ adapters]
- configuring [MSMQ adapters], message queues
ms.assetid: b802348e-8543-4b06-a6e4-149b86139fb1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2f5c2d4861a59ded7c19da84d0ca0e6ded9ddfe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394562"
---
# <a name="message-queuing-queues"></a><span data-ttu-id="04a30-102">消息队列队列</span><span class="sxs-lookup"><span data-stu-id="04a30-102">Message Queuing Queues</span></span>
<span data-ttu-id="04a30-103">本部分介绍如何使用 MSMQ 适配器时指定 Microsoft 消息队列 (也称为 MSMQ) 队列。</span><span class="sxs-lookup"><span data-stu-id="04a30-103">This section describes how to specify Microsoft Message Queuing (also known as MSMQ) queues when you use the MSMQ adapter.</span></span> <span data-ttu-id="04a30-104">它介绍了指定的路径的约定，并且还描述了格式中将路径翻译成队列指定名称发挥作用的角色。</span><span class="sxs-lookup"><span data-stu-id="04a30-104">It describes the conventions for specifying paths and also describes the role that format names play in translating paths into queue designations.</span></span>  
  
## <a name="queue-path-naming-conventions"></a><span data-ttu-id="04a30-105">队列路径命名约定</span><span class="sxs-lookup"><span data-stu-id="04a30-105">Queue Path Naming Conventions</span></span>  
 <span data-ttu-id="04a30-106">如果队列名称引用一个路径，使用下表中的命名约定。</span><span class="sxs-lookup"><span data-stu-id="04a30-106">If the queue name refers to a path, use the naming conventions in the following table.</span></span>  
  
|<span data-ttu-id="04a30-107">**队列类型**</span><span class="sxs-lookup"><span data-stu-id="04a30-107">**Queue type**</span></span>|<span data-ttu-id="04a30-108">**路径语法**</span><span class="sxs-lookup"><span data-stu-id="04a30-108">**Syntax for path**</span></span>|  
|--------------------|-------------------------|  
|<span data-ttu-id="04a30-109">公用队列</span><span class="sxs-lookup"><span data-stu-id="04a30-109">Public queue</span></span>|<span data-ttu-id="04a30-110">*Computername*\QueueName</span><span class="sxs-lookup"><span data-stu-id="04a30-110">*Computername*\QueueName</span></span>|  
|<span data-ttu-id="04a30-111">专用队列</span><span class="sxs-lookup"><span data-stu-id="04a30-111">Private queue</span></span>|<span data-ttu-id="04a30-112">*Computername*\Private$\QueueName</span><span class="sxs-lookup"><span data-stu-id="04a30-112">*Computername*\Private$\QueueName</span></span>|  
|<span data-ttu-id="04a30-113">日记队列</span><span class="sxs-lookup"><span data-stu-id="04a30-113">Journal queue</span></span>|<span data-ttu-id="04a30-114">*Computername*\QueueName\Journal$</span><span class="sxs-lookup"><span data-stu-id="04a30-114">*Computername*\QueueName\Journal$</span></span>|  
|<span data-ttu-id="04a30-115">计算机日志队列**注意：** 用于仅接收队列。</span><span class="sxs-lookup"><span data-stu-id="04a30-115">Computer journal queue **Note:**  Use for receive queue only.</span></span>|<span data-ttu-id="04a30-116">*Computername*\Journal$</span><span class="sxs-lookup"><span data-stu-id="04a30-116">*Computername*\Journal$</span></span>|  
|<span data-ttu-id="04a30-117">计算机死信队列**注意：** 用于仅接收队列。</span><span class="sxs-lookup"><span data-stu-id="04a30-117">Computer dead-letter queue **Note:**  Use for receive queue only.</span></span>|<span data-ttu-id="04a30-118">*Computername*\Deadletter$</span><span class="sxs-lookup"><span data-stu-id="04a30-118">*Computername*\Deadletter$</span></span>|  
|<span data-ttu-id="04a30-119">计算机事务死信队列**注意：** 用于仅接收队列。</span><span class="sxs-lookup"><span data-stu-id="04a30-119">Computer transaction dead-letter queue **Note:**  Use for receive queue only.</span></span>|<span data-ttu-id="04a30-120">*Computername*\XactDeadletter$</span><span class="sxs-lookup"><span data-stu-id="04a30-120">*Computername*\XactDeadletter$</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="04a30-121">队列路径必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="04a30-121">The path of the queue must be unique.</span></span>  
  
 <span data-ttu-id="04a30-122">如果队列名称引用格式名称，它将指示队列是否为公用或专用，根据需要和生成 GUID 对队列和其他标识符以字符串的形式。</span><span class="sxs-lookup"><span data-stu-id="04a30-122">If the queue name refers to a format name, it takes the form of a string that indicates whether a queue is public or private, followed by a generated GUID for the queue and other identifiers as needed.</span></span> <span data-ttu-id="04a30-123">下表中使用的命名约定。</span><span class="sxs-lookup"><span data-stu-id="04a30-123">Use the naming conventions in the following table.</span></span>  
  
|<span data-ttu-id="04a30-124">**格式类型**</span><span class="sxs-lookup"><span data-stu-id="04a30-124">**Format type**</span></span>|<span data-ttu-id="04a30-125">**格式名称的语法**</span><span class="sxs-lookup"><span data-stu-id="04a30-125">**Syntax for format name**</span></span>|  
|---------------------|--------------------------------|  
|<span data-ttu-id="04a30-126">公共</span><span class="sxs-lookup"><span data-stu-id="04a30-126">Public</span></span>|<span data-ttu-id="04a30-127">*FormatName*:Public=QueueGUID</span><span class="sxs-lookup"><span data-stu-id="04a30-127">*FormatName*:Public=QueueGUID</span></span>|  
|<span data-ttu-id="04a30-128">直接</span><span class="sxs-lookup"><span data-stu-id="04a30-128">Direct</span></span>|<span data-ttu-id="04a30-129">*FormatName*:DIRECT=SPX:NetworkNumber:HostNumber\QueueName</span><span class="sxs-lookup"><span data-stu-id="04a30-129">*FormatName*:DIRECT=SPX:NetworkNumber:HostNumber\QueueName</span></span><br /><br /> <span data-ttu-id="04a30-130">*格式名称*:DIRECT=TCP:IPAddress\QueueName</span><span class="sxs-lookup"><span data-stu-id="04a30-130">*FormatName*: DIRECT=TCP:IPAddress\QueueName</span></span><br /><br /> <span data-ttu-id="04a30-131">*格式名称*:DIRECT=OS:ComputerName\QueueName</span><span class="sxs-lookup"><span data-stu-id="04a30-131">*FormatName*: DIRECT=OS:ComputerName\QueueName</span></span>|  
  
 <span data-ttu-id="04a30-132">如果发送端口队列路径是通讯组列表，该队列路径语法是：</span><span class="sxs-lookup"><span data-stu-id="04a30-132">If the send port queue path is a distribution list, then the queue path syntax is:</span></span>  
  
 <span data-ttu-id="04a30-133">DL=DistributionListGUID</span><span class="sxs-lookup"><span data-stu-id="04a30-133">DL=DistributionListGUID</span></span>  
  
 <span data-ttu-id="04a30-134">如果发送或接收队列路径是 HTTP 或 HTTPS URL，则语法为：</span><span class="sxs-lookup"><span data-stu-id="04a30-134">If the send or receive queue path is an HTTP or HTTPS URL, then the syntax is:</span></span>  
  
 <span data-ttu-id="04a30-135">格式 = http: / /\<客户端名称\>/msmq/\<队列名称\></span><span class="sxs-lookup"><span data-stu-id="04a30-135">FormatName:DIRECT=http://\<client name\>/msmq/\<queue name\></span></span>  
  
 <span data-ttu-id="04a30-136">格式 = https: / /\<客户端名称\>/msmq/\<队列名称\></span><span class="sxs-lookup"><span data-stu-id="04a30-136">FormatName:DIRECT=https://\<client name\>/msmq/\<queue name\></span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04a30-137">"msmq"是消息队列创建 Internet 信息服务 (IIS) 中的虚拟文件夹。</span><span class="sxs-lookup"><span data-stu-id="04a30-137">"msmq" is the virtual folder that Message Queuing creates in Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04a30-138">您只能使用 HTTP 发送消息。</span><span class="sxs-lookup"><span data-stu-id="04a30-138">You can only use HTTP to send messages.</span></span> <span data-ttu-id="04a30-139">如果使用 HTTP 直接格式名称打开队列，无法读取远程计算机上的队列中的消息。</span><span class="sxs-lookup"><span data-stu-id="04a30-139">You cannot read messages in a queue on a remote computer if the queue is opened using an HTTP direct format name.</span></span> <span data-ttu-id="04a30-140">但是，您仍可以通过使用专用或公用队列的路径不使用 HTTP SOAP （格式化） 消息接收从远程队列。</span><span class="sxs-lookup"><span data-stu-id="04a30-140">However, you can still receive SOAP (formatted) messages from a remote queue by using the private or public queue path without HTTP.</span></span>  
  
 <span data-ttu-id="04a30-141">如果队列名称引用的描述性文本标签，为队列指定的管理员，则引用此标签的队列路径的语法是：</span><span class="sxs-lookup"><span data-stu-id="04a30-141">If the queue name refers to a descriptive text label that the administrator specified for the queue, then the syntax of the queue path referring to this label is:</span></span>  
  
 <span data-ttu-id="04a30-142">LABEL:MyQueue</span><span class="sxs-lookup"><span data-stu-id="04a30-142">LABEL:MyQueue</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04a30-143">标签并不总是唯一。</span><span class="sxs-lookup"><span data-stu-id="04a30-143">Labels are not always unique.</span></span> <span data-ttu-id="04a30-144">因此，如果存在名称冲突，当你尝试使用其标签连接到特定的队列时将收到错误。</span><span class="sxs-lookup"><span data-stu-id="04a30-144">Therefore, you will receive an error if a name conflict exists when you try to connect to a specific queue by using its label.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04a30-145">标签是适配器的必需的传输字段。</span><span class="sxs-lookup"><span data-stu-id="04a30-145">The label is a required transport field for the adapter.</span></span>  
  
## <a name="role-of-the-format-name"></a><span data-ttu-id="04a30-146">格式名称的角色</span><span class="sxs-lookup"><span data-stu-id="04a30-146">Role of the Format Name</span></span>  
 <span data-ttu-id="04a30-147">消息队列使用格式名称来标识队列并确定如何对其进行访问。</span><span class="sxs-lookup"><span data-stu-id="04a30-147">Message Queuing uses the format name to identify a queue and to determine how to access it.</span></span> <span data-ttu-id="04a30-148">消息队列到队列分配格式名称。</span><span class="sxs-lookup"><span data-stu-id="04a30-148">Message Queuing assigns the format name to the queue.</span></span>  
  
 <span data-ttu-id="04a30-149">当指定队列使用的路径名称语法时，例如 myMachine\myQueue，消息队列会查找用于查找关联的格式名称的路径。</span><span class="sxs-lookup"><span data-stu-id="04a30-149">When you specify a queue using the path name syntax, for example myMachine\myQueue, Message Queuing looks up the path to find the associated format name.</span></span> <span data-ttu-id="04a30-150">然后，消息队列使用该格式名称来访问队列。</span><span class="sxs-lookup"><span data-stu-id="04a30-150">Message Queuing then uses that format name to access the queue.</span></span> <span data-ttu-id="04a30-151">当指定的格式名称时，消息队列使用你使用的格式名称。</span><span class="sxs-lookup"><span data-stu-id="04a30-151">When you specify the format name, Message Queuing uses the format name you use.</span></span>  
  
 <span data-ttu-id="04a30-152">有关格式名称的详细信息，请参阅.NET Framework 类库帮助中的"MessageQueue.FormatName 属性"。</span><span class="sxs-lookup"><span data-stu-id="04a30-152">For more information about format names, see "MessageQueue.FormatName Property" in .NET Framework Class Library Help.</span></span>  
  
## <a name="troubleshooting-queue-paths"></a><span data-ttu-id="04a30-153">队列路径疑难解答</span><span class="sxs-lookup"><span data-stu-id="04a30-153">Troubleshooting Queue Paths</span></span>  
  
-   <span data-ttu-id="04a30-154">如果提供的队列路径的语法与在"队列路径命名约定。"的前面部分中所述的格式之一都不匹配，会发生异常</span><span class="sxs-lookup"><span data-stu-id="04a30-154">An exception occurs if the syntax of the provided queue path does not match one of the formats described earlier in "Queue Path Naming Conventions."</span></span>  
  
-   <span data-ttu-id="04a30-155">以下不是有效字符中的队列路径的计算机名称：</span><span class="sxs-lookup"><span data-stu-id="04a30-155">The following are not valid characters for computer names in the queue path:</span></span>  
  
     <span data-ttu-id="04a30-156">\ ; , + "</span><span class="sxs-lookup"><span data-stu-id="04a30-156">\ ; , + "</span></span>  
  
     <span data-ttu-id="04a30-157">如果计算机名称是一个数字，则会发生异常。</span><span class="sxs-lookup"><span data-stu-id="04a30-157">An exception occurs if the computer name is a number.</span></span> <span data-ttu-id="04a30-158">例如：234\private$ \queue。</span><span class="sxs-lookup"><span data-stu-id="04a30-158">For example: 234\private$\queue.</span></span>  
  
-   <span data-ttu-id="04a30-159">计算机死信队列、 计算机日志队列以及计算机事务死信队列，如果用户指定系统队列之一发送的目标队列，会发生异常。</span><span class="sxs-lookup"><span data-stu-id="04a30-159">For a computer dead-letter queue, computer journal queue, and computer transaction dead-letter queue, an exception occurs if the user specifies any one of the system queues as the destination queue for send.</span></span>  
  
-   <span data-ttu-id="04a30-160">**System.Messaging.MessageQueue.Exists**不适用于远程队列。</span><span class="sxs-lookup"><span data-stu-id="04a30-160">**System.Messaging.MessageQueue.Exists** does not work for remote queues.</span></span> <span data-ttu-id="04a30-161">有关详细信息，请参阅.NET Framework 类库帮助中的"MessageQueue.Exists 方法"。</span><span class="sxs-lookup"><span data-stu-id="04a30-161">For more information, see "MessageQueue.Exists Method" in .NET Framework Class Library Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04a30-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="04a30-162">See Also</span></span>  
 [<span data-ttu-id="04a30-163">配置 MSMQ 适配器</span><span class="sxs-lookup"><span data-stu-id="04a30-163">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)