---
title: 上下文属性视图 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, message schemas
- Context Property view [Tracking Profile Editor]
- Tracking Profile Editor, Context Property view
- message schemas, XML messages
ms.assetid: 17a21b86-995c-4dc2-9a3c-1309837d0b9b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84a0f3a1d507e1440f67cd5f9e4afa18bff0b52a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237877"
---
# <a name="context-property-view"></a>上下文属性视图
“上下文属性”视图显示与该属性相关联的 XML 消息的架构。 可以从“业务流程调度”视图中的某些形状的快捷菜单访问此视图。  
  
## <a name="working-with-the-context-property-view"></a>使用上下文属性视图  
 通过单击选择你的上下文属性视图**选择事件源**按钮并单击**选择上下文属性**菜单项。 然后，从已知上下文属性列表中选择一个上下文属性，以加载该属性的架构。 选择属性后，可以将相关架构中的元素拖到活动的数据项文件夹，以指示您希望从此操作的消息内的特定 XPath 表达式提取这些数据。  
  
 可以从业务流程调度视图中打开上下文属性视图，方法是右键单击包含上下文属性的形状。 这将打开上下文菜单，从中你可以单击**上下文属性架构**菜单项以检索与图形相关联的上下文属性的列表。  
  
 可用的上下文属性的列表可能非常大。 如果你知道，而你要搜索的属性名称的一部分，您可以键入**中字符串**文本框中，然后单击**搜索**按钮。 搜索结果中将只显示那些包含您所输入的部分字符串的属性。  
  
> [!NOTE]
>  当选择从“上下文属性”视图映射时，可供选择的属性架构的列表为在 BizTalk Server 安装中配置的各个属性架构的完整列表。  您必须知道，提供的架构对您要处理的流程在运行中所使用的 BizTalk Server 的功能不敏感。 例如，当从上下文属性映射时，可以从提供的架构列表中选择 SOAP 属性的架构，但是正在运行的流程本身可能不使用 SOAP。 任何自未使用的属性映射的 BAM 活动项都会导致 BAM 捕获空数据。  
  
## <a name="see-also"></a>另请参阅  
 [源事件视图是什么？](../core/what-is-the-source-event-view.md)   
 [跟踪配置文件编辑器](../core/tracking-profile-editor.md)