---
title: 上下文属性视图 |Microsoft Docs
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
ms.openlocfilehash: b622c9a82bb199b066dc75b77822a4f0c2e06bdb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390315"
---
# <a name="context-property-view"></a>上下文属性视图
上下文属性视图显示与属性关联的 XML 消息的架构。 该视图是可从某些业务流程调度视图中的形状的快捷菜单。  
  
## <a name="working-with-the-context-property-view"></a>使用上下文属性视图  
 通过单击选择上下文属性视图**选择事件源**按钮，单击**选择上下文属性**菜单项。 然后从已知的上下文属性，若要加载该属性架构列表中选择上下文属性。 一旦您选择的属性，您可以将元素从关联的架构到活动的数据项文件夹以指示您希望从此操作的消息内的特定 XPath 表达式提取这些数据。  
  
 通过右键单击包含上下文属性的形状，可以从业务流程调度视图中打开上下文属性视图。 这将打开一个上下文菜单，你可以单击**上下文属性架构**菜单项来检索与形状相关联的上下文属性的列表。  
  
 可用的上下文属性的列表可能非常大。 如果您知道要搜索的属性名称的一部分，您可以键入**字符串中**文本框中，然后单击**搜索**按钮。 这将选择包含您输入的部分字符串的那些属性。  
  
> [!NOTE]
>  当你选择从上下文属性视图映射时，潜在属性架构的列表是在 BizTalk Server 安装中配置每个属性架构的完整列表。  您必须知道提供的架构不敏感到 BizTalk Server 中的哪些功能由正在运行的进程在其使用。 例如，您可以从提供的上下文属性映射时的架构的列表中选择 SOAP 属性的架构，但正在运行的进程本身可能不使用 SOAP。 映射中未使用的属性会导致 bam 捕获的 null 或为空数据的任何 BAM 活动项。  
  
## <a name="see-also"></a>请参阅  
 [什么是源事件视图？](../core/what-is-the-source-event-view.md)   
 [跟踪配置文件编辑器](../core/tracking-profile-editor.md)