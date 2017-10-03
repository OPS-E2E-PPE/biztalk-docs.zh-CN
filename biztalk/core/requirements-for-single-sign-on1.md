---
title: "单一登录 On1 要求 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, Single Sign-On
- SSO, requirements [JD Edwards EnterpriseOne adapters]
- adapters [JD Edwards EnterpriseOne adapters], Single Sign-On
- Single Sign-On, requirements [JD Edwards EnterpriseOne adapters]
- Single Sign-On, enabling [JD Edwards EnterpriseOne adapters]
ms.assetid: d1111377-2fe1-4d65-ac0d-c89d2f1740b8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfab6d6cfea2ddef3b953d3fb3bb15900420fdcf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="requirements-for-single-sign-on"></a>单一登录的要求
若要使用单一登录 (SSO)，您必须安装下列软件：  
  
-   Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   企业单一登录  
  
-   支持 SSO 的服务器系统  
  
-   隔离的主机应配置为**受信任的身份验证**。  
  
### <a name="to-enable-sso"></a>启用 SSO 的步骤  
  
1.  在**传输属性**窗口中，选择**是**为**使用 SSO**。  
  
2.  在指定传输属性时选择相应的关联应用程序。  
  
 有关创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications4.md)。  
  
> [!NOTE]
>  后执行的操作使用 SSO，请记得重置到任何 Web 共享文件夹**不共享**。 如果相应文件夹仍为共享模式，则使用该文件夹的应用程序将不会正确更新或卸载，因为该文件夹会被视为在使用中。  
  
## <a name="see-also"></a>另请参阅  
 [使用单一登录](../core/using-single-sign-on1.md)