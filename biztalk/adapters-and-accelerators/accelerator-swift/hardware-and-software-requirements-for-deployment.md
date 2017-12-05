---
title: "硬件和部署的软件要求 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, hardware requirements
- deploying, software requirements
ms.assetid: 1dd9c4bb-b724-4195-8496-eff95cd1548a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e772c409533e5ef6e3fedd13e3db7acbfdc572c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="hardware-and-software-requirements-for-deployment"></a>硬件和软件要求的部署
下表列出的硬件和软件的建议和规定的部署体系结构中每个服务器的要求。 有关配置所需的软件的详细信息，请参阅[部署你的服务器](../../adapters-and-accelerators/accelerator-swift/deploying-your-servers.md)。  
  
 对于所有的服务器类型，选择硬盘磁盘空间、 处理器时钟速度和基于当前和预期技术要求随机存取内存 (RAM) 量 (中所述[步骤 1： 安装基础平台](../../adapters-and-accelerators/accelerator-swift/step-1-installing-the-base-platform.md)).  
  
|Server|硬件建议|软件要求|  
|------------|------------------------------|---------------------------|  
|域控制器|-1 个网络适配器|-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server 2012 R2 或 2012<br />-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsAD](../../includes/btsad-md.md)]服务器<br />-域名服务器 (DNS)|  
|Microsoft SQL server|-2 的网络适配器<br />可选： 对于存储区域网络 (SAN) 磁盘中，选择所需的平均吞吐量、 最高吞吐量和峰值吞吐量时间加上的硬盘空间的平均消息大小。 SAN 应分成三个驱动器： 数据、 事务日志和仲裁。|-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server 2012 R2 或 2012<br />-   [!INCLUDE[SQLServer2008or2005](../../includes/sqlserver2008or2005-md.md)]|  
|消息传送的 BizTalk 服务器|-2 的网络适配器|-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server 2012 R2 或 2012<br />-BizTalk Server<br />-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]|  
|BizTalk HTTP 前端服务器 （MRSR 站点）|-2 的网络适配器|-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server 2012 R2 或 2012<br />-Internet Information Services (IIS)<br />已启用路由的消息队列服务<br />-BizTalk Server<br />-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]|  
|业务流程的 BizTalk 服务器|-1 个网络适配器|-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server 2012 R2 或 2012<br />-BizTalk Server<br />-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]|