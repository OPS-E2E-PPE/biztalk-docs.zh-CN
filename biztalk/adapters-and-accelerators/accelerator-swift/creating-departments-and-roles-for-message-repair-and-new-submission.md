---
title: 为消息修复和新提交创建部门和角色 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fbfe21ff49a8793e818215b72fe7f844cae85e5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378411"
---
# <a name="creating-departments-and-roles-for-message-repair-and-new-submission"></a>为消息修复和新提交创建部门和角色
消息修复和新提交涉及以下四个不同的操作：  
  
- 一条消息，未通过验证的修复  
  
- 修复 （包括重新生成密钥） 的验证  
  
- 批准的修复  
  
- 创建新消息  
  
  若要执行这些操作之一，用户必须假设与操作关联的角色。 角色还必须处理部门 （如下所述） 的一部分。 若要将消息提交工作流中执行一个阶段后，用户必须使用与用户关联的有效证书签名消息。  
  
## <a name="creating-departments-and-roles"></a>创建部门和角色  
 配置文件 Web 客户端文档，请参阅。  
  
## <a name="rules-of-role-use"></a>角色使用的规则  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 用户、 角色和部门必须符合以下规则：  
  
- 修复后的消息的完整工作流是修复、 验证，然后批准消息。 创建消息的完整工作流是创建、 修复、 验证，然后批准消息。 验证和批准步骤是可选的。  
  
- 部门的工作流必须以与创建角色或修复角色中。 如果工作流包括创建和修复步骤 （创建消息的工作流），创建步骤必须立即在修复步骤之前。  
  
- 用于创建消息的工作流必须包含一个且只有一个已创建的一项功能的角色。  
  
- 每个工作流必须包含一个且只有一个角色包含的修复功能。  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户可以与多个角色相关联，但没有单个用户可以在单个工作流中执行多个步骤。 例如，如果用户 A 修复一条消息，并且用户 B 会验证消息，然后用户 A 和用户 B 都不可以批准消息。  
  
- 没有相对于其他角色 RekeyVerify 或批准的功能与 RekeyVerify 或批准的功能具有角色的顺序进行检查。  
  
- 如果你已经修复了消息验证再次失败，它将返回到 MRSR 站点文档库中的修复收件箱。 在此情况下，（基于谁具有已执行工作流中的角色） 的验证和审批者角色上的上一限制不再适用。 例如，如果用户 A 修复一条消息，用户 B 会拒绝该消息中验证和用户 A 修复消息第二次，然后用户 B 以外的用户无法验证的消息。 如果是这样，用户 B 可以批准消息。 另一个示例是，如果用户 A 创建一条消息，用户 B 会拒绝该消息中验证，并且用户 C 修复消息，然后用户 A 无法验证的消息。  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]创建一条消息用户还可以修复该消息，如果它未通过验证。  
  
- 仅[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]与工作流关联的部门中的用户可以在工作流中执行一个步骤。 当[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户提交一条消息，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]验证用户与消息关联在部门中具有的角色 （通过用户配置文件 （如果在部门不是默认值） 配置文件 web 客户端中）。  
  
- 管理员可以提供单个[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户在部门内的多个角色。 单个用户可以执行修复、 验证、 审批或创建过程中或这些角色，在上述任何一个工作流的限制的任何子集。  
  
## <a name="certificates"></a>证书  
 若要在本地计算机上的消息提交后修复、 验证、 审批或创建过程中，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户必须使用其自己的证书对消息进行签名。 有关创建证书的详细信息，请参阅[安装证书](../../adapters-and-accelerators/accelerator-swift/installing-certificates.md)。  
  
 若要能够修复、 验证、 审核或通过从远程客户端计算机访问 MRSR 站点创建一条消息，用户必须添加用户的证书的证书-当前用户/个人/证书存储区 （用户不具有其客户端计算机的是管理员才能执行此操作）。 此外，在服务器上的管理员必须添加用户的证书 （和任何其他用户从其客户端计算机访问服务器的） 证书 （本地计算机） / 其他人 / 证书存储在服务器上。  
  
 单个用户可能有多个分配的角色，并且执行所有这些角色时应使用相同的证书。