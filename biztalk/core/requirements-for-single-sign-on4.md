---
title: TIBCO EMS 适配器的 SSO 要求 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 645c7b3f-f860-4c20-b5ca-a8fb93736344
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8baf665a7f997293130a2c1eb93f893167f39a4f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967878"
---
# <a name="requirements-for-single-sign-on"></a>单一登录的要求

## <a name="overview"></a>概述
用于 TIBCO Enterprise Message Service (EMS) 的 Microsoft BizTalk 适配器提供单一登录 (SSO) 支持。 由企业单一登录工具创建的关联应用程序表示诸如 TIBCO EMS 等服务器系统。  
  
 若要使用单一登录，需具备以下各项：  
  
- Microsoft BizTalk Server
  
- Visual Studio  
  
- 企业单一登录  
  
- 支持 SSO 的服务器系统  
  
  独立主机应配置为受信任的身份验证。
  
## <a name="enable-sso"></a>启用 SSO  
  
1.  在中**传输属性**窗口中，选择**是**有关**使用 SSO**。  
  
2.  在指定传输属性时选择相应的关联应用程序。  
  
     有关如何创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications5.md)。  
  
    > [!NOTE]
    >  执行相应操作后使用 SSO，请重置到任何 Web 共享文件夹**不共享**。 使用该文件夹的应用程序将不更新，或如果共享的文件夹，因为它被视为在使用中正确卸载。  
  
## <a name="see-also"></a>请参阅  
[保护适配器](../core/security-in-biztalk-adapter-for-tibco-ems.md)