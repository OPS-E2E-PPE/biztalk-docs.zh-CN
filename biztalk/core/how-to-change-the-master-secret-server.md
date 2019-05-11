---
title: 如何更改主密钥服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, promoting
- managing [Master Secret server], promoting servers
- managing [SSO], promoting servers
- SSO, Master Secret server
- modifying, Master Secret server
- Master Secret server, changing
ms.assetid: 44a786ca-4645-44a8-b33e-d0019f0aeca9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23e588e4ea7ac91b5f4ff8124b33b3611e91e8d4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387003"
---
# <a name="how-to-change-the-master-secret-server"></a>如何更改主密钥服务器
在设置主密钥服务器并配置 SSO 数据库后，可以更改主密钥服务器，如果在原始主服务器失败，并且无法恢复。 若要更改主密钥服务器，你需要升级 SSO 服务器成为主密钥服务器。  
  
### <a name="to-change-the-master-secret-server-using-the-mmc-snap-in"></a>若要更改主密钥服务器使用 mmc 管理单元  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在作用域窗格中，右键单击**系统**，然后单击**属性**。 主服务器上将显示**常规**选项卡**系统属性**对话框。  
  
3.  单击**更改**以选择新的主密钥服务器。  
  
    > [!IMPORTANT]
    >  当使用 MMC 管理单元更改主密钥服务器，必须在主密钥服务器上执行操作。 不能更改主密钥服务器不是主密钥服务器的计算机使用 MMC 管理单元。  
  
4.  登录到新的主服务器，将主密钥还原到新的主注册表机密密钥服务器。  
  
5.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
6.  在命令行提示符下，转至企业单一登录安装目录。 默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。  
  
7.  重新启动新的主密钥服务器。  
  
8.  类型**ssoconfig-restoreSecret\<还原文件\>**，其中**\<还原文件\>** 是路径和主密钥的文件的名称存储中。  
  
     主密钥存储在注册表中的以下位置：  
  
     HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
### <a name="to-promote-a-single-sign-on-server-to-master-secret-server-using-the-command-line"></a>若要单一登录将服务器提升为使用命令行的主密钥服务器  
  
1.  创建一个包含你想要升级到主密钥服务器的 SSO 服务器的名称的 XML 文件。 例如，  
  
    ```  
    <sso>  
      <globalInfo>  
         <secretServer>SSO Server name</secretServer>  
      </globalInfo>  
    </sso>  
    ```  
  
    > [!IMPORTANT]
    >  若要更改主密钥服务器不是主密钥服务器的计算机，请确保指定的 XML 文件包含仅的主密钥服务器名称。 具体而言，它不应包含 SSO 管理员 XML 标记或**ssomanage-updatedb**操作将失败。  
  
2.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
3.  在命令行提示符下，转至企业单一登录安装目录。 默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssomanage – updatedb** \<**更新文件**\>，其中\<**更新文件**\>是 XML 文件的名称步骤 1 中创建。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
5.  重新启动主密钥服务器。  
  
6.  类型**ssoconfig-restoresecret\<还原文件\>**，其中**\<还原文件\>** 是路径和主密钥的文件的名称存储中。  
  
     主密钥存储在注册表中的以下位置：  
  
     HKEY_LOCAL_MACHINESOFTWAREMicrosoftENTSSOSSOSS  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [主密钥服务器](../core/master-secret-server.md)   
 [如何群集主密钥服务器](../core/how-to-cluster-the-master-secret-server1.md)   
 [如何更新 SSO 数据库](../core/how-to-update-the-sso-database.md)   
 [使用 SSO](../core/using-sso.md)