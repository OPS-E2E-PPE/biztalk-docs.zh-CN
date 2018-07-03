---
title: 将权限分配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b736fc7eb84964f9c0e74a3c319c9de1f3a3a44
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989670"
---
# <a name="assigning-rights"></a>分配权限
应在文档库，用于在上一主题中创建每个站点组上授予以下权限：  


|                                         文档库                                         |                                   站点组                                   | 要应用的自定义文档库的权限 |
|--------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------|----------------------------------------------|
|                                    模板文档库                                    | Payments_Creators<br /><br /> Payments_Repairers<br /><br /> Payments_Approvers |                  查看项                  |
|                                     未分析 （下面的详细信息）                                     |                               Payments_Repairers                                |       查看、 插入、 编辑和删除项       |
|                              新 SWIFT MT 消息 （下面的详细信息）                               |                                Payments_Creators                                |       查看、 插入、 编辑和删除项       |
|                              新 SWIFT MX 消息 （下面的详细信息）                               |                                Payments_Creators                                |       查看、 插入、 编辑和删除项       |
|                                        Payments_Repairers                                        |                               Payments_Repairers                                |       查看、 插入、 编辑和删除项       |
|                                        Payments_Approvers                                        |                               Payments_Approvers                                |       查看、 插入、 编辑和删除项       |
| [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Outbox | Payments_Creators<br /><br /> Payments_Repairers<br /><br /> Payments_Approvers |       查看、 插入、 编辑和删除项       |

## <a name="unparsed-document-library"></a>未分析的文档库  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]消息修复过程处理的失败分析以特殊方式的消息。 未分析的消息 （不能转换为 XML 的消息） 被路由到单个的未分析的消息文档库。 未分析的文档库应限制为允许仅特定人员，而不是整个组，若要访问的文件夹。 这将确保未分析的文件夹是尽可能安全。  

 已修复未分析的消息的权限的用户定义在 MMC 配置控制台中，至少一个部门需要修复角色中的权限，并且还需要 NT 组中注册[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户组。  

## <a name="new-swift-mt-mx-messages-document-library"></a>新的 SWIFT MT / MX 消息文档库  
 在部署 MRSR 网站的时创建新的 SWIFT MT 消息和新 SWIFT MX 消息文档库。 新 SWIFT MT 消息和新 SWIFT MX 消息文档库中存储新 SWIFT XML 模板或"样本"消息。 这些消息可用于创建新的 SWIFT InfoPath XML 格式表示的消息。 这些消息上传的新 SWIFT MT 消息和新 SWIFT MX 消息文档库中由用户通过单击文档库中的上传按钮。 您可以进一步分发新 SWIFT 消息模板来限制对指定的用户访问。 为此，您首先创建一个新的文档库，并复制所需的文档库的 XML 模板。  

 有关 FormPublish 工具的详细信息，请参阅[FormPublish 工具](http://msdn.microsoft.com/09a6ed31-5917-4776-9a5e-955af440cdac)工具部分中。