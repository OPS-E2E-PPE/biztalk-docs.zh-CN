---
title: 如何启用 SSO |Microsoft 文档
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
ms.openlocfilehash: a843c0f6cdea32ba5218140069163058fcd42442
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25970403"
---
# <a name="how-to-enable-sso"></a>如何启用 SSO
可以通过使用 MMC 管理单元中或命令行启用整个企业单一登录 (SSO) 系统。  
  
 运行启用命令后，没有一个短暂的延迟之前启用所有单一登录服务器，因为每个轮询 SSO 数据库的最新的全局信息。  
  
 如果你想要配置 SSO 系统中的关联应用程序和映射，你还必须创建关联应用程序。 SSO affiliate 后管理员创建关联应用程序、 应用程序管理员可以对其，进行更改和应用程序用户 （最终用户） 可以创建自己的映射。 有关详细信息，请参阅[管理 Affiliate 应用程序](../core/managing-affiliate-applications.md)和[管理用户映射](../core/managing-user-mappings.md)。  
  
### <a name="to-enable-the-sso-system-using-the-mmc-snap-in"></a>若要启用 SSO 系统 MMC 管理单元中使用  
  
1.  单击 **启动**, ，单击 **所有程序**, ，单击 **Microsoft Enterprise 上单一登录**, ，然后单击 **SSO 管理**。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击 **系统**, ，然后单击 **启用**。  
  
### <a name="to-enable-the-sso-system-using-the-command-line"></a>若要启用 SSO 系统使用命令行  
  
1.  依次单击 **“开始”** 和 **“运行”**，然后键入 **cmd**。  
  
2.  在命令行提示符下，转至企业单一登录安装目录。 默认安装目录是**\<驱动器\>**: \program Files\Enterprise 单一登录。  
  
3.  类型 **ssomanage-enablesso**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
### <a name="to-enable-sso-to-create-affiliate-applications-and-mappings"></a>若要启用创建的 SSO affiliate 应用程序和映射  
  
1.  以 SSO administrator 帐户或 SSO 服务器，SSO 关联管理员登录，或者在计算机上具有 SSO 的 SSO 管理子服务。  
  
2.  上 **启动** 菜单上，单击 **运行**, ，然后键入 **cmd**。  
  
3.  在命令行提示符下，转至企业单一登录安装目录。 默认安装目录是*\<驱动器\>*: \program Files\Enterprise 单一登录。  
  
4.  类型 **ssomanage enablesso** 启用企业单一登录服务。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
5.  作为 SSO affiliate 管理员登录。  
  
6.  类型**ssomanage createapps *\<应用程序文件\>*** 创建关联应用程序，其中\<应用程序文件\>是 XML 文件包含关联应用程序的定义。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>另请参阅  
 [如何设置 SSO 服务器](../core/how-to-set-the-sso-server.md)   
 [如何禁用 SSO](../core/how-to-disable-sso.md)   
 [如何更新 SSO 数据库](../core/how-to-update-the-sso-database.md)   
 [使用 SSO](../core/using-sso.md)