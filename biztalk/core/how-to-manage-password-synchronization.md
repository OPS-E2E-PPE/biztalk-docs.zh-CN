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
- Password Synchronization [SSO], managing
- managing [SSO], disabling features
- managing [SSO], enabling features
- Password Synchronization [SSO], SSOMANAGE command line utility
- SSO database, SSOMANAGE command line utility
- managing, Password Synchronization [SSO]
- SSO database, database settings
- SSOMANAGE command line utility
ms.assetid: 033e63f2-e5b0-4400-99c3-145679d9b84e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df4030becd9dfe86abfaa5745cb72e42c0a4b0c8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384654"
---
# <a name="how-to-manage-password-synchronization"></a>如何管理密码同步
若要启用或禁用 SSO 功能，并显示当前 SSO 数据库设置，请使用 MMC 管理单元或 SSOMANAGE 命令行实用工具。  
  
### <a name="to-manage-features-or-display-settings-using-the-mmc-snap-in"></a>若要管理功能或显示设置，请使用 MMC 管理单元  
  
1.  右键单击相应的功能或数据库。  
  
2.  单击相应的菜单项。  
  
### <a name="to-enable-sso-features-using-the-command-line"></a>使用命令行启用 SSO 功能  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssomanage-启用**然后按 Enter。  
  
### <a name="to-disable-sso-features-using-the-command-line"></a>使用命令行禁用 SSO 功能  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssomanage-禁用**然后按 Enter。  
  
### <a name="to-display-current-database-settings-using-the-command-line"></a>若要显示使用命令行的当前数据库设置  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssomanage-displaydb**然后按 Enter。  
  
## <a name="see-also"></a>请参阅  
 [密码同步](../core/password-synchronization2.md)