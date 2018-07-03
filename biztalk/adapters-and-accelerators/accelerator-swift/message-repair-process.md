---
title: 消息修复进程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages
- errors, messages
- messages, errors
- validating, messages
- messages, validating
ms.assetid: 87b97cec-5796-4684-bcf0-53285aca7ee2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb8e8cd5a23cd0187b5476688a00d1ca800c45d4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999062"
---
# <a name="message-repair-process"></a>消息修复进程
默认情况下， [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] MessageBox 数据库的挂起队列中挂起失败的消息。 此过程处理独立于成功的消息失败的消息。 使用此默认的机制，但是，可以检索失败的消息并修复它们的能力有限。 消息修复和新提交的功能[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]使[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户修复一条消息并将其重新提交。 另一个[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]然后，用户可以验证修复，并且第三个可以批准修复。  
  
> [!NOTE]
>  在此上下文中，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户是在部门修复工作流中执行角色的用户。 此 A4SWIFT 用户是定义，并且关联中的配置文件 Web 客户端的用户链接的证书。 这[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户不是与相同[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]用户帐户，如中所定义[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户组中[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]计算机管理实用程序。 作为工作的人员[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户必须具有[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]用户帐户，以便提交一条消息时，他们可以使用该帐户的证书。 但是，此人也可以用作其他[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户： repairer、 验证、 审批者或创建者。 有关详细信息，请参阅[创建部门和角色用于消息修复和新提交](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)。  
  
 借助此修复工作流，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]不会挂起失败的消息。 它在失败的消息中，执行其他处理，然后会将消息放入 MessageBox 中，就像一样成功消息。 修复业务流程放置到消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MRSR 站点，在用户能够在其函数[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。  
  
## <a name="message-validation"></a>消息验证  
 消息修复和新提交将发送到用于修复 MRSR 站点以下的验证失败的任何消息：  
  
- 执行的平面文件分析器 （未分析消息） 的结构验证  
  
- 执行的验证读取器的 XML 的数据验证  
  
- 执行由业务规则引擎 (BRE) 的 SWIFT 网络和使用情况的规则验证  
  
  [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 收集随 SWIFT 消息的错误集合对象中的验证过程中遇到任何错误。 修复过程包括到 XML 中，并将其附加到错误过程中的消息序列化的错误信息。 这种处理还包括将标记一个已升级的属性，指示消息未通过验证的消息 ([!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed = = True)，并报告该错误的另一个已提升的属性的每个验证阶段计数。 生成的多部分消息由以下内容组成：  
  
- 包含失败的消息正文部分  
  
- 错误部分，其中包含错误集合 XML  
  
- 升级的属性，该值指示故障状态  
  
## <a name="message-repair"></a>消息修复  
 MRSRDepartmentPolicy 将 MRSRDepartmentRule 业务规则确定哪个部门将处理失败的消息。 消息修复业务流程首先修复工作流将消息路由到与该部门中的修复角色相关联的收件箱。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]执行修复角色的用户打开中的消息[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，修复该消息，然后对进行签名并将其提交。 业务流程将修复后的消息路由到的每个修复、 重新生成密钥验证或审批角色和工作流已成功完成后，将消息路由到发送端口。  
  
 除了验证[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]检查消息以确定以下各项上的签名：  
  
- 修复工作流中的用户属于同一部门  
  
- 每个用户具有只需一次签名  
  
- 将对应于用户的角色的序列匹配定义该部门的工作流中的序列  
  
  有关部门的详细信息，请参阅[创建部门和角色用于消息修复和新提交](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)。  
  
  [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 此外可以修复未分析的消息。 但是，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]修复未分析消息上执行不同的处理。 有关详细信息，请参阅[修复未分析消息](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)。