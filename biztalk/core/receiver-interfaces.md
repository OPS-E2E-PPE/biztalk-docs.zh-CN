---
title: "接收方接口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7ab77d4-705a-4b39-8c33-a7532ae6484c
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77b42530d721a6dcee52e082fe46deae9ae06405
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receiver-interfaces"></a><span data-ttu-id="43e53-102">接收器接口</span><span class="sxs-lookup"><span data-stu-id="43e53-102">Receiver Interfaces</span></span>
<span data-ttu-id="43e53-103">除了标准适配器接口，接收适配器需要实现**IBTTransportConfig**。</span><span class="sxs-lookup"><span data-stu-id="43e53-103">In addition to the standard adapter interfaces, receive adapters need to implement **IBTTransportConfig**.</span></span> <span data-ttu-id="43e53-104">BizTalk 消息引擎在此接口上将接收位置配置传送给适配器。</span><span class="sxs-lookup"><span data-stu-id="43e53-104">This is the interface on which the BizTalk Messaging Engine delivers receive location configuration to the adapter.</span></span>  
  
## <a name="request-response-adapters"></a><span data-ttu-id="43e53-105">请求-响应适配器</span><span class="sxs-lookup"><span data-stu-id="43e53-105">Request-Response Adapters</span></span>  
 <span data-ttu-id="43e53-106">在某些情况下，接收适配器可能还需要处理发送消息。</span><span class="sxs-lookup"><span data-stu-id="43e53-106">Receive adapters may also need to handle send messages in some cases.</span></span> <span data-ttu-id="43e53-107">执行此操作的适配器通常称为双向适配器或请求-响应适配器。</span><span class="sxs-lookup"><span data-stu-id="43e53-107">Adapters that do this are usually referred to as two-way, or Request-Response adapters.</span></span> <span data-ttu-id="43e53-108">若要能够发送消息，接收适配器需要实现**IBTTransmitter**。</span><span class="sxs-lookup"><span data-stu-id="43e53-108">To be able to send messages, a receive adapter needs to implement **IBTTransmitter**.</span></span>  
  
 <span data-ttu-id="43e53-109">下图显示由实现的接口接收适配器。</span><span class="sxs-lookup"><span data-stu-id="43e53-109">The following figure shows the interfaces implemented by receive adapters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43e53-110">**IBTBatchTransmitter**请求-响应适配器不支持界面。</span><span class="sxs-lookup"><span data-stu-id="43e53-110">The **IBTBatchTransmitter** interface is not supported for Request-Response adapters.</span></span>  
  
 ![](../core/media/requestresponseadapters.gif "RequestResponseAdapters")