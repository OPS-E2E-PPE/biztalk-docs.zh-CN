---
title: "为消息修复和新提交创建部门和角色 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- departments, creating
- creating, roles
- roles, requirements
- roles, creating
- creating, departments
- certificates, messages
- messages, certificates
ms.assetid: 6337bd57-63c5-4d97-b558-ac27d5eb60d7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d033ab3910657373f6e48b1f6e6bed076f730b51
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-departments-and-roles-for-message-repair-and-new-submission"></a>为消息修复和新提交创建部门和角色
消息修复和新提交涉及以下四个不同的操作：  
  
-   未通过验证的消息的修复  
  
-   验证的修复 （包括重新生成密钥）  
  
-   批准的修复  
  
-   创建新的消息  
  
 若要执行这些操作之一，用户必须假定与操作关联的角色。 角色还必须处理部门 （如下所述） 的一部分。 若要在工作流中执行某一阶段之后提交消息，用户必须对消息进行签名与用户关联的有效证书。  
  
## <a name="creating-departments-and-roles"></a>创建部门和角色  
 请参阅配置文件 Web 客户端文档。  
  
## <a name="rules-of-role-use"></a>规则的角色，请使用  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户、 角色和部门必须符合以下规则：  
  
-   修复后的消息的完整工作流是修复、 验证，并随后批准该消息。 创建消息的完整工作流是创建、 修复、 验证，并随后批准该消息。 验证和审批步骤是可选的。  
  
-   部门的工作流必须与创建角色或修复角色后开始。 如果工作流包括创建和修复步骤 （创建消息的工作流），创建步骤必须早立即修复步骤。  
  
-   用于创建消息的工作流必须包含一个且仅有一个已创建的一项功能的角色。  
  
-   每个工作流必须包含一个且只有一个角色具有的修复功能。  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户可能与多个角色，但没有单个用户可以在单个工作流中执行多个步骤。 例如，如果用户 A 修复一条消息，并且用户 B 会验证消息，然后用户 A 和用户 B 中都不可以批准消息。  
  
-   没有与相对于其他角色 RekeyVerify 或批准的功能与 RekeyVerify 或批准的功能的角色的顺序检查。  
  
-   如果一条消息，您已修复失败再次验证，它将返回到 MRSR 站点文档库中的修复收件箱。 在此情况下，前面提到的限制上 （基于谁具有已执行工作流中的角色） 验证和审批者角色将不再适用。 例如，如果用户 A 修复一条消息，用户 B 拒绝的消息验证，和用户 A 修复消息第二次，然后用户 B 以外的用户无法验证的消息。 如果是这种情况，用户 B 无法批准消息。 另一个示例是，如果用户 A 创建一条消息，用户 B 拒绝的消息验证，并且用户 C 修复消息，则用户 A 无法验证的消息。  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]创建一条消息的用户还可以修复该消息，如果它未通过验证。  
  
-   仅[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]与工作流关联的部门中的用户可以在工作流执行一个步骤。 当[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户提交一条消息，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]验证用户中与消息关联的部门具有某种角色 （通过用户中的配置文件 （以防部门不是默认值） 配置文件 web 客户端）。  
  
-   管理员可以向单个授予[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户在部门内的多个角色。 单个用户可以执行修复、 验证、 审批或创建或这些角色，在上述任何一个工作流限制的任何子集。  
  
## <a name="certificates"></a>证书  
 若要提交后修复、 验证、 审批或创建过程中，本地计算机上的消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户必须使用其自己的证书对消息进行签名。 有关创建证书的详细信息，请参阅[安装证书](../../adapters-and-accelerators/accelerator-swift/installing-certificates.md)。  
  
 要能够修复、 验证、 批准，或通过从远程客户端计算机访问 MRSR 站点创建一条消息，用户必须添加用户的证书的证书-当前用户/个人/证书 （用户不具有其客户端计算机存储中要作为管理员进行管理）。 此外，服务器上的管理员必须将添加用户的证书 （以及任何其他用户从其客户端计算机访问服务器的） 到证书 （本地计算机） / 其他的人员证书存储在服务器上。  
  
 单个用户可能具有多个分配的角色，并执行任何这些角色时应使用相同的证书。