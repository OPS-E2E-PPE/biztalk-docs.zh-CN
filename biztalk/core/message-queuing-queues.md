---
title: "消息队列的队列 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa8d2521a8cf434c7a0ea56f749f9df3f032551e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="message-queuing-queues"></a><span data-ttu-id="bbb9d-102">消息队列的队列</span><span class="sxs-lookup"><span data-stu-id="bbb9d-102">Message Queuing Queues</span></span>
<span data-ttu-id="bbb9d-103">本部分将介绍如何在使用 MSMQ 适配器时指定 Microsoft 消息队列（也称为 MSMQ）。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-103">This section describes how to specify Microsoft Message Queuing (also known as MSMQ) queues when you use the MSMQ adapter.</span></span> <span data-ttu-id="bbb9d-104">本部分对指定路径的约定进行了说明，并介绍了格式名称在将路径翻译成队列指定格式的过程中所起的作用。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-104">It describes the conventions for specifying paths and also describes the role that format names play in translating paths into queue designations.</span></span>  
  
## <a name="queue-path-naming-conventions"></a><span data-ttu-id="bbb9d-105">队列路径命名约定</span><span class="sxs-lookup"><span data-stu-id="bbb9d-105">Queue Path Naming Conventions</span></span>  
 <span data-ttu-id="bbb9d-106">如果队列名称引用路径，则将使用下表中的命名约定：</span><span class="sxs-lookup"><span data-stu-id="bbb9d-106">If the queue name refers to a path, use the naming conventions in the following table.</span></span>  
  
|<span data-ttu-id="bbb9d-107">**队列类型**</span><span class="sxs-lookup"><span data-stu-id="bbb9d-107">**Queue type**</span></span>|<span data-ttu-id="bbb9d-108">**路径的语法**</span><span class="sxs-lookup"><span data-stu-id="bbb9d-108">**Syntax for path**</span></span>|  
|--------------------|-------------------------|  
|<span data-ttu-id="bbb9d-109">公用队列</span><span class="sxs-lookup"><span data-stu-id="bbb9d-109">Public queue</span></span>|<span data-ttu-id="bbb9d-110">*Computername*\QueueName</span><span class="sxs-lookup"><span data-stu-id="bbb9d-110">*Computername*\QueueName</span></span>|  
|<span data-ttu-id="bbb9d-111">专用队列</span><span class="sxs-lookup"><span data-stu-id="bbb9d-111">Private queue</span></span>|<span data-ttu-id="bbb9d-112">*Computername*\Private$\QueueName</span><span class="sxs-lookup"><span data-stu-id="bbb9d-112">*Computername*\Private$\QueueName</span></span>|  
|<span data-ttu-id="bbb9d-113">日志队列</span><span class="sxs-lookup"><span data-stu-id="bbb9d-113">Journal queue</span></span>|<span data-ttu-id="bbb9d-114">*Computername*\QueueName\Journal$</span><span class="sxs-lookup"><span data-stu-id="bbb9d-114">*Computername*\QueueName\Journal$</span></span>|  
|<span data-ttu-id="bbb9d-115">计算机日记队列**注意：**用于仅接收队列。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-115">Computer journal queue **Note:**  Use for receive queue only.</span></span>|<span data-ttu-id="bbb9d-116">*Computername*\Journal$</span><span class="sxs-lookup"><span data-stu-id="bbb9d-116">*Computername*\Journal$</span></span>|  
|<span data-ttu-id="bbb9d-117">计算机死信队列**注意：**用于仅接收队列。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-117">Computer dead-letter queue **Note:**  Use for receive queue only.</span></span>|<span data-ttu-id="bbb9d-118">*Computername*\Deadletter$</span><span class="sxs-lookup"><span data-stu-id="bbb9d-118">*Computername*\Deadletter$</span></span>|  
|<span data-ttu-id="bbb9d-119">计算机事务性死信队列**注意：**用于仅接收队列。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-119">Computer transaction dead-letter queue **Note:**  Use for receive queue only.</span></span>|<span data-ttu-id="bbb9d-120">*Computername*\XactDeadletter$</span><span class="sxs-lookup"><span data-stu-id="bbb9d-120">*Computername*\XactDeadletter$</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="bbb9d-121">该队列路径必须唯一。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-121">The path of the queue must be unique.</span></span>  
  
 <span data-ttu-id="bbb9d-122">如果队列名称引用格式名称，则将采用字符串形式，以指示队列是公用队列还是专用队列，并在后面附加生成的队列 GUID 和其他标识符（根据需要）。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-122">If the queue name refers to a format name, it takes the form of a string that indicates whether a queue is public or private, followed by a generated GUID for the queue and other identifiers as needed.</span></span> <span data-ttu-id="bbb9d-123">请使用下表中的命名约定：</span><span class="sxs-lookup"><span data-stu-id="bbb9d-123">Use the naming conventions in the following table.</span></span>  
  
