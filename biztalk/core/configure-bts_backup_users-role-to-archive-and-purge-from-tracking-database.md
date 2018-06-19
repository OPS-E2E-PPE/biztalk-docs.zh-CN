---
title: 如何配置用于存档和清除数据从跟踪数据库 BizTalk BTS_BACKUP_USERS 角色 |Microsoft 文档
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
ms.openlocfilehash: 923fb083f3755259ab2176541213d1637ce872c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232445"
---
# <a name="how-to-configure-the-btsbackupusers-role-for-archiving-and-purging-data-from-the-biztalk-tracking-database"></a>如何配置 BTS_BACKUP_USERS 角色以存档和清除 BizTalk 跟踪数据库中的数据
DTA 清除和存档 (BizTAlkDTADb) 作业通常使用已登录的 SQL Server 代理服务帐户用户的凭据运行。 但是，为了增强安全性，可以将 DTA 清除和存档 (BizTalkDTADb) 作业配置为使用 BTS_BACKUP_USERS 角色的成员帐户的凭据运行。 通过以具有基本权限的帐户身份运行 SQL Server 代理作业，这样可以防止特权提升。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须以 SQL Server sysadmin 固定服务器角色成员的帐户登录。  
  
### <a name="to-configure-the-btsbackupusers-role-for-archiving-and-purging-data-from-the-biztalk-tracking-database"></a>配置 BTS_BACKUP_USERS 角色以存档和清除 BizTalk 跟踪数据库中的数据  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP2**，然后单击**SQL Server Management Studio**。  
  
2.  在**连接到服务器**对话框中，指定 BizTalk 跟踪 (BizTalkDTADb) 数据库所在的 SQL server 和适当的身份验证类型的名称，然后单击**连接**到连接到相应的 SQL Server。  
  
3.  在**Microsoft SQL Server Management Studio**，双击**BizTalkDTADb**，双击**安全**，双击**角色**，和然后双击**数据库角色**。  
  
4.  在**对象资源管理器详细信息**窗格中，双击**BTS_BACKUP_USERS**。  
  
5.  在**数据库角色属性-BTS_BACKUP_USERS**对话框中，在**此角色的成员**，单击**添加**。  
  
6.  在**选择数据库用户或角色**对话框中，输入具有 SQL Server 代理服务凭据的用户帐户，然后单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)