---
title: 接收适配器的接口的支持批的 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa6ee780-189c-41e3-9ab0-6b869e791c0a
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b009a3ff5b7ac8aa8f449c7b2c58ad95ededec8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973182"
---
# <a name="interfaces-for-a-batch-supported-receive-adapter"></a>支持批处理的接收适配器的接口
接收适配器总是成批提交消息。 批是一个可用于除提交以外的各种操作的数据库操作单位。 例如，接收适配器可以在同一批中提交一组消息，挂起一组消息，并删除另外一组消息。 将这些单独的操作放在同一批中可以尽可能减少所需的数据库往返次数，优化性能，因而是一种大力提倡的做法。  
  
 进程内的和独立的接收适配器需要实现以下接口才能将各批消息提交到服务器上：  
  
- **IBTTransport**  
  
- **IBTTransportControl** （仅适用于进程内适配器）  
  
- **IBTTransportConfig**  
  
- **IBaseComponent**  
  
- **IPersistPropertyBag**  
  
- **IBTBatchCallBack**  
  
  以下步骤说明接收适配器在向服务器提交消息时进行的一系列操作。  
  
1. 接收适配器通过调用从传输代理获取批处理**GetBatch**方法**IBTTransportProxy**接口。 对其调用中**GetBatch**适配器传入一个指向其**IBTBatchCallback**接口实现。  
  
2. 适配器会将消息添加一个每次向该批次通过调用**SubmitMessage**方法**IBTTransportBatch**接口。 如果这是一个双向操作，例如要求-响应消息传送**SubmitResponseMessage**调用此相同接口的方法来提交响应消息。  
  
3. 当所有消息都已都添加到批时，适配器调用**完成**方法**IBTTransportBatch**接口来提交到传输代理批。 由于接收适配器是在本质上异步时，适配器可以立即获取新批开始提交其他消息之后它将调用,**完成**。  
  
4. 处理批后，消息引擎调用适配器的**BatchComplete**使用传输代理来进行实际调用的回调方法。 一个数组**BTBatchOperationStatus**对象包含提交状态传递给适配器。 每个对象对应于一个操作类型，包含操作的总体状态以及操作所针对的每个消息的状态。 以下系列步骤说明适配器在分析批处理状态时需要进行的操作：  
  
   1.  检查总体批状态 HRESULT 值作为参数传递给**BatchComplete**方法。 如果该值显示错误，则意味着批中至少有一个操作不成功。 因此整个批作为一个实体提交失败。 之后适配器应尝试发现有问题的消息，并只将原来未造成错误者作为一批重新提交。  
  
        如果总体批状态为成功，则意味着提交给传输代理的所有消息都已保留到磁盘上。 然而，这并非意味着管道已成功处理了所有消息。 可能会有在管道中失败的消息被挂起。 对于在管道中失败的消息，由于数据已写入磁盘，所以返回的总体批状态是成功的。  
  
   2.  检查 `operationStatus` 参数中每个操作类型的状态。 如果状态为 **，则为 S_OK**，则此操作的提交成功，并且不需要进一步检查其状态。 如果将状态设置为**BTS_S_EPM_MESSAGE_SUSPENDED**的某些消息已挂起。 **BTS_S_EPM_SECURITY_CHECK_FAILED**表示一些消息未能中的身份验证身份验证要求的接收端口。 如果**E_FAIL**返回任何内容，或值小于零，此操作失败，则消息提交的任何 HRESULT。  
  
   3.  检查操作类型的各个消息的状态。 对于提交操作类型，每个消息的状态设置为 **，则为 S_OK**如果提交成功。 **BTS_S_EPM_MESSAGE_SUSPENDED**返回消息已挂起。 **BTS_S_EPM_SECURITY_CHECK_FAILED**返回消息如果失败的身份验证要求进行身份验证的接收端口。 **E_BTS_NO_SUBSCRIPTION**回如果发布的消息没有订户。 如果**E_FAIL**返回任何内容，或值小于零，则消息提交失败的任何 HRESULT。  
  
   4.  具体取决于您的适配器，您可能想要返回的消息挂起**E_FAIL**或任何失败的 HRESULT。  
  
5. **BatchComplete**方法需要返回任一 **，则为 S_OK**或**E_FAIL**以指示执行的结果。 如果**BatchComplete**方法将返回**E_FAIL**或负的任何 HRESULT，传输代理记录一个错误。  
  
   下图显示在创建支持批处理的接收适配器时的对象交互。  
  
   ![](../core/media/ebiz-sdk-devadapter1.gif "ebiz_sdk_devadapter1")  
   接收适配器提交一批消息的工作流  
  
## <a name="see-also"></a>请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发接收适配器](../core/developing-a-receive-adapter.md)   
 [实例化和初始化接收适配器](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [接收适配器的进程内的接口](../core/interfaces-for-an-in-process-receive-adapter.md)   
 [接口独立接收适配器](../core/interfaces-for-an-isolated-receive-adapter.md)   
 [接收适配器的接口的事务性批处理支持](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)   
 [同步请求-响应接收适配器的接口](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)