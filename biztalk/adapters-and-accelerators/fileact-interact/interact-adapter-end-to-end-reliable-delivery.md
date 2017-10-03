---
title: "交互适配器端到端可靠传递 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac7c22f2-ee4a-4e9b-af40-da7eb58daf51
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90ca0fc7ae5872598ed9a61cd7541017a6a39667
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interact-adapter-end-to-end-reliable-delivery"></a>交互适配器端到端可靠传递
时发送给收件人电子邮件或文件，我们建议你确保传递的消息或文件，和的业务事务包含在这些执行不详细的时间比预期。  
  
 当互相进行通信这两个实体可以使用持久存储 （例如，由持久性面向消息的中间件和使用它的接口应用程序提供） 时，很容易地实现可靠的传递，如果进行通信的方式标准化察觉到的状态消息。  
  
 下图显示 E2EControl 的结构的示例。  
  
 ![结束 &#45; 到 &#45; 最终控件](../../adapters-and-accelerators/fileact-interact/media/63e39b43-118e-4572-9d75-21770253a1ee.gif "63e39b43-118e-4572-9d75-21770253a1ee")  
  
 图中所示的示例中的元素是在 SwInt:Request 内发送和传递到接收应用程序 SwInt:RequestHandle 内不变。 行 02 允许为请求分配的唯一标识符。 在同一请求的每个后续重新传输上重复此唯一标识符。  
  
 构造此标识符的方式留给实施者，但通常基于 uuidgen()，如系统调用也可能是计算 sha-1 上发送的请求的结果 （使用带前缀的 Sw:MsgId，然后将它通过 base64 编码 sha-1 s字符串）。 主要需求是全局唯一 （具有极高的概率）。  
  
 Sw:CreationTime 是创建的原始请求的时间。 它是一个可选参数，但它可用于限制最终搜索以前的此消息的通信尝试。  
  
 元素 Sw:PDIndication 不存在，表示这是第二个或更多尝试将消息传输。 然后，接收应用程序所知的 E2EControl 可用 Sw:MsgId 来返回查找或不是否已收到的消息。 可选 Sw:EmissionList 包含以前尝试的时间。 此时间是使用 Sw:GetDateTime 函数时收到发件人发件人 （采用世界时间） 的本地时间。 再次，这可能会十分有用来限制搜索。  
  
## <a name="see-also"></a>另请参阅  
 [交互适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [交互适配器组件](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [适用于业务 Exchange 交互适配器消息](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [交互适配器客户端应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [交互适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [交互适配器存储和转发](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [交互适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [交互适配器状态监视](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [交互适配器不可否认性](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)