|<span data-ttu-id="bbb9d-124">**格式类型**</span><span class="sxs-lookup"><span data-stu-id="bbb9d-124">**Format type**</span></span>|<span data-ttu-id="bbb9d-125">**语法对格式名**</span><span class="sxs-lookup"><span data-stu-id="bbb9d-125">**Syntax for format name**</span></span>|  
|---------------------|--------------------------------|  
|<span data-ttu-id="bbb9d-126">公共</span><span class="sxs-lookup"><span data-stu-id="bbb9d-126">Public</span></span>|<span data-ttu-id="bbb9d-127">*通过 FormatName*： 公共 = QueueGUID</span><span class="sxs-lookup"><span data-stu-id="bbb9d-127">*FormatName*:Public=QueueGUID</span></span>|  
|<span data-ttu-id="bbb9d-128">直接</span><span class="sxs-lookup"><span data-stu-id="bbb9d-128">Direct</span></span>|<span data-ttu-id="bbb9d-129">*通过 FormatName*: DIRECT = SPX:NetworkNumber:HostNumber\QueueName</span><span class="sxs-lookup"><span data-stu-id="bbb9d-129">*FormatName*:DIRECT=SPX:NetworkNumber:HostNumber\QueueName</span></span><br /><br /> <span data-ttu-id="bbb9d-130">*通过 FormatName*: DIRECT = TCP:IPAddress\QueueName</span><span class="sxs-lookup"><span data-stu-id="bbb9d-130">*FormatName*: DIRECT=TCP:IPAddress\QueueName</span></span><br /><br /> <span data-ttu-id="bbb9d-131">*通过 FormatName*: DIRECT = OS:ComputerName\QueueName</span><span class="sxs-lookup"><span data-stu-id="bbb9d-131">*FormatName*: DIRECT=OS:ComputerName\QueueName</span></span>|  
  
 <span data-ttu-id="bbb9d-132">如果发送端口队列路径是分发列表，则该队列路径语法为：</span><span class="sxs-lookup"><span data-stu-id="bbb9d-132">If the send port queue path is a distribution list, then the queue path syntax is:</span></span>  
  
 <span data-ttu-id="bbb9d-133">DL=DistributionListGUID</span><span class="sxs-lookup"><span data-stu-id="bbb9d-133">DL=DistributionListGUID</span></span>  
  
 <span data-ttu-id="bbb9d-134">如果发送或接收队列路径是 HTTP 或 HTTPS URL，则语法为：</span><span class="sxs-lookup"><span data-stu-id="bbb9d-134">If the send or receive queue path is an HTTP or HTTPS URL, then the syntax is:</span></span>  
  
 <span data-ttu-id="bbb9d-135">FormatName:DIRECT = http: / /\<客户端名称\>/msmq/\<队列名称\></span><span class="sxs-lookup"><span data-stu-id="bbb9d-135">FormatName:DIRECT=http://\<client name\>/msmq/\<queue name\></span></span>  
  
 <span data-ttu-id="bbb9d-136">FormatName:DIRECT = https: / /\<客户端名称\>/msmq/\<队列名称\></span><span class="sxs-lookup"><span data-stu-id="bbb9d-136">FormatName:DIRECT=https://\<client name\>/msmq/\<queue name\></span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bbb9d-137">“msmq”是消息队列在 Internet 信息服务 (IIS) 中创建的虚拟文件夹。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-137">"msmq" is the virtual folder that Message Queuing creates in Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bbb9d-138">您只能使用 HTTP 发送消息。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-138">You can only use HTTP to send messages.</span></span> <span data-ttu-id="bbb9d-139">如果使用 HTTP 直接格式名称打开队列，则将无法读取远程计算机上的队列中的消息。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-139">You cannot read messages in a queue on a remote computer if the queue is opened using an HTTP direct format name.</span></span> <span data-ttu-id="bbb9d-140">但是，不使用 HTTP，仍可以通过使用专用或公用队列路径从远程队列接收 SOAP（格式化）消息。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-140">However, you can still receive SOAP (formatted) messages from a remote queue by using the private or public queue path without HTTP.</span></span>  
  
 <span data-ttu-id="bbb9d-141">如果队列名称引用管理员为队列指定的说明性文本标签，则引用此标签的队列路径的语法应为：</span><span class="sxs-lookup"><span data-stu-id="bbb9d-141">If the queue name refers to a descriptive text label that the administrator specified for the queue, then the syntax of the queue path referring to this label is:</span></span>  
  
 <span data-ttu-id="bbb9d-142">LABEL:MyQueue</span><span class="sxs-lookup"><span data-stu-id="bbb9d-142">LABEL:MyQueue</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bbb9d-143">标签并不总是唯一的。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-143">Labels are not always unique.</span></span> <span data-ttu-id="bbb9d-144">因此，如果在尝试使用某队列的标签连接到该队列时存在名称冲突，则会收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-144">Therefore, you will receive an error if a name conflict exists when you try to connect to a specific queue by using its label.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bbb9d-145">标签是适配器的必需传输字段。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-145">The label is a required transport field for the adapter.</span></span>  
  
