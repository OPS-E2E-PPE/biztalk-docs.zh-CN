---
title: 消息修复和新提交 |Microsoft Docs
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
ms.openlocfilehash: e17faaf34279140dd67fa3c82c69805db91d4f5d
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530278"
---
# <a name="message-repair-and-new-submission"></a>消息修复和新提交
消息修复和新提交功能[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]提供修复 MT 和 MX 消息未能通过验证的一种方法。 使用 MRSR SharePoint 站点 （已部署的用户），您可以看到如何在消息未能通过验证。 从 MRSR 站点，可以使您能够识别的错误、 修复消息，并将其提交以进行重新处理的 InfoPath 窗体中打开消息。  
  
 消息修复和新提交支持基于角色的消息修复。 完整的修复工作流包括修复、 验证和批准。 修复工作流都具有一个定义工作流的角色 （或阶段） 和配置为每个角色的 A4SWIFT 用户的部门相关联。 每个修复角色具有适用于该角色的单独 MRSR 站点视图。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 执行验证和执行角色签名消息，每个 A4SWIFT 用户使用的证书，以确保安全的过程。  
  
 除了消息修复 A4SWIFT 可以提交新消息使用增强型[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。 第四个 A4SWIFT 用户，创建者，执行此功能。 该过程还执行验证，并可以涉及到修复、 验证和审批的角色，以确保成功提交。 A4SWIFT 处理新消息提交通过[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]形成它处理修复后的消息的相同方式。  
  
 本部分包含：  
  
-   [消息修复进程](../../adapters-and-accelerators/accelerator-swift/message-repair-process.md)  
  
-   [为消息修复和新提交创建部门和角色](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)  
  
-   [使用 InfoPath 表单修复消息或提交新消息](../../adapters-and-accelerators/accelerator-swift/using-an-infopath-form-to-repair-a-message-or-submit-a-new-message.md)  
  
-   [消息修复和新提交中的特殊处理](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md)  
  
-   [修复未分析的消息](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)  
  
-   [消息修复和新提交服务处理](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission-service-processing.md)