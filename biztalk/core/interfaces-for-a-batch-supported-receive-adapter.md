---
title: "批处理支持的接口接收适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa6ee780-189c-41e3-9ab0-6b869e791c0a
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2de4d27ec65620adbb5428491c5ab1a53300fd7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-a-batch-supported-receive-adapter"></a>支持批处理的接收适配器的接口
接收适配器总是成批提交消息。 批是一个可用于除提交以外的各种操作的数据库操作单位。 例如，接收适配器可以在同一批中提交一组消息，挂起一组消息，并删除另外一组消息。 将这些单独的操作放在同一批中可以尽可能减少所需的数据库往返次数，优化性能，因而是一种大力提倡的做法。  
  
 进程内的和独立的接收适配器需要实现以下接口才能将各批消息提交到服务器上：  
  
-   **IBTTransport**  
  
-   **IBTTransportControl** （仅适用于进程内适配器）  
  
-   **IBTTransportConfig**  
  
-   **IBaseComponent**  
  
-   **IPersistPropertyBag**  
  
-   **IBTBatchCallBack**  
  
 以下步骤说明接收适配器在向服务器提交消息时进行的一系列操作。  
  
1.  通过调用从传输代理接收适配器获取批处理**GetBatch**方法**IBTTransportProxy**接口。 对其调用中**GetBatch**适配器将中指向的指针传递其**IBTBatchCallback**接口实现。  
  
2.  适配器将添加一个消息一次向该批次通过调用**SubmitMessage**方法**IBTTransportBatch**接口。 如果这是一种双向操作，如请求-响应消息传递， **SubmitResponseMessage**调用此相同的接口的方法以提交响应消息。  
  
3.  在所有消息都添加到批处理后，调用该适配器**完成**方法**IBTTransportBatch**接口以提交到传输代理批。 因为接收适配器为异步性质中，可以立即获取一个新的批处理和启动提交其他消息之后它会调用, 该适配器**完成**。  
  
4.  处理批后，消息引擎时，将调用适配器的**BatchComplete**使用传输代理进行实际调用的回调方法。 数组**BTBatchOperationStatus**对象包含提交的状态传递给适配器。 每个对象对应于一个操作类型，包含操作的总体状态以及操作所针对的每个消息的状态。 以下系列步骤说明适配器在分析批处理状态时需要进行的操作：  
  
    1.  检查的总体批处理状态 HRESULT 值通过作为参数传递给**BatchComplete**方法。 如果该值显示错误，则意味着批中至少有一个操作不成功。 因此整个批作为一个实体提交失败。 之后适配器应尝试发现有问题的消息，并只将原来未造成错误者作为一批重新提交。  
  
         如果总体批状态为成功，则意味着提交给传输代理的所有消息都已保留到磁盘上。 然而，这并非意味着管道已成功处理了所有消息。 可能会有在管道中失败的消息被挂起。 对于在管道中失败的消息，由于数据已写入磁盘，所以返回的总体批状态是成功的。  
  
    2.  检查 `operationStatus` 参数中每个操作类型的状态。 如果状态为**，则为 S_OK**，对于此操作提交成功，并且不需要进一步任何检查的状态。 如果状态设置为**BTS_S_EPM_MESSAGE_SUSPENDED**一些的消息已挂起。 **BTS_S_EPM_SECURITY_CHECK_FAILED**表示某些消息失败中的身份验证需要身份验证-接收端口。 如果**E_FAIL**返回，或使用一个值，小于零，为此操作失败的消息提交任何 HRESULT。  
  
    3.  检查操作类型的各个消息的状态。 对于提交操作类型，每条消息的状态设置为**，则为 S_OK**如果提交成功。 **BTS_S_EPM_MESSAGE_SUSPENDED**返回已挂起消息。 **BTS_S_EPM_SECURITY_CHECK_FAILED**返回消息如果失败上接收端口要求身份验证的身份验证。 **E_BTS_NO_SUBSCRIPTION**附带回如果没有任何订户已发布消息。 如果**E_FAIL**返回，或任何与一个值，小于零，消息提交失败的 HRESULT。  
  
    4.  具体取决于您的适配器，你可能想要挂起返回消息**E_FAIL**或任何失败的 HRESULT。  
  
5.  **BatchComplete**方法需要返回**，则为 S_OK**或**E_FAIL**以指示执行的结果。 如果**BatchComplete**方法返回**E_FAIL**或任何负 HRESULT 传输代理记录错误。  
  
 下图显示在创建支持批处理的接收适配器时的对象交互。  
  
 ![](../core/media/ebiz-sdk-devadapter1.gif "ebiz_sdk_devadapter1")  
接收适配器提交一批消息的工作流  
  
## <a name="see-also"></a>另请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发接收适配器](../core/developing-a-receive-adapter.md)   
 [实例化和初始化接收适配器](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [进程内的接口接收适配器](../core/interfaces-for-an-in-process-receive-adapter.md)   
 [一个独立的接口接收适配器](../core/interfaces-for-an-isolated-receive-adapter.md)   
 [批处理支持为一个事务性接口接收适配器](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)   
 [接口同步请求-响应接收适配器](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)