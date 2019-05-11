---
title: 将使用请求-答复消息相关联 |Microsoft Docs
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
ms.openlocfilehash: 91790a879816efa7b2bfa7a5a16f4ea1dfbb13a2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390207"
---
# <a name="correlating-messages-using-request-reply"></a><span data-ttu-id="d9af7-102">使用请求-答复相关消息</span><span class="sxs-lookup"><span data-stu-id="d9af7-102">Correlating Messages Using Request-Reply</span></span>
<span data-ttu-id="d9af7-103">有两种方法来将 IBM WebSphere MQ，Windows 平台请求-答复方案的服务器组件的 BizTalk 业务流程中的消息关联。</span><span class="sxs-lookup"><span data-stu-id="d9af7-103">There are two ways to correlate messages in BizTalk orchestrations for IBM WebSphere MQ, server component for Windows platforms request-reply scenarios.</span></span> <span data-ttu-id="d9af7-104">第一种是通过设置将消息 Id 提供相关标识符 (**MQMD_MSGID**) 和相关 Id (**MQMD_CorrelId**) 到相同的值。</span><span class="sxs-lookup"><span data-stu-id="d9af7-104">The first is to supply the correlation identifier by setting both the MessageID (**MQMD_MSGID**) and the CorrelationID (**MQMD_CorrelId**) to the same value.</span></span> <span data-ttu-id="d9af7-105">第二个是使用**BizTalk_CorrelationId**上下文属性。</span><span class="sxs-lookup"><span data-stu-id="d9af7-105">The second is to use the **BizTalk_CorrelationId** context property.</span></span>  
  
## <a name="setting-mqmdmsgid-and-mqmdcorrelid-to-the-same-value"></a><span data-ttu-id="d9af7-106">将 MQMD_MsgId 和 MQMD_CorrelId 设置为相同的值</span><span class="sxs-lookup"><span data-stu-id="d9af7-106">Setting MQMD_MsgId and MQMD_CorrelId to the Same value</span></span>  
 <span data-ttu-id="d9af7-107">将消息发送到 IBM WebSphere MQ 队列管理器，您可以设置消息标识符 (**MQMD_MSGID**) 和相关标识符 (**MQMD_CorrelId**) 为传出消息中相同的值.</span><span class="sxs-lookup"><span data-stu-id="d9af7-107">When sending the message to an IBM WebSphere MQ Queue Manager, you can set the message identifier (**MQMD_MSGID**) and the correlation identifier (**MQMD_CorrelId**) to the same value in the outgoing message.</span></span> <span data-ttu-id="d9af7-108">IBM WebSphere MQ 队列管理器将消息 Id 复制到答复消息的 CorrelationID。</span><span class="sxs-lookup"><span data-stu-id="d9af7-108">The IBM WebSphere MQ Queue Manager copies the MessageID to the CorrelationID for the reply message.</span></span> <span data-ttu-id="d9af7-109">下图显示了该过程。</span><span class="sxs-lookup"><span data-stu-id="d9af7-109">The following figure shows the process.</span></span>  
  
 <span data-ttu-id="d9af7-110">![简单关联](../core/media/bts-dev-mqsimplecorrelation.gif "BTS_Dev_MQSimpleCorrelation")</span><span class="sxs-lookup"><span data-stu-id="d9af7-110">![Simple Correlation](../core/media/bts-dev-mqsimplecorrelation.gif "BTS_Dev_MQSimpleCorrelation")</span></span>  
  
 <span data-ttu-id="d9af7-111">您可以初始化传出消息和沿用这些相关集使用的值的传入消息的相关集**MQMD_CorrelId**。</span><span class="sxs-lookup"><span data-stu-id="d9af7-111">You can initialize the correlation sets for the outgoing message and follow the correlation sets for the incoming message using the value of **MQMD_CorrelId**.</span></span>  
  
