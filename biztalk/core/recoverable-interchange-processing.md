---
title: "可恢复的交换处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b341b3673cd7118d459197fecea1eca25efe4e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="recoverable-interchange-processing"></a><span data-ttu-id="a07f7-102">可恢复的交换处理</span><span class="sxs-lookup"><span data-stu-id="a07f7-102">Recoverable Interchange Processing</span></span>
<span data-ttu-id="a07f7-103">本部分讨论**可恢复的交换处理**功能，允许进行完全处理，即使在每个阶段的阶段以下一个或多个消息交换中的失败的交换：</span><span class="sxs-lookup"><span data-stu-id="a07f7-103">This section discusses **recoverable interchange processing** feature, which allows an interchange to be processed completely even if one or more messages in the interchange fail at the following stages/phases:</span></span>  
  
-   <span data-ttu-id="a07f7-104">接收管道的拆装阶段</span><span class="sxs-lookup"><span data-stu-id="a07f7-104">Disassembly stage of a receive pipeline</span></span>  
  
-   <span data-ttu-id="a07f7-105">接收管道的 XML 验证阶段</span><span class="sxs-lookup"><span data-stu-id="a07f7-105">XML validation stage of a receive pipeline</span></span>  
  
-   <span data-ttu-id="a07f7-106">接收端口的映射执行阶段</span><span class="sxs-lookup"><span data-stu-id="a07f7-106">Map execution phase of a receive port</span></span>  
  
 <span data-ttu-id="a07f7-107">需要支持包含多个可标识消息的单个交换的处理时激发可恢复交换处理，以便有效消息通过消息传送路径传播，而无效消息被挂起。</span><span class="sxs-lookup"><span data-stu-id="a07f7-107">Recoverable interchange processing is motivated by the need to support successful processing of a single interchange that contains multiple identifiable messages so that valid messages are propagated through the messaging pathway and invalid messages are suspended.</span></span> <span data-ttu-id="a07f7-108">使用标准交换处理，给定交换中存在的任何无效消息都会导致整个交换被挂起，即使交换中包含一个或多个有效消息。</span><span class="sxs-lookup"><span data-stu-id="a07f7-108">With standard interchange processing, the existence of any invalid message in a given interchange causes the entire interchange to be suspended even if it contains one or more valid messages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a07f7-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="a07f7-109">In This Section</span></span>  
  
-   [<span data-ttu-id="a07f7-110">反汇编阶段 （可恢复的交换处理）</span><span class="sxs-lookup"><span data-stu-id="a07f7-110">Disassembly Stage (Recoverable Interchange Processing)</span></span>](../core/disassembly-stage-recoverable-interchange-processing.md)  
  
-   [<span data-ttu-id="a07f7-111">XML 验证阶段 （可恢复的交换处理）</span><span class="sxs-lookup"><span data-stu-id="a07f7-111">XML Validation Stage (Recoverable Interchange Processing)</span></span>](../core/xml-validation-stage-recoverable-interchange-processing.md)  
  
-   [<span data-ttu-id="a07f7-112">映射阶段 （可恢复的交换处理）</span><span class="sxs-lookup"><span data-stu-id="a07f7-112">Mapping Phase (Recoverable Interchange Processing)</span></span>](../core/mapping-phase-recoverable-interchange-processing.md)