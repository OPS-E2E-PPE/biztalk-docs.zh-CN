---
title: 开发拆装管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDisassemblerComponent interface, disassembling
- pipeline components [custom], IDisassemblerComponent
- pipeline components [custom], IBaseComponent
- IBaseComponent interface, disassembling
- pipeline components [custom], disassembling
ms.assetid: 77c0aa7d-4d1b-4a8f-bef8-d38e7e4045c6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00258b86f2da320b0ec13963a96a93aca8de477a
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530927"
---
# <a name="developing-a-disassembling-pipeline-component"></a>开发拆装管道组件
拆装管道组件接收输入一条消息，并生成输出的零个或多个消息。 拆装组件用于拆分成单个文档的消息交换。 拆装器组件必须实现以下接口：  
  
- `IBaseComponent`
  
- `IDisassemblerComponent`
  
- `IComponentUI`
  
- **IPersistPropertyBag。** 请参阅此接口的.NET Framework SDK 文档。  
  
  你可以通过扩展来创建自己的拆装组件**FFDasmComp**或**XMLDasmComp**类。  
  
> [!WARNING]
>  如果自定义拆装器将设置 MessageDestination 上下文属性为 SuspendQueue，拆装器返回的流必须支持挂起 Seek(0) 工作。  
  
> [!NOTE]
>  自定义管道组件应从输入消息复制到输出消息任何其他部分。 这会保留它们在管道中做进一步处理。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [处理管道组件中的传入数据流](../core/handling-incoming-data-streams-in-pipeline-components.md)  
  
-   [在反汇编程序管道组件中处理编码](../core/handling-encoding-in-a-disassembler-pipeline-component.md)  
  
-   [扩展平面文件反汇编程序管道组件](../core/extending-the-flat-file-disassembler-pipeline-component.md)