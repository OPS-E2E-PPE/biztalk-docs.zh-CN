---
title: 如何配置密码同步 |Microsoft 文档
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
ms.openlocfilehash: b2e8348cdf78db3e95ed75e5d83e6ea53bdffdee
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968907"
---
# <a name="how-to-configure-password-synchronization"></a>如何配置密码同步
使用 SSOCONFIG 命令行实用工具可配置密码同步设置。  
  
### <a name="to-specify-the-directory-for-replay-files"></a>为重播文件指定目录  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \program Files\Enterprise 单一登录。  
  
4.  类型**ssoconfig replayfiles\<重播文件目录\>&#124; 默认**，然后按 enter 键。  
  
> [!NOTE]
>  更改服务帐户时不会删除重播文件。 如果更改此帐户，则需要手动删除重播文件。  
  
#### <a name="to-display-or-change-maximum-password-synchronization-age"></a>显示或更改密码同步最长期限  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \program Files\Enterprise 单一登录。  
  
4.  类型**ssoconfig-syncage\<以小时为单位的密码最长期限\>** ，然后按 enter 键。  
  
> [!NOTE]
>  SSOCONFIG 实用工具将 SQL Server 计算机上的时间用作其系统时间。 在使用与时间相关的任何命令时，请注意这一点。  
  
## <a name="see-also"></a>另请参阅  
 [密码同步](../core/password-synchronization2.md)