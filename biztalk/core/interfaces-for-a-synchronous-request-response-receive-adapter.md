---
title: 接收适配器的接口的同步请求-响应 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0c60832-52b5-4d2c-81ec-94c46c375b15
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dcf63c64298c40152f0b7f01c764f514fde6f37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382004"
---
# <a name="interfaces-for-a-synchronous-request-response-receive-adapter"></a>接收适配器的同步请求-响应的接口
所有接收适配器需要实现以下接口，在请求-响应模式下工作：  
  
- **IBTTransport**  
  
- **IBTTransportControl** （仅适用于常规适配器）  
  
- **IBTTransportConfig**  
  
- **IBaseComponent**  
  
- **IPersistPropertyBag**  
  
- **IBTBatchCallBack**  
  
- **IBTTransmitter**  
  
  接收适配器支持请求-响应协议 （例如，HTTP 接收适配器） 提交请求消息时，执行以下操作：  
  
1. 接收适配器接收传入的请求消息。 通过调用从传输代理上获取一批**GetBatch**方法**IBTTransportProxy**接口。 此调用中，适配器将中的传递回调指针到其实现**IBTBatchCallBack.BatchComplete**方法。  
  
2. 适配器通过调用将请求消息添加到批处理**SubmitRequestMessage**方法**IBTTransportBatch**接口，一次为每个请求消息。  
  
3. 当所有消息都已都添加时，适配器调用**完成**方法**IBTTransportBatch**接口，它将提交到消息引擎通过传输代理批。  
  
4. 处理批后，消息引擎调用适配器的**IBTBatchCallBack.BatchComplete**通过传输代理的回调方法。 提交状态作为与批处理中每个消息相对应的 HRESULT 值的数组传递到适配器。 如果批失败，管道中或在业务流程，SOAP 错误消息作为响应返回给适配器。  
  
5. 传入的请求消息可能具有业务流程订阅服务器。 在业务流程完成并已处理的请求消息后，消息引擎通过调用适配器的适配器发送响应消息通过传输代理**TransmitMessage** 方法**IBTTransmitter**接口。  
  
6. 适配器发送响应消息，并从 MessageBox 数据库中删除原始消息。  
  
   下图显示了接收适配器创建一个同步请求-响应所涉及的对象交互。  
  
   ![](../core/media/ebiz-sdk-devadapter3.gif "ebiz_sdk_devadapter3")  
   接收适配器提交同步消息的工作流  
  
## <a name="see-also"></a>请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发接收适配器](../core/developing-a-receive-adapter.md)   
 [实例化和初始化接收适配器](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [接收适配器的进程内的接口](../core/interfaces-for-an-in-process-receive-adapter.md)   
 [接口独立接收适配器](../core/interfaces-for-an-isolated-receive-adapter.md)   
 [接收适配器的支持批的接口](../core/interfaces-for-a-batch-supported-receive-adapter.md)   
 [支持批处理的事务性接收适配器的接口](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)