---
title: "将权限分配 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user accounts, assigning permissions
- security, user accounts
- document library, new messages
- document library, unparsed
- messages, document library
- privileges
- permissions
- unparsed document library
- security, permissions
ms.assetid: cee44240-aa00-4080-9e7f-728b2421102b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a980fde1a4aea5d2e741fa576e55e659c0835f9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="assigning-rights"></a>分配权限
应在文档库，用于在前面的主题中创建每个站点组上授予以下权限：  
  
|文档库|站点组|要应用的自定义文档库的权限|  
|----------------------|-----------------|--------------------------------------------------|  
|模板文档库|Payments_Creators<br /><br /> Payments_Repairers<br /><br /> Payments_Approvers|查看项|  
|未分析 （下面的详细信息）|Payments_Repairers|查看、 插入、 编辑、 删除项|  
|新 SWIFT MT 消息 （下面详细信息）|Payments_Creators|查看、 插入、 编辑、 删除项|  
|新 SWIFT MX 消息 （下面详细信息）|Payments_Creators|查看、 插入、 编辑、 删除项|  
|Payments_Repairers|Payments_Repairers|查看、 插入、 编辑、 删除项|  
|Payments_Approvers|Payments_Approvers|查看、 插入、 编辑、 删除项|  
|[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Outbox|Payments_Creators<br /><br /> Payments_Repairers<br /><br /> Payments_Approvers|查看、 插入、 编辑、 删除项|  
  
## <a name="unparsed-document-library"></a>未分析的文档库  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]失败以特殊方式分析的消息，处理消息修复过程。 未分析的消息 （不能转换为 XML 的消息） 都路由到单一未分析的消息文档库中。 未分析的文档库应被限制以允许仅特定用户，而不是整个组，无法访问该文件夹。 这将确保未分析的文件夹是尽可能安全。  
  
 用户有权修复未分析的消息在 MMC 配置控制台中，定义的至少一个部门需要修复角色的权限，还需要在 NT 组中注册[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户组。  
  
## <a name="new-swift-mt-mx-messages-document-library"></a>新 SWIFT MT / MX 消息文档库  
 在部署 MRSR 网站时创建新 SWIFT MT 消息和新 SWIFT MX 消息文档库。 新 SWIFT MT 消息和新 SWIFT MX 消息文档库中存储新 SWIFT XML 模板或"样本"消息。 这些消息可用于创建新 SWIFT InfoPath XML 格式表示的消息。 这些消息都上载到新 SWIFT MT 消息和新 SWIFT MX 消息文档库由用户通过单击文档库中的上载按钮。 你可以进一步分发新 SWIFT 消息模板以限制对指定的用户访问。 为此，首先要创建新的文档库中，，然后将复制所需的文档库的 XML 模板。  
  
 有关 FormPublish 工具的详细信息，请参阅[FormPublish 工具](http://msdn.microsoft.com/en-us/09a6ed31-5917-4776-9a5e-955af440cdac)工具部分中。