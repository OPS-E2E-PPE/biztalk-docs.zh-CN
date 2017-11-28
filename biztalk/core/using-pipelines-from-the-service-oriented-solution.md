---
title: "使用从服务的管道面向解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service solution tutorial, pipelines
- pipelines, service solutions
ms.assetid: 0870fce1-52ec-4ff8-884f-a3199bd7ccbb
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d6b8021a22db366b31cde26abdc3ef48f3e51a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-pipelines-from-the-service-oriented-solution"></a><span data-ttu-id="e15f8-102">使用从服务的管道面向解决方案</span><span class="sxs-lookup"><span data-stu-id="e15f8-102">Using Pipelines from the Service Oriented Solution</span></span>
<span data-ttu-id="e15f8-103">客户服务业务流程的内联版本 (**CustomerService**) 调用直接跟踪系统的付款。</span><span class="sxs-lookup"><span data-stu-id="e15f8-103">The inline version of the customer service orchestration (**CustomerService**) calls the payment tracking system directly.</span></span> <span data-ttu-id="e15f8-104">为准备发送的消息和处理接收的消息，业务流程将通过代码调用管道。</span><span class="sxs-lookup"><span data-stu-id="e15f8-104">To prepare the sent message and process the received message, the orchestration calls the pipelines from code.</span></span> <span data-ttu-id="e15f8-105">这将允许重用其他方案版本中的管道。</span><span class="sxs-lookup"><span data-stu-id="e15f8-105">This allows the reuse of the pipelines from the other scenarios versions.</span></span> <span data-ttu-id="e15f8-106">还可保持业务流程与管道阶段的分离状态。</span><span class="sxs-lookup"><span data-stu-id="e15f8-106">It also maintains the decoupling of the orchestration from the pipeline stages.</span></span>  
  
## <a name="calling-the-pipelines"></a><span data-ttu-id="e15f8-107">调用管道</span><span class="sxs-lookup"><span data-stu-id="e15f8-107">Calling the Pipelines</span></span>  
 <span data-ttu-id="e15f8-108">若要通过代码使用管道，则必须创建消息集合，向该集合添加要处理的消息，创建用于接收结果消息的空消息，然后调用管道。</span><span class="sxs-lookup"><span data-stu-id="e15f8-108">To use the pipelines from code, you must create a message collection, add the message to process to the collection, create an empty message to receive the result message, and invoke the pipeline.</span></span>  
  
 <span data-ttu-id="e15f8-109">下面的代码从**CustomerService** orchestration 是在**ConstructRequestMessageAfterSendPipeline**形状：</span><span class="sxs-lookup"><span data-stu-id="e15f8-109">The following code from the **CustomerService** orchestration is in the **ConstructRequestMessageAfterSendPipeline** shape:</span></span>  
  
```  
// Create the collection of messages to be sent to the send pipeline...  
sendPipelineInputMessages =   
    new Microsoft.XLANGs.Pipeline.SendPipelineInputMessages();  
sendPipelineInputMessages.Add(LastPaymentRequest);  
  
// Create an empty message for the output from the pipeline...  
LastPaymentRequestAfterSendPipeline = null;  
  
// Execute the send pipeline and get the message output from   
// the send pipeline.  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.  
    ExecuteSendPipeline(  
        typeof(  
            Microsoft.Samples.BizTalk.  
                WoodgroveBank.PaymentTrackerPipelines.  
                    PaymentTrackerSendPipeline  
        ),  
        sendPipelineInputMessages,  
        LastPaymentRequestAfterSendPipeline  
    );  
```  
  
 <span data-ttu-id="e15f8-110">**GetLastPaymentResponse**形状采用上面的代码从消息、 将其发送到跟踪系统，付款和处理返回的消息，接收管道：</span><span class="sxs-lookup"><span data-stu-id="e15f8-110">The **GetLastPaymentResponse** shape takes the message from the above code, sends it to the payment tracking system, and processes the returned message through the receive pipeline:</span></span>  
  
```  
// Execute the inline method to send the message to the   
// Payment Tracking System and get the response.  
// The response message received should be passed through the   
// receive pipeline.  
  
LastPaymentResponseBeforeReceivePipeline =   
    Microsoft.Samples.BizTalk.  
        WoodgroveBank.  
            PaymentTrackerCall.  
                PaymentTrackerCaller.  
                    GetPaymeTrackerResponse  
                    (  
                        LastPaymentRequestAfterSendPipeline  
                    );   
  
// Execute the receive pipeline using the helper class so that we don't  
// need to declare the non-serializable types involved.  
  
// Set the documentspec name so the xml disassembler in the   
// pipeline can resolve the schemas for the received message  
// without ambiguity.  
LastPaymentResponseBeforeReceivePipeline(XMLNORM.DocumentSpecName) =   
"Microsoft.Samples.BizTalk.WoodgroveBank.Schemas.LastPaymentResponse, Microsoft.Samples.BizTalk.WoodgroveBank.Schemas, Version=1.0.0.0, Culture=neutral, PublicKeyToken=5f57a322d27bc5fb";  
// Create an empty response message and fill it in with the   
// real response from the Payment Tracking System  
LastPaymentResponse = null;  
  
Microsoft.Samples.BizTalk.WoodgroveBank.Utilities.  
    ReceivePipelineHelper.CallReceivePipeLine (  
        typeof(  
            Microsoft.Samples.BizTalk.WoodgroveBank.  
                PaymentTrackerPipelines.PaymentTrackerReceivePipeline  
            ),  
            LastPaymentResponseBeforeReceivePipeline,  
            LastPaymentResponse  
        );  
```  
  
## <a name="see-also"></a><span data-ttu-id="e15f8-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e15f8-111">See Also</span></span>  
 [<span data-ttu-id="e15f8-112">服务实现重点介绍面向解决方案</span><span class="sxs-lookup"><span data-stu-id="e15f8-112">Implementation Highlights of the Service Oriented Solution</span></span>](../core/implementation-highlights-of-the-service-oriented-solution.md)