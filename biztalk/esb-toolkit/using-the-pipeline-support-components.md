---
title: 使用管道支持组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df0346ea-15d4-49c5-98d8-f9ec06f4e036
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6313a337e8527f3fb275f7c15745a5a7f6552151
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295597"
---
# <a name="using-the-pipeline-support-components"></a>使用管道支持组件
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括以下管道组件：  
  
-   **ESB 路线选择器**。 可用于此组件在接收端 （在接收管道） 中选择一条消息，请按照服务器端路线。 有关详细信息，请参阅[ESB 路线选择器组件](../esb-toolkit/the-esb-itinerary-selector-component.md)。  
  
-   **ESB 路线**。 可以使用在接收端 （在接收管道） 中的此组件将 ESB 元数据属性从 SOAP 标头提升到消息上下文。 有关详细信息，请参阅[ESB 路线组件](../esb-toolkit/the-esb-itinerary-component.md)。  
  
-   **ESB 路线转发器**。 有关详细信息，请参阅[ESB 路线转发器组件](../esb-toolkit/the-esb-itinerary-forwarder-component.md)。  
  
-   **ESB 路线缓存**。 你可以缓存路线到使用此组件，并重新它们应用于在请求-响应发送端口收到的响应消息。 有关详细信息，请参阅[ESB 路线组件](../esb-toolkit/the-esb-itinerary-component.md)。  
  
-   **ESB JMS 解码器**。 你可用于此组件 （在接收位置） 的业务流程或发送端口的接收端中分析出 IBM JMS (MQRFH2) 标头和保留作为上下文属性。 然后，可以访问这些上下文属性，并在与任何其他 BizTalk 上下文属性相同的方式中修改它们。 有关详细信息，请参阅[ESB JMS 编码器和解码器组件](../esb-toolkit/the-esb-jms-encoder-and-decoder-components.md)。  
  
-   **ESB JMS 编码器**。 可以使用在发送端口中的此组件要写入到消息的 IBM JMS (MQRFH2) 标头。 有关详细信息，请参阅[ESB JMS 编码器和解码器组件](../esb-toolkit/the-esb-jms-encoder-and-decoder-components.md)。  
  
-   **ESB 添加 Namespace**。 接收位置或发送端口中的此组件可用于将命名空间添加到 XML 文档。 有关详细信息，请参阅[ESB 添加 Namespace 和删除 Namespace 组件](../esb-toolkit/the-esb-add-namespace-and-remove-namespace-components.md)。  
  
-   **ESB 删除 Namespace**。 接收位置或发送端口中的此组件可用于从 XML 文档中删除命名空间。 有关详细信息，请参阅[ESB 添加 Namespace 和删除 Namespace 组件](../esb-toolkit/the-esb-add-namespace-and-remove-namespace-components.md)。  
  
-   **ESB 异常编码器**。 可以使用此组件将错误消息发送到文件系统，Microsoft InfoPath 或 Microsoft SharePoint。 此组件是属于 ESB 异常处理机制，和它对进行规范化，并通过丰富处理的发送端口的所有异常。 该组件将序列化异常信息 （包括嵌入的持久的消息和上下文属性） 到规范格式，以便所有包含消息的异常自身且可提供。  
  
-   **ESB 转换**。 此组件可用于通过指定 BizTalk 映射转换到另一个从一种格式的消息。  
  
-   **ESB BAM 跟踪器**。 可以使用此组件用于截获从 ESB 异常编码器发出的错误消息和消息中的数据插入 BAM 主导入表 （使用管道中的 BAM 事件流）。 此组件是 ESB 异常处理机制的一部分。  
  
-   **ESB 调度程序**。 你可以使用此组件中接收位置 （入站管道），动态设置出站消息的终结点位置属性。 你可以在发送管道中使用此组件执行路线的消息传递服务。 有关详细信息，请参阅[ESB 调度程序组件](../esb-toolkit/the-esb-dispatcher-component.md)。  
  
-   **ESB 调度程序反汇编**。 你可以使用此组件中接收位置 （入站管道），动态设置出站消息的终结点位置属性。 此组件的行为是类似于 ESB 调度程序组件，只不过它会改变结果消息 (如果指定的值**映射名称**属性)。 消息传递 XML 反汇编程序，从而提高属性和消息类型。 ESB 调度程序反汇编组件还支持批处理的调度到不同的终结点的多个消息。 有关详细信息，请参阅[ESB 调度程序反汇编组件](../esb-toolkit/the-esb-dispatcher-disassemble-component.md)。