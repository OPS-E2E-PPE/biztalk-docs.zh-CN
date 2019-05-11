---
title: 创建自定义处理程序被拒绝消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom handlers
- Message Repair and New Submission, rejected messages
- Message Repair and New Submission, custom handlers
ms.assetid: 28d74504-6c62-427a-b75d-456fbe43ec3a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7fb2ebe02d4f64923239bb67aa3667ac4f3ff0b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378501"
---
# <a name="creating-a-custom-handler-for-rejected-messages"></a>为已拒绝消息创建自定义处理程序
如果在验证或审批阶段中，拒绝消息，则[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]该消息返回给工作流 （这在此情况下是始终修复，即使创建工作流中的第一个阶段） 定义的第一个阶段。 但是，如果工作流的第一个阶段会拒绝该消息，修复业务流程将消息发布到 MessageBox 与升级的属性，该值指示 MrsrRepair 业务流程已拒绝该消息。 若要处理这些消息，可以创建一个自定义处理程序 （业务流程），订阅这些升级的属性，并处理所需的消息。  
  
 一条消息失败 MrsrRepair 业务流程中存在多个原因。 当它执行业务流程升级下表中的属性，并将这些属性分配值，或显示表的右侧列中的值之一。  
  
|属性|值|  
|--------------|------------|  
|BTS.Operation|A4SWIFT_MRSRFailed|  
|A4SWIFT_MRSRFailedReason|超时<br /><br /> 已拒绝 （表示消息已被拒绝来自第一个阶段）<br /><br /> CantRepairInInfoPath|  
|A4SWIFT_MRSRLastStage|\<消息已在失败之前的最后一个阶段 （角色） 的名称\>|  
|A4SWIFT_MRSRDepartment|\<系的名称\>|