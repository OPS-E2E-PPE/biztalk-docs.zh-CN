---
title: 使消息使用请求-答复关联 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, MQSeries adapters
- messages, correlating
- MQSeries adapters, correlating messages
ms.assetid: 4615b586-663b-41d8-949c-fefb6143c590
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2f13d8dea9192e982f597311ca3ea13fa213ed0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237989"
---
# <a name="correlating-messages-using-request-reply"></a><span data-ttu-id="4d52f-102">使消息使用请求-答复关联</span><span class="sxs-lookup"><span data-stu-id="4d52f-102">Correlating Messages Using Request-Reply</span></span>
<span data-ttu-id="4d52f-103">可通过两种方法使 IBM WebSphere MQ 的 BizTalk 业务流程中的消息相关，IBM WebSphere MQ 是 Windows 平台请求-答复方案的服务器组件。</span><span class="sxs-lookup"><span data-stu-id="4d52f-103">There are two ways to correlate messages in BizTalk orchestrations for IBM WebSphere MQ, server component for Windows platforms request-reply scenarios.</span></span> <span data-ttu-id="4d52f-104">第一种是通过设置这两个 MessageID 提供的相关标识符 (**MQMD_MSGID**) 和 CorrelationID (**MQMD_CorrelId**) 为相同的值。</span><span class="sxs-lookup"><span data-stu-id="4d52f-104">The first is to supply the correlation identifier by setting both the MessageID (**MQMD_MSGID**) and the CorrelationID (**MQMD_CorrelId**) to the same value.</span></span> <span data-ttu-id="4d52f-105">第二个是使用**BizTalk_CorrelationId**上下文属性。</span><span class="sxs-lookup"><span data-stu-id="4d52f-105">The second is to use the **BizTalk_CorrelationId** context property.</span></span>  
  
## <a name="setting-mqmdmsgid-and-mqmdcorrelid-to-the-same-value"></a><span data-ttu-id="4d52f-106">将 MQMD_MsgId 和 MQMD_CorrelId 设置为相同值</span><span class="sxs-lookup"><span data-stu-id="4d52f-106">Setting MQMD_MsgId and MQMD_CorrelId to the Same value</span></span>  
 <span data-ttu-id="4d52f-107">当发送消息到 IBM WebSphere MQ 队列管理器，您可以设置的消息标识符 (**MQMD_MSGID**) 的相关标识符和 (**MQMD_CorrelId**) 为传出消息中相同的值.</span><span class="sxs-lookup"><span data-stu-id="4d52f-107">When sending the message to an IBM WebSphere MQ Queue Manager, you can set the message identifier (**MQMD_MSGID**) and the correlation identifier (**MQMD_CorrelId**) to the same value in the outgoing message.</span></span> <span data-ttu-id="4d52f-108">IBM WebSphere MQ 队列管理器会将消息 ID 复制到答复消息的相关 ID。</span><span class="sxs-lookup"><span data-stu-id="4d52f-108">The IBM WebSphere MQ Queue Manager copies the MessageID to the CorrelationID for the reply message.</span></span> <span data-ttu-id="4d52f-109">下图显示进程。</span><span class="sxs-lookup"><span data-stu-id="4d52f-109">The following figure shows the process.</span></span>  
  
 <span data-ttu-id="4d52f-110">![简单关联](../core/media/bts-dev-mqsimplecorrelation.gif "BTS_Dev_MQSimpleCorrelation")</span><span class="sxs-lookup"><span data-stu-id="4d52f-110">![Simple Correlation](../core/media/bts-dev-mqsimplecorrelation.gif "BTS_Dev_MQSimpleCorrelation")</span></span>  
  
 <span data-ttu-id="4d52f-111">可以将其初始化为传出消息并遵循相关设置使用的值的传入消息的相关集**MQMD_CorrelId**。</span><span class="sxs-lookup"><span data-stu-id="4d52f-111">You can initialize the correlation sets for the outgoing message and follow the correlation sets for the incoming message using the value of **MQMD_CorrelId**.</span></span>  
  
