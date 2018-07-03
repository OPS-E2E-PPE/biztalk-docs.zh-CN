---
title: 硬件和部署的软件要求 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, hardware requirements
- deploying, software requirements
ms.assetid: 1dd9c4bb-b724-4195-8496-eff95cd1548a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f61a8b66f455aeffee1b5416ebb5911be61fdbec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984654"
---
# <a name="hardware-and-software-requirements-for-deployment"></a>硬件和软件要求的部署
下表列出了硬件和软件建议和规定的部署体系结构中每个服务器的要求。 有关配置所需的软件的详细信息，请参阅[部署你的服务器](../../adapters-and-accelerators/accelerator-swift/deploying-your-servers.md)。  

 对于所有服务器类型，选择硬盘空间、 处理器时钟速度、 和的随机存取内存 (RAM) 量基于当前和预计技术要求 (如中所述[步骤 1： 安装基础平台](../../adapters-and-accelerators/accelerator-swift/step-1-installing-the-base-platform.md)).  


|                    “服务器”                    |                                                                                                                                           建议的硬件要求                                                                                                                                            |                                                                                                                                                   软件要求                                                                                                                                                    |
|----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|             域控制器             |                                                                                                                                             -1 的网络适配器                                                                                                                                             |                                       Microsoft Windows Server 2012 R2 或 2012<br />Microsoft[!INCLUDE[btsAD](../../includes/btsad-md.md)]服务器<br />-域名服务器 (DNS)                                       |
|           Microsoft SQL server            | -2 个网络适配器<br />可选： 对于存储区域网络 (SAN) 磁盘中，选择所需的平均吞吐量、 峰值吞吐量和峰值吞吐量时间加上的硬盘空间的平均消息大小。 SAN 应分为三个驱动器： 数据、 事务日志和仲裁。 |                                                                        Microsoft Windows Server 2012 R2 或 2012<br />-   [!INCLUDE[SQLServer2008or2005](../../includes/sqlserver2008or2005-md.md)]                                                                         |
|       BizTalk server 消息传送        |                                                                                                                                            -2 个网络适配器                                                                                                                                             |                                                  Microsoft Windows Server 2012 R2 或 2012<br />BizTalk Server<br />-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]                                                   |
| BizTalk HTTP 前端服务器 （MRSR 站点） |                                                                                                                                            -2 个网络适配器                                                                                                                                             | Microsoft Windows Server 2012 R2 或 2012<br />Internet 信息服务 (IIS)<br />-启用了路由消息队列服务<br />BizTalk Server<br />-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] |
|     业务流程的 BizTalk 服务器     |                                                                                                                                             -1 的网络适配器                                                                                                                                             |                                                  Microsoft Windows Server 2012 R2 或 2012<br />BizTalk Server<br />-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]                                                   |

