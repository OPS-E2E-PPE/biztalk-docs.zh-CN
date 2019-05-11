---
title: 如何配置 BTS_BACKUP_USERS 角色以存档和清除 BizTalk 跟踪数据库中的数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- purging, BTS_BACKUP_USERS role
- Tracking database, purging
- BTS_BACKUP_USERS role
- DTA Purge and Archive job
- archiving [Tracking database], BTS_BACKUP_USERS role
- archiving [Tracking database], DTA Purge and Archive job
- Tracking database, BTS_BACKUP_USERS role
- Tracking database, archiving
- purging, DTA Purge and Archive job
ms.assetid: c27aad2a-5788-4236-b5eb-ca730bf79851
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3717372e4c421636c601f7b34d1a6b2667a4a1ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391452"
---
# <a name="how-to-configure-the-btsbackupusers-role-for-archiving-and-purging-data-from-the-biztalk-tracking-database"></a>如何配置 BTS_BACKUP_USERS 角色以存档和清除 BizTalk 跟踪数据库中的数据
DTA 清除和存档 (BizTAlkDTADb) 作业通常使用登录的 SQL Server 代理服务帐户用户的凭据运行。 为了提高安全性，但是，你可以配置 DTA 清除和存档 (BizTalkDTADb) 作业使用的是 BTS_BACKUP_USERS 角色的成员的帐户的凭据运行。 这有助于防止特权提升，通过运行具有基本权限的帐户下的 SQL Server 代理作业。  
  
## <a name="prerequisites"></a>先决条件  
 您必须是 SQL Server sysadmin 固定服务器角色的成员才能执行此过程的帐户登录。  
  
### <a name="to-configure-the-btsbackupusers-role-for-archiving-and-purging-data-from-the-biztalk-tracking-database"></a>若要配置 BTS_BACKUP_USERS 角色以存档和清除 BizTalk 跟踪数据库中的数据  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP2**，然后单击**SQL Server Management Studio**。  
  
2.  在中**连接到服务器**对话框中，指定 BizTalk 跟踪 (BizTalkDTADb) 数据库所在的 SQL 服务器和相应的验证类型的名称，然后单击**Connect**到连接到相应的 SQL Server。  
  
3.  在中**Microsoft SQL Server Management Studio**，双击**BizTalkDTADb**，双击**安全**，双击**角色**，和然后双击**数据库角色**。  
  
4.  在中**对象资源管理器详细信息**窗格中，双击**BTS_BACKUP_USERS**。  
  
5.  在中**数据库角色属性-BTS_BACKUP_USERS**对话框中的**此角色的成员**，单击**添加**。  
  
6.  在中**选择数据库用户或角色**对话框中，输入具有 SQL Server 代理服务凭据的用户帐户，然后单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)