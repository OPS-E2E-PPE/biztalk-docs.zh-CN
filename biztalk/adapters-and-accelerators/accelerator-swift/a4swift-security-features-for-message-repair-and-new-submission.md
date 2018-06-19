---
title: A4SWIFT 消息修复和新提交的安全功能 |Microsoft 文档
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
ms.openlocfilehash: 00170fcdca39de36290e73779881a5d697be8010
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208165"
---
# <a name="a4swift-security-features-for-message-repair-and-new-submission"></a>A4SWIFT 消息修复和新提交的安全功能
[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]提供创建 SWIFT 消息、 修复、 重新生成密钥验证和批准了现成可用的功能。 业务用户创建、 编辑和查看的使用 SWIFT 消息[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]，它提供图形表示形式和用户界面的财务 (FIN) 消息。 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]从由 A4SWIFT 运行时生成的 XML 呈现条目/修复/重新生成密钥验证窗体和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 A4SWIFT 提供[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]用于每个 FIN 模板消息类型 （基于相应的 A4SWIFT XSD 架构），以便你可以打开在任何 SWIFT FIN 消息类型[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]。 A4SWIFT 提供以下功能以帮助安全。  
  
## <a name="infopath-forms"></a>InfoPath 窗体  
 通过[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]提供通过 A4SWIFT，业务用户提交并检索 SWIFT 使用 FormGenerator 实用程序生成的窗体消息到和从收件箱和发件箱上实现安全的 Windows SharePoint Services Web 文件夹。 [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]Web 文件夹的安全性提供完全由[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]使用文件系统访问控制列表 (Acl)[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]身份验证，和 Internet 信息服务 (IIS) 安全功能。 "在网络"时受保护的数据是之间[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]Web 文件夹和[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]通过安全套接字层 (SSL) 和 HTTPS 传输协议。  
  
 A4SWIFT[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]来创建窗体为"不受信任。" 此状态提供最高级别的安全。 有关受信任和不受信任的详细信息，请参阅[InfoPath 安全](../../adapters-and-accelerators/accelerator-swift/infopath-security.md)。  
  
## <a name="runtime-service"></a>运行时服务  
 A4SWIFT 提供的运行时 （作为 BizTalk 业务流程实现） 的服务进行身份验证，验证、 处理和路由 SWIFT 消息之间的 SharePoint Web 文件夹、 消息修复/条目业务流程、 后端系统，并最终，到 SWIFT网络。 此运行时服务被称为 A4SWIFT 消息修复和新的提交。  
  
## <a name="secure-messages"></a>安全消息  
 存储和传递 SWIFT 消息之间[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]， [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]，并消息修复和新提交受基础服务 ([!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]，IIS， [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]) 和传输协议 （SSL、 HTTPS）。 但是，消息创建、 修复、 批准和提交基础结构组成的消息修复和新提交[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]，和[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]所需的其他用户级安全，以强制执行真实性和 SWIFT 消息的保护由最终用户处理。  
  
 A4SWIFT 还定义并实现用户级安全语义来确保 SWIFT 消息进行修改和提交只能由受信任和授权的用户，并且不更改或篡改提交在异步步骤期间该消息数据处理 （例如，在等待用户干预的 SharePoint Web 文件夹中存在消息）。 调整和 choreographed 在工作站上的安全功能 (通过[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]) 和服务器 （通过 A4SWIFT 消息修复和新的提交） 强制实施这些用户级安全策略。