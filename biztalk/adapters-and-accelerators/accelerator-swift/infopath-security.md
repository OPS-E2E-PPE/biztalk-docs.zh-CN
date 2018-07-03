---
title: InfoPath 安全性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, InfoPath forms
- InfoPath forms, security
ms.assetid: 6ed7b5cc-9801-45a5-8fdb-e5d56dd36435
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef3b1eff57f225d90e7f491f0a8f48ef88f00463
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983574"
---
# <a name="infopath-security"></a>InfoPath 安全性
Microsoft [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年会使用 XML 签名来让你使用的数字证书对表单进行数字签名。 XML 签名定义一个标准的基于 XML 的数字签名，用来帮助保护在 XML 文档中包含的数据。 XML 签名是受 World Wide Web 联合会 (W3C) 标准。  
  
 数字签名是宏或文档上的身份验证了电子、 基于加密的、 安全戳。 进行数字签名时[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，通过在窗体输入的 XML 实例"标记"使用数字签名 (签名公共密钥和签名的数据摘要写入到 XML 中的专用节点)。 此签名确认 XML 文档来源于签名者，而不更改。 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 提供可验证、 否认签名、 部分签名、 cosigning 和副署通过增强的数字签名的支持。  
  
 SWIFT[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]使用提供的 A4SWIFT FormGenerator 实用工具生成的窗体使用数字签名的 countersigning 方法以便 countersigners 以彼此堆叠的签名。 此 countersigning 签名堆栈模型的创建或编辑 SWIFT 消息、 条消息由一个或多个审阅者和审批者审阅和批准和最后在工作流中的所有阶段后才提交该消息面向人员的过程具有已注销。  
  
 Repairers、 审阅者或审批者而不考虑是否批准或拒绝它对消息进行签名。 签名表示响应的真实性，并不一定表示"已接受"决策。  
  
 当[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]提交窗体时，它会检查消息的有效性，签名窗体用户属于正确的角色。  
  
 如果消息被拒绝在任何阶段 （除了修复） 工作流中，则将消息发送回修复阶段。 如果消息被拒绝在 repairer 或创建者阶段，消息修复和新提交具有将消息标记为已拒绝的特定属性将消息发送回消息修复和新提交业务流程实例。  
  
 本部分介绍如何消息修复和新提交处理的数字签名为角色定义的功能。 角色和功能的组合称为"阶段"工作流中。  
  
> [!NOTE]
>  "创建"角色是跨所有部门限于单一的创建者。  
  
 本部分包含：  
  
-   [创建和修复阶段](../../adapters-and-accelerators/accelerator-swift/creating-and-repairing-stages.md)  
  
-   [重新生成密钥验证阶段](../../adapters-and-accelerators/accelerator-swift/rekey-verification-stage.md)  
  
-   [审批阶段](../../adapters-and-accelerators/accelerator-swift/approval-stage.md)  
  
-   [分发数字证书](../../adapters-and-accelerators/accelerator-swift/distributing-digital-certificates.md)