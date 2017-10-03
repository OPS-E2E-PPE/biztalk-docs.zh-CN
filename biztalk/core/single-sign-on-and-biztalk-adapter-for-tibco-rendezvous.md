---
title: "有关 TIBCO 会合单一登录和 BizTalk 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, using with the adapter
- Single Sign-On, using with the adapter
- HTTP requests, processing
ms.assetid: 52e698bb-38ba-4a12-b15a-d1581061d62f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54529d8eefb351471ea1c2bd7278c744737b66f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-and-biztalk-adapter-for-tibco-rendezvous"></a>TIBCO Rendezvous 的单一登录和 BizTalk 适配器
当你在为 TIBCO 会合使用 Microsoft BizTalk 适配器使用单一登录 (SSO) 时，适配器从 SSO 凭据数据库; 获取凭据因此，你无需输入服务器系统中的登录凭据**传输属性**窗口。  
  
 在设计时，适配器将会在启动 BizTalk Server 项目的用户的上下文中，为指定的关联应用程序获取用于系统的凭据。 此用户应为应用程序用户。 运行时，将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 接收适配器用作使用 SSO 时的简单直通方案中的接收位置。  
  
## <a name="processing-requests"></a>处理请求  
 当 Internet 信息服务 (IIS) 从 Web 客户端接收到 HTTP 请求时，IIS 将验证该用户。 使用 ISAPI 扩展插件模拟 Windows 用户，并调用要获得加密的票证的 SSO 凭据存储区。 此票证在消息上下文中以 SSOTicket 属性形式存储。  
  
 消息即定向到 MessageBox 数据库。 用于 TIBCO Rendezvous 的 BizTalk 适配器从 MessageBox 数据库接收消息时，它使用加密票证和关联应用程序名来调用 `ValidateAndRedeemTicket`，以从 SSO 存储中检索登录凭据。 然后，适配器将使用外部凭据连接该系统并处理请求。  
  
> [!NOTE]
>  SSO 配置是 BizTalk Server 安装程序的一部分。 如果你收到 SSO 错误，请验证使用域帐户时配置 BizTalk Server 中，因为这会影响企业 SSO 服务的功能。 SSO 仅在域帐户下起作用。  
  
## <a name="see-also"></a>另请参阅  
 [创建关联应用程序](../core/creating-affiliate-applications1.md)   
 [使用单一登录](../core/using-single-sign-on5.md)