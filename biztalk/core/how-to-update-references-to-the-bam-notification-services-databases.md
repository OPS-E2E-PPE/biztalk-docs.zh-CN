---
title: 如何更新对 BAM Notification Services 数据库 |Microsoft Docs
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
ms.openlocfilehash: 93a285b770ce7f2ab20cc8865e7804e31141336f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383631"
---
# <a name="how-to-update-references-to-the-bam-notification-services-databases"></a>如何更新对 BAM Notification Services 数据库的引用
在执行业务活动监视 (BAM) Notification Services 数据库还原到目标系统所需的步骤后，必须重新注册中的所有计算机上的通知服务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]正在运行的组Notification Services (NSservice.exe)。 这可使 Notification Services 连接到其新位置中的数据库。  
  
 注册 Notification Services 的实例创建 NS$ instance_name 服务、 本地服务器上创建性能计数器并将信息添加到注册表。 您必须注册以下服务器上的实例：  
  
- 运行 NS$ instance_name 服务每个服务器。 该服务运行事件提供程序宿主、 生成器和分发服务器组件。 对于横向扩展配置，该服务在多台服务器上运行。  
  
- 运行订阅管理应用程序每个服务器。 如果订阅管理应用程序在其自己的服务器上运行，请不会创建 NS$ instance_name 服务注册该实例时。  
  
- 运行独立事件提供程序的所有服务器。 如果独立事件提供程序在其自己的服务器或数据库服务器上运行，请不会创建 NS$ instance_name 服务注册该实例时。  
  
  如果数据库服务器没有还运行 Notification Services 实例或客户端组件，并注册此服务器上的实例。  
  
## <a name="prerequisites"></a>先决条件  
  
-   您必须为要执行此过程的管理员组的成员身份登录。  
  
-   必须将要还原 BAM Notification Services 数据库的计算机上安装 SQL Notification Services 的业务活动监视 (BAM) 警报提供程序。  
  
### <a name="to-update-references-to-the-bam-notification-services-databases-sql-server-2008-r2sp1"></a>若要更新对 BAM Notification Services 数据库 (SQL Server 2008 R2/SP1) 的引用  
  
1. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 在命令提示符处，导航到以下目录：[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。  
  
3. 类型： **bm.exe get-config –**  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
4. 打开在步骤 2 以获取在其必须重新注册 Notification Services 的计算机的列表中创建的 xml 文件。  
  
    中列出了计算机名称**\<属性名称\=\>** 中的参数**\<DeploymentUnit 名称 ="Alert"\>** xml 文件的部分：  
  
   ```  
   -<DeploymentUnit Name="Alert">  
   <Property Name="GeneratorServerName" />  
   <Property Name="ProviderServerName" />  
   <Property Name="DistributorServerName" />  
     </DeploymentUnit>  
   ```  
  
5. Xml 文件中列出每台计算机，停止 NS 服务，然后注销 Notification services 实例：  
  
   1.  单击**启动**，单击**程序**，单击**Microsoft SQL Server 2008 R2**，单击**配置工具**，然后单击**Notification Services 命令提示符下**。  
  
   2.  在命令提示符处，键入： **net stop NS$ BamAlerts**  
  
   3.  键入以下命令，注销该实例：  
  
        **nscontrol unregister-name BamAlerts**  
  
        注销实例删除注册表项、 NS$ instance_name 服务 （如果存在），并删除该服务的性能计数器。  
  
6. 重新注册 Notification Service:  
  
   1.  单击**启动**，单击**程序**，单击**Microsoft SQL Server 2008 R2**，单击**配置工具**，然后单击**Notification Services 命令提示符下**。  
  
   2.  在命令提示符处，键入： **nscontrol register-name BamAlerts-server**  *\<ServerName\>***-服务-serviceusername"*** \<ServiceUserName\>***"-servicepassword"***\<ServicePassword\>* * *"**  
  
        这可使 Notification Services 登录到正确的数据库 （此信息保留在服务计算机的注册表中由 nscontrol）。  
  
       > [!IMPORTANT]
       >  请记得使用新的 Notification Services 数据库服务器 **-服务器**选项时重新注册该服务。 此外，您应使用新的 Notification Services 服务的同一用户名称与旧。  
  
7. 在承载 BAM 门户的计算机，单击**启动**，单击**程序**，单击**Microsoft SQL Server 2008 R2**，单击**配置工具**，然后单击**Notification Services 命令提示**。  
  
8. 在命令提示符下，键入：  
  
    **net stop NS$ BamAlerts**  
  
9. 在命令提示符下，键入：  
  
     **nscontrol unregister-name BamAlerts**  
  
10. 在命令提示符下，键入：  
  
     **nscontrol register  -name**  *\<BamAlerts\>*  **-server** *\<NotificationServicesDatabaseServer\>*  
  
11. 在命令提示符处，键入： **net start NS$ BamAlerts**。  
  
12. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
13. 在命令提示符处，导航到以下目录：[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。  
  
14. 在命令提示符下，键入：  
  
     **bm.exe update-config –FileName:config.xml**  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [备份和还原 BAM](../core/backing-up-and-restoring-bam.md)