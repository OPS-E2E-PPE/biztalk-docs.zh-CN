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
ms.openlocfilehash: 9a07e4ecf344b06c9d1f98297acb3b3a851283e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399122"
---
# <a name="requirements-for-single-sign-on"></a>单一登录的要求

## <a name="overview"></a>概述
用于 TIBCO Enterprise Message Service (EMS) 的 Microsoft BizTalk 适配器提供单一登录 (SSO) 支持。 由企业单一登录工具创建关联应用程序代表诸如 TIBCO EMS 等服务器系统。  
  
 若要使用单一登录，必须具有：  
  
- Microsoft BizTalk Server
  
- Visual Studio  
  
- 企业单一登录  
  
- 支持 SSO 的服务器系统  
  
  独立主机应配置为受信任的身份验证。
  
## <a name="enable-sso"></a>启用 SSO  
  
1.  在中**传输属性**窗口中，选择**是**有关**使用 SSO**。  
  
2.  指定传输属性时，请选择相应的关联应用程序。  
  
     有关如何创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications5.md)。  
  
    > [!NOTE]
    >  执行相应操作后使用 SSO，请重置到任何 Web 共享文件夹**不共享**。 使用该文件夹的应用程序将不更新，或如果共享的文件夹，因为它被视为在使用中正确卸载。  
  
## <a name="see-also"></a>请参阅  
[保护适配器](../core/security-in-biztalk-adapter-for-tibco-ems.md)