## <a name="using-the-mqseriesbiztalkcorrelationid-context-property"></a><span data-ttu-id="d9af7-112">使用 MQSeries.BizTalk_CorrelationId 上下文属性</span><span class="sxs-lookup"><span data-stu-id="d9af7-112">Using the MQSeries.BizTalk_CorrelationId Context Property</span></span>  
 <span data-ttu-id="d9af7-113">而不是为传出消息中相同的值设置 MessageID 和 CorrelationID，可以使用**BizTalk_CorrelationID**上下文属性与要求响应发送端口的 MQSeries 适配器。</span><span class="sxs-lookup"><span data-stu-id="d9af7-113">Instead of setting the MessageID and CorrelationID to the same value in the outgoing message, you can use the **BizTalk_CorrelationID** context property with a solicit-response send port of the MQSeries adapter.</span></span> <span data-ttu-id="d9af7-114">下图显示了此过程。</span><span class="sxs-lookup"><span data-stu-id="d9af7-114">The following figure shows this process.</span></span>  
  
 <span data-ttu-id="d9af7-115">![使用要求&#45;响应生成 CorrelationID](../core/media/bts-dev-mqgeneratedcorrelation.gif "BTS_Dev_MQGeneratedCorrelation")</span><span class="sxs-lookup"><span data-stu-id="d9af7-115">![Using Solicit&#45;Response to generate CorrelationID](../core/media/bts-dev-mqgeneratedcorrelation.gif "BTS_Dev_MQGeneratedCorrelation")</span></span>  
  
 <span data-ttu-id="d9af7-116">若要使用在 BizTalk 业务流程中的关联性提供的 IBM WebSphere MQ 服务器标识符，BizTalk Server 必须先获得该标识符。</span><span class="sxs-lookup"><span data-stu-id="d9af7-116">To use identifiers provided by IBM WebSphere MQ Server for correlations in your BizTalk orchestration, BizTalk Server must first obtain the identifier.</span></span> <span data-ttu-id="d9af7-117">你的应用程序这都是通过要求-响应请求。</span><span class="sxs-lookup"><span data-stu-id="d9af7-117">Your application does this through a solicit-response request.</span></span> <span data-ttu-id="d9af7-118">通过使用 MQSeries 适配器，BizTalk Server 将要求-响应请求发送到 IBM WebSphere MQ Server。</span><span class="sxs-lookup"><span data-stu-id="d9af7-118">BizTalk Server sends a solicit-response request to the IBM WebSphere MQ Server by using the MQSeries adapter.</span></span> <span data-ttu-id="d9af7-119">反过来，接收到响应时使用的消息标识符 (**MQMD_MSGId**) 和相关标识符 (**MQMD_CorrelId**)。</span><span class="sxs-lookup"><span data-stu-id="d9af7-119">In return, it receives a response with the message identifier (**MQMD_MSGId**) and the correlation identifier (**MQMD_CorrelId**).</span></span>  
  
 <span data-ttu-id="d9af7-120">对于要求-响应发送端口中的传出消息，适配器将复制**MQMD_MSGID**生成的 IBM WebSphere MQ Server 到**MQSeries.BizTalk_CorrelationId**上下文属性。</span><span class="sxs-lookup"><span data-stu-id="d9af7-120">For the outgoing message in a solicit-response send port, the adapter copies the **MQMD_MSGID** generated by IBM WebSphere MQ Server to the **MQSeries.BizTalk_CorrelationId** context property.</span></span>  
  
 <span data-ttu-id="d9af7-121">适配器接收消息时，将复制**MQMD_CorrelId**到**MQSeries.BizTalk_CorrelationId**。</span><span class="sxs-lookup"><span data-stu-id="d9af7-121">When receiving messages, the adapter copies the **MQMD_CorrelId** to the **MQSeries.BizTalk_CorrelationId**.</span></span> <span data-ttu-id="d9af7-122">在这种情况下，使用相关集，您可以初始化传出消息和沿用这些相关集传入的消息使用的相关集**MQSeries.BizTalk_CorrelationId**。</span><span class="sxs-lookup"><span data-stu-id="d9af7-122">In this case, using correlation sets, you can initialize the correlation sets for the outgoing message and follow the correlation sets for the incoming message using the **MQSeries.BizTalk_CorrelationId**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9af7-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9af7-123">See Also</span></span>  
 [<span data-ttu-id="d9af7-124">MQSCorrelationSetOrchestrationWithSolicitResponse（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="d9af7-124">MQSCorrelationSetOrchestrationWithSolicitResponse (BizTalk Server Sample)</span></span>](../core/mqscorrelationsetorchestrationwithsolicitresponse-biztalk-server-sample.md)