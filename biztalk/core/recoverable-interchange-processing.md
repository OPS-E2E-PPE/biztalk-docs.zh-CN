---
title: 可恢复交换处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interchange processing [Messaging Engine], modes
- parties, party resolution
- Messaging Engine, examples
- messages, interchange modes
- interchange processing [Messaging Engine], examples
- Messaging Engine, Recoverable Interchange Processing property
- Messaging Engine, failures
- interchange processing [Messaging Engine], party resolution
- Messaging Engine, interchange processing
- disassembly stage, pipelines
- Recoverable Interchange Processing property
- Messaging Engine, interchange modes
- receive pipelines, disassembly stage
- interchange processing [Messaging Engine], failures
- interchange processing [Messaging Engine], restrictions
- System.Xml.XmlReader
- interchange modes [Messaging Engine]
ms.assetid: d9e366fe-b2a0-4f1a-b6b9-1264717e4731
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f61cd972466c912391e2ae899d00e6b92c2e13c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398042"
---
# <a name="recoverable-interchange-processing"></a><span data-ttu-id="7db3b-102">可恢复交换处理</span><span class="sxs-lookup"><span data-stu-id="7db3b-102">Recoverable Interchange Processing</span></span>
<span data-ttu-id="7db3b-103">本部分讨论**可恢复交换处理**功能，它允许的交换进行完全处理，即使交换中的一个或多个消息失败，在以下阶段：</span><span class="sxs-lookup"><span data-stu-id="7db3b-103">This section discusses **recoverable interchange processing** feature, which allows an interchange to be processed completely even if one or more messages in the interchange fail at the following stages/phases:</span></span>  
  
- <span data-ttu-id="7db3b-104">接收管道的拆装阶段</span><span class="sxs-lookup"><span data-stu-id="7db3b-104">Disassembly stage of a receive pipeline</span></span>  
  
- <span data-ttu-id="7db3b-105">接收管道的 XML 验证阶段</span><span class="sxs-lookup"><span data-stu-id="7db3b-105">XML validation stage of a receive pipeline</span></span>  
  
- <span data-ttu-id="7db3b-106">接收端口的映射执行阶段</span><span class="sxs-lookup"><span data-stu-id="7db3b-106">Map execution phase of a receive port</span></span>  
  
  <span data-ttu-id="7db3b-107">需要支持，以便有效消息通过消息传送路径传播和无效的消息是包含多个可标识消息的单个交换成功地处理时激发可恢复交换处理挂起。</span><span class="sxs-lookup"><span data-stu-id="7db3b-107">Recoverable interchange processing is motivated by the need to support successful processing of a single interchange that contains multiple identifiable messages so that valid messages are propagated through the messaging pathway and invalid messages are suspended.</span></span> <span data-ttu-id="7db3b-108">使用标准交换处理，给定交换中的任何无效消息存在将导致整个交换被挂起，即使它包含一个或多个有效的消息。</span><span class="sxs-lookup"><span data-stu-id="7db3b-108">With standard interchange processing, the existence of any invalid message in a given interchange causes the entire interchange to be suspended even if it contains one or more valid messages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7db3b-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="7db3b-109">In This Section</span></span>  
  
-   [<span data-ttu-id="7db3b-110">反汇编阶段（可恢复交换处理）</span><span class="sxs-lookup"><span data-stu-id="7db3b-110">Disassembly Stage (Recoverable Interchange Processing)</span></span>](../core/disassembly-stage-recoverable-interchange-processing.md)  
  
-   [<span data-ttu-id="7db3b-111">XML 验证阶段（可恢复交换处理）</span><span class="sxs-lookup"><span data-stu-id="7db3b-111">XML Validation Stage (Recoverable Interchange Processing)</span></span>](../core/xml-validation-stage-recoverable-interchange-processing.md)  
  
-   [<span data-ttu-id="7db3b-112">映射阶段（可恢复的交换处理）</span><span class="sxs-lookup"><span data-stu-id="7db3b-112">Mapping Phase (Recoverable Interchange Processing)</span></span>](../core/mapping-phase-recoverable-interchange-processing.md)