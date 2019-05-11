---
title: 使用 TPE |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, about Tracking Profile Editor
- tracking profiles, prerequisites
ms.assetid: ebe9a5da-66ec-482d-8aac-892a829ca996
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f46b8ce50662fca8c6b2b34eb6243ec094f6ad8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302840"
---
# <a name="using-the-tpe"></a>使用 TPE
使用跟踪配置文件编辑器 (TPE) 将业务流程和属性映射到 BAM 活动定义。  
  
 TPE 的用户创建的映射，即跟踪配置文件，如里程碑和上下文数据 （有时称为"可见性列表"） 的 BAM 活动中的项与这些项的 BizTalk 解决方案源之间。  
  
 **创建跟踪配置文件**  
  
 例如，考虑包含名为"接收的 PO。"里程碑的 BAM 活动 开发人员创建在其他 BizTalk Server 开发工具，了流程知道实际流程，包括通过哪些采购订单流动来启动处理的消息传送端口。 开发人员确定名为"收到的采购订单，"活动里程碑是与 BizTalk 消息传送的解决方案中的端口安全名为"PortEndTime"的属性最正确关联。 开发人员实现此映射和任何其他映射，以通过加载活动、 选择事件源，并将相应的项从事件源和放置在活动树定义中的相应节点上完成跟踪配置文件。  
  
 **创建一个配置文件的先决条件**  
  
 有两个用于创建跟踪配置文件的先决条件：  
  
1. BAM 活动作为一个整体的观察模型的一部分定义由业务分析员并已由系统管理员部署。  
  
2. BizTalk 解决方案 （包括业务流程、 架构、 映射和管道） 已成功部署在目标环境中。  
  
   这些系统必备组件是必需的因为安装后 TPE 不填充与要从数据库中检索任何数据。  
  
   **为自定义的 BAM 解决方案创建一个配置文件**  
  
   跟踪配置文件都只与具有侦听器的运行时间相关。 对于由使用 BAM Api 的自定义代码的 BAM 解决方案，没有任何关联的 BAM 运行时侦听器，并将数据发送到 BAM 可以完成的唯一一种方法通过两种方式：  
  
- 直接通过 BAM Api。 使用 Api，开发人员可以显式将事件数据发送到 BAM 基础结构中。 有关使用 BAM Api 的详细信息，请参阅[与事件流实现 BAM 活动](../core/implementing-bam-activities-with-event-streams.md)。  
  
- 通过间接，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]属性。 在具有关联的侦听技术，如自定义管道或表达式/操作形状中调用自定义程序集，一些运行时上下文内执行的自定义代码的位置的情况下可以使用 BAM Api，如上文所述，或使用传统数据升级技术。 通过升级属性，使用户可进行到 TPE 和事件数据复制到 BAM 活动项的关联然后可在 TPE 中使用正确的上下文属性。 有关升级属性的详细信息，请参阅[升级属性](../core/promoting-properties.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [创建跟踪配置文件](../core/creating-tracking-profiles.md)  
  
-   [如何删除孤立的跟踪配置文件](../core/how-to-remove-orphaned-tracking-profiles.md)  
  
-   [使用多个继续符](../core/using-multiple-continuations.md)