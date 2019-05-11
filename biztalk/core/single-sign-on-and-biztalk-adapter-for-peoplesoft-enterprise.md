---
title: 用于 PeopleSoft Enterprise 的单一登录和 BizTalk 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- processing HTTP requests
- Single Sign-On, using with the adapter
- HTTP requests, processing
ms.assetid: d8ad75f1-a83f-4722-a43f-50dc95df2f9d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6819b89f7c09fdf347f362f89038e732f6f24396
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393016"
---
# <a name="single-sign-on-and-biztalk-adapter-for-peoplesoft-enterprise"></a>用于 PeopleSoft Enterprise 的单一登录和 BizTalk 适配器
当用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器使用单一登录 (SSO) 时，适配器将从 SSO 凭据数据库中; 获取凭据因此，您无需输入服务器系统的登录凭据**传输属性**对话框。  
  
 在设计时用于 PeopleSoft Enterprise 的 BizTalk 适配器获取用于启动 BizTalk Server 项目的用户的上下文 （适用于指定的关联应用程序） 系统的凭据。 该用户应为应用程序用户。  
  
## <a name="processing-requests"></a>处理请求  
 当 Internet 信息服务 (IIS) 从 Web 客户端收到 HTTP 请求时，IIS 会进行用户身份验证。 ISAPI 扩展模拟 Windows 用户，然后调用 SSO 凭据存储区获取加密的票证。 此票证在消息的上下文中以 SSOTicket 属性形式存储。  
  
 消息然后定向到 Messagebox 数据库。 当 PeopleSoft 企业的 BizTalk 适配器从 Messagebox 数据库接收消息时，它调用 validateandredeemticket，以使用加密票证和关联应用程序名来从 SSO 存储中检索登录凭据。 然后，适配器使用的外部凭据连接到系统并处理该请求。  
  
> [!NOTE]
>  SSO 配置是 BizTalk Server 安装程序的一部分。 如果收到 SSO 错误，请确认使用的域帐户配置 BizTalk Server 中，因为它会影响企业 SSO 服务的功能。 SSO 仅在域帐户下起作用。  
  
## <a name="see-also"></a>请参阅  
 [创建关联应用程序](../core/creating-affiliate-applications2.md)   
 [保护适配器](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)