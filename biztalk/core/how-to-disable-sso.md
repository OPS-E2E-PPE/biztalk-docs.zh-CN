---
title: "如何禁用 SSO |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disabling, SSO
- SSO, disabling
- managing [SSO], disabling
ms.assetid: 0fe4f87a-d7c2-4af6-afee-1065bc4a5285
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c8069ffb291b64d832a1d3ce483e7ab09be655f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-disable-sso"></a>如何禁用 SSO
通过使用 MMC 管理单元或命令行，可以禁用整个单一登录系统。  
  
 禁用所有单一登录服务器将有短时间的延迟，因为它们会轮询 SSO 数据库以获取最新的全局信息。  
  
### <a name="to-disable-enterprise-single-sign-on-using-the-mmc-snap-in"></a>使用 MMC 管理单元禁用企业单一登录  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击**系统**，然后单击**禁用**。  
  
### <a name="to-disable-enterprise-single-sign-on-using-the-command-line"></a>使用命令行禁用企业单一登录  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行提示符下，转至企业单一登录安装目录。 默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。  
  
3.  类型**ssomanage-disablesso**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>另请参阅  
 [如何启用 SSO](../core/how-to-enable-sso.md)   
 [使用 SSO](../core/using-sso.md)