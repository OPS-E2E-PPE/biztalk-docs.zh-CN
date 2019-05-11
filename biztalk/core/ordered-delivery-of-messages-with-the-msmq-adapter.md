---
title: 按序送达使用 MSMQ 适配器的消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, ordered delivery
- MSMQ adapters, ordered delivery
ms.assetid: e8dafc76-e894-4120-9cea-d014d635850e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54395febdadb62584d0a8d6422b9fd05ab3821d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322274"
---
# <a name="ordered-delivery-of-messages-with-the-msmq-adapter"></a><span data-ttu-id="3b4f8-102">按序送达消息使用 MSMQ 适配器</span><span class="sxs-lookup"><span data-stu-id="3b4f8-102">Ordered Delivery of Messages with the MSMQ Adapter</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="3b4f8-103">提供了**按序送达**选项适用于静态发送端口。</span><span class="sxs-lookup"><span data-stu-id="3b4f8-103">provides an **Ordered Delivery** option for static send ports.</span></span> <span data-ttu-id="3b4f8-104">设置**按序送达**上的发送端口选项**True**可确保 BizTalk Server 向发送端口在发布到 MessageBox 数据库的相同顺序传送消息。</span><span class="sxs-lookup"><span data-stu-id="3b4f8-104">Setting the **Ordered Delivery** option on a send port to **True** ensures that BizTalk Server delivers messages to the send port in the same order that they are published to the MessageBox database.</span></span> <span data-ttu-id="3b4f8-105">若要提供端到端按序的送达必须满足以下条件:</span><span class="sxs-lookup"><span data-stu-id="3b4f8-105">To provide end-to-end ordered delivery the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="3b4f8-106">必须与适配器提交给 BizTalk Server 时保留消息的顺序接收消息。</span><span class="sxs-lookup"><span data-stu-id="3b4f8-106">Messages must be received with an adapter that preserves the order of the messages when submitting them to BizTalk Server.</span></span>  
  
-   <span data-ttu-id="3b4f8-107">您必须订阅这些消息与发送端口都**按序送达**选项设为**True**。</span><span class="sxs-lookup"><span data-stu-id="3b4f8-107">You must subscribe to these messages with a send port that has the **Ordered Delivery** option to **True**.</span></span>  
  
-   <span data-ttu-id="3b4f8-108">如果业务流程来的处理消息，只能运行一个业务流程实例应使用，该业务流程应配置为使用顺序保护，并**按序送达**属性业务流程的接收端口应设置为 **，则返回 True**。</span><span class="sxs-lookup"><span data-stu-id="3b4f8-108">If an orchestration is used to process the messages, only a single instance of the orchestration should be used, the orchestration should be configured to use a sequential convoy, and the **Ordered Delivery** property of the orchestration's receive port should be set to **True**.</span></span>  
  
## <a name="using-the-msmq-adapter-for-ordered-delivery-of-messages"></a><span data-ttu-id="3b4f8-109">使用 MSMQ 适配器按序送达消息</span><span class="sxs-lookup"><span data-stu-id="3b4f8-109">Using the MSMQ Adapter for Ordered Delivery of Messages</span></span>  
 <span data-ttu-id="3b4f8-110">MSMQ 接收适配器提交给 BizTalk Server 中时保留消息的顺序提供支持。</span><span class="sxs-lookup"><span data-stu-id="3b4f8-110">The MSMQ receive adapter provides support for preserving the order of messages when submitting them to BizTalk Server.</span></span> <span data-ttu-id="3b4f8-111">端到端地按序送达消息通过 BizTalk Server 可以使用 MSMQ 适配器中如果通过使用配置的发送端口处理消息接收消息**按序送达**选项设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="3b4f8-111">End-to-end ordered delivery of messages through BizTalk Server can be achieved when receiving messages with the MSMQ adapter if the messages are processed by a send port that is configured with the **Ordered Delivery** option set to **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b4f8-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="3b4f8-112">See Also</span></span>  
 <span data-ttu-id="3b4f8-113">[按序送达消息](../core/ordered-delivery-of-messages.md) </span><span class="sxs-lookup"><span data-stu-id="3b4f8-113">[Ordered Delivery of Messages](../core/ordered-delivery-of-messages.md) </span></span>  
 [<span data-ttu-id="3b4f8-114">如何配置 MSMQ 接收位置</span><span class="sxs-lookup"><span data-stu-id="3b4f8-114">How to Configure an MSMQ Receive Location</span></span>](../core/how-to-configure-an-msmq-receive-location.md)