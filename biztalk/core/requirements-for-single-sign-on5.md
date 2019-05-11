---
title: 单一登录的要求 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 318b9977-ce24-48d6-971b-49a059a1bdbc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03d043ef526957cd4590edc2a5d74396c1225a8b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395276"
---
# <a name="requirements-for-single-sign-on"></a>单一登录的要求
若要使用单一登录 (SSO)，必须具有：  
  
- Microsoft BizTalk Server 
  
- Visual Studio  
  
- 企业单一登录  
  
- 支持 SSO 的服务器系统  
  
  独立主机应配置为受信任的身份验证。  
  
## <a name="enable-sso"></a>启用 SSO  
  
1.  在中**传输属性**窗口中，选择**是**有关**使用 SSO**。  
  
2.  指定传输属性时，请选择相应的关联应用程序。  
  
     有关创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications3.md)。  
  
    > [!NOTE]
    >  执行相应操作后使用 SSO，请记住要重置任何**Web 共享**向文件夹**不共享**。 使用该文件夹的应用程序将不更新，或如果共享的文件夹，因为它被视为在使用中正确卸载。  
  
## <a name="see-also"></a>请参阅  
 [适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)