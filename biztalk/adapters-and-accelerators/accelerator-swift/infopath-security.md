---
title: InfoPath 安全 |Microsoft 文档
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
ms.openlocfilehash: 9ec5478af7c404840bf1c5c80be5520e405bd26a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209653"
---
# <a name="infopath-security"></a>InfoPath 安全
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年使用 XML 签名，以便你可以使用数字证书对表单进行数字签名。 XML 签名定义一个标准的基于 XML 的数字签名用于帮助保护在 XML 文档中包含的数据。 XML 签名是由万维网联合会 (W3C) 控制的标准。  
  
 数字签名是宏或文档上的身份验证电子的、 基于加密的、 安全戳。 进行数字签名时[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，在窗体输入 XML 实例"标记"使用数字签名 (签名公共密钥和签名的数据摘要写入到 XML 中的专用节点)。 此签名确认 XML 文档来自签名者且未更改。 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]提供可验证、 非 repudiable 签名、 部分签名、 cosigning 和 countersigning 通过增强型的数字签名支持。  
  
 SWIFT[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]使用提供的 A4SWIFT FormGenerator 实用程序生成的窗体使用数字签名的 countersigning 方法以便 countersigners 以堆叠在每个其他的签名。 此 countersigning 签名堆栈模型的创建或编辑 SWIFT 消息、 具有消息评审和批准一个或多个审阅和审批者，以及在工作流中的所有阶段后才最后提交该消息的面向用户的过程已。  
  
 Repairers、 审阅者或审批者而不考虑是否批准或拒绝它对消息进行签名。 该签名表示响应的真实性并不一定表示"接受"决策。  
  
 当[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]提交表单，它会检查消息的有效性并将签名窗体用户处于正确的角色。  
  
 如果在工作流 （除了修复） 中的任何阶段被拒绝消息，则会将消息发送回修复阶段。 如果消息被拒绝在 repairer 或创建者阶段，消息修复和新的提交将消息发送回消息修复和新提交业务流程实例，具有将消息标记为拒绝的特定属性。  
  
 本部分介绍如何消息修复和新提交处理基于为角色定义的功能的数字签名。 角色和功能组合称为"阶段"工作流中。  
  
> [!NOTE]
>  "创建"角色是跨所有部门限制为单个的创建者。  
  
 本部分包含：  
  
-   [创建和修复阶段](../../adapters-and-accelerators/accelerator-swift/creating-and-repairing-stages.md)  
  
-   [重新生成密钥验证阶段](../../adapters-and-accelerators/accelerator-swift/rekey-verification-stage.md)  
  
-   [审核阶段](../../adapters-and-accelerators/accelerator-swift/approval-stage.md)  
  
-   [分发数字证书](../../adapters-and-accelerators/accelerator-swift/distributing-digital-certificates.md)