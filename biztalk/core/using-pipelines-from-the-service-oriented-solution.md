---
title: 使用该服务中的管道面向解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, pipelines
- pipelines, service solutions
ms.assetid: 0870fce1-52ec-4ff8-884f-a3199bd7ccbb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aeddd2168f6fc796752aa5d1e276816f9a087ce2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396609"
---
# <a name="using-pipelines-from-the-service-oriented-solution"></a>使用该服务中的管道面向解决方案
客户服务业务流程的内联版本 (**CustomerService**) 调用付款跟踪系统直接。 若要准备发送的消息和处理接收的消息，业务流程将从代码调用管道。 这将允许重用其他方案版本中的管道。 它还维护业务流程与管道阶段的分离。  
  
## <a name="calling-the-pipelines"></a>调用管道  
 若要使用的代码中的管道，你必须创建消息集合，添加要处理到集合，创建用于接收结果消息的空消息并调用管道的消息。  
  
 中的以下代码**CustomerService**业务流程处于**ConstructRequestMessageAfterSendPipeline**形状：  
  
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
  
 **GetLastPaymentResponse**形状采用上面的代码中的消息，将其发送到付款跟踪系统，并处理通过接收管道返回的消息：  
  
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
  
## <a name="see-also"></a>请参阅  
 [面向服务的解决方案的实施要点](../core/implementation-highlights-of-the-service-oriented-solution.md)