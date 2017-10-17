---
title: "单一登录要求 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae4b5c1f-1718-4628-9159-2fb877498913
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 472893a2a65d762f17747dac78b67b373165c0cf
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2017
---
# <a name="requirements-for-single-sign-on"></a>单一登录的要求
若要使用单一登录 (SSO)，你需要：  
  
-   BizTalk Server
  
-   Visual Studio  
  
-   企业单一登录  
  
-   支持 SSO 的服务器系统  
  
 隔离的主机应配置为受信任的身份验证。  
  
## <a name="enable-sso"></a>启用 SSO  
  
1.  在**传输属性**窗口中，选择**是**为**使用 SSO**。  
  
2.  在指定传输属性时选择相应的关联应用程序。  
  
 有关如何创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications2.md)。  
  
> [!NOTE]
>  后执行的操作使用 SSO，请记得重置到任何 Web 共享文件夹**不共享**。 使用该文件夹的应用程序将不更新，或如果共享文件夹，因为它被视为可在使用正常卸载。  
  
## <a name="see-also"></a>另请参阅  
 [运行 SSO 项目](../core/running-sso-projects1.md)   
 [使用单一登录](../core/using-single-sign-on2.md)