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
ms.openlocfilehash: 843958cdfe00a9fc9d1a2c178cb85adfe4ffc8d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999718"
---
# <a name="developing-a-disassembling-pipeline-component"></a>开发拆装管道组件
拆装管道组件在输入端接收单个消息，在输出端生成零个或多个消息。 拆装组件用于将消息交换拆分成单个文档。 拆装器组件必须实现以下接口：  
  
- `IBaseComponent`
  
- `IDisassemblerComponent`
  
- `IComponentUI`
  
- **IPersistPropertyBag。** 有关此接口的信息，请参阅 .NET Framework SDK 文档。  
  
  你可以通过扩展来创建自己的拆装组件**FFDasmComp**或**XMLDasmComp**类。  
  
> [!WARNING]
>  如果要将您的自定义拆装器的 MessageDestination 上下文属性设置为 SuspendQueue，则该拆装器返回的流必须支持 Seek(0) 才能实现挂起。  
  
> [!NOTE]
>  自定义管道组件应将输入消息的所有附加部分复制到输出消息。 这样可以在管道中对它们作进一步处理。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [处理管道组件中的传入数据流](../core/handling-incoming-data-streams-in-pipeline-components.md)  
  
-   [在反汇编程序管道组件中处理编码](../core/handling-encoding-in-a-disassembler-pipeline-component.md)  
  
-   [扩展平面文件反汇编程序管道组件](../core/extending-the-flat-file-disassembler-pipeline-component.md)