## <a name="role-of-the-format-name"></a><span data-ttu-id="bbb9d-146">格式名称的作用</span><span class="sxs-lookup"><span data-stu-id="bbb9d-146">Role of the Format Name</span></span>  
 <span data-ttu-id="bbb9d-147">消息队列使用格式名称来标识队列和确定访问队列的方式。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-147">Message Queuing uses the format name to identify a queue and to determine how to access it.</span></span> <span data-ttu-id="bbb9d-148">消息队列可为队列分配格式名称。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-148">Message Queuing assigns the format name to the queue.</span></span>  
  
 <span data-ttu-id="bbb9d-149">在使用路径名称语法（例如 myMachine\myQueue）指定队列时，消息队列将查找该路径以找到关联的格式名称。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-149">When you specify a queue using the path name syntax, for example myMachine\myQueue, Message Queuing looks up the path to find the associated format name.</span></span> <span data-ttu-id="bbb9d-150">然后，消息队列将使用该格式名称访问相应的队列。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-150">Message Queuing then uses that format name to access the queue.</span></span> <span data-ttu-id="bbb9d-151">在指定格式名称时，消息队列将使用您所用的格式名称。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-151">When you specify the format name, Message Queuing uses the format name you use.</span></span>  
  
 <span data-ttu-id="bbb9d-152">有关格式名称的详细信息，请参阅 .NET Framework 类库帮助中的“MessageQueue.FormatName 属性”。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-152">For more information about format names, see "MessageQueue.FormatName Property" in .NET Framework Class Library Help.</span></span>  
  
## <a name="troubleshooting-queue-paths"></a><span data-ttu-id="bbb9d-153">队列路径疑难解答</span><span class="sxs-lookup"><span data-stu-id="bbb9d-153">Troubleshooting Queue Paths</span></span>  
  
-   <span data-ttu-id="bbb9d-154">如果提供的队列路径的语法与先前在“队列路径命名约定”中介绍的某种格式不匹配，则会出现异常。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-154">An exception occurs if the syntax of the provided queue path does not match one of the formats described earlier in "Queue Path Naming Conventions."</span></span>  
  
-   <span data-ttu-id="bbb9d-155">队列路径中的计算机名称不能使用以下字符：</span><span class="sxs-lookup"><span data-stu-id="bbb9d-155">The following are not valid characters for computer names in the queue path:</span></span>  
  
     <span data-ttu-id="bbb9d-156">\ ; , + "</span><span class="sxs-lookup"><span data-stu-id="bbb9d-156">\ ; , + "</span></span>  
  
     <span data-ttu-id="bbb9d-157">如果计算机名称为数字，则会出现异常。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-157">An exception occurs if the computer name is a number.</span></span> <span data-ttu-id="bbb9d-158">例如： 234\private$ \queue。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-158">For example: 234\private$\queue.</span></span>  
  
-   <span data-ttu-id="bbb9d-159">对于计算机死信队列、计算机日志队列以及计算机事务死信队列，如果用户将某个系统队列指定为发送的目标队列，则会出现异常。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-159">For a computer dead-letter queue, computer journal queue, and computer transaction dead-letter queue, an exception occurs if the user specifies any one of the system queues as the destination queue for send.</span></span>  
  
-   <span data-ttu-id="bbb9d-160">**System.Messaging.MessageQueue.Exists**并不适用于远程队列。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-160">**System.Messaging.MessageQueue.Exists** does not work for remote queues.</span></span> <span data-ttu-id="bbb9d-161">有关详细信息，请参阅 .NET Framework 类库帮助中的“MessageQueue.Exists 方法”。</span><span class="sxs-lookup"><span data-stu-id="bbb9d-161">For more information, see "MessageQueue.Exists Method" in .NET Framework Class Library Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbb9d-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bbb9d-162">See Also</span></span>  
 [<span data-ttu-id="bbb9d-163">配置 MSMQ 适配器</span><span class="sxs-lookup"><span data-stu-id="bbb9d-163">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)