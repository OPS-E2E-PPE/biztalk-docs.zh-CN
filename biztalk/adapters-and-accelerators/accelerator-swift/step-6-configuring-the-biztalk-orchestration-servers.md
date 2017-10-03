---
title: "步骤 6： 配置 BizTalk 业务流程服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestration server, configuring
- configuring, orchestration servers
ms.assetid: 1eb38fac-264d-4730-b16b-572dbb6fabd9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acf5cb36908031f9256f25dd68435003b74d2633
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-configuring-the-biztalk-orchestration-servers"></a>步骤 6： 配置 BizTalk 业务流程服务器
本节提供有关将 BizTalk 业务流程服务器配置的准则。  
  
### <a name="to-configure-the-biztalk-orchestration-servers"></a>若要配置 BizTalk 业务流程服务器  
  
1.  通过选择添加/删除从启用网络分布式事务处理协调器 (DTC) 访问[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]应用程序服务器类别下的组件。 在上启用网络 DTC 客户端访问[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]前面步骤中的计算机。 请参阅以下知识库文章[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]有关 DTC 问题疑难解答信息的帮助和支持网站：  
  
    -   如何为解决 MS DTC 防火墙问题，位于[http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870)。  
  
    -   如何为使用 DTCTester 工具，位于[http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871)。  
  
    -   如果 DTC 位于防火墙后面，请参阅配置[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]分布式事务处理协调器 (DTC) 到工作通过防火墙，位于[http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872)。  
  
2.  安装其他软件的先决条件 BizTalk Server 中，以及安装和配置[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]中所述，[安装和业务流程服务器上配置 BizTalk Server](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md)。  
  
3.  安装和配置[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]安装中所述和[安装和配置 BizTalk Accelerator for 消息传送服务器上的 SWIFT](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)。  
  
 本部分包含：  
  
-   [安装和配置 BizTalk Server 业务流程服务器上](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md)  
  
-   [安装和配置 BizTalk Accelerator for SWIFT Orchestration 服务器上](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-orchestration-servers.md)