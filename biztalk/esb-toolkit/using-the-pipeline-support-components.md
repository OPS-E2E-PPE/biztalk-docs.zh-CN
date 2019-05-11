---
title: 使用管道支持组件 |Microsoft Docs
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
ms.openlocfilehash: 3645649bb7c284fe4ab486a9851b2e680de70f8c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396381"
---
# <a name="using-the-pipeline-support-components"></a>使用管道支持组件
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括以下管道组件：  
  
-   **ESB 路线选择器**。 可用于此组件在接收端 （在接收管道） 选择一条消息，请执行服务器端的路线。 有关详细信息，请参阅[ESB 路线选择器组件](../esb-toolkit/the-esb-itinerary-selector-component.md)。  
  
-   **ESB 路线**。 可用于此组件在接收端 （在接收管道） 将 ESB 元数据属性从 SOAP 标头升级到消息上下文。 有关详细信息，请参阅[ESB 路线组件](../esb-toolkit/the-esb-itinerary-component.md)。  
  
-   **ESB 路线转发器**。 有关详细信息，请参阅[ESB 路线转发器组件](../esb-toolkit/the-esb-itinerary-forwarder-component.md)。  
  
-   **ESB 路线缓存**。 可以使用此组件缓存路线并重新它们应用到在要求-响应发送端口中接收的响应消息。 有关详细信息，请参阅[ESB 路线组件](../esb-toolkit/the-esb-itinerary-component.md)。  
  
-   **ESB JMS 解码器**。 可用于此组件在接收端 （在接收位置） 的业务流程或发送端口中分析出 IBM JMS (MQRFH2) 标头，并为上下文属性中保留它们。 然后，可以访问这些上下文属性，并在相同的方式与任何其他 BizTalk 上下文属性中修改它们。 有关详细信息，请参阅[ESB JMS 编码器和解码器组件](../esb-toolkit/the-esb-jms-encoder-and-decoder-components.md)。  
  
-   **ESB JMS 编码器**。 在发送端口中，可以使用此组件将 IBM JMS (MQRFH2) 标头写入消息。 有关详细信息，请参阅[ESB JMS 编码器和解码器组件](../esb-toolkit/the-esb-jms-encoder-and-decoder-components.md)。  
  
-   **ESB 添加 Namespace**。 可以使用此组件在接收位置或发送端口以将命名空间添加到 XML 文档。 有关详细信息，请参阅[ESB 添加 Namespace 和删除 Namespace 组件](../esb-toolkit/the-esb-add-namespace-and-remove-namespace-components.md)。  
  
-   **ESB 删除 Namespace**。 此组件在接收位置或发送端口可用于从 XML 文档中删除的命名空间。 有关详细信息，请参阅[ESB 添加 Namespace 和删除 Namespace 组件](../esb-toolkit/the-esb-add-namespace-and-remove-namespace-components.md)。  
  
-   **ESB 异常编码器**。 可以使用此组件将错误消息发送到文件系统，Microsoft InfoPath 或 Microsoft SharePoint。 此组件是 ESB 异常处理机制的一部分，它将规范化，并使其更加丰富发送端口处理的所有异常。 组件序列化为异常信息 （包括嵌入的持久的消息和上下文属性） 规范的格式，以便所有包含消息本身的异常，且支持。  
  
-   **ESB 转换**。 此组件可用于通过指定 BizTalk 映射转换到另一个消息从一种格式。  
  
-   **ESB BAM 跟踪器**。 此组件可用于截获从 ESB 异常编码器发出的错误消息和消息中的数据插入 BAM 主导入表 （使用管道中的 BAM 事件 Stream）。 此组件是 ESB 异常处理机制的一部分。  
  
-   **ESB 调度程序**。 在接收位置 （入站管道） 中，可以使用此组件可动态设置终结点的出站消息的位置属性。 此外可以在发送管道中使用此组件来执行路线消息传递服务。 有关详细信息，请参阅[ESB 调度程序组件](../esb-toolkit/the-esb-dispatcher-component.md)。  
  
-   **ESB 调度程序反汇编**。 在接收位置 （入站管道） 中，可以使用此组件可动态设置终结点的出站消息的位置属性。 此组件的行为是类似于 ESB 调度程序组件中，不同之处在于，它将转换结果消息 (如果指定的值**MapName**属性)。 该消息会传递通过 XML 拆装器，这将升级属性和消息类型。 ESB 调度程序反汇编组件还支持批处理多个将消息分派给不同的终结点。 有关详细信息，请参阅[ESB 调度程序反汇编组件](../esb-toolkit/the-esb-dispatcher-disassemble-component.md)。