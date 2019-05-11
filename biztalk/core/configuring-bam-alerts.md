---
title: 配置 BAM 警报 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, alerts
- alerts, timeout values
- Notification Services, configuration tips
- alerts, configuring
- managing [BAM definitions], configuring alerts
ms.assetid: 29327466-c8e9-41e8-bc12-f3ac6b5d3096
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8d9a1d00735d867aa73493a7eff257947749fee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391324"
---
# <a name="configuring-bam-alerts"></a>配置 BAM 警报
管理员可以修改 BAM 警报框架的某些元素。 本主题介绍适用于管理员的配置选项。  
  
> [!NOTE]
>  创建警报时应注意该数据存储在 OLAP、 星型架构和 Notification Services 数据库上的本地时间格式的时间。 此外，还假设所有三个数据库位于相同的时区。 在主导入数据库中，信息存储在 UTC 时间格式，并且可以采用相同或不同的时区。  
  
## <a name="changing-the-adf-configuration"></a>更改 ADF 配置  
 在部署视图时，BAM 管理实用程序使用 bm.exe.config 文件中指定的 CommandTimeout 值来填充 Notification Services 应用程序定义文件\<EventRule\>\\< ActionTimeout\>元素。  
  
 更改 bm.exe.config 中的 CommandTimeout 值不会更改在更改之前所部署的视图的 CommandTimeout 值。  
  
 下面的过程使用 ProcessBamNSFiles.vbs 来获得配置和 Notification Services 应用程序定义文件。 该脚本的详细信息，请参阅[BAM 通知服务配置文件的命令行脚本](../core/bam-command-line-script-for-notification-services-configuration-files.md)。  
  
 如何更改用于已部署的视图的 NS 的 ActionTimeout:  
  
#### <a name="to-change-the-command-timeout-value"></a>若要更改命令超时值  
  
1.  打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  通过在命令提示符下键入，导航到跟踪文件夹**cd"C:\Program Files\Microsoft BizTalk Server\<版本\>\Tracking"** 或**cd"C:\Program Files (x86) \Microsoft BizTalk服务器\<版本\>\Tracking"** 64 位计算机上。 按 **Enter**。  
  
3.  检索 ADF 文件。 类型**cscript ProcessBamNSFiles.vbs-Get \<ConfigFilePath\> \<文件路径\> \< PID Server\> \< PID 数据库\>** . ConfigFilePath、 文件路径、 PID 服务器和 PID 数据库替换为你安装的相应值。  
  
4.  按 **Enter**。  
  
5.  在编辑器中打开 ADF 文件并搜索\<ActionTimeout\>、 使用所需的值更新和请注意，此值是 XML 持续时间。  
  
6.  保存该 ADF 文件。 类型**cscript ProcessBamNSFiles.vbs-Update \<ConfigFilePath\> \<文件路径\> \< PID Server\> \< PID 数据库\>**.  
  
7.  按 **Enter**。  
  
### <a name="notification-service-configuration-tips"></a>通知服务配置提示  
 如果运行的远程计算机上放置警报数据库的方式配置 BAM 警报[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，则必须在 SQL Server 实例上安装 Notification Services 数据库组件。 如果这些组件不存在的 SQL 实例上，BAM 警报的配置将因出现错误，指示无法通知服务扩展存储过程授予的权限。 有关安装 Notification Services 组件的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=61999 ](http://go.microsoft.com/fwlink/?LinkId=61999)。  
  
 BAM 可更改 BAM 用于访问 Notification Services 的帐户。 如果更改此帐户以任何方式用运行 NSControl 之外，您将收到一个错误，通知你使用 NSControl 更改帐户。  
  
> [!NOTE]
>  不能使用 LocalSystem 或 SYSTEM 帐户安装和配置 Notification Services。 这些是特殊帐户无法登录到并且不能使用文件和 SQL Server 权限授予 BAM 警报用户。  
>   
>  若要安装和配置 Notification Services，在本地计算机上创建新的用户帐户，授予其所有必需的权限，然后使用它来配置 Notification Services。  
  
##### <a name="to-change-ns-user-account-for-bam"></a>若要为 BAM 更改 NS 用户帐户  
  
1. 使用 NSControl 更新用户帐户。  
  
2. 授予 NS 用户读取、 写入和更改到 BAM 警报文件位置共享的权限。  
  
3. 将 NS 用户添加为 BAMAlerts 实例和应用程序数据库中的 NSRunService 角色的成员。  
  
4. 授予 NS 用户权限使用在文档在本地计算机上的[ http://go.microsoft.com/fwlink/?LinkId=62005 ](http://go.microsoft.com/fwlink/?LinkId=62005)。  
  
5. 根据数据库对 NS NS 权限授予[ http://go.microsoft.com/fwlink/?LinkId=62008 ](http://go.microsoft.com/fwlink/?LinkId=62008)。  
  
6. 授予 NS 用户登录到主导入数据库的 SQL 服务器和数据库访问权限。  
  
7. 将 NS 用户添加为 BAM_ManagmentNSReader SQL 角色。  
  
8. 将 NS 用户添加到 BamAnalysis 数据库中的"BAM 警报"角色。  
  
   如果修改了送达的警报的文件的文件存放位置。 必须重新启动 SQL Notification Services。  
  
   如果不重新启动 NS 服务，警报将继续传送到原始文件存放位置。  
  
   通过修改 BAM 配置文件的以下行并使用 BAM 管理实用程序 update-config 命令可以更改文件存放位置。  
  
   \<属性名称 ="FileDropUNC"\>\\\\< 计算机名\>\alerts\</Property\>  
  
   有关 BAM 管理实用程序的详细信息，请参阅[BAM 管理实用程序](../core/bam-management-utility.md)。