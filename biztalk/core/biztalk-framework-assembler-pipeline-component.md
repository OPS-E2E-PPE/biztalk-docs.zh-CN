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
ms.openlocfilehash: 139d4bedbe8f42e9e7c97b2647b27d712697e8f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358073"
---
# <a name="biztalk-framework-assembler-pipeline-component"></a><span data-ttu-id="ba29f-102">BizTalk 框架组装器管道组件</span><span class="sxs-lookup"><span data-stu-id="ba29f-102">BizTalk Framework Assembler Pipeline Component</span></span>
<span data-ttu-id="ba29f-103">BizTalk 框架是一种方法进行完全的一次性传送即可使用线上传输协议，例如 HTTP 或 SMTP 送达。</span><span class="sxs-lookup"><span data-stu-id="ba29f-103">The BizTalk Framework is one approach for doing exactly-once guaranteed delivery using over-the-wire transport protocols such as HTTP or SMTP.</span></span> <span data-ttu-id="ba29f-104">此框架自 1998 年起，已存在，并且可以为 Web 服务，特别是 WSReliable 基础的视为挂起标准计划的前提。</span><span class="sxs-lookup"><span data-stu-id="ba29f-104">This framework has existed since 1998, and can be thought of as a precursor to pending standards initiatives based on Web services, specifically WSReliable.</span></span> <span data-ttu-id="ba29f-105">通常情况下，这一问题完全保证的传递的数据后的技术，如消息队列 (也称为 MSMQ) 的域。</span><span class="sxs-lookup"><span data-stu-id="ba29f-105">Typically, the problem of guaranteed exactly-once delivery of data has been the domain of technologies like Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="ba29f-106">但是，此类技术通常需要在数据流中，两个终结点的常见软件，并且还不到地址使用的开放传输协议执行基于公共网络，例如，通过使用在企业边界之间流动的数据Internet。</span><span class="sxs-lookup"><span data-stu-id="ba29f-106">However, such technologies usually require common software at the two endpoints of a data flow, and also do nothing to address the use of open transport protocols based on public networks, for example, data that flows across enterprise boundaries by using the Internet.</span></span>  
  
 <span data-ttu-id="ba29f-107">毫无疑问，BizTalk 框架将实施某些在早期尝试解决这一问题中的相同机制保证的一次性传送即可送达数据。</span><span class="sxs-lookup"><span data-stu-id="ba29f-107">Not surprisingly, the BizTalk Framework implements some of the same mechanisms present in earlier attempts to solve this problem of guaranteed exactly-once delivery of data.</span></span> <span data-ttu-id="ba29f-108">其他解决方案的问题的一个典型示例是电子数据交换 (EDI)，其中 ANSI X12 控制编号和标准 997 功能确认文档形成保证的基础数据只接收一次，而且发件人是收到通知的接收端上的任何问题。</span><span class="sxs-lookup"><span data-stu-id="ba29f-108">A good example of other solutions to the problem is electronic data interchange (EDI), where ANSI X12 control numbers and standard 997 functional acknowledgment documents form the basis of guaranteeing that data is received only one time, and that the sender is notified of any problems on the receiving end.</span></span>  
  
 <span data-ttu-id="ba29f-109">BizTalk 框架假定，但是不同贸易数据的系统，它们都了解 BizTalk 框架协议的以下要求：</span><span class="sxs-lookup"><span data-stu-id="ba29f-109">The BizTalk Framework assumes that, however disparate the systems trading data, they both understand the BizTalk Framework protocol requirements of:</span></span>  
  
- <span data-ttu-id="ba29f-110">换行传输使用的可预测信封格式。</span><span class="sxs-lookup"><span data-stu-id="ba29f-110">Using a predictable envelope format for wrapping transmissions.</span></span>  
  
- <span data-ttu-id="ba29f-111">标记具有全局唯一标识符的每个出站传输。</span><span class="sxs-lookup"><span data-stu-id="ba29f-111">Tagging every outbound transmission with a globally unique identifier.</span></span>  
  
- <span data-ttu-id="ba29f-112">始终返回到发件人的收据，其中包含的全局唯一标识符，即使对于数据已确认接收、 已确认和处理。</span><span class="sxs-lookup"><span data-stu-id="ba29f-112">Always returning to the sender an acknowledgment of receipt that includes the globally unique identifier, even for data already received, acknowledged, and processed.</span></span>  
  
- <span data-ttu-id="ba29f-113">一些方法，依据发件人可以重复的传输直到接收来自接收方，或持续的时间段超过该传输将不再有效。</span><span class="sxs-lookup"><span data-stu-id="ba29f-113">Some means by which the sender can repeat transmission until either a receipt arrives from the receiver, or some time period passes beyond which the transmission is no longer valid.</span></span>  
  
  <span data-ttu-id="ba29f-114">BizTalk 框架组装器管道组件负责在传输和重新发送的情况中分配的时间段内回执未送达之前序列化 BizTalk 框架信封和消息内容。</span><span class="sxs-lookup"><span data-stu-id="ba29f-114">The BizTalk Framework Assembler pipeline component is responsible for serializing the BizTalk Framework envelope and contents onto the message before transmission and resending in the event that a receipt does not arrive in the allotted time period.</span></span> <span data-ttu-id="ba29f-115">它是还负责接收和处理回执并删除消息实例。</span><span class="sxs-lookup"><span data-stu-id="ba29f-115">It is also responsible for receiving and processing the receipts and deleting the message instance.</span></span> <span data-ttu-id="ba29f-116">（已发送消息的消息实例的副本保留在 MessageBox 数据库中直到 BizTalk 收到来自目标的确认回执。</span><span class="sxs-lookup"><span data-stu-id="ba29f-116">(A copy of the message instance of the sent message is kept in the MessageBox database until BizTalk receives a confirmation receipt from the destination.</span></span> <span data-ttu-id="ba29f-117">收到的确认回执后，消息实例会删除由消息引擎。）</span><span class="sxs-lookup"><span data-stu-id="ba29f-117">After the confirmation receipt is received, the message instance is deleted by the Messaging Engine.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba29f-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba29f-118">See Also</span></span>  
 <span data-ttu-id="ba29f-119">[如何配置 BizTalk 框架组装器管道组件](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="ba29f-119">[How to Configure the BizTalk Framework Assembler Pipeline Component](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="ba29f-120">管道组件</span><span class="sxs-lookup"><span data-stu-id="ba29f-120">Pipeline Components</span></span>](../core/pipeline-components.md)