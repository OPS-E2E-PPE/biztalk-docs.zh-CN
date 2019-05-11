---
title: 准备灾难恢复 SQL Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44b77fe8-393d-4781-b0b0-5b7f6e50a67b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 036f5ab2510744ad0f1dc30e36e6135ed5ac0d1c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398524"
---
# <a name="preparing-the-disaster-recovery-sql-servers"></a>准备灾难恢复 SQL Server
设置来创建一个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库灾难恢复站点中的实例。 若要确保灾难恢复[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库实例可以提供相同级别的性能与生产[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库实例、 灾难恢复[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]应具有类似配置数据库实例硬件和物理计算机运行的数量[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 在此方案中，BizTalk Server 将为每个生产配置日志传送[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]要将应用于相应的数据库实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]在灾难恢复站点的数据库实例。  
  
 BizTalk Server 日志传送要求的密钥是存储数据库文件的生产站点上的驱动器号，匹配在灾难恢复站点，其中还原数据库文件驱动器号。 因此，如果[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库文件组位于 G:\data 在生产环境中，目标 (DR) 服务器上必须有一个 G:\data 目录或还原会失败。  
  
 BizTalk Server 日志传送不支持**RESTORE WITH MOVE** [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]命令。 因此，我们建议在灾难恢复站点的数据库实例名称匹配在生产环境中的数据库实例名称 （默认情况下，实例名称是文件路径的一部分）。 另一个选项是只需上创建一个目录中运行的灾难恢复计算机的相应驱动器号[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，以便**还原**操作可以创建该文件在相同的目录结构中使用生产环境。  
  
 创建[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]的灾难恢复站点的安全登录名对应于生产站点，以便在的故障转移到灾难恢复站点是必需的所有必需的安全登录名均存在于目标系统。  
  
 一次的灾难恢复安装[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例已完成，请执行 master 和 msdb 数据库的完整备份，以便可以还原干净的系统，在切换到灾难恢复站点失败的事件。