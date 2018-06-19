---
title: 与 MSMQ 适配器的消息的有序传送 |Microsoft 文档
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
ms.openlocfilehash: ac842fcd1e9b386fa885844f3a797504ed7c4c3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263581"
---
# <a name="ordered-delivery-of-messages-with-the-msmq-adapter"></a><span data-ttu-id="a1662-102">与 MSMQ 适配器的消息的有序传送</span><span class="sxs-lookup"><span data-stu-id="a1662-102">Ordered Delivery of Messages with the MSMQ Adapter</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a1662-103">提供**按序送达**选项适用于静态发送端口。</span><span class="sxs-lookup"><span data-stu-id="a1662-103"> provides an **Ordered Delivery** option for static send ports.</span></span> <span data-ttu-id="a1662-104">设置**按序送达**到发送端口上的选项**True**可确保 BizTalk 服务器将消息传送到发送端口与它们发布到 MessageBox 数据库相同的顺序。</span><span class="sxs-lookup"><span data-stu-id="a1662-104">Setting the **Ordered Delivery** option on a send port to **True** ensures that BizTalk Server delivers messages to the send port in the same order that they are published to the MessageBox database.</span></span> <span data-ttu-id="a1662-105">为提供端对端的按序送达功能，必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="a1662-105">To provide end-to-end ordered delivery the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="a1662-106">接收消息的适配器必须保持消息提交给 BizTalk Server 时的顺序。</span><span class="sxs-lookup"><span data-stu-id="a1662-106">Messages must be received with an adapter that preserves the order of the messages when submitting them to BizTalk Server.</span></span>  
  
-   <span data-ttu-id="a1662-107">您必须订阅拥有的发送端口与这些消息**按序送达**选项设为**True**。</span><span class="sxs-lookup"><span data-stu-id="a1662-107">You must subscribe to these messages with a send port that has the **Ordered Delivery** option to **True**.</span></span>  
  
-   <span data-ttu-id="a1662-108">如果业务流程用于的处理应使用的消息，仅业务流程的单个实例，应将业务流程配置为使用顺序保护和**按序送达**属性业务流程的接收端口应设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="a1662-108">If an orchestration is used to process the messages, only a single instance of the orchestration should be used, the orchestration should be configured to use a sequential convoy, and the **Ordered Delivery** property of the orchestration's receive port should be set to **True**.</span></span>  
  
## <a name="using-the-msmq-adapter-for-ordered-delivery-of-messages"></a><span data-ttu-id="a1662-109">为有序的消息传递使用 MSMQ 适配器</span><span class="sxs-lookup"><span data-stu-id="a1662-109">Using the MSMQ Adapter for Ordered Delivery of Messages</span></span>  
 <span data-ttu-id="a1662-110">MSMQ 接收适配器可以保持消息提交给 BizTalk Server 时的顺序。</span><span class="sxs-lookup"><span data-stu-id="a1662-110">The MSMQ receive adapter provides support for preserving the order of messages when submitting them to BizTalk Server.</span></span> <span data-ttu-id="a1662-111">端到端顺序接收消息使用 MSMQ 适配器，如果通过使用配置发送端口处理消息时可以获得的传递消息通过 BizTalk Server**按序送达**选项设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="a1662-111">End-to-end ordered delivery of messages through BizTalk Server can be achieved when receiving messages with the MSMQ adapter if the messages are processed by a send port that is configured with the **Ordered Delivery** option set to **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1662-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1662-112">See Also</span></span>  
 <span data-ttu-id="a1662-113">[有序的消息传送](../core/ordered-delivery-of-messages.md) </span><span class="sxs-lookup"><span data-stu-id="a1662-113">[Ordered Delivery of Messages](../core/ordered-delivery-of-messages.md) </span></span>  
 [<span data-ttu-id="a1662-114">如何配置 MSMQ 接收位置</span><span class="sxs-lookup"><span data-stu-id="a1662-114">How to Configure an MSMQ Receive Location</span></span>](../core/how-to-configure-an-msmq-receive-location.md)