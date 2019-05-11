---
title: 如何禁用 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disabling, SSO
- SSO, disabling
- managing [SSO], disabling
ms.assetid: 0fe4f87a-d7c2-4af6-afee-1065bc4a5285
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c14f83d4130153f7066b542702007bf9f704387
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338084"
---
# <a name="how-to-disable-sso"></a>如何禁用 SSO
可以使用 MMC 管理单元或命令行来禁用整个单一登录系统。  
  
 将所有单一登录服务器要禁用短时间的延迟，因为它们会轮询 SSO 数据库的最新的全局信息。  
  
### <a name="to-disable-enterprise-single-sign-on-using-the-mmc-snap-in"></a>若要禁用企业单一登录使用 Mmc 管理单元  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击**系统**，然后单击**禁用**。  
  
### <a name="to-disable-enterprise-single-sign-on-using-the-command-line"></a>若要禁用企业单一登录使用命令行  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行提示符下，转至企业单一登录安装目录。 默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssomanage – disablesso**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [如何启用 SSO](../core/how-to-enable-sso.md)   
 [使用 SSO](../core/using-sso.md)