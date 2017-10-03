---
title: "使用键入 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, about Tracking Profile Editor
- tracking profiles, prerequisites
ms.assetid: ebe9a5da-66ec-482d-8aac-892a829ca996
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0fa826ce68042336c2b6e4fb006ecb278a3f981
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-tpe"></a>使用键入
使用跟踪配置文件编辑器 (TPE)，可以将业务流程和属性映射到 BAM 活动定义。  
  
 TPE 用户可以创建 BAM 活动中的项（如里程碑和上下文数据，有时称为“所需可见性列表”）与其 BizTalk 解决方案源之间的映射，即跟踪配置文件。  
  
 **创建跟踪配置文件**  
  
 例如，请考虑包含名为“接收的 PO”里程碑的一个 BAM 活动。 开发人员由于已在其他 BizTalk Server 开发工具中创建了流程，因此他们知道实际流程包含一个消息传送端口，采购订单通过该消息端口流动来启动处理过程。 开发人员由此可以确定，名为“接收的 PO”的活动里程碑最可能与解决方案中用于端口的名为“PortEndTime”的 BizTalk 消息传送属性相关联。 开发人员通过加载活动、选择事件源，然后将适当的项从事件源拖放到活动树定义中的相应节点，来作出此映射以及任何其他映射，以完成跟踪配置文件。  
  
 **创建配置文件的先决条件**  
  
 创建跟踪配置文件有两个前提条件：  
  
1.  BAM 活动已由业务分析员定义为整个观察模型的一部分，并已由系统管理员部署。  
  
2.  BizTalk 解决方案（包括业务流程、架构、映射和管道）已在目标环境中成功部署。  
  
 这些前提条件是必需的，因为在安装后，没有使用从数据库中检索的任何数据填充 TPE。  
  
 **为自定义的 BAM 解决方案中创建配置文件**  
  
 跟踪配置文件只与具有侦听器的运行时相关。 对于由使用 BAM API 的自定义代码构成的 BAM 解决方案，没有任何关联的 BAM 运行时侦听器，并且可以采用以下两种方式之一将数据发送至 BAM：  
  
-   直接通过 BAM API。 使用 API，开发人员可以将事件数据显式发送至 BAM 基础结构。 有关使用 BAM Api 的详细信息，请参阅[实现事件流 BAM 活动](../core/implementing-bam-activities-with-event-streams.md)。  
  
-   通过间接，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]属性。 在此情况下，当调用自定义程序集时，将在某些具有关联的侦听技术（例如，自定义管道或表达式/操作形状）的运行时上下文中执行自定义代码。您可以按上述说明使用 BAM API，也可以使用传统的数据升级技术。 通过升级属性，可使 TPE 能够访问它们，并使用正确的上下文属性在 TPE 中关联事件数据和 BAM 活动项。 有关将升级属性的详细信息，请参阅[提升属性](../core/promoting-properties.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [创建跟踪配置文件](../core/creating-tracking-profiles.md)  
  
-   [如何删除孤立的跟踪配置文件](../core/how-to-remove-orphaned-tracking-profiles.md)  
  
-   [使用多个延续](../core/using-multiple-continuations.md)