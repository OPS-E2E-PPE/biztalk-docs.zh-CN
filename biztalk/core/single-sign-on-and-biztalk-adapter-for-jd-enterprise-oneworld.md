---
title: "有关博士企业 OneWorld 单一登录和 BizTalk 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Single Sign-On
ms.assetid: 44fea3a4-8073-4b64-94e5-1eacbae845d9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3b0fbe7aa671d543a0fd6cd7da78e05d18c63c3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="single-sign-on-and-biztalk-adapter-for-jd-enterprise-oneworld"></a>有关博士企业 OneWorld 单一登录和 BizTalk 适配器
单一登录 (SSO) 凭据是从数据库中获取 SSO 凭据;因此，不需要输入中的服务器系统的登录凭据**传输属性**窗口。  
  
 在设计时，用于 JD Edwards OneWorld 的 BizTalk 适配器即会在启动 BizTalk Server 项目的用户的上下文中，为指定的关联应用程序获取用于系统的凭据。 此用户应为应用程序用户。  
  
 运行时，将 JD Edwards OneWorld 的 BizTalk 适配器用作使用 SSO 时的简单直通方案中的接收位置。  
  
 当 Internet 信息服务 (IIS) 从 Web 客户端接收到 HTTP 请求时，IIS 将验证该用户。 使用 ISAPI 扩展插件模拟 Windows 用户，并调用要获得加密的票证的 SSO 凭据存储区。 此票证在消息上下文中以 SSOTicket 属性形式存储。  
  
 消息即定向到 MessageBox 数据库。 适配器从 MessageBox 数据库接收消息时，它使用加密票证和关联应用程序名来调用 IBTSTicket.ValidateAndRedeemTicket 方法，以从 SSO 存储中检索登录凭据。 然后，用于 JD Edwards OneWorld 的 BizTalk 适配器使用外部凭据连接到系统并处理请求。  
  
> [!NOTE]
>  SSO 配置是 BizTalk Server 安装程序的一部分。 如果你收到 SSO 错误，请验证使用域帐户时配置 BizTalk Server 中，因为这会影响企业 SSO 服务的功能。 SSO 仅在域帐户下起作用。  
  
## <a name="see-also"></a>另请参阅  
 [创建关联应用程序](../core/creating-affiliate-applications3.md)   
 [适配器中的安全](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)