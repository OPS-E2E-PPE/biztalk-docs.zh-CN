---
title: 如何管理密码同步 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7c9b7485584c102b925b51d26ab11d37f4b8f6f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387211"
---
# <a name="how-to-administer-password-synchronization"></a>如何管理密码同步
你可以管理通过 MMC 管理单元或命令行的密码同步。  
  
 MMC 管理单元中显示适配器及其属性的列表。 您可以右键单击适配器，然后使用菜单来执行以下命令：  
  
- 创建适配器  
  
- 设置属性  
  
- Update  
  
- DELETE  
  
- 启用  
  
- Disable  
  
- 向适配器添加应用程序  
  
- 从适配器删除应用程序  
  
- 重置通知  
  
- 将适配器添加到适配器组  
  
- 从适配器组删除适配器  
  
  SSOPS 命令行实用程序还可用于管理密码同步。 大多数命令在本部分中由管理员仅适用于使用。  
  
  对于多数命令，命令输出显示在两个列在屏幕上。 因为某些屏幕设置可能会导致数据被截断，为获得最佳结果，应更改屏幕缓冲区大小/Windows 大小超过 120 个字符。  
  
  下表列出了各种 SSOPS 命令。 本主题的其余部分位于过程和更多说明。  
  
|Command|函数|  
|-------------|--------------|  
|-list|列出现有适配器|  
|-display|显示适配器信息|  
|-create|创建新的适配器|  
|-setprops|适配器的设置属性|  
|-update|更新现有适配器|  
|-delete|删除现有适配器|  
|-enable|启用适配器|  
|-disable|禁用适配器|  
|-addapp|添加适配器的应用程序|  
|-deleteapp|删除适配器的应用程序|  
|-reset|重置通知或阻止队列|  
|-addtogroup|添加适配器向适配器组|  
|-deletefromgroup|从适配器组中删除适配器|  
  
### <a name="to-list-existing-adapters"></a>若要列出现有适配器  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssops-列表**然后按 Enter。  
  
     将列出各适配器及其说明。 （E） 表示适配器已启用，(D) 表示已禁用。  
  
### <a name="to-display-adapter-information"></a>若要显示适配器信息  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssops-显示\<适配器名称\>** 然后按 Enter。  
  
     屏幕输出将显示指定的适配器的信息。  
  
     除了名称、 类型、 说明、 计算机和帐户，显示以下信息。  
  
    |适配器标志|详细信息|  
    |------------------|-------------|  
    |适配器已启用|确定启用该适配器。<br /><br /> 标志：SSO_FLAG_ENABLED<br /><br /> 属性名称： enableApp<br /><br /> 默认值：否|  
    |允许本地帐户|确定 App Admin 或 App Users 帐户可以是本地帐户。<br /><br /> 标志：SSO_FLAG_APP_ALLOW_LOCAL<br /><br /> 属性名称： allowLocalAccounts<br /><br /> 默认值：否|  
    |从适配器接收密码更改|确定允许适配器接收外部密码更改。<br /><br /> 标志：SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB<br /><br /> 属性名称： syncFromAdapter<br /><br /> 默认值：否|  
    |验证旧密码|确定是否接收外部密码更改时，适配器将验证旧密码。 如果设置此标志在外部密码更改的外部适配器必须提供旧的外部密码以及新的外部密码。 旧的外部密码然后与该外部帐户在 SSO 数据库中的现有外部密码进行比较。 如果它们匹配，则接受密码更改。 如果不匹配，则拒绝密码更改。<br /><br /> 标志：SSO_FLAG_SYNC_VERIFY_EXTERNAL_CREDS<br /><br /> 属性名称： verifyOldPassword<br /><br /> 默认值：是|  
    |更改 Windows 密码|确定在 Windows 的外部密码更改时，还将更改密码收到 （完全同步）。 ENTSSO 始终使用旧 Windows 密码存储在 SSO 数据库中的 Windows 密码更改为新值 （Windows 需要旧的和新密码才能更改用户密码），因此这必须初始化之前 Windows 密码更改可能会成功. 如果为特定映射配置密码同步，然后通过管理工具 (ssomanage 或 ssoclient-setcredentials) 设置外部凭据时存储在 SSO 数据库中的 Windows 密码也将会。标志：SSO_FLAG_FULL_SYNC_FROM_EXTERNAL_TO_WINDOWS<br /><br /> 属性名称： changeWindowsPassword<br /><br /> 默认值：否|  
    |将 Windows 密码更改发送到适配器|确定将 Windows 密码更改发送到外部适配器。<br /><br /> 标志：SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL<br /><br /> 属性名称： syncToAdapter<br /><br /> 默认值：否|  
    |将旧密码发送到适配器|如果是，（从 SSO 数据库中） 的旧密码值也将发送到外部适配器，以及新的密码值。 某些外部系统可能需要这两个旧的和新密码值更改的密码。<br /><br /> 标志：SSO_FLAG_SYNC_PROVIDE_OLD_EXTERNAL_CREDS<br /><br /> 属性名称： sendOldPassword<br /><br /> 默认值：否|  
    |允许映射冲突|确定适配器将允许映射冲突。<br /><br /> 映射不唯一时，将发生映射冲突。 在单个 SSO 单个应用程序中，映射始终是一对一： 一个 Windows 帐户映射到一个外部帐户，反之亦然。<br /><br /> 但是，就可以分配给适配器的多个应用程序。 因此，就可以有一个与在另一个映射冲突的应用程序中的映射。<br /><br /> 此标志的目的就是防止此情况发生。 它是更安全，除非有特定明确要求，此行为不允许映射冲突。<br /><br /> 标志：SSO_FLAG_SYNC_ALLOW_MAPPING_CONFLICTS<br /><br /> 属性名称： allowMappingConflicts<br /><br /> 默认值：否|  
  
    |适配器描述|详细信息|  
    |-------------------------|-------------|  
    |通知重试次数|默认值为 1。|  
    |通知重试延迟时间 （分钟）|默认值为 5。|  
    |最大挂起通知数|默认值为 8。|  
    |存储通知 （脱机时）|True/False。|  
    |服务器名称|服务器名称。|  
    |端口号|端口号。|  
    |此适配器的应用程序|当前分配给适配器的应用程序的列表。|  
  
