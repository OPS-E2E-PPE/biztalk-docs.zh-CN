---
title: 发送适配器的同步接口的支持批的 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b191c41-ca4f-4d2b-bd15-a93ad87a743d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 091b735604a0b38044498f712de63ad9eac1c057
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331607"
---
# <a name="interfaces-for-a-synchronous-batch-supported-send-adapter"></a>同步的支持批的发送适配器的接口
可识别批的适配器可以同步或以异步方式发送消息，并且可以执行事务性的发送操作。 若要发送消息批，发送适配器必须实现以下接口：  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
- **IBTBatchTransmitter**  
  
- **IBTTransmitterBatch**  
  
  对于同步批发送，消息引擎从适配器获取批，并将添加到该批传输的消息。 消息引擎将每个消息添加到批处理和发送消息，仅当它调用**完成**批上的方法。 适配器返回`True`有关**bDeleteMessage**为打算同步传输每个消息。 适配器应将消息数据，而不是消息指针保存在其**TransmitMessage**实现。 这是因为消息指针将不再有效后`True`返回，并且不应使用或缓存供以后使用。  
  
  下图显示了发送适配器中创建同步的支持批所涉及的对象交互。  
  
  ![](../core/media/ebiz-sdk-devadapter6.gif "ebiz_sdk_devadapter6")  
  同步提交消息的工作流  
  
## <a name="see-also"></a>请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发发送适配器](../core/developing-a-send-adapter.md)   
 [实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md)   
 [发送适配器的同步接口](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [发送适配器的异步接口](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [异步的支持批的发送适配器的的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [事务性异步的支持批的发送适配器的接口](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [要求-响应发送适配器的接口](../core/interfaces-for-a-solicit-response-send-adapter.md)