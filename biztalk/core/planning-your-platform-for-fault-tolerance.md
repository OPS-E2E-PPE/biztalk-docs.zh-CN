---
title: 规划你的平台容错 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, BizTalk Server
- MessageBox database, fault tolerance
- clustering, fault tolerance
- SQL Server RAID
- databases [BAM], fault tolerance
- BizTalk Server, planning
- fault tolerance
- clustering, fail-overs
- planning, fault tolerance
- Primary Import database [BAM]
- BizTalk Server, backing up
- fault tolerance, planning
- planning, BizTalk Server
- Primary Import database [BAM], fault tolerance
- fail-over clustering
ms.assetid: 512ed6b8-db1e-434a-8009-63e952cf5500
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5ddc4565449171c71685bcddd2c68b699f5113b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007486"
---
# <a name="planning-your-platform-for-fault-tolerance"></a>规划你的平台容错功能
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 是基于 Microsoft Windows 和 Microsoft SQL Server 平台建立的。 BizTalk Server 幸免于灾难或从灾难中恢复的能力取决于其底层平台幸免或恢复的能力。  
  
 有关业务活动监视 (BAM) 数据库和 MessageBox 数据库，我们建议你以下操作：  
  
- 建立故障转移群集，此功能在 SQL Server Enterprise Edition 中可用。 使用故障转移群集，SQL Server 可自动将 SQL Server 实例的处理从故障服务器切换到正常工作的服务器。  
  
   BAM 主导入数据库收集事件数据。 在系统发生灾难时，自上次备份后写入 BAM 主导入数据库的数据将会丢失。 由于无法重新生成这些丢失的事件，因此，在 BAM 主导入数据库上启用故障转移群集是十分重要的。  
  
- 尤其对于 MessageBox 数据库和 BAM 主导入数据库，请使用 SQL Server RAID（独立磁盘冗余阵列）。  
  
  使用以下资源来设计 Windows 和 SQL Server 部署以实现容错。 您需要了解硬件和服务器冗余技术（例如群集和磁盘镜像），以防止服务故障和数据丢失。  
  
- [白皮书： 高可用性-Alwayson 技术](http://go.microsoft.com/fwlink/?LinkId=130376)  
  
   "高可用性 – Always On Technologies"白皮书描述 SQL Server 2008 提供的高可用性功能。  
  
- [高可用性解决方案概述](http://go.microsoft.com/fwlink/?LinkId=130377)  
  
   介绍了 SQL Server 2008 中若干改善服务器或数据库可用性的高可用性解决方案。  
  
- [第 15 章-高可用性选项，SQL Server 资源工具包](http://go.microsoft.com/fwlink/?LinkId=24431)  
  
   Microsoft SQL Server 资源工具包涉及了广泛的管理及部署规划领域的内容。 第 15 章介绍了如何针对容错和恢复进行规划。  
  
- [Windows 部署服务分步指南](http://go.microsoft.com/fwlink/?LinkId=130379)  
  
   包含有关如何在 Windows Server 2008 中使用 Windows 部署服务角色的循序渐进指南  
  
- [Windows Server 2003 部署工具包： 规划服务器部署](http://go.microsoft.com/fwlink/?LinkId=24433)。  
  
   本书介绍了有关规划服务器存储的信息，以及有关设计和部署大、中型组织中的文件服务器、打印服务器和终端服务器的信息。  
  
   还可使用本书中的指导来规划远程服务器管理、设计和部署服务器群集与网络负载平衡群集，从而最大限度地提高服务器的可用性和可伸缩性。  
  
## <a name="backing-up-your-platform"></a>备份您的平台  
 对系统进行配置后，准备服务器的完整备份，以便在数据丢失的情况下可以快速还原相同的服务器。  
  
 若要备份平台，请对以下各种技术执行所记录的备份过程：  
  
- Microsoft Windows Server Standard、Enterprise 或 Datacenter Edition  
  
- Internet 信息服务 (IIS)  
  
- Microsoft SQL Server  
  
- Windows SharePoint Services，由 Windows SharePoint Services 适配器使用。  
  
  请遵循"备份 BizTalk Server"可在"BizTalk Server 操作指南"中的建议[清单： 灾难恢复与提高可用性](http://go.microsoft.com/fwlink/?LinkId=130498)。  
  
  对备份和还原过程进行彻底测试，然后将其放置于安全的远程位置。  
  
## <a name="see-also"></a>请参阅  
 [备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)