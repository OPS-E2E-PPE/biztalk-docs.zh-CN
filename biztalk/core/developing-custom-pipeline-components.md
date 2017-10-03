---
title: "开发自定义管道组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 723cd04a2a907fdb5d770975c27d47e1752d08ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="developing-custom-pipeline-components"></a>开发自定义管道组件
本部分介绍如何开发管道组件。 您可以创建三种类型的管道组件：普通、组装和拆卸。 这三种类型均可实现附加的探测功能。 每种类型的管道组件具有关联的界面，必须以插入到 BizTalk 消息传送引擎，则组件的实现区分类型的组件的管道接口为**IComponent**， **IAssemblerComponent**，和**IDisassemblerComponent**。 用于探测组件，则必须实现**IProbeMessage**接口。  
  
 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中包含一个示例管道组件，您在创建自己的组件时可以参考。 该示例组件演示如何将数据附加到消息的结尾以及如何将数据添加到消息的开头。 有关示例管道组件的详细信息，请参阅[CustomComponent （BizTalk Server 示例）](../core/customcomponent-biztalk-server-sample.md)。  
  
> [!CAUTION]
>  如果你引用中的管道中的自定义管道组件[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，可能会发生编译时错误。 若要更正该错误，请在编译前关闭管道设计器，然后重新打开。 也可以删除该组件，然后添加它。  
  
> [!IMPORTANT]
>  在升级到 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 时，请确保现有自定义管道组件中的任何字符串变量都不包含任何“\n”之类的换行符。 否则，在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中编译此组件时将会发生“常数中有换行符”错误。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用管道接口](../core/using-pipeline-interfaces.md)  
  
-   [开发的常规管道组件](../core/developing-a-general-pipeline-component.md)  
  
-   [开发组装的管道组件](../core/developing-an-assembling-pipeline-component.md)  
  
-   [开发分解的管道组件](../core/developing-a-disassembling-pipeline-component.md)  
  
-   [开发探测的管道组件](../core/developing-a-probing-pipeline-component.md)  
  
-   [实现查找托管流式处理管道组件中的方法](../core/implementing-a-seek-method-in-a-managed-streaming-pipeline-component.md)  
  
-   [使用了分析和序列化引擎](../core/using-the-parsing-and-serializing-engines.md)  
  
-   [从管道组件的报告错误](../core/reporting-errors-from-pipeline-components.md)  
  
-   [部署管道组件](../core/deploying-pipeline-components.md)  
  
-   [调试自定义管道](../core/debugging-custom-pipelines.md)