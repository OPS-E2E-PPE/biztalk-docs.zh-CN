---
title: 开发组合管道组件 |Microsoft 文档
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
ms.openlocfilehash: 8de06a815e1c5a6bf71700ad373ae3f278b3a9a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239613"
---
# <a name="developing-an-assembling-pipeline-component"></a>开发组装的管道组件
组装管道组件是一种 .NET 或 COM 组件，它在输入端接收若干消息，在输出端生成一个消息。 组装组件用于将若干单独的文档收集到消息交换批中。  
  
> [!NOTE]
>  未使用程序集功能，因此 BizTalk Server 始终将一个文档传递到组件输入。  
  
 组装组件必须实现以下接口：  
  
-   `IBaseComponent`  
  
-   `IAssemblerComponent`
  
-   `IComponentUI`
  
-   **IPersistPropertyBag。** 有关此接口的信息，请参阅 .NET Framework SDK 文档。  
  
> [!NOTE]
>  自定义管道组件应将输入消息的所有附加部分复制到输出消息。 这样可以在管道中对它们作进一步处理。  
  
## <a name="see-also"></a>另请参阅  
 [开发的常规管道组件](../core/developing-a-general-pipeline-component.md)   
 [开发分解的管道组件](../core/developing-a-disassembling-pipeline-component.md)   
 [开发探测的管道组件](../core/developing-a-probing-pipeline-component.md)   
 [从管道组件的报告错误](../core/reporting-errors-from-pipeline-components.md)   
 [配置本机管道组件](../core/configuring-native-pipeline-components.md)   
 [部署管道组件](../core/deploying-pipeline-components.md)   
 [CustomComponent （BizTalk Server 示例）](../core/customcomponent-biztalk-server-sample.md)