---
title: "如何更改主密钥服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, promoting
- managing [Master Secret server], promoting servers
- managing [SSO], promoting servers
- SSO, Master Secret server
- modifying, Master Secret server
- Master Secret server, changing
ms.assetid: 44a786ca-4645-44a8-b33e-d0019f0aeca9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4676db07025b4395d58df7c24252769ba65ecfb4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-the-master-secret-server"></a>如何更改主密钥服务器
在设置主密钥服务器并配置 SSO 数据库后，如果原始的主密钥服务器发生故障并且无法恢复，则可以更改主密钥服务器。 若要更改主密钥服务器，则需要将 SSO 服务器升级为主密钥服务器。  
  
### <a name="to-change-the-master-secret-server-using-the-mmc-snap-in"></a>使用 MMC 管理单元更改主密钥服务器  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在作用域窗格中，右键单击**系统**，然后单击**属性**。 主服务器显示在**常规**选项卡**系统属性**对话框。  
  
3.  单击**更改**以选择新的主服务器密钥服务器。  
  
    > [!IMPORTANT]
    >  使用 MMC 管理单元更改主密钥服务器时，必须在主密钥服务器上执行此操作。 无法通过不是主密钥服务器的计算机使用 MMC 管理单元更改主密钥服务器。  
  
4.  登录到新的主密钥服务器，将主密钥还原到新的主密钥服务器的注册表中。  
  
5.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
6.  在命令行提示符下，转至企业单一登录安装目录。 默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。  
  
7.  重新启动新的主密钥服务器。  
  
8.  类型**ssoconfig-restoreSecret\<还原文件 >**，其中**\<还原文件 >**是路径和主密钥的存储位置的文件的名称。  
  
     主密钥存储在注册表中，位置为：  
  
     HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
### <a name="to-promote-a-single-sign-on-server-to-master-secret-server-using-the-command-line"></a>使用命令行将单一登录服务器升级为主密钥服务器  
  
1.  创建一个包含要升级为主密钥服务器的 SSO 服务器名称的 XML 文件。 例如：  
  
    ```  
    <sso>  
      <globalInfo>  
         <secretServer>SSO Server name</secretServer>  
      </globalInfo>  
    </sso>  
    ```  
  
    > [!IMPORTANT]
    >  若要从不是主密钥服务器的计算机更改主密钥服务器，请确保指定的 XML 文件仅包含主密钥服务器的名称。 具体而言，它不应包含的 SSO 管理员 XML 标记或**ssomanage updatedb**操作将失败。  
  
2.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
3.  在命令行提示符下，转至企业单一登录安装目录。 默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。  
  
4.  类型**ssomanage-updatedb** \<**更新文件**>，其中\<**更新文件**> 是你在步骤 1 中创建的 XML 文件的名称。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
5.  重新启动主密钥服务器。  
  
6.  类型**ssoconfig-restoresecret\<还原文件 >**，其中**\<还原文件 >**是路径和主密钥的存储位置的文件的名称。  
  
     主密钥存储在注册表中，位置为：  
  
     HKEY_LOCAL_MACHINESOFTWAREMicrosoftENTSSOSSOSS  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>另请参阅  
 [主密钥服务器](../core/master-secret-server.md)   
 [如何安装群集主密钥服务器](../core/how-to-cluster-the-master-secret-server1.md)   
 [如何更新 SSO 数据库](../core/how-to-update-the-sso-database.md)   
 [使用 SSO](../core/using-sso.md)