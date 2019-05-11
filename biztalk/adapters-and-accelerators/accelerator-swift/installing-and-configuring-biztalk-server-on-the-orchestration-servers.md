---
title: 安装和配置 BizTalk Server 业务流程服务器上 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Server, installing on orchestration server
- orchestration server, installing BizTalk Server
ms.assetid: 72376a80-1377-4058-9478-fee668b804d0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4b1883199408b503cdbd79b276257bec604ab60
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377726"
---
# <a name="installing-and-configuring-biztalk-server-on-the-orchestration-servers"></a>安装和配置 BizTalk Server 业务流程服务器上
本部分介绍如何安装和配置 BizTalk Server 以便用作运行消息修复 / 新建提交业务流程以及 FIN 修复和对帐业务流程的业务流程服务器。  

### <a name="to-install-and-configure-biztalk-server-on-the-orchestration-server"></a>若要安装和配置 BizTalk Server 业务流程服务器上  

1. 执行的自定义安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]选择除 EDI、 工作流服务 (HWS) 和 MRSR，之外的所有功能，除非所需的其他应用程序。  

   > [!NOTE]
   >  在单台计算机部署中，此计算机是运行 HTTP 前端服务和 BizTalk 消息传送服务器所在的计算机。  

2. 执行的配置[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  

   > [!NOTE]
   >  配置 BizTalk 业务流程服务器时，请考虑以下准则：  

   - 此服务器要求只有一个网络适配器，以将其连接到[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]计算机。 它不需要像 HTTP 前端服务器或消息服务器的公共一端的另一个网络适配器并这使其更加安全，免受黑客攻击企图来自 Internet 或内部和外部。  

3. 安装所需的任何其他修补程序[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]安装指南中为可用。
