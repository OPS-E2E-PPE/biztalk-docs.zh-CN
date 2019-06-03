---
title: 如何启用 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], creating
- SSO, enabling
- maps [SSO], creating
- managing [SSO], enabling
- SSO, maps
- SSO, applications
- creating, applications [SSO]
- managing [SSO], creating affiliate applications
ms.assetid: dda89d15-6b70-4c40-b658-2f6cbdd545c8
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 863a17fc08ea09b79dc89ecb4a285c9cf7aa2d47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385094"
---
# <a name="how-to-enable-sso"></a>如何启用 SSO
可以通过使用 MMC 管理单元或命令行启用整个企业单一登录 (SSO) 系统。  
  
 在运行启用命令后，没有一个短暂的延迟之前启用了所有单一登录服务器，因为每个轮询 SSO 数据库的最新的全局信息。  
  
 如果你想要在 SSO 系统中配置关联应用程序和映射，您还必须创建关联应用程序。 SSO 关联之后管理员创建关联应用程序、 应用程序管理员可以对其进行更改和应用程序用户 （最终用户） 可以创建他们自己的映射。 有关详细信息，请参阅[管理关联应用程序](../core/managing-affiliate-applications.md)并[管理用户映射](../core/managing-user-mappings.md)。  
  
### <a name="to-enable-the-sso-system-using-the-mmc-snap-in"></a>若要启用 SSO 系统 MMC 管理单元中使用  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft 企业单一登录**，然后单击**SSO 管理**。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击**系统**，然后单击**启用**。  
  
### <a name="to-enable-the-sso-system-using-the-command-line"></a>若要启用 SSO 系统使用命令行  
  
1.  依次单击 **“开始”** 和 **“运行”** ，然后键入 **cmd**。  
  
2.  在命令行提示符下，转至企业单一登录安装目录。 默认安装目录 **\<驱动器\>** : \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssomanage – enablesso**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
### <a name="to-enable-sso-to-create-affiliate-applications-and-mappings"></a>若要启用 SSO 创建关联应用程序和映射  
  
1. SSO 管理员或 SSO 关联管理员到 SSO 服务器，以登录或 SSO 的 SSO 管理辅助服务具有一台计算机上。  
  
2. 上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
3. 在命令行提示符下，转至企业单一登录安装目录。 默认安装目录 *\<驱动器\>* : \Program Files\Common Files\Enterprise Single Sign-on。  
  
4. 类型**ssomanage enablesso**启用企业单一登录服务。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
5. 作为 SSO 关联管理员身份登录。  
  
6. 类型**ssomanage-createapps *\<应用程序文件\>* **创建关联应用程序，其中\<应用程序文件\>是 XML 文件包含关联应用程序的定义的。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [如何设置 SSO 服务器](../core/how-to-set-the-sso-server.md)   
 [如何禁用 SSO](../core/how-to-disable-sso.md)   
 [如何更新 SSO 数据库](../core/how-to-update-the-sso-database.md)   
 [使用 SSO](../core/using-sso.md)