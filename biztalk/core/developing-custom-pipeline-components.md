---
title: 开发自定义管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom]
- pipeline components [custom], about pipeline components
- pipeline components [custom], creating
- customizing, pipeline components
- pipeline interfaces
- IDisassemblerComponent
- pipeline interfaces, about pipeline interfaces
- creating, pipeline components [custom]
- IAssemblerComponent
- IComponent
- pipeline components [custom], customizing
- pipeline interfaces, interface types
- pipeline components [custom], interfaces
- pipeline components [custom], component types
ms.assetid: cce61e0d-f1e3-4ec2-b38c-7c6eaf83ac10
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0067f4583ec1612a3ba3a55761705029582caf7
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530887"
---
# <a name="developing-custom-pipeline-components"></a>开发自定义管道组件
本部分介绍如何开发管道组件。 可以创建三种类型的管道组件： 常规、 组装和拆装。 三种类型的每个可实现探测功能。 每种类型的管道组件具有关联的界面，必须为要插入到 BizTalk 消息引擎; 的组件实现区分组件类型的管道接口**IComponent**， **IAssemblerComponent**，并**IDisassemblerComponent**。 探测组件，必须实现**IProbeMessage**接口。  
  
 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包含创建您自己的组件时可以参考的示例管道组件。 示例组件演示如何将数据追加到末尾的一条消息并在消息的开头添加数据。 有关示例管道组件的详细信息，请参阅[CustomComponent （BizTalk Server 示例）](../core/customcomponent-biztalk-server-sample.md)。  
  
> [!CAUTION]
>  如果引用的自定义管道组件的管道中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，可能会发生编译时错误。 若要更正此错误，关闭管道设计器，并在编译前重新打开它。 或者，可以删除该组件，并将其添加。  
> 
> [!IMPORTANT]
>  升级到 BizTalk Server 时，请确保现有自定义管道组件中的任何字符串变量不包含任何 \n 之类的换行符。 否则，将发生"常数中的有换行符"错误，编译中的此组件时[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用管道接口](../core/using-pipeline-interfaces.md)  
  
-   [开发常规管道组件](../core/developing-a-general-pipeline-component.md)  
  
-   [开发汇编程序管道组件](../core/developing-an-assembling-pipeline-component.md)  
  
-   [开发拆装管道组件](../core/developing-a-disassembling-pipeline-component.md)  
  
-   [开发探测管道组件](../core/developing-a-probing-pipeline-component.md)  
  
-   [在托管流管道组件中实现 Seek 方法](../core/implementing-a-seek-method-in-a-managed-streaming-pipeline-component.md)  
  
-   [使用解析和序列化引擎](../core/using-the-parsing-and-serializing-engines.md)  
  
-   [报告来自管道组件的错误](../core/reporting-errors-from-pipeline-components.md)  
  
-   [部署管道组件](../core/deploying-pipeline-components.md)  
  
-   [调试自定义管道](../core/debugging-custom-pipelines.md)