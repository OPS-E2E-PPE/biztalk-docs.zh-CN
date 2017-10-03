---
title: "创建自定义处理程序拒绝消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom handlers
- Message Repair and New Submission, rejected messages
- Message Repair and New Submission, custom handlers
ms.assetid: 28d74504-6c62-427a-b75d-456fbe43ec3a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7c2f678bde1d438f352b749eed76b5aa0ab5d7e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-custom-handler-for-rejected-messages"></a>为被拒绝的邮件创建自定义处理程序
如果在验证或批准阶段中，拒绝消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]将消息返回至工作流 （这在此情况下是始终修复，即使创建该工作流中的第一个阶段） 定义的第一个阶段。 但是，如果工作流的第一个阶段会拒绝该消息，修复业务流程将发布消息到 MessageBox 具有提升的属性，该值指示 MrsrRepair 业务流程已拒绝该消息。 若要处理这些消息，你可以创建自定义处理 （业务流程） 来订阅这些提升的属性并处理所需的消息。  
  
 MrsrRepair 业务流程中有多个原因情况下，一条消息可能会失败。 不，业务流程提升下表中的属性，并将这些属性分配值，或表的右侧列中显示的值之一。  
  
|属性|值|  
|--------------|------------|  
|BTS。操作|A4SWIFT_MRSRFailed|  
|A4SWIFT_MRSRFailedReason|超时<br /><br /> 被拒绝 （表示消息已被拒绝来自第一个阶段）<br /><br /> CantRepairInInfoPath|  
|A4SWIFT_MRSRLastStage|\<消息在失败之前已在最后一个阶段 （角色） 的名称 >|  
|A4SWIFT_MRSRDepartment|\<部门的名称 >|