---
title: 如何移动 BAM Notification Services 数据库 2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Notification Services Application database [BAM]
- Notification Services Instance database [BAM]
- migrating, Notification Services database [BAM]
ms.assetid: 4b7f3397-65c9-4c71-8374-8764f4c2e2e3
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df16514ebd799f08caaea6eddcdc16ee671723a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384509"
---
# <a name="how-to-move-the-bam-notification-services-databases"></a>如何移动 BAM Notification Services 数据库
可以使用此过程将 BAM Notification Services 数据库移动到另一台服务器。  
  
> [!NOTE]
>  必须一起移动 BAM Notification Services 应用程序 (BAMAlertsApplication) 数据库和 BAM Notification Services 实例 (BAMAlertsNSMain) 数据库。  
  
## <a name="prerequisites"></a>先决条件  
 您必须是 SQL Server sysadmin 固定服务器角色的成员才能执行此过程的帐户登录。  
  
### <a name="to-move-the-bam-notification-services-databases"></a>移动 BAM Notification Services 数据库  
  
1. 获取用于还原 BAM 的.xml 文件的副本：  
  
   1. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
   2. 在命令提示符处，导航到以下目录：  
  
       **%SystemDrive%\Program Files\Microsoft**  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\Tracking**  
  
   3. 在命令提示符下，键入：  
  
      ```  
      Bm.exe get-config –filename:BAMConfiguration.xml  
      ```  
  
      > [!NOTE]
      >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
2. 在命令提示符下，键入：  
  
   ```  
   Net stop NS$BamAlerts  
   ```  
  
3. 有关如何在旧服务器上备份数据库按照 SQL Server 联机丛书中的说明。  
  
4. 将 BAM Notification Services 数据库复制到新的 SQL server。  
  
5. 有关如何还原新服务器上的数据库，请按照 SQL Server 联机丛书中的说明进行操作。  
  
6. 编辑 BAMConfiguration.xml 文件，将 Alert DeploymentUnit 部分中的 ServerName 更改为新的服务器名称。  
  
7. 保存并关闭 BAMConfiguration.xml 文件。  
  
8. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
9. 在命令提示符处，导航到以下目录：  
  
     **%SystemDrive%\Program Files\Microsoft**  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\Tracking**  
  
10. 在命令提示符下，键入：  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
11. 更新对 BAM Notification Services 数据库的引用。 有关详细信息，请参阅[如何更新对 BAM Notification Services 数据库](../core/how-to-update-references-to-the-bam-notification-services-databases.md)。  
  
## <a name="see-also"></a>请参阅  
 [移动 BizTalk Server 数据库](../core/moving-biztalk-server-databases.md)