---
title: "配置 BAM 警报 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, alerts
- alerts, timeout values
- Notification Services, configuration tips
- alerts, configuring
- managing [BAM definitions], configuring alerts
ms.assetid: 29327466-c8e9-41e8-bc12-f3ac6b5d3096
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8198b17d07288bff04b64b0a1ad05db0cde4fd91
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="configuring-bam-alerts"></a>配置 BAM 警报
管理员可以修改 BAM 警报框架的某些元素。 本主题介绍管理员可用的配置选项。  
  
> [!NOTE]
>  在创建警报时，应该知道时间数据以本地时间格式存储在 OLAP 数据库、星型架构数据库和 Notification Services 数据库中。 而且还假定这三个数据库处于同一时区中。 在主导入数据库中，信息以 UTC 时间格式存储，可以在同一时区，也可以在不同时区。  
  
## <a name="changing-the-adf-configuration"></a>更改 ADF 配置  
 部署的 BAM 管理实用工具使用 bm.exe.config 文件中指定的 CommandTimeout 值来填充 Notification Services 应用程序定义文件的视图时\<EventRule\>\\< ActionTimeout\>元素。  
  
 更改 bm.exe.config 中的 CommandTimeout 值，并不会更改之前所部署的视图中的 CommandTimeout 值。  
  
 以下过程使用 ProcessBamNSFiles.vbs 来获得配置和 Notification Services 应用程序定义文件。 该脚本的详细信息，请参阅[BAM 通知服务配置文件的命令行脚本](../core/bam-command-line-script-for-notification-services-configuration-files.md)。  
  
 如何为已部署的视图更改 NS 的 ActionTimeout：  
  
#### <a name="to-change-the-command-timeout-value"></a>更改命令超时值  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  导航到的跟踪文件夹中，在命令提示符处键入**cd"C:\Program Files\Microsoft BizTalk Server\<版本\>\Tracking"**或**cd"C:\Program Files (x86) \Microsoft BizTalk服务器\<版本\>\Tracking"** 64 位计算机上。 按 **Enter**。  
  
3.  检索 ADF 文件。 类型**cscript ProcessBamNSFiles.vbs-获取\<ConfigFilePath\> \<ADFFilePath\> \< PID 服务器\> \< PID 数据库\>** . 请将其中的“配置文件路径”、“ADF 文件路径”、“PID 服务器”和“PID 数据库”替换为适合你的安装的值。  
  
4.  按 **Enter**。  
  
5.  在编辑器中打开 ADF 文件并搜索\<ActionTimeout\>、 更新具有所需的值和请注意，此值是 XML 持续时间。  
  
6.  保存该 ADF 文件。 类型**cscript ProcessBamNSFiles.vbs-更新\<ConfigFilePath\> \<ADFFilePath\> \< PID 服务器\> \< PID 数据库\>**.  
  
7.  按 **Enter**。  
  
### <a name="notification-service-configuration-tips"></a>Notification Services 配置提示  
 如果将 BAM 警报配置为在运行 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 的远程计算机上放置警报数据库，则 SQL Server 实例上必须安装有 Notification Services 数据库组件。 如果 SQL 实例上没有安装这些组件，则 BAM 警报的配置将失败，并且出现一条错误，指出不能将权限授予 Notification Services 扩展存储过程。 有关安装 Notification Services 组件的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=61999](http://go.microsoft.com/fwlink/?LinkId=61999)。  
  
 通过 BAM 可更改 BAM 用于访问 Notification Services 的帐户。 如果用运行 NSControl 之外的方法来更改此帐户，则会出现错误，通知你使用 NSControl 更改帐户。  
  
> [!NOTE]
>  你不能使用 LocalSystem 或 SYSTEM 帐户来安装和配置 Notification Services。 它们是你无法登录到的特殊帐户，并且你不能使用这些帐户将文件和 SQL Server 权限授予 BAM 警报用户。  
>   
>  若要安装和配置 Notification Services，请在本地计算机上创建新的用户帐户，向该帐户授予所有必需的权限，然后使用它来配置 Notification Services。  
  
##### <a name="to-change-ns-user-account-for-bam"></a>为 BAM 更改 NS 用户帐户  
  
1.  使用 NSControl 更新用户帐户。  
  
2.  授予 NS 用户对 BAM 警报文件位置共享的读取、写入和更改权限。  
  
3.  将 NS 用户添加为 BAMAlerts 实例和应用程序数据库的 NSRunService 角色的成员。  
  
4.  授予本地计算机使用在文档上的 NS 用户权限[http://go.microsoft.com/fwlink/?LinkId=62005](http://go.microsoft.com/fwlink/?LinkId=62005)。  
  
5.  根据数据库到 NS NS 权限授予[http://go.microsoft.com/fwlink/?LinkId=62008](http://go.microsoft.com/fwlink/?LinkId=62008)。  
  
6.  授予 NS 用户对 SQL 服务器的登录权限以及对主导入数据库的访问权限。  
  
7.  将 NS 用户添加为 BAM_ManagmentNSReader SQL 角色。  
  
8.  将 NS 用户添加为 BamAnalysis 数据库的揃“BAM 警报”角色。  
  
 如果修改了送达的警报的文件存放位置， 则必须重新启动 SQL Notification Services。  
  
 如果没有重新启动 NS 服务，则警报将继续传送到原始的文件存放位置。  
  
 修改 BAM 配置文件的以下行并使用 BAM 管理实用程序 update-config 命令，可以更改文件存放位置。  
  
 \<属性名称 ="FileDropUNC"\>\\\\< 计算机名\>\alerts\</Property\>  
  
 BAM 管理实用程序的详细信息，请参阅[BAM 管理实用工具](../core/bam-management-utility.md)。