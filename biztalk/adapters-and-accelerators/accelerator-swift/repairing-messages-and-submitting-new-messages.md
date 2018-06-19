---
title: 修复消息和提交新消息 |Microsoft 文档
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
ms.openlocfilehash: 59ece524ce06430492a3927c0cd1437eef4b216d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214021"
---
# <a name="repairing-messages-and-submitting-new-messages"></a>修复消息和提交新消息
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]消息修复和新的提交，可修复 XML 或业务规则引擎的验证失败的消息。 修复过程包括验证和审核的步骤，以确保准确性和消息修复的适合程度。 执行此过程使用[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] MRSR 站点内的窗体。  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]另外，可以提交新消息使用此过程。 创建者提交消息，并且工作流可以包括 repairer、 验证程序和审批者执行相同的任务，如下所示消息修复。  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]通过分配不同的用户可以执行每项任务，可确保此过程的安全性。 分配适当的修复、 验证，或批准角色到每个这些用户，并且每个用户必须使用特定证书以执行的任务。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]此外支持在处理过程中的部门使用修复和提交消息。 每个部门涉及到一组特定的消息上执行的任务的特定工作流。 在任何创建的修复、 验证，或时提交消息，批准步骤，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]调用 BRE 验证，并验证用户是否属于相应的部门。 有关消息修复和新提交的详细信息，请参阅[消息修复和新提交](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md)。  
  
 如果接收未分析的消息，消息修复和新提交显示的消息和中失败的描述[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，并使你能够打印消息或将其保存到文件。 然后，你可以修复并重新提交消息。 但是，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]不会调用 BRE 验证或提交已修复未分析的消息时检查部门中的成员身份。 此外，不验证重新提交未分析的消息或将其批准。 未分析消息有关的详细信息，请参阅[修复未分析消息](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)。  
  
 本部分包含：  
  
-   [修复消息](../../adapters-and-accelerators/accelerator-swift/repairing-a-message.md)  
  
-   [验证消息](../../adapters-and-accelerators/accelerator-swift/verifying-a-message.md)  
  
-   [批准一条消息](../../adapters-and-accelerators/accelerator-swift/approving-a-message.md)  
  
-   [处理未分析的消息](../../adapters-and-accelerators/accelerator-swift/handling-an-unparsed-message.md)  
  
-   [创建和提交新消息](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md)  
  
-   [创建新的消息模板](../../adapters-and-accelerators/accelerator-swift/creating-a-new-message-template.md)