---
title: "定义消息修复和新提交数据的自定义 BAM 视图 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM views
- Message Repair and New Submission, BAM views
ms.assetid: 76a6e78d-9b11-4b43-a500-a9d7666ee468
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e88ec7506a299476dccb6ef9f9d0125768ea80b6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="defining-a-custom-bam-view-for-message-repair-and-new-submission-data"></a>定义消息修复和新提交数据的自定义 BAM 视图
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序提供定义的业务活动和业务视图的 BAM 定义文件。 你可以部署的 BAM 定义文件要使用该视图，或者可以创建自定义视图，你可以将它们添加到 BAM 定义文件。  
  
 BAM 定义文件是在 MrsrActivities.xml *\<驱动器\>*: files\microsoft BizTalk Accelerator for SWIFT\BAMTracking。 它定义消息活动和 RepairView 视图。 有关使用 bm 部署 MrsrActivities.xml 详细信息部署实用工具，请参阅 BizTalk Server 帮助。  
  
 在业务活动监视视图向导从 BAM 工作簿中创建的自定义视图。 有关创建自定义视图的详细信息，请参阅"创建 BAM 视图"中[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server 信息工作人员帮助。  
  
 MrsrActivities.xml 中的消息活动包括以下各项可添加到自定义视图：  
  
> [!NOTE]
>  持续时间在计算时 BAM 中，它们以一天 （14.4 分钟 =.01 天） 为单位测量。  
  
|项|改用|项类型|  
|----------|---------|---------------|  
|目标 BIC|消息接收方的 LT 地址 (从应用程序标头块的输入消息 SWIFT，或从块 1 的消息会从 SWIFT 其中[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]机构是目标)。<br /><br /> 此数据是始终存在 （从应用程序标头输入目标 LT 对于 SWIFTBound 消息，或从 SWIFT 收到的消息的基本标头 LT）。|业务数据的文本|  
|结束时间|日期和时间 MRSRRepair 业务流程完成处理消息 （MRSR_Completed 或 MRSR_Failed）。<br /><br /> 此数据是否出现，仅对于已完成，即 MRSR 工作流的消息均已退出与**BTS。操作** == **A4SWIFT_MRSRCompleted**或**A4SWIFT_MRSRFailed**。|业务里程碑|  
|参考|此消息或事务发送的机构; 分配的唯一引用标识符摘自字段 20 或 20C(SEME)|业务数据的文本|  
|消息类型|FIN 或 GPA 消息的类型。<br /><br /> 此数据将始终存在 （应用程序标头输入或应用程序标头输出）。|业务数据的文本|  
|新的提交|指示器是否这是新的条目 (Y) 或从另一个系统或 SWIFT (N) 发出的消息。<br /><br /> 此数据不存在只对已按角色发起与创建功能的消息。|业务数据的文本|  
|Priority|SWIFT 邮件的优先级 (N = 正常，U = 紧急，S = 系统)。<br /><br /> 此数据是始终存在。|业务数据的文本|  
|接收的时间|日期和时间 MRSRRepair 业务流程最近一次收到消息 （从上一阶段 – 请参阅下面的阶段）。<br /><br /> 此数据是始终存在。|业务里程碑|  
|发件人 BIC|中的原始消息的发件人的 LT 地址 (来自块 1 的消息到 SWIFT 其中[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]机构是发送方，或从应用程序来自 SWIFT 的消息的标头输出)。<br /><br /> 此数据是始终存在 （从基本的标头 LT 地址对于 SWIFTBound 消息，或从 SWIFT 接收的消息的应用程序标头输出）。|业务数据的文本|  
|发送时间|日期和时间时 MRSRRepair 业务流程上次将邮件发送给 MRSR 站点 （对于当前的阶段中）。<br /><br /> 此数据将始终存在，除非消息位于业务流程中的过程。|业务里程碑|  
|Start Time|日期和时间时 MRSRRepair 业务流程最初收到消息作为新提交或来自接口 （内部系统或 SWIFT） 消息。<br /><br /> 此数据是始终存在。|业务里程碑|  
|最后一个阶段|最后完成的工作流 （始终之前消息现阶段） 中的步骤|业务数据的文本|  
|状态|可以是：<br /><br /> -已完成 （如果成功）<br />-重置和解释 （适用于重置如果重新启动工作流的工作流）<br />-失败，原因 （如果未成功，完成的消息，即已拒绝或超时）。<br /><br /> 此数据是始终存在。|业务数据的文本|  
|部门|通过根据部门策略 MRSRRepair 业务流程所选的部门 (依赖于[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]机构)|业务数据的文本|  
|用户名|与上一阶段关联的用户的名称 （请参阅上面的阶段）|业务数据的文本|  
|当前阶段|MRSRRepair 业务流程已向其传递的消息 （例如，收件箱） 工作流步骤。<br /><br /> 除非消息已完成消息修复，此数据不存在。|业务数据的文本|