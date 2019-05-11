---
title: 步骤 6：配置 BizTalk 业务流程服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration server, configuring
- configuring, orchestration servers
ms.assetid: 1eb38fac-264d-4730-b16b-572dbb6fabd9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59b1eea5ca26e951f25ebda75a09941afba6fabf
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530105"
---
# <a name="step-6-configuring-the-biztalk-orchestration-servers"></a>步骤 6：配置 BizTalk 业务流程服务器
本部分提供有关配置 BizTalk 业务流程服务器的指导原则。  
  
### <a name="to-configure-the-biztalk-orchestration-servers"></a>若要配置 BizTalk 业务流程服务器  
  
1. 通过选择添加/删除从启用网络分布式事务处理协调器 (DTC) 访问[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]类别下的应用程序服务器组件。 已启用网络 DTC 客户端访问在[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]前面步骤中的计算机。 有关 DTC 问题故障排除信息 Microsoft 帮助和支持网站上，请参阅以下知识库文章：  
  
   - 如何为进行故障排除 MS DTC 防火墙问题，位于[ http://go.microsoft.com/fwlink/?linkid=48870 ](http://go.microsoft.com/fwlink/?linkid=48870)。  
  
   - 如何使用 DTCTester 工具，位于[ http://go.microsoft.com/fwlink/?linkid=48871 ](http://go.microsoft.com/fwlink/?linkid=48871)。  
  
   - 如果 DTC 防火墙后面，请参阅配置 Microsoft 分布式事务处理协调器 (DTC) 为通过防火墙工作，位于[ http://go.microsoft.com/fwlink/?linkid=48872 ](http://go.microsoft.com/fwlink/?linkid=48872)。  
  
2. 安装 BizTalk Server 的其他软件必备组件安装和配置 BizTalk Server 中所述[安装和业务流程服务器上配置 BizTalk Server](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md)。  
  
3. 安装和配置[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]安装中所述和[安装和配置 BizTalk Accelerator for SWIFT 消息传送服务器上](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)。  
  
   本部分包含：  
  
-   [在业务流程服务器上安装和配置 BizTalk Server](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md)  
  
-   [在业务流程服务器上安装和配置 BizTalk Accelerator for SWIFT](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-orchestration-servers.md)