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
ms.openlocfilehash: 42c4331dacd451e2a4d9f495d495dbf10fbf911a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379718"
---
# <a name="what-is-a-tracking-profile"></a>什么是跟踪配置文件？
配置文件是一组定义业务流程的特征。 跟踪配置文件包含这些特性从活动到业务流程和端口的映射。 跟踪配置文件是扩展名为.btt 的文件。  
  
## <a name="using-tracking-profiles-in-the-tpe"></a>在 TPE 中使用跟踪配置文件  
 TPE 的用户创建的映射，即跟踪配置文件，BAM 活动中的项与这些项的 BizTalk Server 解决方案源之间。 BAM 活动里程碑和构成"想看的列表"的上下文数据组成，并跟踪配置文件跟随在业务中定义的工作单元。 有关活动的详细信息，请参阅[与事件流实现 BAM 活动](../core/implementing-bam-activities-with-event-streams.md)。  
  
 当创建跟踪配置文件使用 TPE 时，您正在使用以下对象：  
  
- BAM 活动  
  
- 在已部署的程序集中 BizTalk 业务流程  
  
- 接收和发送端口  
  
- 在已部署程序集的消息架构  
  
- 上下文属性  
  
- BAM 主导入数据库  
  
- BizTalk 管理数据库  
  
- BizTalk 跟踪数据库  
  
  通过将项从消息架构、 业务流程形状和上下文属性放入业务里程碑 （事件） 和数据项文件夹定义从业务流程的数据提取。  
  
  例如，考虑包含名为 PO Received 里程碑且具有通过哪些采购订单流动来启动处理的消息传送端口的 BAM 活动。 开发人员可以将相关联`PO Received`里程碑与 BizTalk 消息传送属性调用`PortEndTime`在其解决方案中的端口。 也就是说，这表明只要接收端口结束其操作并填充成功接收采购订单`PortEndTime`属性。 开发人员实现此映射和所有其他映射来完成跟踪配置文件。 如果它们具有 BizTalk Server 源，或处于活动中的所有项将都映射未映射，以便通过 API 调用直接如果填充的数据或事件的源是从 BizTalk Server 运行时环境之外的进程。  
  
  尽管每个窗格或在 TPE 中的视图有一个独特的功能，但所有视图和文件夹将都具有相似的导航功能以帮助您查找和操作信息。  
  
## <a name="who-uses-tracking-profiles-and-the-tpe"></a>谁可使用跟踪配置文件和 TPE？  
 涉及企业集成开发的用户使用跟踪配置文件和 TPE 将 BizTalk Server 事件源映射到 BAM 目标活动。 生成的.btt 文件被移交至 IT 实施的部署。  
  
 IT 实现用户通常将应用跟踪配置文件使用命令行工具 (BTTDeploy)。 IT 用户还可以使用 TPE 直接以应用跟踪配置文件。  
  
 IT 操作中的用户可能负责对跟踪配置文件按计划定期 （包括必需的例如备份和还原任何数据库操作），尤其是由于业务要求的更改而进行定期更新。  
  
## <a name="see-also"></a>请参阅  
 [跟踪配置文件编辑器](../core/tracking-profile-editor.md)