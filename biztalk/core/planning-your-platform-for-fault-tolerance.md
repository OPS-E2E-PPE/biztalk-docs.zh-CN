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
ms.openlocfilehash: 3564be0d8e49d64b3726f7aca360bfa4042343db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394968"
---
# <a name="planning-your-platform-for-fault-tolerance"></a>规划你的平台容错功能
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]基于 Microsoft Windows 和 Microsoft SQL Server 平台。 BizTalk Server 幸免或从灾难中恢复的能力取决于底层平台幸免或恢复的能力。  
  
 有关业务活动监视 (BAM) 数据库和 MessageBox 数据库，我们建议你以下操作：  
  
- 设置故障转移群集，这是 SQL Server Enterprise Edition 中可用。 故障转移群集，SQL Server 可自动切换到工作服务器从发生故障的服务器的 SQL Server 实例的处理。  
  
   BAM 主导入数据库收集事件数据。 发生灾难时，自上次备份后写入 BAM 主导入数据库的数据将会丢失。 因为没有方法来重新生成丢失的事件，是你启用故障转移群集在 BAM 主导入数据库上尤其重要。  
  
- 使用 SQL Server RAID （独立磁盘冗余阵列），特别是对于 MessageBox 数据库和 BAM 主导入数据库。  
  
  使用以下资源来设计您的 Windows 和 SQL Server 部署以实现容错。 需要时间来了解硬件和服务器冗余技术，如聚类分析和磁盘镜像，以防止服务中断和数据丢失。  
  
- [白皮书：高可用性-Alwayson 技术](http://go.microsoft.com/fwlink/?LinkId=130376)  
  
   "高可用性 – Always On Technologies"白皮书描述 SQL Server 2008 提供的高可用性功能。  
  
- [高可用性解决方案概述](http://go.microsoft.com/fwlink/?LinkId=130377)  
  
   为提高可用性的服务器或数据库的 SQL Server 2008 引入了多个高可用性解决方案。  
  
- [第 15 章-高可用性选项，SQL Server 资源工具包](http://go.microsoft.com/fwlink/?LinkId=24431)  
  
   Microsoft SQL Server 资源工具包涉及范围广泛的管理和部署规划领域。 第 15 章介绍了规划容错和恢复。  
  
- [Windows 部署服务分步指南](http://go.microsoft.com/fwlink/?LinkId=130379)  
  
   包含有关如何在 Windows Server 2008 中使用 Windows 部署服务角色循序渐进指南  
  
- [Windows Server 2003 部署工具包：规划服务器部署](http://go.microsoft.com/fwlink/?LinkId=24433)。  
  
   本书提供了有关设计和部署文件服务器、 打印服务器和中型和大型组织中的终端服务器的规划服务器存储和信息有关的信息。  
  
   您还可用于指导原则在本书中的远程服务器管理的规划、 设计和部署服务器群集和设计和部署网络负载平衡群集中最大化可用性和可伸缩性的服务器。  
  
## <a name="backing-up-your-platform"></a>备份你的平台  
 配置您的系统后，准备你的服务器的完整备份，以便在发生数据丢失时可以快速还原相同的服务器。  
  
 若要备份你的平台，请执行以下技术的每个有案可稽的备份过程：  
  
- Microsoft Windows Server Standard、 Enterprise 或 Datacenter Edition  
  
- Internet 信息服务 (IIS)  
  
- Microsoft SQL Server  
  
- Windows SharePoint Services，它由 Windows SharePoint Services 适配器。  
  
  请遵循"备份 BizTalk Server"可在"BizTalk Server 操作指南"中的建议[核对清单：提供高可用性灾难恢复](http://go.microsoft.com/fwlink/?LinkId=130498)。  
  
  进行全面测试备份和还原过程，并将其放在一个安全的远程位置。  
  
## <a name="see-also"></a>请参阅  
 [备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)