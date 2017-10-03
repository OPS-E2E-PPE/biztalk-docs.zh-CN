---
title: "FileAct 适配器文件和传输标识 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a9aaff1-8816-42cf-b100-fedf964caaf5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5340f9ad739009ff1cb1257365ceeeb7459511a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="fileact-adapter-file-and-transfer-identification"></a>FileAct 适配器文件和传输标识
A4SWIFT FileAct 适配器允许开发人员提供在运行时的文件和传输标识详细信息。 这些参数包括：  
  
-   **物理文件的名称**– 的完整路径和要读取或写入的文件的名称。 此参数绝对不传递和本地文件处理程序组件。  
  
-   **逻辑文件名**– 跨 SWIFTNet，发送应用程序中对接收应用程序传递的文件名称。 这是可选的并且，如果未提供，不含路径的物理文件名称适用。  
  
-   **文件传输事件终结点**– 订阅事件基元中应用程序处理文件传输事件所指定的名称。 此参数链接到应用程序接收事件报告的文件传输。  
  
-   **文件传输引用**– 标记字符串创建和使用的传输中的句柄为 FileAct 子系统本身。 就而言 FileAct 适配器，这是只需一个唯一的此传输的字符串。  
  
-   **将密钥传送**– 由应用程序标识的传输，分配的字符串中止目的。 如果不是由应用程序，这是与文件关联的 GUID。  
  
-   **传输分区**– 用于与多个传输的字符串。 如果未在调用中提供的开发人员，这将是指定定义相关发送时的"应用程序名称"或接收位置。  
  
-   **用户参考**– 应用程序以唯一标识为不可否认性传输定义的字符串。 如果不是由应用程序，这将是与文件关联的 GUID。  
  
-   **消息 ID** – 唯一定义的初始请求或响应的标识符。 这是与相应的请求或响应消息关联的 GUID，因为生成的发送的适配器。 因此，客户端生成的请求消息 ID，服务器所执行操作的响应。  
  
## <a name="see-also"></a>另请参阅  
 [FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct 适配器实时端到端基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [FileAct 适配器实时本地基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [FileAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [FileAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [FileAct 适配器支持信息传输](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct 适配器传递通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [FileAct 适配器状态监视](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)