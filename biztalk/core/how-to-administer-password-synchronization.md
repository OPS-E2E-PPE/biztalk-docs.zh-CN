---
title: "如何管理密码同步 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Password Synchronization [SSO], applications
- Password Synchronization [SSO], notifications
- applications, Password Synchronization [SSO]
- SSOPS command line utility [SSO]
- administering, Password Synchronization [SSO]
- Password Synchronization [SSO], adapters
- Password Synchronization [SSO], administering
- notifications [SSO]
- Password Synchronization [SSO], SSOPS command line utility
ms.assetid: e5568cc2-7530-452c-9902-d7ffcad66088
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddd696da8b4cab24a8de6a4b5d8ac8f26856f7e1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-administer-password-synchronization"></a>如何管理密码同步
您可以通过 MMC 管理单元或命令行管理密码同步。  
  
 MMC 管理单元可显示适配器及其属性的列表。 使用右键单击适配器后显示的菜单可执行以下命令：  
  
-   创建适配器  
  
-   设置属性  
  
-   Update  
  
-   DELETE  
  
-   启用  
  
-   Disable  
  
-   向适配器添加应用程序  
  
-   从适配器删除应用程序  
  
-   重置通知  
  
-   将适配器添加到适配器组  
  
-   从适配器组删除适配器  
  
 您还可以使用 SSOPS 命令行实用工具管理密码同步。 此部分的大多数命令仅供管理员使用。  
  
 对于多数命令，将在屏幕上按两列显示命令输出。 由于某些屏幕设置可能会引起数据显示不完整，因此应将屏幕缓冲区大小/Windows 大小更改为 120 个字符以获得最佳效果。  
  
 下表列出了各种 SSOPS 命令。 本主题的其余部分介绍了相应的执行步骤并做了进一步说明。  
  
|Command|函数|  
|-------------|--------------|  
|-list|列出现有的适配器|  
|-display|显示适配器信息|  
|-create|创建新的适配器|  
|-setprops|设置适配器的属性|  
|-update|更新现有适配器|  
|-delete|删除现有适配器|  
|-enable|启用适配器|  
|-disable|禁用适配器|  
|-addapp|为适配器添加应用程序|  
|-deleteapp|为适配器删除应用程序|  
|-reset|重置通知或阻止队列|  
|-addtogroup|向适配器组添加适配器|  
|-deletefromgroup|从适配器组中删除适配器|  
  
### <a name="to-list-existing-adapters"></a>列出现有适配器  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \program Files\Enterprise 单一登录。  
  
4.  类型**ssops-列表**，然后按 enter 键。  
  
     此时，将列出各适配器及其说明。 (E) 表示适配器已启用，(D) 表示适配器已禁用。  
  
### <a name="to-display-adapter-information"></a>显示适配器信息  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \program Files\Enterprise 单一登录。  
  
4.  类型**ssops-显示\<适配器名称\>** ，然后按 enter 键。  
  
     屏幕输出将显示指定的适配器的信息。  
  
     除了名称、类型、说明、计算机和帐户以外，还会显示以下信息：  
  
    |适配器标志|详细信息|  
    |------------------|-------------|  
    |适配器已启用|确定适配器是否已启用。<br /><br /> 标志： SSO_FLAG_ENABLED<br /><br /> 属性名称： enableApp<br /><br /> 默认： 否|  
    |允许本地帐户|确定 App Admin 或 App Users 帐户是否可用作本地帐户。<br /><br /> 标志： SSO_FLAG_APP_ALLOW_LOCAL<br /><br /> 属性名称： allowLocalAccounts<br /><br /> 默认： 否|  
    |从适配器接收密码更改|确定是否允许适配器接收外部密码更改。<br /><br /> 标志： SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB<br /><br /> 属性名称： syncFromAdapter<br /><br /> 默认： 否|  
    |验证旧密码|确定适配器在接收外部密码更改时是否验证旧密码。 如果设置此标志，则在外部密码发生更改时，外部适配器必须提供旧的外部密码以及新的外部密码。 然后，旧的外部密码会与该外部帐户在 SSO 数据库中的现有外部密码进行比较。 如果匹配，则接受密码更改。 如果不匹配，则拒绝密码更改。<br /><br /> 标志： SSO_FLAG_SYNC_VERIFY_EXTERNAL_CREDS<br /><br /> 属性名称： verifyOldPassword<br /><br /> 默认值: 是|  
    |更改 Windows 密码|确定在收到外部密码更改时是否同时更改 Windows 密码（完全同步）。 ENTSSO 始终需要使用 SSO 数据库中存储的旧 Windows 密码才能将 Windows 密码更改为新值（Windows 需要同时使用旧密码和新密码才能更改用户密码），因此，必须进行初始化才能成功地更改 Windows 密码。 如果密码同步配置为特定的映射，然后当通过管理工具 (ssomanage 或 ssoclient-setcredentials) 设置外部凭据存储在 SSO 数据库中的 Windows 密码将也可以设置。标志： SSO_FLAG_FULL_SYNC_FROM_EXTERNAL_TO_WINDOWS<br /><br /> 属性名称： changeWindowsPassword<br /><br /> 默认： 否|  
    |将 Windows 密码更改发送到适配器|确定将 Windows 密码更改发送到的外部适配器。<br /><br /> 标志： SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL<br /><br /> 属性名称： syncToAdapter<br /><br /> 默认： 否|  
    |将旧密码发送到适配器|如果设置为“是”，则旧密码值（位于 SSO 数据库中）将同新密码值一起发送到外部适配器。 某些外部系统可能需要同时使用旧密码值和新密码值才能更改密码。<br /><br /> 标志： SSO_FLAG_SYNC_PROVIDE_OLD_EXTERNAL_CREDS<br /><br /> 属性名称： sendOldPassword<br /><br /> 默认： 否|  
    |允许映射冲突|确定适配器将允许映射冲突。<br /><br /> 当映射不唯一时，就会发生映射冲突。 在单个 SSO 单个应用中，映射是始终一对一： 一个 Windows 帐户映射到一个外部帐户，反之亦然。<br /><br /> 但是，可以将多个应用程序分配给一个适配器。 因此，可能导致某个应用程序中的映射与其他应用程序中的映射产生冲突。<br /><br /> 此标志的目的就是防止这种情况发生。 除非有明确要求，否则请不要允许映射冲突。<br /><br /> 标志： SSO_FLAG_SYNC_ALLOW_MAPPING_CONFLICTS<br /><br /> 属性名称： allowMappingConflicts<br /><br /> 默认： 否|  
  
    |适配器说明|详细信息|  
    |-------------------------|-------------|  
    |通知重试计数|默认值为 1。|  
    |通知重试延迟时间(分钟)|默认值为 5。|  
    |最大挂起通知|默认值为 8。|  
    |存储通知 （在脱机时）|True/False。|  
    |服务器名称|服务器名称。|  
    |端口号|端口号。|  
    |此适配器的应用程序|列出当前分配给适配器的应用程序。|  
  
