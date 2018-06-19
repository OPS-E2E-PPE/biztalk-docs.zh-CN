---
title: 消息修复和新提交 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages
- resubmitting messages
- errors, messages
- messages, errors
- messages, resubmitting
ms.assetid: 5bc6bfa2-8210-4dd3-89bb-5455e294ca92
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bc15351848fe68d6ef54c31fc6d58c075bb1c58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209981"
---
# <a name="message-repair-and-new-submission"></a>消息修复和新的提交
消息修复和新提交功能[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]提供有助于您修复 MT 和 MX 未通过验证的消息。 使用 MRSR SharePoint 站点 （由用户已部署），你可以看到如何消息未能通过验证。 从 MRSR 站点，可以打开的 InfoPath 窗体，可用于识别的错误、 修复消息，并将其提交进行重新处理中的邮件。  
  
 消息修复和新提交支持基于角色的消息修复。 完整的修复工作流包括修复、 验证和批准。 修复工作流都与一个部门，定义工作流的角色 （或阶段），并配置每个角色的 A4SWIFT 用户关联。 每个修复角色具有定制到角色的单独 MRSR 站点视图。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]执行验证和执行角色签名消息，每个 A4SWIFT 用户使用的证书，以确保安全的过程。  
  
 除消息修复 A4SWIFT 使您能够提交使用增强的新消息[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。 第四个 A4SWIFT 用户，创建者，执行此函数。 此过程还执行验证，而可以涉及到修复、 验证和批准的角色，以确保成功提交。 A4SWIFT 处理通过新消息提交[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体相同的方式，它处理的修复后的消息。  
  
 本部分包含：  
  
-   [消息修复过程](../../adapters-and-accelerators/accelerator-swift/message-repair-process.md)  
  
-   [为消息修复和新提交创建部门和角色](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)  
  
-   [使用 InfoPath 窗体来修复消息或提交新消息](../../adapters-and-accelerators/accelerator-swift/using-an-infopath-form-to-repair-a-message-or-submit-a-new-message.md)  
  
-   [在消息修复和新提交的特殊处理](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md)  
  
-   [修复未分析的消息](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)  
  
-   [消息修复和新提交服务处理](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission-service-processing.md)