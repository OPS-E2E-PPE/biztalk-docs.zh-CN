---
title: 用于 JD Enterprise OneWorld 的单一登录和 BizTalk 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Single Sign-On
ms.assetid: 44fea3a4-8073-4b64-94e5-1eacbae845d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec5be842305bbad1fb6e6963b4fcdd770a989224
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393036"
---
# <a name="single-sign-on-and-biztalk-adapter-for-jd-enterprise-oneworld"></a>用于 JD Enterprise OneWorld 的单一登录和 BizTalk 适配器
单一登录 (SSO) 凭据获取从 SSO 凭据数据库;因此，不需要输入中的服务器系统的登录凭据**传输属性**窗口。  
  
 在设计时用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器获取用于启动 BizTalk Server 项目的用户的上下文 （适用于指定的关联应用程序） 系统的凭据。 该用户应为应用程序用户。  
  
 在运行时使用的 BizTalk 适配器用于 JD Edwards OneWorld 的简单直通方案中的接收位置以使用 SSO 时。  
  
 当 Internet 信息服务 (IIS) 从 Web 客户端收到 HTTP 请求时，IIS 会进行用户身份验证。 ISAPI 扩展模拟 Windows 用户，并调用要获取加密的票证的 SSO 凭据存储区。 此票证在消息的上下文中以 SSOTicket 属性形式存储。  
  
 消息然后定向到 Messagebox 数据库。 当适配器从 Messagebox 数据库接收消息时，它调用 IBTSTicket.ValidateAndRedeemTicket 方法使用加密票证和关联应用程序名来从 SSO 存储中检索登录凭据。 用于 JD Edwards OneWorld 的 BizTalk 适配器使用的外部凭据连接到系统并处理该请求。  
  
> [!NOTE]
>  SSO 配置是 BizTalk Server 安装程序的一部分。 如果收到 SSO 错误，请确认使用的域帐户配置 BizTalk Server 中，因为这会影响企业 SSO 服务的功能。 SSO 仅在域帐户下起作用。  
  
## <a name="see-also"></a>请参阅  
 [创建关联应用程序](../core/creating-affiliate-applications3.md)   
 [适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)