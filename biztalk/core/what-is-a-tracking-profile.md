---
title: 什么是跟踪配置文件？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking profiles, about tracking profiles
- tracking profiles, Tracking Profile Editor
- Tracking Profile Editor, tracking profiles
- tracking profiles
ms.assetid: b579bdc4-7c69-4fa0-bbc1-f98170c13d4f
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da032fb6063d81cedca9f21899c5e2bbe6eca947
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289701"
---
# <a name="what-is-a-tracking-profile"></a>什么是跟踪配置文件？
配置文件是定义业务流程的特性组。 跟踪配置文件包含这些特性从活动到业务流程和端口的映射。 跟踪配置文件是文件扩展名为 .btt 的文件。  
  
## <a name="using-tracking-profiles-in-the-tpe"></a>在 TPE 中使用跟踪配置文件  
 TPE 的用户可以创建 BAM 活动中的项和这些项的 BizTalk Server 解决方案源之间的映射或跟踪配置文件。 BAM 活动由构成“想看的列表”的里程碑和上下文数据组成，并在业务中定义了跟踪配置文件跟随的工作单位。 有关活动的详细信息，请参阅[实现事件流 BAM 活动](../core/implementing-bam-activities-with-event-streams.md)。  
  
 在使用 TPE 创建跟踪配置文件时，您要使用以下对象：  
  
-   BAM 活动  
  
-   已部署的程序集中的 BizTalk 业务流程  
  
-   接收端口和发送端口  
  
-   已部署的程序集中的消息架构  
  
-   上下文属性  
  
-   BAM 主导入数据库  
  
-   BizTalk 管理数据库  
  
-   BizTalk 跟踪数据库  
  
 将项从消息架构、业务流程形状和上下文属性中拖到业务里程碑（事件）和数据项文件夹中，可以定义从业务流程的数据提取。  
  
 例如，假设 BAM 活动包含名为“PO Received”的里程碑，并且具有一个消息传送端口，采购订单流通过该端口启动处理过程。 开发人员可以在其解决方案中将 `PO Received` 里程碑与该端口的一个名为 `PortEndTime` 的 BizTalk 消息传送属性关联在一起。 也就是说，这表明只要接收端口结束其操作并填充 `PortEndTime` 属性，PO 就成功被接收。 开发人员实现此映射和所有其他映射来完成跟踪配置文件。 如果活动中的所有项都具有 BizTalk Server 源，则这些项会被映射，否则如果数据源或事件源来自于 BizTalk Server 运行时环境之外的进程，则这些项将保留为未映射，以便被 API 调用直接填充。  
  
 尽管 TPE 中的每个窗格或视图都具有唯一的功能，但所有视图和文件夹都具有相似的导航功能以帮助您查找和操作信息。  
  
## <a name="who-uses-tracking-profiles-and-the-tpe"></a>谁使用跟踪配置文件和 TPE？  
 涉及企业集成开发的用户使用跟踪配置文件和 TPE 将 BizTalk Server 事件源映射到 BAM 目标活动。 生成的 .btt 文件被移交至 IT 实施部门以便进行部署。  
  
 通常，IT 实施部门的用户将使用命令行工具 (BTTDeploy) 应用跟踪配置文件。 IT 用户还可以直接使用 TPE 应用跟踪配置文件。  
  
 IT 运作部门的用户可能负责根据计划定期对跟踪配置文件进行更新（其中包括必需的任何数据库操作，如备份和还原），尤其当业务要求发生更改时。  
  
## <a name="see-also"></a>另请参阅  
 [跟踪配置文件编辑器](../core/tracking-profile-editor.md)