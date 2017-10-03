---
title: "如何启用 SSO 的 SSL |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, SSL
- managing [SSO], enabling SSL
- SSL
ms.assetid: 0d75962a-a0b0-4e69-8001-54e7df617006
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ae2f3840cd2620f9c03a5b207b32d8bbd4feee9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-ssl-for-sso"></a>如何启用 SSO 的 SSL
使用此命令可以在所有企业单一登录 (SSO) 服务器与 SSO 数据库间启用安全套接字层 (SSL)。  
  
### <a name="to-enable-ssl-for-enterprise-single-sign-on"></a>为企业单一登录启用 SSL  
  
1.  依次单击 **“开始”**和 **“运行”**，然后键入 **cmd**。  
  
2.  在命令行上，转至企业单一登录安装目录。 默认安装目录是**\<驱动器 >**: \program Files\Enterprise 单一登录。  
  
3.  类型**ssoconfig-setSSL\<是/否 >**，其中\<**是/否**> 该值指示是否要启用 SSO 系统中的 SSL。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>另请参阅  
 [使用 SSO](../core/using-sso.md)