---
title: 服务器运行时安全性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, server runtime
- servers, security
- servers, runtime
ms.assetid: 40f5ca3e-d9d3-4543-bd38-82283c343b76
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dca50fff848f07fbb17728f2527683a6c6d67340
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530046"
---
# <a name="server-runtime-security"></a>服务器运行时安全性
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 消息修复和新提交中以安全且具有确定性的方式控制业务用户、 后端系统和 SWIFT 网络终结点之间的 SWIFT 消息的流。 它由业务用户提交的消息进行身份验证，验证数据和业务规则正确性的消息并将消息路由到后端系统或最终传送到 SWIFT 网络。 有关数字证书的详细信息，请参阅"加密和签名证书"MSDN 库网站上在[ http://go.microsoft.com/fwlink/?linkid=50285 ](http://go.microsoft.com/fwlink/?linkid=50285)。  
  
 消息修复和新提交是[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]业务流程应用程序，托管并按执行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安全上下文。 作为保护[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]前面所述的安全功能。 消息修复和新提交还定义并强制实施特定于 SWIFT 消息的创建、 修复、 批准和提交的用户级安全策略，如下所示：  
  
- 新的或已修复的所有消息都提交到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]通过消息修复和新提交必须来自受信任的用户。  
  
- 创建或修复消息的受信任的用户必须具有正确的授权和权限。 批准或拒绝的消息的受信任的用户必须具有正确的授权和权限。  
  
- 所有消息必须由已知数量的受信任的用户都批准。 必须是唯一的消息创建者、 repairer 和审批者链中每个受信任的用户-同一个用户不能创建或修复并批准或拒绝消息。 同一用户不能输入多个批准或拒绝多步审批过程中的单个消息的决策。 不能批准您自己创建或已修复的消息，也可以批准为多个审批者相同的消息。  
  
- 您不能批准过程中更改一条消息 （即，一条消息不能更改原始提交到消息修复和新提交，为新的或已修复消息后）。  
  
- 更改在重新生成密钥验证阶段的消息必须与原始消息 （创建或修复） 完全匹配。  
  
  若要强制这些安全语义，消息修复和新提交，请验证它接收每个阶段的创建或修复审批提交过程的每个 XML 消息中嵌入的数字签名。 消息修复和新提交的数字签名验证将执行以下检查。 如果一个或多个这些检查会失败，消息修复和新提交停止，并且将一直保留到消息框中和安全故障事件日志中记录：  
  
- XML 消息必须进行数字签名，因此必须包含相应的数字签名。  
  
- 必须通过使用受信任的数字证书进行每个工作流中使用的数字签名。 这可确保消息创建者、 repairer、 验证和审批者是受信任。  
  
- 每个受信任的数字证书必须属于[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]域用户都具有有逻辑的颁发机构或执行操作中的权限的域组成员身份[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。 这可确保在创建或修复审批提交过程中的各参与者具有正确的颁发机构或执行它们所执行的特定操作的权限。  
  
   通过 SharePoint 站点通过站点用户组和窗体提交代码上的 Acl 会强制执行前面的规则。 如果作用于消息的用户不在[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户组 （域或本地） 消息修复和新提交会拒绝该消息。  
  
   例如，强制执行三个阶段审批流程的组织可能会定义这三个逻辑角色：Repairers、 性验证程序 （重新生成密钥阶段） 和审批者。 相应地，参与角色的用户必须属于[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户域组。 SharePoint 站点的进一步锁定用户应可组织到逻辑域组 （如 repairers、 验证、 审批者）。  
  
   有关站点用户组的详细信息请参阅[Windows SharePoint Services 安全性](../../adapters-and-accelerators/accelerator-swift/windows-sharepoint-services-security.md)。  
  
- 堆栈中的每个数字签名必须是唯一的。 也就是说，必须通过使用 （相对于同一堆栈中的其他签名） 的唯一数字证书进行每个数字签名。 这可确保消息未经批准的创建/修复消息的人员并没有人批准为多个审批者相同的消息。  
  
  消息修复和新提交到消息创建、 修复、 批准和提交基础结构的每个入口点处添加检查点通过实施严格的安全策略。 这些检查点的消息修复和新提交的核心功能与紧密耦合，并不能绕过。 尽管消息修复和新提交旨在与无缝集成[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体签名功能，它还旨在是安全且足够可靠，以强制执行真实性和 SWIFT 消息，即使保护[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]是不使用消息直接最终用户提交到消息修复和新提交接收终结点 （SharePoint Web 文件夹）。