---
title: 消息修复和新提交的 A4SWIFT 安全功能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, messages
- A4SWIFT, security
- security, A4SWIFT
- messages, security
ms.assetid: c34bcba7-fecd-4e2f-ab49-a6ccfd96198b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82b49f1f0a99e52e5505f2a3d8260bc03d9c08bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378700"
---
# <a name="a4swift-security-features-for-message-repair-and-new-submission"></a>消息修复和新提交的 A4SWIFT 安全功能
[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] 用于 SWIFT 消息的创建、 修复、 重新生成密钥验证和批准提供开箱工具。 业务用户创建、 编辑和查看使用的是 Microsoft 的 SWIFT 消息[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]，财务 (FIN) 消息提供的图形表示形式和用户界面。 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 从 A4SWIFT 运行时生成的 XML 呈现条目/修复/重新生成密钥验证窗体和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 提供了 A4SWIFT[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]模板为每个 FIN 消息类型 （基于相应的 A4SWIFT XSD 架构），以便你可以打开在任何 SWIFT FIN 消息类型[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]。 A4SWIFT 提供以下功能来帮助安全。  
  
## <a name="infopath-forms"></a>InfoPath Forms  
 通过[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体生成带有 FormGenerator 实用程序，提供通过 A4SWIFT，业务用户提交，并检索 SWIFT 消息到和从收件箱和发件箱上实现安全的 Windows SharePoint Services Web 文件夹。 [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)] Web 文件夹的安全性完全由 Microsoft 提供[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]使用文件系统访问控制列表 (Acl)、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]身份验证，以及 Internet 信息服务 (IIS) 安全功能。 数据时"上在线"受保护之间[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]Web 文件夹和[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]通过安全套接字层 (SSL) 和 HTTPS 传输协议。  
  
 A4SWIFT[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]来创建窗体为"不受信任。" 此状态提供最高级别的安全性。 有关受信任和不受信任的详细信息，请参阅[InfoPath 安全性](../../adapters-and-accelerators/accelerator-swift/infopath-security.md)。  
  
## <a name="runtime-service"></a>运行时服务  
 A4SWIFT 提供的运行时服务 （作为 BizTalk 业务流程实现） 进行身份验证，验证、 处理和路由之间的 SharePoint Web 文件夹、 消息修复/登记业务流程、 后端系统和从根本上讲，到 SWIFT 的 SWIFT 消息网络。 此运行时服务被称为 A4SWIFT 消息修复和新提交。  
  
## <a name="secure-messages"></a>安全消息  
 存储和传递的 SWIFT 消息之间[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]， [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]，以及消息修复和新提交保护的基础服务 ([!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]，IIS， [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]) 和传输协议 （SSL、 HTTPS）。 但是，消息创建、 修复、 批准和提交基础结构组成的消息修复和新提交[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]，和[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]需要额外的用户级安全以强制执行真实性和 SWIFT 消息的保护处理由最终用户。  
  
 A4SWIFT 还定义和实现用户级安全语义来确保 SWIFT 消息修改并提交只能由受信任且获得授权的用户，并不更改或在异步提交的步骤期间篡改该消息数据处理 （例如，虽然消息坐在等待用户干预的 SharePoint Web 文件夹中）。 协调和编排在工作站上的安全功能 (通过[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]) 和 （通过 A4SWIFT 消息修复和新提交） 服务器强制实施这些用户级安全策略。