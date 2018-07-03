---
title: 修复消息和提交新消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages
- Message Repair and New Submission
- submitting, messages
- submitting, Message Repair and New Submission
- messages, Message Repair and New Submission
- messages, submitting
- Message Repair and New Submission. about Message Repair and New Submission
ms.assetid: 6abcce90-f611-422a-b3c8-e25f1e75b039
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 569ab44588c2bd89c3533af8cc765e58f743a229
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003310"
---
# <a name="repairing-messages-and-submitting-new-messages"></a>修复消息和提交新消息
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 消息修复和新提交，可修复未通过 XML 或业务规则引擎验证一条消息。 修复过程包括验证和审批步骤，以确保准确性和消息修复的适合程度。 使用 Microsoft 执行此过程[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] MRSR 站点内的窗体。  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 此外可以提交新消息，使用此过程。 创建者将该消息，提交和工作流可以包含 repairer、 验证程序，并执行相同的任务，如下所示消息修复的审批者。  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 可将分配不同的用户执行每个任务以确保此过程的安全性。 分配适当的修复、 验证，或批准的这些用户，每个角色，并且每个用户必须使用特定证书来执行该任务。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 在处理消息修复和提交消息，还支持部门使用。 每个部门涉及到特定的工作流的一组特定的消息上执行的任务。 在任何创建的修复、 验证，或提交该消息时审批步骤，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]调用 BRE 验证并验证用户是否属于相应的部门。 有关消息修复和新提交的详细信息，请参阅[消息修复和新提交](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md)。  
  
 如果接收未分析的消息，消息修复和新提交显示的消息和中失败的描述[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，并使您可以打印该消息或将其保存到文件。 然后，您可以修复重新提交消息。 但是，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]不会调用 BRE 验证或提交已修复未分析的消息时检查部门中的成员身份。 此外，不验证重新提交未分析的消息或将其批准。 有关未分析的消息的详细信息，请参阅[修复未分析消息](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)。  
  
 本部分包含：  
  
-   [修复消息](../../adapters-and-accelerators/accelerator-swift/repairing-a-message.md)  
  
-   [验证消息](../../adapters-and-accelerators/accelerator-swift/verifying-a-message.md)  
  
-   [审核消息](../../adapters-and-accelerators/accelerator-swift/approving-a-message.md)  
  
-   [处理未分析消息](../../adapters-and-accelerators/accelerator-swift/handling-an-unparsed-message.md)  
  
-   [创建和提交新消息](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md)  
  
-   [创建新消息模板](../../adapters-and-accelerators/accelerator-swift/creating-a-new-message-template.md)