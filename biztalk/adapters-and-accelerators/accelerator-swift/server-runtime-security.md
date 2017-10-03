---
title: "服务器运行时安全性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, server runtime
- servers, security
- servers, runtime
ms.assetid: 40f5ca3e-d9d3-4543-bd38-82283c343b76
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a5979162a521185b87977191c9d709fb754b1ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="server-runtime-security"></a>服务器运行时安全性
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]消息修复和新提交控制的业务用户、 后端系统和 SWIFT 网络终结点之间的 SWIFT 消息流的安全和确定性的方式。 它由业务用户提交的消息进行身份验证、 验证数据和业务规则正确性的消息和将消息路由到后端系统或从而最终提交到 SWIFT 网络。 有关数字证书的详细信息，请参阅"加密和签名证书"MSDN 库网站上在[http://go.microsoft.com/fwlink/?linkid=50285](http://go.microsoft.com/fwlink/?linkid=50285)。  
  
 消息修复和新提交是[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]orchestration 应用程序，托管以及在中执行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安全上下文。 作为保护[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]前面所述的安全功能。 消息修复和新提交还定义并强制实施 SWIFT 消息创建、 修复、 批准和提交到特定的用户级安全策略，如下所示：  
  
-   所有消息，新的或修复后，都提交到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]通过消息修复和新提交必须源自受信任的用户。  
  
-   创建或修复消息的受信任的用户必须具有正确授权和权限。 批准或拒绝的消息的受信任的用户必须具有正确授权和权限。  
  
-   必须由大量已知的受信任的用户审批所有消息。 必须是唯一的消息创建者、 repairer，和审批者链中的每个受信任的用户-相同的用户不能创建或修复和批准或拒绝消息。 同一个用户无法输入多个批准或拒绝对一个多步骤批准过程，在单个消息的决策。 您无法批准您自己创建的或修复后的消息，也可以批准为多个审批者，同一消息。  
  
-   在批准过程中，不能更改一条消息 （即，一条消息不能进行更改后原始提交到消息修复和新的提交，为新的或修复后的消息）。  
  
-   在重新生成密钥验证阶段期间改变的消息必须精确匹配原始消息 （创建或修复）。  
  
 若要强制这些安全语义，消息修复和新的提交，请验证每个接收，在创建或修复批准提交处理的每个阶段的 XML 消息中嵌入的数字签名。 消息修复和新提交数字签名验证将执行下列检查。 如果一个或多个这些检查失败，消息修复和新提交停止，将一直保留到消息框中和安全故障事件日志中记录：  
  
-   XML 消息必须进行数字签名，因此必须包含相应的数字签名。  
  
-   必须通过使用受信任的数字证书进行每个工作流中使用的数字签名。 这可确保消息创建者、 repairer、 验证和审批者是受信任。  
  
-   每个受信任的数字证书必须属于[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]有中具有逻辑机构或在内执行操作的权限的域组的成员身份的域用户[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。 这可确保在创建或修复批准提交过程中的每个参与者具有正确的颁发机构或权限，才能执行它们所执行的特定操作。  
  
     在前面的规则是通过 SharePoint 站点通过站点用户组和窗体提交代码上的 Acl 强制的。 如果作用于消息的用户不在[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户组 （域或本地），消息修复和新提交会拒绝该消息。  
  
     例如，强制执行三个阶段审批过程的组织可以定义以下三种逻辑角色： Repairers、 验证程序 （重新生成密钥阶段） 和审批者。 相应地，参与角色的用户必须属于[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户域组。 到 SharePoint 站点的进一步锁定用户应组织到逻辑域组 （如 repairers、 验证、 审批者） 中。  
  
     有关站点用户组的详细信息请参阅[Windows SharePoint Services 安全](../../adapters-and-accelerators/accelerator-swift/windows-sharepoint-services-security.md)。  
  
-   堆栈中的每个数字签名必须是唯一的。 也就是说，必须通过使用 （相对于同一堆栈中的其他签名） 的唯一数字证书进行每个数字签名。 这可确保消息未被批准的人员创建/修复消息，且没有人批准作为多个审批者，同一消息。  
  
 消息修复和新提交有一定严格的安全策略，通过在消息创建、 修复、 批准和提交基础结构每个入口点的检查点。 这些检查点紧密关联的消息修复和新提交的核心功能，并且不能绕过。 虽然消息修复和新提交旨在与无缝集成[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]表单签名功能，它还旨在作为安全且足够可靠，以强制执行真实性和保护 SWIFT 消息即使[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]是未使用和消息提交直接的消息修复的最终用户和新提交接收终结点 （SharePoint Web 文件夹）。