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
# <a name="mapping-phase-recoverable-interchange-processing"></a>映射阶段 （可恢复的交换处理）
默认情况下，当交换一条消息在接收端口的映射阶段失败时，整个交换将挂起。 可以通过添加一个名为属性更改此行为**BTS。SuspendMessageOnMappingFailure**到消息上下文，并通过设置为上下文属性的值`True`从管道组件。 当此属性设置为`True`，终结点管理器将放在挂起队列中的映射过程中失败，并继续处理剩余消息交换中的消息。  
  
 下面的代码设置的值**SuspendMessageOnMappingFailure**属性设为 True。  
  
```  
  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
    bool bSuspend = true;  
    inmsg.Context.Write("SuspendMessageOnMappingFailure", "http://schemas.microsoft.com/BizTalk/2003/system-properties", bSuspend);   
    …  
}  
  
```
