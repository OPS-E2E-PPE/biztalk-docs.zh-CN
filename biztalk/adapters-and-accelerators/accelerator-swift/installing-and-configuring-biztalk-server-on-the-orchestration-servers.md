---
title: "上安装和配置 BizTalk Server 业务流程服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Server, installing on orchestration server
- orchestration server, installing BizTalk Server
ms.assetid: 72376a80-1377-4058-9478-fee668b804d0
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18a13d553e31739c959ff6baf317240c3c268ecc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="installing-and-configuring-biztalk-server-on-the-orchestration-servers"></a>安装和配置 BizTalk Server 业务流程服务器上
本部分介绍如何安装和配置 BizTalk Server 以用于与业务流程服务器运行消息修复/新建提交业务流程和 FIN 修复和对帐业务流程。  
  
### <a name="to-install-and-configure-biztalk-server-on-the-orchestration-server"></a>若要安装和配置 BizTalk Server 业务流程服务器上  
  
1.  执行的自定义安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]选择除 EDI、 人工工作流服务 （工作流服务） 和 MRSR，以外的所有功能，除非所需的其他应用程序。  
  
    > [!NOTE]
    >  在单台计算机部署中，此计算机是为运行 HTTP 前端服务和 BizTalk 消息传送服务器在同一台计算机。  
  
2.  执行配置[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
    > [!NOTE]
    >  配置 BizTalk 业务流程服务器时，请考虑以下准则：  
  
    -   此服务器要求只有一个网络适配器连接到[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]计算机。 它不需要另一个网络适配器，如 HTTP 前端服务器或消息服务器的公共端并这使其更利于防止黑客攻击来自 Internet 或 intranet/extranet 的企图。  
  
3.  安装所需的任何其他修补程序[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]为可安装指南中。