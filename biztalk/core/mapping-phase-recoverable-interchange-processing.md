---
title: 映射阶段 （可恢复的交换处理） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 544d85c7-bc47-46c1-8990-82b48a8f2f23
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91f7b00bb5bd1490b5a3249ed2b37fb1335e266b
ms.sourcegitcommit: 68239c81fb12b84a479bf6a4ed8c5b25b249f5ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58852365"
---
# <a name="mapping-phase-recoverable-interchange-processing"></a><span data-ttu-id="d183c-102">映射阶段 （可恢复的交换处理）</span><span class="sxs-lookup"><span data-stu-id="d183c-102">Mapping Phase (Recoverable Interchange Processing)</span></span>
<span data-ttu-id="d183c-103">默认情况下，当交换一条消息在接收端口的映射阶段失败时，整个交换将挂起。</span><span class="sxs-lookup"><span data-stu-id="d183c-103">By default, when a message in an interchange fails at the mapping phase of a receive port, the entire interchange is suspended.</span></span> <span data-ttu-id="d183c-104">可以通过添加一个名为属性更改此行为**BTS。SuspendMessageOnMappingFailure**到消息上下文，并通过设置为上下文属性的值`True`从管道组件。</span><span class="sxs-lookup"><span data-stu-id="d183c-104">You can change this behavior by adding a property named **BTS.SuspendMessageOnMappingFailure** to the message context, and by setting the value of the context property to `True` from a pipeline component.</span></span> <span data-ttu-id="d183c-105">当此属性设置为`True`，终结点管理器将放在挂起队列中的映射过程中失败，并继续处理剩余消息交换中的消息。</span><span class="sxs-lookup"><span data-stu-id="d183c-105">When this property is set to `True`, the end point manager places the message that failed during mapping in the suspended queue and continues to process remaining messages in the interchange.</span></span>  
  
 <span data-ttu-id="d183c-106">下面的代码设置的值**SuspendMessageOnMappingFailure**属性设为 True。</span><span class="sxs-lookup"><span data-stu-id="d183c-106">The following code sets the value of the **SuspendMessageOnMappingFailure** property to True.</span></span>  
  
```  
  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
    bool bSuspend = true;  
    inmsg.Context.Write("SuspendMessageOnMappingFailure", "http://schemas.microsoft.com/BizTalk/2003/system-properties", bSuspend);   
    …  
}  
  
```