## <a name="using-the-mqseriesbiztalkcorrelationid-context-property"></a><span data-ttu-id="4d52f-112">使用 MQSeries.BizTalk_CorrelationId 上下文属性</span><span class="sxs-lookup"><span data-stu-id="4d52f-112">Using the MQSeries.BizTalk_CorrelationId Context Property</span></span>  
 <span data-ttu-id="4d52f-113">而不是设置为相同的值在传出消息的 MessageID 和 CorrelationID，你可以使用**BizTalk_CorrelationID**上下文属性与请求-响应发送 MQSeries 适配器的端口。</span><span class="sxs-lookup"><span data-stu-id="4d52f-113">Instead of setting the MessageID and CorrelationID to the same value in the outgoing message, you can use the **BizTalk_CorrelationID** context property with a solicit-response send port of the MQSeries adapter.</span></span> <span data-ttu-id="4d52f-114">下图显示了这一过程：</span><span class="sxs-lookup"><span data-stu-id="4d52f-114">The following figure shows this process.</span></span>  
  
 <span data-ttu-id="4d52f-115">![使用请求作出 &#45;响应生成 CorrelationID](../core/media/bts-dev-mqgeneratedcorrelation.gif "BTS_Dev_MQGeneratedCorrelation")</span><span class="sxs-lookup"><span data-stu-id="4d52f-115">![Using Solicit&#45;Response to generate CorrelationID](../core/media/bts-dev-mqgeneratedcorrelation.gif "BTS_Dev_MQGeneratedCorrelation")</span></span>  
  
 <span data-ttu-id="4d52f-116">若要将 IBM WebSphere MQ 服务器提供的标识符用于 BizTalk 业务流程中的相关，则 BizTalk Server 必须先获得该标识符。</span><span class="sxs-lookup"><span data-stu-id="4d52f-116">To use identifiers provided by IBM WebSphere MQ Server for correlations in your BizTalk orchestration, BizTalk Server must first obtain the identifier.</span></span> <span data-ttu-id="4d52f-117">应用程序可通过要求-响应请求来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4d52f-117">Your application does this through a solicit-response request.</span></span> <span data-ttu-id="4d52f-118">通过使用 MQSeries 适配器，BizTalk Server 可向 IBM WebSphere MQ 服务器发送要求-响应请求。</span><span class="sxs-lookup"><span data-stu-id="4d52f-118">BizTalk Server sends a solicit-response request to the IBM WebSphere MQ Server by using the MQSeries adapter.</span></span> <span data-ttu-id="4d52f-119">反过来，接收到响应时使用的消息标识符 (**MQMD_MSGId**) 的相关标识符和 (**MQMD_CorrelId**)。</span><span class="sxs-lookup"><span data-stu-id="4d52f-119">In return, it receives a response with the message identifier (**MQMD_MSGId**) and the correlation identifier (**MQMD_CorrelId**).</span></span>  
  
 <span data-ttu-id="4d52f-120">请求-响应发送端口中的传出消息，该适配器将复制**MQMD_MSGID**由服务器生成的 IBM WebSphere MQ 到**MQSeries.BizTalk_CorrelationId**上下文属性。</span><span class="sxs-lookup"><span data-stu-id="4d52f-120">For the outgoing message in a solicit-response send port, the adapter copies the **MQMD_MSGID** generated by IBM WebSphere MQ Server to the **MQSeries.BizTalk_CorrelationId** context property.</span></span>  
  
 <span data-ttu-id="4d52f-121">如果将接收消息，该适配器将复制**MQMD_CorrelId**到**MQSeries.BizTalk_CorrelationId**。</span><span class="sxs-lookup"><span data-stu-id="4d52f-121">When receiving messages, the adapter copies the **MQMD_CorrelId** to the **MQSeries.BizTalk_CorrelationId**.</span></span> <span data-ttu-id="4d52f-122">在这种情况下，使用相关集，可以将其初始化为传出消息并遵循相关设置传入的消息使用的相关集**MQSeries.BizTalk_CorrelationId**。</span><span class="sxs-lookup"><span data-stu-id="4d52f-122">In this case, using correlation sets, you can initialize the correlation sets for the outgoing message and follow the correlation sets for the incoming message using the **MQSeries.BizTalk_CorrelationId**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d52f-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d52f-123">See Also</span></span>  
 [<span data-ttu-id="4d52f-124">MQSCorrelationSetOrchestrationWithSolicitResponse （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="4d52f-124">MQSCorrelationSetOrchestrationWithSolicitResponse (BizTalk Server Sample)</span></span>](../core/mqscorrelationsetorchestrationwithsolicitresponse-biztalk-server-sample.md)