### <a name="to-create-new-adapters"></a>若要创建新的适配器  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \program Files\Enterprise 单一登录。  
  
4.  类型**ssops-创建\<适配器文件\>** ，然后按 enter 键。  
  
     屏幕输出将显示新创建的适配器的信息。  
  
### <a name="to-set-properties-for-an-adapter"></a>若要为适配器设置属性  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \program Files\Enterprise 单一登录。  
  
4.  类型**ssops setprops\<适配器名称\>** ，然后按 enter 键。  
  
     屏幕输出将显示指定的适配器的属性。 如果需要，可以对其进行编辑，但将不会对新值进行验证。  
  
### <a name="to-update-existing-adapters"></a>若要更新现有的适配器  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \program Files\Enterprise 单一登录。  
  
4.  类型**ssops-更新\<适配器文件\>** ，然后按 enter 键。  
  
     使用此命令可更新指定的适配器的设置和标志。 请不要使用此命令设置属性，而应使用 -setprops 命令来进行设置。  
  
### <a name="to-delete-an-existing-adapter"></a>若要删除现有适配器  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \program Files\Enterprise 单一登录。  
  
4.  类型**ssops-删除\<适配器名称\>** ，然后按 enter 键。  
  
     此时，将删除指定的适配器。  
  
### <a name="to-enable-an-adapter"></a>若要启用适配器  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \program Files\Enterprise 单一登录。  
  
4.  类型**ssops-启用\<适配器名称\>** ，然后按 enter 键。  
  
     此时，将启用指定的适配器。  
  
### <a name="to-disable-an-adapter"></a>若要禁用适配器  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \program Files\Enterprise 单一登录。  
  
4.  类型**ssops-禁用\<适配器名称\>** ，然后按 enter 键。  
  
     此时，将禁用指定的适配器。  
  
### <a name="to-add-an-application-to-an-adapter"></a>若要添加到适配器的应用程序  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \program Files\Enterprise 单一登录。  
  
4.  类型**ssops addapp\<适配器名称\>\<应用程序名称\>** ，然后按 enter 键。  
  
     指定的 SSO 应用程序将分配给所指定的适配器。 这意味着该应用程序中各映射的密码将使用此适配器进行同步。  
  
     虽然可以向一个适配器分配多个应用程序，但任何给定的应用程序都只能分配给一个适配器。  
  
### <a name="to-delete-an-application-from-an-adapter"></a>若要从适配器中删除的应用程序  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \program Files\Enterprise 单一登录。  
  
4.  类型**ssops-deleteapp\<应用程序名称\>** ，然后按 enter 键。  
  
     指定的 SSO 应用程序将从适配器中删除。 （由于一个应用程序只能分配给一个适配器，因此无需指定适配器名称。）  
  
### <a name="to-reset-notification"></a>若要重置通知  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \program Files\Enterprise 单一登录。  
  
4.  类型**ssops-重置\<适配器名称 &#124; 所有 &#124; 阻止\>** ，然后按 enter 键。  
  
     此命令将根据指定清除单个适配器或所有适配器的阻止表和/或通知队列。 阻止表可存储 10 分钟的密码更改历史记录。 在接受或发送密码更改之前，企业 SSO 系统会检查阻止表以查看最近是否执行了同样的更改。 如果已执行过，则会放弃新的更改。  
  
### <a name="to-add-an-adapter-to-an-adapter-group"></a>要将适配器添加到适配器组  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \program Files\Enterprise 单一登录。  
  
4.  类型**ssops addtogroup\<适配器名称\>\<适配器组\>** ，然后按 enter 键。  
  
     此命令将向所指定的适配器组添加指定的适配器。 虽然一个适配器只能属于一个适配器组，但一个适配器组可包含多个适配器。  
  
### <a name="to-delete-an-adapter-from-an-adapter-group"></a>若要从适配器组中删除适配器  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \program Files\Enterprise 单一登录。  
  
4.  类型**ssops deletefromgroup\<适配器名称\>\<适配器组\>** ，然后按 enter 键。  
  
     此命令将从所指定的适配器组中删除指定的适配器。  
  
## <a name="see-also"></a>另请参阅  
 [密码同步](../core/password-synchronization2.md)