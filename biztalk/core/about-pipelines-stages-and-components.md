---
title: "有关管道、 阶段和组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Microsoft.BizTalk.Component.Interop namespace
- pipelines, about pipelines
ms.assetid: a98e1c93-f264-4577-bd12-4430a5859e3c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 070c785924021f8e398a547c01afe969fa6430cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="about-pipelines-stages-and-components"></a>关于管道、阶段和组件
管道是软件基础结构的一部分，包含一组按预定义顺序处理消息的 .NET 组件或 COM 组件。 管道将处理过程划分为称作阶段的不同工作类别，并确定阶段的执行顺序。 每个阶段将定义逻辑工作组，确定该阶段中可包含的组件，并指定如何运行阶段中的管道组件。  
  
 在每个阶段中，管道组件都将执行特定的任务。 例如，在接收管道的不同阶段内的组件可以进行解码、拆装，然后将文档从其他格式转换为 XML。 发送管道的操作与此正好相反：将文档从 XML 转换为其他格式并进行组装和加密，其中每个管道组件执行整个过程的一部分。 尽管阶段是组件的容器，但每个阶段本身也是带有元数据的组件。 与管道组件（有执行代码）相反，阶段没有执行代码。  
  
 下图显示了管道在管道设计图面上如何表示。 此管道有两个阶段，即组装阶段和编码阶段。 XML 汇编程序管道组件已添加到组装阶段中，但因为它仍将显示编码阶段是仍为空，**拖至此处 ！** 若要指示管道组件，可以添加到的阶段。  
  
 ![阶段和 BizTalk 管道中的组件](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")  
BizTalk 管道中的阶段和组件说明图  
  
 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包含一组管道模板、管道组件和默认管道。 你可以创建和使用管道设计器用户界面; 配置管道使用中的 API 实现管道**Microsoft.BizTalk.Component.Interop**命名空间。 但是，无法修改管道模板。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [类型的管道](../core/types-of-pipelines.md)  
  
-   [类型的管道组件](../core/types-of-pipeline-components.md)  
  
-   [管道阶段](../core/pipeline-stages.md)  
  
-   [默认管道](../core/default-pipelines.md)  
  
-   [管道模板](../core/pipeline-templates.md)  
  
-   [管道组件](../core/pipeline-components.md)  
  
-   [管道组件中的架构解析](../core/schema-resolution-in-pipeline-components.md)  
  
-   [在 XML 汇编程序和反汇编程序管道组件中的信封使用](../core/envelope-use-in-the-xml-assembler-and-disassembler-pipeline-components.md)  
  
-   [汇编程序管道组件中的属性降级](../core/property-demotion-in-assembler-pipeline-components.md)  
  
-   [在反汇编程序管道组件中的属性提升](../core/property-promotion-in-disassembler-pipeline-components.md)  
  
-   [反汇编程序中的可分辨的字段管道组件](../core/distinguished-fields-in-disassembler-pipeline-components.md)