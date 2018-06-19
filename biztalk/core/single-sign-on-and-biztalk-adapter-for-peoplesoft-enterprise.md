---
title: PeopleSoft 企业单一登录和 BizTalk 适配器 |Microsoft 文档
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
ms.openlocfilehash: 2bb898906bfd3087ef909e59990a16ce16c2822c
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015596"
---
# <a name="single-sign-on-and-biztalk-adapter-for-peoplesoft-enterprise"></a>PeopleSoft Enterprise 的单一登录和 BizTalk 适配器
当使用单一登录 (SSO) 与 Microsoft BizTalk 适配器 PeopleSoft 企业时，适配器从 SSO 凭据数据库; 获取凭据因此，你无需输入服务器系统中的登录凭据**传输属性**对话框。  
  
 在设计时，用于 PeopleSoft Enterprise 的 BizTalk 适配器即会在启动 BizTalk Server 项目的用户的上下文中，为指定的关联应用程序获取用于系统的凭据。 此用户应为应用程序用户。  
  
## <a name="processing-requests"></a>处理请求  
 当 Internet 信息服务 (IIS) 从 Web 客户端接收到 HTTP 请求时，IIS 将验证该用户。 ISAPI 扩展模拟该 Windows 用户，然后调用 SSO 凭据存储以获取加密的票证。 此票证在消息上下文中以 SSOTicket 属性形式存储。  
  
 消息即定向到 MessageBox 数据库。 用于 PeopleSoft Enterprise 的 BizTalk 适配器从 MessageBox 数据库接收消息时，它使用加密票证和关联应用程序名来调用 ValidateAndRedeemTicket，以从 SSO 存储中检索登录凭据。 然后，适配器将使用外部凭据连接该系统并处理请求。  
  
> [!NOTE]
>  SSO 配置是 BizTalk Server 安装程序的一部分。 如果你收到 SSO 错误，请验证使用域帐户时配置 BizTalk Server 中，因为这会影响企业 SSO 服务的功能。 SSO 仅在域帐户下起作用。  
  
## <a name="see-also"></a>另请参阅  
 [创建关联应用程序](../core/creating-affiliate-applications2.md)   
 [安全适配器](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)