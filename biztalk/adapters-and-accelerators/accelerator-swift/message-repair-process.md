---
title: 消息修复过程 |Microsoft 文档
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
ms.openlocfilehash: 442e49c347b4adf84dd7e6ee86c3b3595452cb34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22211189"
---
# <a name="message-repair-process"></a>消息修复过程
默认情况下，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]在 MessageBox 数据库的挂起队列中挂起失败的消息。 此进程处理失败的消息分开成功消息。 使用此默认机制，但是，你具有有限的功能来检索失败的消息和修复它们。 消息修复和新提交功能[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]使[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户修复一条消息并将其重新提交。 另一个[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]然后，用户可以验证修复、 和第三个可以批准修复。  
  
> [!NOTE]
>  在此上下文中，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户是用户，在执行部门修复工作流中的角色。 此 A4SWIFT 用户进行定义，并与中的配置文件的 Web 客户端的用户链接的证书关联。 这[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户不与相同[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]用户帐户中, 定义[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户组中[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]计算机管理实用工具。 作为工作的人员[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户必须具有[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]用户帐户，以便他们可以提交一条消息时使用该帐户的证书。 但是，该用户还可以充当其他[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户： repairer、 验证、 审批者或创建者。 有关详细信息，请参阅[创建部门和适用于消息修复和新提交角色](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)。  
  
 借助此修复工作流中，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]不会挂起失败的消息。 它在失败的消息中，执行额外的处理，然后将消息放置到 MessageBox，就像将成功的消息。 修复业务流程将删除该消息到[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MRSR 站点，其中用户可以执行在其功能[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。  
  
## <a name="message-validation"></a>消息验证  
 消息修复和新的提交将发送到 MRSR 站点修复以下验证失败的任何消息：  
  
-   执行的平面文件分析器 （未分析消息） 的结构验证  
  
-   通过 XML 验证读取器执行数据验证  
  
-   执行由业务规则引擎 (BRE) 的 SWIFT 网络和使用情况的规则验证  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]收集验证错误集合对象中将一直伴随 SWIFT 消息过程中遇到任何错误。 修复过程包括到 XML 并将其连接到作为错误一部分消息的序列化错误信息。 此处理还包括标记提升的属性，该值指示消息未通过验证的消息 ([!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed = = True)，将报告错误的另一个提升的属性的和计数的每个验证阶段。 生成的多部分消息由以下内容组成：  
  
-   包含在失败的消息正文部分  
  
-   一个包含错误集合 XML 错误零件  
  
-   提升属性指示的失败状态  
  
## <a name="message-repair"></a>消息修复  
 MRSRDepartmentPolicy 将 MRSRDepartmentRule 业务规则确定哪个部门将处理失败的消息。 消息修复业务流程通过将消息路由到与部门中的修复角色关联的收件箱来启动修复工作流。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]执行修复角色的用户打开中的消息[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，修复消息，然后进行签名并将其提交。 业务流程将修复后的消息路由到每个修复、 重新生成密钥验证或审批角色和工作流已成功完成后，将消息路由到发送端口。  
  
 除了验证，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]检查消息以确定以下各项上的签名：  
  
-   修复工作流中的用户属于同一部门  
  
-   每个用户具有只需一次签名  
  
-   对应于用户的角色序列匹配定义该部门工作流中序列  
  
 有关部门的详细信息，请参阅[创建部门和适用于消息修复和新提交角色](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)。  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]另外，可以修复未分析的消息。 但是，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]修复后未分析消息执行不同的处理。 有关详细信息，请参阅[修复未分析消息](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)。