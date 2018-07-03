---
title: BizTalk 框架组装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Assembler
- BizTalk Framework Assembler [pipeline component]
ms.assetid: 116dff8d-b7f8-4564-a7fb-6440682683dc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50b1be8b898bc00e814bbb251682f2e2f474ade1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990246"
---
# <a name="biztalk-framework-assembler-pipeline-component"></a><span data-ttu-id="1f3cb-102">BizTalk 框架组装器管道组件</span><span class="sxs-lookup"><span data-stu-id="1f3cb-102">BizTalk Framework Assembler Pipeline Component</span></span>
<span data-ttu-id="1f3cb-103">BizTalk 框架是用于在使用网络传输协议(例如 HTTP 或 SMTP)时保证一次性传送即可送达的一种方法。</span><span class="sxs-lookup"><span data-stu-id="1f3cb-103">The BizTalk Framework is one approach for doing exactly-once guaranteed delivery using over-the-wire transport protocols such as HTTP or SMTP.</span></span> <span data-ttu-id="1f3cb-104">此框架自 1998 年起就已存在，并且可被视为基于 Web services（尤其是 WSReliable）的挂起标准计划的先驱。</span><span class="sxs-lookup"><span data-stu-id="1f3cb-104">This framework has existed since 1998, and can be thought of as a precursor to pending standards initiatives based on Web services, specifically WSReliable.</span></span> <span data-ttu-id="1f3cb-105">通常，保证一次性传送即可送达数据的问题已属于诸如消息队列（也称为 MSMQ）之类的技术领域。</span><span class="sxs-lookup"><span data-stu-id="1f3cb-105">Typically, the problem of guaranteed exactly-once delivery of data has been the domain of technologies like Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="1f3cb-106">不过，此类技术通常需要在数据流的两个终结点具有通用软件，并且不适用于使用基于公共网络的开放传输协议，例如使用 Internet 在企业边界间传输的数据。</span><span class="sxs-lookup"><span data-stu-id="1f3cb-106">However, such technologies usually require common software at the two endpoints of a data flow, and also do nothing to address the use of open transport protocols based on public networks, for example, data that flows across enterprise boundaries by using the Internet.</span></span>  
  
 <span data-ttu-id="1f3cb-107">BizTalk 框架将实施某些在早期尝试中所使用的相同机制，以解决保证一次性传送即可送达数据的问题，这一点并不奇怪。</span><span class="sxs-lookup"><span data-stu-id="1f3cb-107">Not surprisingly, the BizTalk Framework implements some of the same mechanisms present in earlier attempts to solve this problem of guaranteed exactly-once delivery of data.</span></span> <span data-ttu-id="1f3cb-108">对于该问题的其他解决方案的一个很好示例是电子数据交换 (EDI)，其中 ANSI X12 控制编号和标准 997 功能确认文档形成了保证只接收一次数据并将有关接收端的任何问题通知发件人的基础。</span><span class="sxs-lookup"><span data-stu-id="1f3cb-108">A good example of other solutions to the problem is electronic data interchange (EDI), where ANSI X12 control numbers and standard 997 functional acknowledgment documents form the basis of guaranteeing that data is received only one time, and that the sender is notified of any problems on the receiving end.</span></span>  
  
 <span data-ttu-id="1f3cb-109">BizTalk 框架假定无论系统交换数据的方式如何不同，这些系统都了解 BizTalk 框架协议的以下要求：</span><span class="sxs-lookup"><span data-stu-id="1f3cb-109">The BizTalk Framework assumes that, however disparate the systems trading data, they both understand the BizTalk Framework protocol requirements of:</span></span>  
  
- <span data-ttu-id="1f3cb-110">使用换行传输的可预测信封格式。</span><span class="sxs-lookup"><span data-stu-id="1f3cb-110">Using a predictable envelope format for wrapping transmissions.</span></span>  
  
- <span data-ttu-id="1f3cb-111">使用全局唯一标识符标记每个出站传输。</span><span class="sxs-lookup"><span data-stu-id="1f3cb-111">Tagging every outbound transmission with a globally unique identifier.</span></span>  
  
- <span data-ttu-id="1f3cb-112">即使对于已接收、已确认和已处理的数据，也始终向发件人返回包括全局唯一标识符的回执确认。</span><span class="sxs-lookup"><span data-stu-id="1f3cb-112">Always returning to the sender an acknowledgment of receipt that includes the globally unique identifier, even for data already received, acknowledged, and processed.</span></span>  
  
- <span data-ttu-id="1f3cb-113">在收到收件人的回执或达到传输变为无效前持续的时间段之前，发件人可通过某些方式重复传输。</span><span class="sxs-lookup"><span data-stu-id="1f3cb-113">Some means by which the sender can repeat transmission until either a receipt arrives from the receiver, or some time period passes beyond which the transmission is no longer valid.</span></span>  
  
  <span data-ttu-id="1f3cb-114">BizTalk 框架组装器管道组件负责在传输前将 BizTalk 框架信封和内容序列化为消息，并在分配的时段内回执未送达的情况下进行重新发送。</span><span class="sxs-lookup"><span data-stu-id="1f3cb-114">The BizTalk Framework Assembler pipeline component is responsible for serializing the BizTalk Framework envelope and contents onto the message before transmission and resending in the event that a receipt does not arrive in the allotted time period.</span></span> <span data-ttu-id="1f3cb-115">该组件还负责接收和处理回执，以及删除消息实例。</span><span class="sxs-lookup"><span data-stu-id="1f3cb-115">It is also responsible for receiving and processing the receipts and deleting the message instance.</span></span> <span data-ttu-id="1f3cb-116">（在 BizTalk 收到来自目标的确认回执之前，已发送消息的消息实例副本将保存在 MessageBox 数据库中。</span><span class="sxs-lookup"><span data-stu-id="1f3cb-116">(A copy of the message instance of the sent message is kept in the MessageBox database until BizTalk receives a confirmation receipt from the destination.</span></span> <span data-ttu-id="1f3cb-117">收到确认回执后，消息引擎将删除该消息实例。）</span><span class="sxs-lookup"><span data-stu-id="1f3cb-117">After the confirmation receipt is received, the message instance is deleted by the Messaging Engine.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f3cb-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f3cb-118">See Also</span></span>  
 <span data-ttu-id="1f3cb-119">[如何配置 BizTalk 框架组装器管道组件](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="1f3cb-119">[How to Configure the BizTalk Framework Assembler Pipeline Component](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="1f3cb-120">管道组件</span><span class="sxs-lookup"><span data-stu-id="1f3cb-120">Pipeline Components</span></span>](../core/pipeline-components.md)