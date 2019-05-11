---
title: 步骤 5：配置 BizTalk 消息服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, BizTalk Messaging servers
- BizTalk Messaging servers, configuring
ms.assetid: 598d336d-b006-4d02-9249-e9d6d9b6b7b5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72211a5570d40e1eaae7ad3974496937ca9aed2a
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530086"
---
# <a name="step-5-configuring-the-biztalk-messaging-servers"></a>步骤 5：配置 BizTalk 消息服务器
本部分提供有关配置 BizTalk 消息传送服务器的指导原则。  
  
### <a name="to-configure-the-biztalk-messaging-servers"></a>若要配置 BizTalk 消息传送服务器  
  
1. 通过选择添加/删除从启用网络分布式事务处理协调器 (DTC) 访问[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]类别下的应用程序服务器组件。 已启用网络 DTC 客户端访问在[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]前面步骤中的计算机。 有关 DTC 问题故障排除信息 Microsoft 帮助和支持网站上，请参阅以下知识库文章：  
  
   - 如何为进行故障排除 MS DTC 防火墙问题，位于[ http://go.microsoft.com/fwlink/?linkid=48870 ](http://go.microsoft.com/fwlink/?linkid=48870)。  
  
   - 如何使用 DTCTester 工具，位于[ http://go.microsoft.com/fwlink/?linkid=48871 ](http://go.microsoft.com/fwlink/?linkid=48871)。  
  
   - 如果 DTC 防火墙后面，请参阅"配置 Microsoft 分布式事务处理协调器 (DTC) 为通过防火墙工作"，位于[ http://go.microsoft.com/fwlink/?linkid=48872 ](http://go.microsoft.com/fwlink/?linkid=48872)。  
  
2. 配置并验证网络负载平衡在 biztalk 接收服务器中所述[步骤 2:在服务器上配置 NLB](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md)。  
  
3. 安装和配置[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]中所述[安装和配置 BizTalk Accelerator for SWIFT 消息传送服务器上](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)。  
  
   本部分包含：  
  
-   [在消息服务器上安装和配置 BizTalk Server](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-messaging-server.md)  
  
-   [在消息服务器上安装和配置 BizTalk Accelerator for SWIFT](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)