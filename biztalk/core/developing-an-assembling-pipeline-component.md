---
title: 开发组装管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IComponentUI interface, assembling
- IBaseComponent interface, assembling
- pipeline interfaces, IBaseComponent
- pipeline components [custom], interfaces
- pipeline interfaces, IComponentUI
- IAssemblerComponent interface, assembling
- pipeline interfaces, IAssemblerComponent
- pipeline components [custom], assembling
ms.assetid: 2f85421d-2010-4a36-82b5-ea8016f8aa99
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff36bac9dc5f14048e7d448f912f72c243146b8a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389427"
---
# <a name="developing-an-assembling-pipeline-component"></a>开发汇编程序管道组件
汇编程序管道组件是一种.NET 或 COM 组件接收输入的多条消息并生成输出一条消息。 组装组件用于到消息交换批中收集的各个文档。  
  
> [!NOTE]
>  不使用程序集功能，因此 BizTalk Server 始终将一个文档传递到组件输入。  
  
 组装组件必须实现以下接口：  
  
-   `IBaseComponent`  
  
-   `IAssemblerComponent`
  
-   `IComponentUI`
  
-   **IPersistPropertyBag。** 请参阅此接口的.NET Framework SDK 文档。  
  
> [!NOTE]
>  自定义管道组件应从输入消息复制到输出消息任何其他部分。 这会保留它们在管道中做进一步处理。  
  
## <a name="see-also"></a>请参阅  
 [开发常规管道组件](../core/developing-a-general-pipeline-component.md)   
 [开发拆装管道组件](../core/developing-a-disassembling-pipeline-component.md)   
 [开发探测管道组件](../core/developing-a-probing-pipeline-component.md)   
 [报告来自管道组件的错误](../core/reporting-errors-from-pipeline-components.md)   
 [配置本地管道组件](../core/configuring-native-pipeline-components.md)   
 [部署管道组件](../core/deploying-pipeline-components.md)   
 [CustomComponent（BizTalk Server 示例）](../core/customcomponent-biztalk-server-sample.md)