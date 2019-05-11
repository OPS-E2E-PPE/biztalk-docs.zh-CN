---
title: 接收器接口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7ab77d4-705a-4b39-8c33-a7532ae6484c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 540da1fac24c69bd352a5fd0db9f2831f62f920f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398082"
---
# <a name="receiver-interfaces"></a><span data-ttu-id="56b5a-102">接收器接口</span><span class="sxs-lookup"><span data-stu-id="56b5a-102">Receiver Interfaces</span></span>
<span data-ttu-id="56b5a-103">除了标准适配器接口，接收适配器需要实现**IBTTransportConfig**。</span><span class="sxs-lookup"><span data-stu-id="56b5a-103">In addition to the standard adapter interfaces, receive adapters need to implement **IBTTransportConfig**.</span></span> <span data-ttu-id="56b5a-104">这是在其 BizTalk 消息引擎将接收位置配置适配器的接口。</span><span class="sxs-lookup"><span data-stu-id="56b5a-104">This is the interface on which the BizTalk Messaging Engine delivers receive location configuration to the adapter.</span></span>  
  
## <a name="request-response-adapters"></a><span data-ttu-id="56b5a-105">请求-响应适配器</span><span class="sxs-lookup"><span data-stu-id="56b5a-105">Request-Response Adapters</span></span>  
 <span data-ttu-id="56b5a-106">接收适配器可能还需要处理在某些情况下发送消息。</span><span class="sxs-lookup"><span data-stu-id="56b5a-106">Receive adapters may also need to handle send messages in some cases.</span></span> <span data-ttu-id="56b5a-107">执行此操作通常称为双向，或请求-响应适配器。</span><span class="sxs-lookup"><span data-stu-id="56b5a-107">Adapters that do this are usually referred to as two-way, or Request-Response adapters.</span></span> <span data-ttu-id="56b5a-108">若要能够发送消息，接收适配器需要实现**IBTTransmitter**。</span><span class="sxs-lookup"><span data-stu-id="56b5a-108">To be able to send messages, a receive adapter needs to implement **IBTTransmitter**.</span></span>  
  
 <span data-ttu-id="56b5a-109">下图显示了实现的接口接收适配器。</span><span class="sxs-lookup"><span data-stu-id="56b5a-109">The following figure shows the interfaces implemented by receive adapters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56b5a-110">**IBTBatchTransmitter**请求-响应适配器不支持接口。</span><span class="sxs-lookup"><span data-stu-id="56b5a-110">The **IBTBatchTransmitter** interface is not supported for Request-Response adapters.</span></span>  
  
 <span data-ttu-id="56b5a-111">![](../core/media/requestresponseadapters.gif "RequestResponseAdapters")</span><span class="sxs-lookup"><span data-stu-id="56b5a-111">![](../core/media/requestresponseadapters.gif "RequestResponseAdapters")</span></span>