### <a name="to-create-new-adapters"></a>若要创建新的适配器  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssops-创建\<适配器文件\>** 然后按 Enter。  
  
     屏幕输出将显示新创建的适配器的信息。  
  
### <a name="to-set-properties-for-an-adapter"></a>若要为适配器设置属性  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssops-setprops\<适配器名称\>** 然后按 Enter。  
  
     屏幕输出将显示指定的适配器的属性。 您可以编辑; 如有必要，但不是会验证新值。  
  
### <a name="to-update-existing-adapters"></a>若要更新现有适配器  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssops-更新\<适配器文件\>** 然后按 Enter。  
  
     使用此命令更新的设置和指定适配器的标志。 不使用此命令设置属性;改为使用-setprops 命令。  
  
### <a name="to-delete-an-existing-adapter"></a>若要删除现有适配器  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssops-删除\<适配器名称\>** 然后按 Enter。  
  
     将删除指定的适配器。  
  
### <a name="to-enable-an-adapter"></a>若要启用适配器  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssops-启用\<适配器名称\>** 然后按 Enter。  
  
     将启用指定的适配器。  
  
### <a name="to-disable-an-adapter"></a>若要禁用适配器  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssops-禁用\<适配器名称\>** 然后按 Enter。  
  
     指定的适配器将被禁用。  
  
### <a name="to-add-an-application-to-an-adapter"></a>若要向适配器添加应用程序  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssops-addapp\<适配器名称\>\<应用程序名称\>** 然后按 Enter。  
  
     指定的 SSO 应用程序将分配给指定的适配器。 这意味着，密码的映射，因为现在将同步应用程序使用此适配器。  
  
     虽然可以给一个适配器分配多个应用程序，但任何给定应用程序只能分配给一个适配器。  
  
### <a name="to-delete-an-application-from-an-adapter"></a>若要从适配器删除应用程序  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssops-deleteapp\<应用程序名称\>** 然后按 Enter。  
  
     将从适配器中删除指定的 SSO 应用程序。 （应用程序只能分配给一个适配器，因为它不需要指定适配器名称。）  
  
### <a name="to-reset-notification"></a>若要重置通知  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssops-重置\<适配器名称&#124;所有&#124;阻止\>** 然后按 Enter。  
  
     此命令可清除单个适配器或所有适配器，指定阻止的表和/或通知队列。 阻止表可存储 10 分钟的密码更改历史记录。 企业 SSO 系统地接受或发送密码更改之前，它会检查阻止表以查看最近是否执行相同的更改。 如果是，而放弃新的更改。  
  
### <a name="to-add-an-adapter-to-an-adapter-group"></a>若要将适配器添加到适配器组  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssops-addtogroup\<适配器名称\>\<适配器组\>** 然后按 Enter。  
  
     此命令将指定的适配器添加到指定的适配器组。 适配器只能属于一个适配器组，一个适配器组包含多个适配器。  
  
### <a name="to-delete-an-adapter-from-an-adapter-group"></a>若要从适配器组删除适配器  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssops-deletefromgroup\<适配器名称\>\<适配器组\>** 然后按 Enter。  
  
     此命令从指定的适配器组中删除指定的适配器。  
  
## <a name="see-also"></a>请参阅  
 [密码同步](../core/password-synchronization2.md)