---
title: "创建使用 BizTalk 映射程序图 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, maps
- maps, creating
- orchestrations, maps
- translations [maps]
- maps, about maps
- transformations [maps]
- maps
ms.assetid: 265e61d8-8cff-44c9-a717-8e895cb4b9bf
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c12da6732729052119bfcc7841424db6d0dcaff9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-maps-using-biztalk-mapper"></a>使用 BizTalk 映射器创建映射
BizTalk 映射程序是一个工具，在 Microsoft 内运行[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境。 BizTalk 映射程序可用来创建和编辑映射，用于将转换或转换 xml 消息。 下图建议，并还可以用于处理在接收端口收到的消息和然后转换通过发送的消息将发送端口业务流程，用于映射。  
  
 ![使用映射业务处理关系图。] (../core/media/ebiz-dev-busprcsg.gif "ebiz_dev_busprcsg")  
业务处理中的映射  
  
 使用映射可以翻译和转换消息。 翻译是将消息从一种格式转换为另一种格式的过程，例如，将平面文件转换为 XML 文件。 转换是从一个消息中获取信息并将获取的信息插入另一个消息的过程。 例如，您可以从采购订单中获取发运地址和帐单邮寄地址，再将这些地址插入发票文档。  
  
 BizTalk 映射器使用其自己的图标和链接图形系统来表示输入实例消息翻译和转换为输出实例消息的过程。 映射器与 BizTalk 编辑器使用相同的图形表示架构。 BizTalk 映射器以可扩展样式表语言转换 (XSLT) 样式表的形式存储其映射。  
  
> [!NOTE]
>  BizTalk 映射器支持 XSLT 1.0。 不支持在 BizTalk 映射器中使用 XSLT 2.0。  
  
 有关创建架构的信息，请参阅[使用 BizTalk 编辑器创建架构](../core/creating-schemas-using-biztalk-editor.md)。 有关使用业务流程中的映射的信息，请参阅[创建业务流程使用 Orchestration 设计器](../core/creating-orchestrations-using-orchestration-designer.md)。  
  
> [!NOTE]
>  映射的性能取决于映射的数量和类型的 functoid、 输入和输出的架构的大小、 输入的消息，以及你的硬件大小的复杂性。  
  
 有关为 BizTalk 映射程序使用的键盘快捷方式的信息，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [计划创建地图](../core/planning-to-create-maps.md)  
  
-   [有关映射](../core/about-maps.md)  
  
-   [使用 BizTalk 映射程序](../core/using-biztalk-mapper.md)  
  
-   [创建映射](../core/creating-maps.md)  
  
-   [编译和测试映射](../core/compiling-and-testing-maps.md)  
  
-   [排除地图故障](../core/troubleshooting-maps.md)