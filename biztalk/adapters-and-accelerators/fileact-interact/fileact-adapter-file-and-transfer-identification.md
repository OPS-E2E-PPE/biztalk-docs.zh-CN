---
title: FileAct 适配器文件和传输标识 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a9aaff1-8816-42cf-b100-fedf964caaf5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4530a524518c96db0b42cbae456ba6705e2e9b0c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367201"
---
# <a name="fileact-adapter-file-and-transfer-identification"></a>FileAct 适配器文件和传输标识
A4SWIFT FileAct 适配器允许开发人员提供在运行时的文件和传输标识详细信息。 这些参数包括：  
  
-   **物理文件名**– 的完整路径和要读取或写入的文件的名称。 此参数永远不会传递，并且是本地的文件处理程序组件。  
  
-   **逻辑文件名**– 跨 SWIFTNet，发送应用程序中对接收应用程序传递的文件的名称。 这是可选的并且如果未提供，则使用不带路径的物理文件名。  
  
-   **文件传输事件的终结点**– 指定订阅事件基元中处理文件传输事件的应用程序的名称。 此参数链接到应用程序接收事件报告的文件传输。  
  
-   **文件传输引用**– 标记字符串创建和使用的传输中的句柄作为 FileAct 子系统本身。 FileAct 适配器而言，这是只需对此传输，唯一的字符串。  
  
-   **将密钥传送**– 字符串分配的应用程序以标识为传输中止目的。 如果未提供应用程序，这是与文件关联的 GUID。  
  
-   **传输分区**– 用于与多个传输的字符串。 如果未在调用中提供的开发人员，这将指定定义相关发送时的"应用程序名称"或接收位置。  
  
-   **用户参考**– 应用程序以唯一标识对不可否认传输定义的字符串。 如果未提供应用程序，这将是与文件关联的 GUID。  
  
-   **消息 ID** – 唯一定义的初始请求或响应的标识符。 这是由发送适配器生成与相应的请求或响应消息关联的 GUID。 因此，客户端生成的请求消息的 ID，该服务器将执行操作的响应。  
  
## <a name="see-also"></a>请参阅  
 [FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct 适配器实时端到端基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [FileAct 适配器实时本地基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [FileAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [FileAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [FileAct 适配器支持信息传输](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct 适配器送达通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [FileAct 适配器状态监视](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)