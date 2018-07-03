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
ms.openlocfilehash: 48346802c25e4b5aeb4d6ac1d5e83552b1220149
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005486"
---
# <a name="requirements-for-single-sign-on"></a>单一登录的要求
若要使用单一登录 (SSO)，需具备以下各项：  
  
- Microsoft BizTalk Server 
  
- Visual Studio  
  
- 企业单一登录  
  
- 支持 SSO 的服务器系统  
  
  独立主机应配置为受信任的身份验证。  
  
## <a name="enable-sso"></a>启用 SSO  
  
1.  在中**传输属性**窗口中，选择**是**有关**使用 SSO**。  
  
2.  在指定传输属性时选择相应的关联应用程序。  
  
     有关创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications3.md)。  
  
    > [!NOTE]
    >  执行相应操作后使用 SSO，请记住要重置任何**Web 共享**向文件夹**不共享**。 如果相应文件夹仍为共享模式，则使用该文件夹的应用程序将不会正确更新或卸载，因为该文件夹会被视为在使用中。  
  
## <a name="see-also"></a>请参阅  
 [适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)