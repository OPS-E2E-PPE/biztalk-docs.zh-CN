---
title: "消息修复和新提交提升属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- promoted properties, Message Repair and New Submission
- Message Repair and New Submission, promoted properties
ms.assetid: e980c905-d07f-4fc2-89ca-05e597410733
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76e4f57e9f5179ceea073ef281131a8cd3573703
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-repair-and-new-submission-promoted-properties"></a>消息修复和新提交提升属性
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]消息修复和新的提交对帐包括以下提升的属性。  
  
|提升的名称|Description|数据类型|值范围|用法示例|  
|-------------------|-----------------|---------------|-----------------|-------------------|  
|**BTS。操作**|指示的状态[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]处理。 可以为以下各项之一：<br /><br /> **A4SWIFT_MrsrCompleted**指示成功的消息修复和新的提交过程。<br /><br /> **A4SWIFT_MrsrFailed**指示消息修复和新的提交过程失败。<br /><br /> **A4SWIFT_MrsrUnparsedFailed**指示未分析的消息的修复失败。<br /><br /> **A4SWIFT_MrsrUnparsedComplete**指示未分析的消息的修复成功。<br /><br /> **A4SWIFT_DasmMarkedAsFailed**指示消息在接收管道的反汇编程序阶段的处理失败。|字符串|-A4SWIFT_MrsrCompleted<br />-A4SWIFT_MrsrFailed<br />-A4SWIFT_MrsrUnparsedFailed<br />-A4SWIFT_MrsrUnparsedCompleted<br />-A4SWIFT_DasmMarkedAsFailed|当 MrsrRepair 业务流程收到修复后未分析的消息时，它在修复之后时，它将设置**BTS。操作**"A4SWIFT_MRSRCompleted"的属性和**A4SWIFT_Failed**属性设置为 False，然后将消息路由到 MessageBox。 这些属性确保修复后未分析的消息不会再次进入消息修复过程。|  
|**Microsoft.Solutions.A4SWIFT。Property.A4SWIFT_Failed**|指示是否[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]成功或失败处理完该消息。|Boolean|True、False|MrsrRepair 业务流程用于仅向消息未通过验证 MessageBox 订阅。|  
|**Microsoft.Solutions.A4SWIFT。Property.A4SWIFT_SwiftBound**|指示消息是否为 SWIFT 网络绑定。|Boolean|True、False|使用 MrsrRepair 业务流程来订阅仅消息从为 SWIFT 网络绑定 MessageBox。|  
|**Microsoft.Solutions.A4SWIFT。MRSRProperty.A4SWIFT_MRSRIsNewSubmission**|指示正在处理的消息是否为新的提交。|Boolean|True、False|MrsrRepair 业务流程用于指示已在工作流的创建阶段创建一条消息。|  
|**Microsoft.Solutions.A4SWIFT。MRSRProperty.A4SWIFT_MRSRLastStage**|指示已成功修复工作流中的最后一个阶段。|字符串|-|为部门工作流定义的阶段之一。 可以将 create、 修复、 重新生成密钥验证，或批准阶段。|  
|**Microsoft.Solutions.A4SWIFT。MRSRProperty.A4SWIFT_ MRSRDepartment**|指示正在使用中的消息修复和新的提交，为指定的 MrsrDepartmentPolicy BRE 策略的部门。|字符串|-|在中设置[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理控制台。|  
|**Microsoft.Solutions.A4SWIFT。MRSRProperty.A4SWIFT_ MRSRFailedReason**|指示消息修复和新的提交过程失败的原因。 可以为以下各项之一：<br /><br /> 拒绝指示该用户拒绝来自内的消息[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。<br /><br /> InvalidDigitalSignature 指示用户的证书无效。<br /><br /> 超时指示已达到 MRSROrchestration 超时值。<br /><br /> InvalidWorkFlow 指示某个部门定义的工作流无效。<br /><br /> CantRepairIn[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]指示无法在打开传入的 XML 消息[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]。<br /><br /> 一般异常|字符串|-拒绝<br />-InvalidDigitalSignature<br />超时<br />-InvalidWorkFlow<br />-常规异常<br />-CantRepairIn[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]|设置消息修复和新提交业务流程后进程失败。|  
  
## <a name="see-also"></a>另请参阅  
 [A4SWIFT_ * 提升属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)   
 [FIN 响应对帐升级的属性](../../adapters-and-accelerators/accelerator-swift/fin-response-reconciliation-promoted-properties.md)