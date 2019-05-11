---
title: 如何配置密码同步 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Password Synchronization [SSO], replay files
- Password Synchronization [SSO], maximum age
- SSOCONFIG command line utility
- Password Synchronization [SSO], SSOCONFIG command line utility
- Password Synchronization [SSO], configuring
- configuring, Password Synchronization [SSO]
ms.assetid: 04000dfc-02b9-4d50-babe-8bc8a07a33b7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1b18d6f59b364a12a9ffe775d64a57e310f76e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341303"
---
# <a name="how-to-configure-password-synchronization"></a>如何配置密码同步
使用 SSOCONFIG 命令行实用工具来配置密码同步设置。  
  
### <a name="to-specify-the-directory-for-replay-files"></a>若要指定为重播文件目录  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssoconfig-replayfiles\<重播文件目录\>&#124;的默认**并按 Enter。  
  
> [!NOTE]
>  当您更改服务帐户时，不会删除重播文件。 如果更改此帐户，你将需要手动删除重播文件。  
  
#### <a name="to-display-or-change-maximum-password-synchronization-age"></a>若要显示或更改最长密码同步期限  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssoconfig-syncage\<以小时为单位的最长密码期限\>** 然后按 Enter。  
  
> [!NOTE]
>  SSOCONFIG 实用工具在 SQL Server 计算机上使用的时间用作其系统时间。 使用与时间相关的任何命令时请记住这一点。  
  
## <a name="see-also"></a>请参阅  
 [密码同步](../core/password-synchronization2.md)