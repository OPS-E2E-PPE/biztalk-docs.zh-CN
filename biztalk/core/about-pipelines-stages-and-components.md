---
title: 关于管道、 阶段和组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Microsoft.BizTalk.Component.Interop namespace
- pipelines, about pipelines
ms.assetid: a98e1c93-f264-4577-bd12-4430a5859e3c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04bef6e1c443ca2723029014f5a4d3b703b4d7a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362348"
---
# <a name="about-pipelines-stages-and-components"></a>关于管道、 阶段和组件
管道是一种软件基础结构，其中包含一组按预定义的顺序处理消息的.NET 或 COM 组件。 管道将处理到类别的工作为称作阶段，并确定的执行阶段的。 每个阶段定义逻辑工作组，确定哪些组件可以在该阶段中，转并指定如何运行阶段中的管道组件。  
  
 在每个阶段，管道组件执行特定任务。 例如，接收管道的阶段中的组件可能解码、 反汇编程序，且然后将文档从其他格式转换为 XML。 发送管道的操作与此正好相反： 将文档从 XML 转换为其他格式、 组装和加密，其中每个管道组件执行整个过程的一部分。 尽管阶段是组件的容器，每个阶段本身就是具有元数据的组件。 阶段有执行代码，而不是管道组件，它们具有执行代码。  
  
 下图显示了如何在管道设计图面了管道。 此管道包含两个阶段，即组装阶段和编码阶段。 XML 组装器管道组件已添加到组装阶段中，但编码阶段仍然为空，因为它仍显示**放到此处 ！** 指示可以向阶段添加管道组件。  
  
 ![阶段和 BizTalk 管道中的组件](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")  
说明了阶段和 BizTalk 管道中的组件。  
  
 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包含一组管道模板、 管道组件和默认管道。 您可以创建和配置管道通过使用管道设计器用户界面;使用中的 API 实现管道**Microsoft.BizTalk.Component.Interop**命名空间。 无法修改管道模板。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [类型的管道](../core/types-of-pipelines.md)  
  
-   [类型的管道组件](../core/types-of-pipeline-components.md)  
  
-   [管道阶段](../core/pipeline-stages.md)  
  
-   [默认管道](../core/default-pipelines.md)  
  
-   [管道模板](../core/pipeline-templates.md)  
  
-   [管道组件](../core/pipeline-components.md)  
  
-   [管道组件中的架构解析](../core/schema-resolution-in-pipeline-components.md)  
  
-   [在 XML 汇编程序和反汇编程序管道组件中使用信封](../core/envelope-use-in-the-xml-assembler-and-disassembler-pipeline-components.md)  
  
-   [汇编程序管道组件中的属性降级](../core/property-demotion-in-assembler-pipeline-components.md)  
  
-   [管道组件中的属性升级](../core/property-promotion-in-disassembler-pipeline-components.md)  
  
-   [反汇编程序管道组件中的可分辨字段](../core/distinguished-fields-in-disassembler-pipeline-components.md)