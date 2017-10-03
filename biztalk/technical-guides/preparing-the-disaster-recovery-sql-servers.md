---
title: "准备灾难恢复 SQL Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 44b77fe8-393d-4781-b0b0-5b7f6e50a67b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01e6021b7114b8b57c62dadfe742be1809df0bd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="preparing-the-disaster-recovery-sql-servers"></a>准备灾难恢复 SQL 服务器
可用来创建一组[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库灾难恢复站点中的实例。 若要确保灾难恢复[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库实例可以提供相同级别的性能与生产[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库实例、 灾难恢复[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]应具有类似配置数据库实例硬件和运行的物理计算机的数量[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 在此方案中，[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]将为每个生产配置日志传送[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库实例，将应用于相应[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]在灾难恢复站点的数据库实例。  
  
 密钥[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]日志传送要求是在其中存储数据库文件的生产站点上的驱动器号与匹配在灾难恢复站点，其中还原数据库文件驱动器号。 因此，如果[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库文件组位于 G:\data 在生产环境中、 在目标 (DR) 服务器上，必须有一个 G:\data 目录或还原将失败。  
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]日志传送不支持**RESTORE WITH MOVE** [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]命令。 因此，我们建议在灾难恢复站点的数据库实例名称匹配在生产环境中的数据库实例名称 （默认情况下，实例名称为的文件路径的一部分）。 另一个选项是仅在相应的驱动器号中运行的灾难恢复计算机上创建一个目录[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]以便**还原**操作可以创建该文件中的相同的目录结构中使用生产。  
  
 创建[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]的灾难恢复站点的安全登录名对应到生产站点，因此，事件中，到灾难恢复站点的故障转移是必需的所有所需的安全登录名是目标系统上存在。  
  
 一次安装灾难恢复[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例完成后，执行 master 和 msdb 数据库的完整备份，以便可以还原干净系统中,，切换到灾难恢复站点失败。