---
title: 如何显示 SSO 数据库信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO], viewing SSO database
- SSO database, viewing
- viewing, SSO database
ms.assetid: 0ebadd2e-6ea5-460c-b0a8-f48589e6bf1c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d90da02edcde220f2f36e0329ba001300ff5443b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385190"
---
# <a name="how-to-display-the-sso-database-information"></a>如何显示 SSO 数据库信息
可以使用 MMC 管理单元或命令行 (ssomanage) 实用工具来查看 SSO 数据库信息。  
  
### <a name="to-display-the-sso-database-information-using-the-mmc-snap-in"></a>若要显示使用 MMC 管理单元中的 SSO 数据库信息  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击“系统” ，然后单击“属性” 。  
  
4.  单击选项卡**系统属性**对话框可以查看 SSO 数据库信息。  
  
### <a name="to-display-the-sso-database-information-using-the-command-line"></a>若要显示 SSO 数据库信息使用命令行  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行提示符下，转至企业单一登录安装目录。 默认安装目录**\<驱动器\>**: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssomanage – displaydb**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
### <a name="to-display-the-sso-database-the-sso-server-is-connected-to-using-the-command-line"></a>若要显示 SSO 数据库 SSO 服务器被连接到使用命令行  
  
1. 上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2. 在命令行提示符下，转至企业单一登录安装目录。 默认安装目录**\<驱动器\>**: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3. 类型**ssomanage – showdb**。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
   下表介绍了这些过程所显示的值。  
  
|属性|ReplTest1|  
|--------------|-----------|  
|SQL Server|**\<SQL Server 名称\>**|  
|单一登录数据库|**\<SQL Server 数据库名称\>**|  
|单一登录密钥服务器名称|**\<单一登录服务器名称\>**|  
|单一登录管理员帐户|域 \ 帐户名|  
|单一登录关联管理员帐户|域 \ 帐户名|  
|已删除应用程序 （审核条目数） 的审核表大小|1000 （默认值）|  
|已删除的用户映射 （审核条目数） 的审核表大小|1000 （默认值）|  
|外部凭据查找 （审核条目数） 的审核表大小|1000 （默认值）|  
|票证超时 （以分钟为单位）|2 （默认值）<br /><br /> 此值可以是 1 到 525,600 之间的整数|  
|凭据缓存超时 （以分钟为单位）|60 （默认值）|  
|单一登录状态|已启用/禁用|  
|允许使用票证|是/否 （默认值）|  
|验证票证|是 （默认值）/否|  
  
## <a name="see-also"></a>请参阅  
 [如何配置 SSO 票证](../core/how-to-configure-the-sso-tickets.md)   
 [使用 SSO](../core/using-sso.md)