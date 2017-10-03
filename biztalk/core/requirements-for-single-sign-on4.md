---
title: "单一登录 On4 要求 |Microsoft 文档"
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
ms.assetid: 645c7b3f-f860-4c20-b5ca-a8fb93736344
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15d7bdbf52869e5b13ae113716689bbb5b7ffec3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="requirements-for-single-sign-on"></a>单一登录的要求
用于 TIBCO Enterprise Message Service (EMS) 的 Microsoft BizTalk 适配器提供单一登录 (SSO) 支持。 由企业单一登录工具创建的关联应用程序表示诸如 TIBCO EMS 等服务器系统。  
  
 若要使用单一登录，需具备以下各项：  
  
-   Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   企业单一登录  
  
-   支持 SSO 某个服务器系统  
  
 独立主机应配置为受信任验证  
  
### <a name="to-enable-sso"></a>启用 SSO 的步骤  
  
1.  在**传输属性**窗口中，选择**是**为**使用 SSO**。  
  
2.  在指定传输属性时选择相应的关联应用程序。  
  
     有关如何创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications5.md)。  
  
    > [!NOTE]
    >  后执行的操作使用 SSO，请记得重置到任何 Web 共享文件夹**不共享**。 使用该文件夹的应用程序将不更新，或如果共享文件夹，因为它被视为可在使用正常卸载。  
  
## <a name="see-also"></a>另请参阅  
 [使用单一登录](../core/using-single-sign-on4.md)