---
title: "与 MQSeries 适配器的消息的有序传送 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, ordered delivery
- MQSeries adapters, ordered delivery
ms.assetid: 517ff2a4-7315-43b5-8d4b-7494adf141e4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f8b602adf93152f6af1e5dbbc576180d570a4ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="ordered-delivery-of-messages-with-the-mqseries-adapter"></a><span data-ttu-id="c88a7-102">使用 MQSeries 适配器按序送达消息</span><span class="sxs-lookup"><span data-stu-id="c88a7-102">Ordered Delivery of Messages with the MQSeries Adapter</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c88a7-103">提供**按序送达**选项适用于静态发送端口。</span><span class="sxs-lookup"><span data-stu-id="c88a7-103"> provides an **Ordered Delivery** option for static send ports.</span></span> <span data-ttu-id="c88a7-104">设置**按序送达**到发送端口上的选项**True**可确保 BizTalk 服务器将消息传送到发送端口与它们发布给 BizTalk MessageBox 数据库相同的顺序。</span><span class="sxs-lookup"><span data-stu-id="c88a7-104">Setting the **Ordered Delivery** option on a send port to **True** ensures that BizTalk Server delivers messages to the send port in the same order that they are published to the BizTalk MessageBox database.</span></span> <span data-ttu-id="c88a7-105">为提供端对端的按序送达功能，必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="c88a7-105">To provide end-to-end ordered delivery the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="c88a7-106">接收消息的适配器必须保持消息提交给 BizTalk Server 时的顺序。</span><span class="sxs-lookup"><span data-stu-id="c88a7-106">Messages must be received with an adapter that preserves the order of the messages when submitting them to BizTalk Server.</span></span> <span data-ttu-id="c88a7-107">例如，在与 MQSeries 接收适配器接收消息，接收位置应配置使用选项**停止使用的顺序**或**与挂起的顺序**。</span><span class="sxs-lookup"><span data-stu-id="c88a7-107">For example, when receiving messages with the MQSeries receive adapter, the receive location should be configured with the option **Order with Stop** or **Order with Suspend**.</span></span>  
  
-   <span data-ttu-id="c88a7-108">您必须订阅拥有的发送端口与这些消息**按序送达**选项设为**True**。</span><span class="sxs-lookup"><span data-stu-id="c88a7-108">You must subscribe to these messages with a send port that has the **Ordered Delivery** option to **True**.</span></span>  
  
-   <span data-ttu-id="c88a7-109">如果业务流程用于的处理应使用的消息，仅业务流程的单个实例，应将业务流程配置为使用顺序保护和**按序送达**属性业务流程的接收端口应设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="c88a7-109">If an orchestration is used to process the messages, only a single instance of the orchestration should be used, the orchestration should be configured to use a sequential convoy, and the **Ordered Delivery** property of the orchestration's receive port should be set to **True**.</span></span>  
  
## <a name="using-the-mqseries-adapter-for-ordered-delivery-of-messages"></a><span data-ttu-id="c88a7-110">使用适用于的消息有序传递 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="c88a7-110">Using the MQSeries Adapter for Ordered Delivery of Messages</span></span>  
 <span data-ttu-id="c88a7-111">MQSeries 接收适配器可以保持消息提交给 BizTalk Server 时的顺序。</span><span class="sxs-lookup"><span data-stu-id="c88a7-111">The MQSeries receive adapter provides support for preserving the order of messages when submitting them to BizTalk Server.</span></span> <span data-ttu-id="c88a7-112">端到端顺序接收消息使用 MQSeries 适配器，如果通过使用配置发送端口处理消息时可以获得的传递消息通过 BizTalk Server**按序送达**选项设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="c88a7-112">End-to-end ordered delivery of messages through BizTalk Server can be achieved when receiving messages with the MQSeries adapter if the messages are processed by a send port that is configured with the **Ordered Delivery** option set to **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c88a7-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c88a7-113">See Also</span></span>  
 <span data-ttu-id="c88a7-114">[有序的消息传送](../core/ordered-delivery-of-messages.md) </span><span class="sxs-lookup"><span data-stu-id="c88a7-114">[Ordered Delivery of Messages](../core/ordered-delivery-of-messages.md) </span></span>  
 [<span data-ttu-id="c88a7-115">如何配置 MQSeries 适配器接收位置和发送端口</span><span class="sxs-lookup"><span data-stu-id="c88a7-115">How to Configure MQSeries Adapter Receive Locations and Send Ports</span></span>](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)