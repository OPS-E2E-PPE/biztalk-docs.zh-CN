---
title: "单一登录 On3 要求 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Single Sign-On, requirements
- SSO, enabling
- Single Sign-On, enabling
- SSO requirements
ms.assetid: 7d5c406b-f548-4df0-8644-fdf6a812a989
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 005f095ae09b3018b9c8fe796520205103c7961a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="requirements-for-single-sign-on"></a>单一登录的要求
若要使用单一登录 (SSO)，必须安装以下软件：  
  
-   Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   企业单一登录  
  
-   支持 SSO 某个服务器系统  
  
-   独立主机应配置为受信任验证。  
  
### <a name="to-enable-sso"></a>启用 SSO 的步骤  
  
1.  在**传输属性**窗口中，选择**是**为**使用 SSO**。  
  
2.  在指定传输属性时选择相应的关联应用程序。  
  
 有关详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications1.md)。  
  
> [!NOTE]
>  后执行的操作使用 SSO，请记得重置到任何 Web 共享文件夹**不共享**。 使用该文件夹的应用程序将不更新，或如果共享文件夹，因为它被视为可在使用正常卸载。  
  
## <a name="see-also"></a>另请参阅  
 [使用单一登录](../core/using-single-sign-on5.md)