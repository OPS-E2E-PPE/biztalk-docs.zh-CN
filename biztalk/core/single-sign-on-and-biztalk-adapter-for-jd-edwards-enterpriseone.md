---
title: "有关博士 Edwards EnterpriseOne 单一登录和 BizTalk 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, Single Sign-On
- Single Sign-On, JD Edwards EnterpriseOne adapters
- adapters [JD Edwards EnterpriseOne adapters], Single Sign-On
ms.assetid: efcc3a2d-18a6-4090-9e95-143fb7a356b2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8daa94a49be4d120180fca9fb82c07b3603cf95
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="single-sign-on-and-biztalk-adapter-for-jd-edwards-enterpriseone"></a>JD Edwards EnterpriseOne 的单一登录和 BizTalk 适配器
当您对用于 JD Edwards EnterpriseOne 的 Microsoft 适配器使用单一登录 (SSO) 时,适配器从 SSO 凭据数据库获取凭据。 因此，不需要输入中的服务器系统的登录凭据**传输属性**对话框。  
  
 在设计时，用于 JD Edwards EnterpriseOne 的 BizTalk 适配器即会在启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目的用户上下文中，为指定的关联应用程序获取用于系统的凭据。 此用户应为应用程序用户。 运行时，将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 接收适配器用作使用 SSO 时的直通方案中的接收位置。  
  
## <a name="processing-requests"></a>处理请求  
 当 Internet 信息服务 (IIS) 从 Web 客户端接收到 HTTP 请求时，IIS 将验证该用户。 使用 ISAPI 扩展插件模拟 Windows 用户，并调用要获得加密的票证的 SSO 凭据存储区。 此票证在消息上下文中以 SSOTicket 属性形式存储。  
  
 消息即定向到 MessageBox 数据库。 当用于 JD Edwards EnterpriseOne 的 BizTalk 适配器从 MessageBox 数据库接收消息时，它会使用加密票证和关联应用程序名来调用 `ValidateAndRedeemTicket`，以从 SSO 存储中检索登录凭据。 然后，适配器将使用外部凭据连接该系统并处理请求。  
  
> [!NOTE]
>  SSO 配置是 BizTalk Server 安装程序的一部分。 如果收到 SSO 错误，请确认您配置 BizTalk Server 时使用的是域帐户，因为它会影响企业 SSO 服务的功能。 SSO 仅在域帐户下起作用。  
  
## <a name="see-also"></a>另请参阅  
 [创建关联应用程序](../core/creating-affiliate-applications4.md)   
 [用于 JD Edwards EnterpriseOne 的 BizTalk 适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)