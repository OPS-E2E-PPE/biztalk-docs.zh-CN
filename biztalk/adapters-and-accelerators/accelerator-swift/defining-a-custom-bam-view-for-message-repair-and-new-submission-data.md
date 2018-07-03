---
title: 定义用于消息修复和新提交数据的自定义 BAM 视图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM views
- Message Repair and New Submission, BAM views
ms.assetid: 76a6e78d-9b11-4b43-a500-a9d7666ee468
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 490c1244b8ea63dda255220569f3ccee4e0f70c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007838"
---
# <a name="defining-a-custom-bam-view-for-message-repair-and-new-submission-data"></a>定义用于消息修复和新提交数据的自定义 BAM 视图
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 安装程序提供了用于定义业务活动和业务视图的 BAM 定义文件。 可以部署 BAM 定义文件中使用该视图中，也可以创建自定义视图，可以将它们添加到 BAM 定义文件。  

 BAM 定义文件是在 MrsrActivities.xml *\<驱动器\>*: \Program Files\Microsoft BizTalk Accelerator for SWIFT\BAMTracking。 它定义了消息活动和 RepairView 视图。 详细了解使用 bm 部署 MrsrActivities.xml 部署实用工具，请参阅 BizTalk Server 帮助。  

 在业务活动监视视图向导从 BAM 工作簿中创建自定义视图。 有关创建自定义视图的详细信息，请参阅"创建 BAM 视图"中 MicrosoftBizTalk 服务器信息工作人员帮助。  

 MrsrActivities.xml 中的消息活动包括以下各项可添加到自定义视图：  

> [!NOTE]
>  持续时间在计算时在 BAM 中，它们被以一天 （14.4 分钟 =.01 天） 的单位。  

|      项       |                                                                                                                                                                                                                                  改用                                                                                                                                                                                                                                   |      项类型       |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------|
| 目标 BIC | 消息的接收方的 l T 地址 (从应用程序标头块的输入消息的 SWIFT，或从块 1 的消息来自 SWIFT 其中[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]机构是目标)。<br /><br /> 此数据始终存在。 （从应用程序标头输入目标 LT SWIFTBound 消息或从基本从 SWIFT 接收的消息的标头 l T） | 业务数据-Text |
|    结束时间     |                                                                            完成日期和时间时 MRSRRepair 业务流程处理消息 （MRSR_Completed 或 MRSR_Failed）。<br /><br /> 仅对已完成，即 MRSR 工作流的消息具有已退出，该数据位于**BTS。操作** == **A4SWIFT_MRSRCompleted**或**A4SWIFT_MRSRFailed**。                                                                             |  业务里程碑  |
|    参考    |                                                                                                                                                                此消息或事务由发送机构; 分配的唯一引用标识符来自字段 20 或 20C(SEME)                                                                                                                                                                | 业务数据-Text |
|  消息类型   |                                                                                                                                                                    FIN 或 GPA 消息的类型。<br /><br /> 此数据将始终存在 （应用程序标头输入或应用程序标头输出）。                                                                                                                                                                    | 业务数据-Text |
| 新提交  |                                                                                                                       指示器是否这是一个新条目 (Y) 或从另一个系统或 SWIFT (N) 发出的消息。<br /><br /> 此数据的已按角色发起与创建功能的消息才存在。                                                                                                                        | 业务数据-Text |
|    Priority     |                                                                                                                                                                            SWIFT 消息的优先级 (N = 正常，U = 紧急，S = 系统)。<br /><br /> 此数据将始终存在。                                                                                                                                                                            | 业务数据-Text |
|  接收的时间  |                                                                                                                                                  日期和 MRSRRepair 业务流程最近一次收到消息的时间 （从上一阶段 – 请参阅下面的阶段）。<br /><br /> 此数据将始终存在。                                                                                                                                                   |  业务里程碑  |
|   发件人 BIC    |        中的原始消息的发件人的 l T 地址 (摘自块 1 的消息向 SWIFT 其中[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]机构是发件人，或从应用程序来自 SWIFT 的消息的标头输出)。<br /><br /> 此数据将始终存在 （从基本的标头 LT 地址对于 SWIFTBound 消息，或从应用程序从 SWIFT 接收的消息的标头输出）。        | 业务数据-Text |
|    发送时间    |                                                                                                                             日期和时间时 MRSRRepair 业务流程上一次将消息发送到 MRSR 站点 （适用于当前阶段）。<br /><br /> 此数据将始终存在，除非该邮件是在业务流程中的过程中。                                                                                                                             |  业务里程碑  |
|   Start Time    |                                                                                                                          日期和时间时 MRSRRepair 业务流程最初收到该消息作为新的提交或来自接口 （内部系统或 SWIFT） 的消息。<br /><br /> 此数据将始终存在。                                                                                                                          |  业务里程碑  |
|   最后一个阶段    |                                                                                                                                                                                       在工作流 （始终之前消息现阶段） 中最后一个已完成的步骤                                                                                                                                                                                       | 业务数据-Text |
|     “登录属性”      |                                                                                               可以是：<br /><br /> -已完成 （如果成功）<br />-重置和推断 （适用于重置如果重新启动工作流的工作流）<br />-失败，原因 （如果未成功，已完成消息，即已拒绝或超时）。<br /><br /> 此数据将始终存在。                                                                                                | 业务数据-Text |
|   部门    |                                                                                                                          部门策略根据 MRSRRepair 业务流程所选的部门 (依赖于[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]机构)                                                                                                                           | 业务数据-Text |
|    用户名     |                                                                                                                                                                                               与上一阶段相关联的用户的名称 （请参阅上面的阶段）                                                                                                                                                                                                | 业务数据-Text |
|  当前阶段  |                                                                                                                                     MRSRRepair 业务流程的消息 （例如，收件箱） 传递到该工作流步骤。<br /><br /> 除非消息已完成消息修复此数据存在。                                                                                                                                      | 业务数据-Text |

