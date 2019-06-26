---
title: 如何为 SSO 启用 SSL |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, SSL
- managing [SSO], enabling SSL
- SSL
ms.assetid: 0d75962a-a0b0-4e69-8001-54e7df617006
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8478f688dc504ba64690f6f7b8d2a0faa4b31feb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337931"
---
# <a name="how-to-enable-ssl-for-sso"></a>如何为 SSO 启用 SSL
此命令用于所有企业单一登录 (SSO) 服务器和 SSO 数据库之间启用安全套接字层 (SSL)。  
  
### <a name="to-enable-ssl-for-enterprise-single-sign-on"></a>若要为企业单一登录启用 SSL  
  
1.  依次单击 **“开始”** 和 **“运行”** ，然后键入 **cmd**。  
  
2.  在命令行中，转至企业单一登录安装目录。 默认安装目录 **\<驱动器\>** : \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssoconfig – setSSL\<是/否\>** ，其中\<**是/否**\>指示您是否希望在 SSO 系统中启用 SSL。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [使用 SSO](../core/using-sso.md)