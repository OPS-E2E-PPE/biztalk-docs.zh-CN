---
title: 如何更新对 BAM 通知引用 Services 数据库 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Notification Services Application database [BAM], restoring
- Notification Services Application database [BAM], updating references
- restoring, BAM
- NS$instance_name service Notification Services Application database [BAM], NS$instance_name service
- restoring [BAM], updating references
- BAM, restoring
- restoring [BAM], Notification Services Application database
- restoring [BAM], NS$instance_name service
ms.assetid: b007fdc2-2e74-4eef-b4c3-43689e9f2180
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c27f1ecaf07c3f953372a9e5733d62c8376a288f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972995"
---
# <a name="how-to-update-references-to-the-bam-notification-services-databases"></a>如何更新对 BAM Notification Services 数据库的引用
执行完将业务活动监视 (BAM) Notification Services 数据库还原到目标系统所需的步骤后，必须在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组中运行 Notification Services (NSservice.exe) 的所有计算机上重新注册 Notification Services。 这样可使 Notification Services 连接到新位置上的数据库。  
  
 注册 Notification Services 实例后会创建 NS$instance_name 服务，在本地服务器上创建性能计数器，并将信息添加到注册表中。 必须在以下服务器上注册该实例：  
  
-   运行 NS$instance_name 服务的所有服务器。 运行事件提供程序宿主、生成器和分发服务器组件的服务。 对于扩展配置，则为在多个服务器上运行的服务。  
  
-   运行订阅管理应用程序的所有服务器。 如果订阅管理应用程序在自己的服务器上运行，则注册该实例时不会创建 NS$instance_name 服务。  
  
-   运行独立事件提供程序的所有服务器。 如果独立事件提供程序在它自己的服务器上或数据库服务器上运行，则注册该实例时不会创建 NS$instance_name 服务。  
  
 如果数据库服务器不同时运行 Notification Services 实例或客户端组件，则不会在此服务器上注册该实例。  
  
## <a name="prerequisites"></a>先决条件  
  
-   必须以 Administrators 组成员的身份登录，才能执行此过程。  
  
-   将要还原 BAM Notification Services 数据库的计算机上必须安装 SQL Notification Services 的业务活动监视 (BAM) 警报提供程序。  
  
### <a name="to-update-references-to-the-bam-notification-services-databases-sql-server-2008-r2sp1"></a>更新对 BAM Notification Services 数据库的引用 (SQL Server 2008 R2/SP1)  
  
1.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  在命令提示符下，导航到以下目录：[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。  
  
3.  类型： **bm.exe get-config –**  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
4.  打开在步骤 2 中创建的 xml 文件以获取必须重新注册 Notification Services 的计算机列表。  
  
     中列出的计算机名称**\<属性名称\=\>** 中的参数 **\<DeploymentUnit 名称 ="警报"\>** xml 文件的部分内容：  
  
    ```  
    -<DeploymentUnit Name="Alert">  
    <Property Name="GeneratorServerName" />  
    <Property Name="ProviderServerName" />  
    <Property Name="DistributorServerName" />  
      </DeploymentUnit>  
    ```  
  
5.  在 xml 文件列出的每台计算机上，停止 NS 服务，然后注销 Notification Services 实例：  
  
    1.  单击**启动**，单击**程序**，单击**Microsoft SQL Server 2008 R2**，单击**配置工具**，然后单击**通知服务命令提示符**。  
  
    2.  在命令提示符处，键入： **net 停止 NS$ BamAlerts**  
  
    3.  键入以下命令，注销该实例：  
  
         **nscontrol unregister-name BamAlerts**  
  
         注销实例会删除注册表项、NS$instance_name 服务（如果存在），还会删除该服务的性能计数器。  
  
6.  重新注册 Notification Service：  
  
    1.  单击**启动**，单击**程序**，单击**Microsoft SQL Server 2008 R2**，单击**配置工具**，然后单击**通知服务命令提示符**。  
  
    2.  在命令提示符处，键入： **nscontrol register-name BamAlerts-服务器**  *\<ServerName\>***-服务-serviceusername"** *\<ServiceUserName\>***"-servicepassword"***\<ServicePassword\>***"**  
  
         这样可使 Notification Services 登录到正确的数据库（此信息由 nscontrol 在服务所在计算机的注册表中维护）。  
  
        > [!IMPORTANT]
        >  请记住使用中的新 Notification Services 数据库服务器 **-服务器**选项时重新注册该服务。 此外，新的 Notification Services 服务使用的用户名应与旧名称相同。  
  
7.  在计算机上承载 BAM 门户，单击**启动**，单击**程序**，单击**Microsoft SQL Server 2008 R2**，单击**配置工具**，然后单击**通知服务命令提示符**。  
  
8.  在命令提示符下，键入：  
  
     **net stop NS$ BamAlerts**  
  
9. 在命令提示符下，键入：  
  
     **nscontrol unregister-name BamAlerts**  
  
10. 在命令提示符下，键入：  
  
     **nscontrol register-名称***\<BamAlerts\>***-服务器**  *\<NotificationServicesDatabaseServer    \>*  
  
11. 在命令提示符处，键入： **net 开始 NS$ BamAlerts**。  
  
12. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
13. 在命令提示符下，导航到以下目录：[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。  
  
14. 在命令提示符下，键入：  
  
     **bm.exe 更新-config –FileName:config.xml**  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>另请参阅  
 [备份和还原 BAM](../core/backing-up-and-restoring-bam.md)