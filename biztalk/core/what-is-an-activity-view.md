---
title: 什么是活动视图？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], Activity view [Tracking Profile Editor]
- activities [BAM], definitions
- Tracking Profile Editor, Activity view
- Activity view [Tracking Profile Editor]
ms.assetid: ae6bcdc8-e426-4148-b83d-08a1a5e99ca3
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48cbf2419f1d3ab0939ed1607df7c17e1ea3f8d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997941"
---
# <a name="what-is-an-activity-view"></a>什么是活动视图？
活动视图包含导入的 BAM 活动定义，该定义是使用 Excel BAM 外接程序创建的。 BAM 活动定义是业务流程的跟踪要求的摘要。 一个活动可以跨多个业务流程和端口。 您可以导入活动定义一次，然后将其映射到实现定义某些部分的每个业务流程或消息传送项目。  
  
 活动视图链接位于跟踪配置文件编辑器 (TPE) 用户界面的左窗格中。  
  
## <a name="activity-view-elements"></a>活动视图元素  
 活动视图以树视图的形式显示跟踪配置文件的整体结构，它包括下列元素：  
  
- 里程碑  
  
- 活动的数据项  
  
- 事件源  
  
- 数据源  
  
  **里程碑**： 里程碑是定义给定进程中的一个点的对象。 里程碑的访问方法有以下三种：  
  
- 可以从业务流程计划中拖动相应形状，BAM 会将该形状的执行结束时间报告为里程碑值。  
  
- 可以将消息传送属性从右侧的示意表示形式中拖至目标里程碑。  
  
- 可以拖动包含里程碑值的消息负载架构节点。  
  
  > [!NOTE]
  >  DATETIME ONLY 类型的架构节点在运行时进行计算。 不论运行时出现任何转换或强制转换问题，都会导致在事件日志中记录一条相应的跟踪错误。  
  
  **数据项**： 数据项是定义消息实例、 系统或升级的属性的 XML 架构中特殊元素的对象。 访问数据项的方法是，展开架构，找到并选择感兴趣的元素，然后将该元素拖至相应的数据项类型文件夹。 有关数据项（例如 XPath）的信息存储在配置文件中。  
  
> [!NOTE]
>  TPE 只支持无表示法或仅有一种表示法的数据项，这是在消息架构中为特定数据字段定义的。 如果存在有一种或多种表示法的数据项，业务流程跟踪过程中可能会出现错误。 在这些情况下，不在 BAM 主导入数据库中存储任何数据。 即使没有出现错误，也无法保证跟踪了哪个数据项。  
  
> [!NOTE]
>  BAM 开发人员需要注意，属性是根据 BizTalk Server 流程规则而不是根据 BAM 填充的。  
>   
>  例如，SMTP 适配器的上下文属性 SMTPServer、CC 和 From 不包含任何值，直到它们被显式填充。 填充这些属性之后，这些属性的值将出现在 BAM 主导入数据库中，并且可以开始对它们进行跟踪。  
  
## <a name="activity-view-context-menus"></a>活动视图上下文菜单  
 活动视图的可用操作的上下文菜单随业务流程视图中所选节点的不同而动态变化。 例如，如果选择活动文件夹节点，则快捷菜单将包含该活动文件夹的快捷菜单项。  
  
 可以将事件和数据与业务活动中的项相关联，方法是，将事件和数据从右侧的源事件窗格中拖至活动视图的事件或数据节点。  
  
 右键单击活动视图树中的某个节点，可以访问该节点的上下文菜单。 以下屏幕显示的是活动视图的根节点。 下表介绍了活动视图不同节点的上下文菜单中的项。  
  
 **活动定义树根节点**  
  
 ![](../core/media/activityviewcontextmenu.gif "activityviewcontextmenu")  
  
|菜单项|用法|  
|---------------|-----------|  
|新建继续符|将新的继续符文件夹插入“活动”树中。 从继续符的源段中映射此文件夹的值。<br /><br /> 与 ContinuationID 文件夹结合使用，提供一种在填充同一活动的多个组件之间移交处理的方法。 这些组件包括 BizTalk 业务流程、端口、BufferedEventStreams 和 DirectEventStreams。 **注意：** 继续符文件夹名可以包含最多 127 个字符。|  
|新建 ContinuationID|将 ContinuationID 文件夹插入“活动”树中。 将此文件夹映射到继续符的 continued-to 段。 例如，如果业务流程 A 继续执行业务流程 B，则此文件夹必须映射到业务流程 B 中的项。<br /><br /> 与继续符文件夹结合使用，提供一种在填充同一活动的多个组件之间移交处理的方法。 这些组件包括 BizTalk 业务流程、端口、BufferedEventStreams 和 DirectEventStreams。 **注意：** ContinuationID 文件夹名只能包含最多 127 个字符。|  
|新建关系|将新的关系文件夹插入“活动”树中。 用于发布构成视图的两个活动之间的关系。 **注意：** 关系文件夹名只能包含最多包含 128 个字符。 其中包括服务器名称和 BizTalk 管理数据库名称。|  
|新建文档引用 URL|将新的文档引用 URL 文件夹插入“活动”树中。 用于设置指向存储此活动的相关文档的位置的引用 URL。 **注意：** 文档引用 URL 文件夹名只能包含最多包含 128 个字符。|  
  
 **属性节点**  
  
|菜单项|用法|  
|---------------|-----------|  
|与所选数据关联|用于在消息负载（或上下文属性数据项）和 BAM 活动数据项文件夹之间创建关联。|  
  
 **事件节点**  
  
|菜单项|用法|  
|---------------|-----------|  
|与所选操作的端点关联|用于在业务流程形状（DateTime 消息负载或 DateTime 上下文属性数据项）和 BAM 活动里程碑文件夹之间创建关联。|  
  
## <a name="see-also"></a>请参阅  
 [与事件流实现 BAM 活动](../core/implementing-bam-activities-with-event-streams.md)   
 [在 Excel 中定义业务活动和视图](../core/defining-business-activities-and-views-in-excel.md)   
 [TPE 的组件](../core/components-of-the-tpe.md)