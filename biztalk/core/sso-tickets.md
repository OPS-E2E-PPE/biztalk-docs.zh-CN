---
title: SSO 票证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tickets [SSO]
ms.assetid: acf01422-4696-4301-b85f-7026e792bb5c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b732704fa9fd7c6a1e48e82b257800f81a02c95
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398969"
---
# <a name="sso-tickets"></a>SSO 票证
在企业环境中，其中用户与各种系统和应用程序交互，它是很有可能在环境不维护通过多个进程、 产品和计算机的用户上下文。 此用户上下文至关重要提供单一登录功能，按需验证原始请求的发起人。 若要解决此问题的企业单一登录 (SSO) 提供了应用程序可用于获取向发出原始请求的用户相对应的凭据的 SSO 票证 （不 Kerberos 票证）。 默认情况下不启用 SSO 票证。 有关启用票证的详细信息，请参阅[如何配置 SSO 票证](../core/how-to-configure-the-sso-tickets.md)。  
  
 SSO 系统颁发票证时请求的身份验证的 Windows 用户。 SSO 系统可以颁发票证发出请求的用户或远程用户。 票证包含加密的域和用户名的当前用户以及票证到期时间。 SSO 系统颁发票证后，其有效期为两个分钟默认情况下。 SSO 管理员可以修改票证的到期时间。 SSO 管理员还可以在关联应用程序级别上设置票证超时。 有关详细信息，请参阅[如何配置 SSO 票证](../core/how-to-configure-the-sso-tickets.md)。  
  
 在应用程序验证原始请求方的标识后，应用程序将兑换票证以获取发起请求关联应用程序的用户的凭据。 应用程序可以兑换票证从 SSO 系统中有两种：  
  
- **只兑换。** 当应用程序启动时若要兑换票证的请求时，请求必须包含要连接到的关联应用程序以及票证本身的名称。 只有特定关联应用程序、 SSO 关联管理员或 SSO 管理员的应用程序管理员才能够兑换票证。 应使用**只兑换**颁发票证的应用程序和兑换票证的应用程序之间的受信任的子系统时。 只有指定的关联应用程序的应用程序管理员可以兑换票证的用户。  
  
- **验证并兑换。** 票证包含 SSO 系统已为其执行凭据查找的用户有关的信息。 在这种情况下，SSO 服务将验证原始消息的发件人和票证的用户相同之前在系统兑换票证。 Microsoft BizTalk Server 适配器方案就利用此机制。  
  
  SSO 管理员可以禁用票证超时上每个关联应用程序。 尽管这不建议在早期版本中，此版本支持使用每个关联应用程序票证超时。 此选项可以在关联应用程序级别上设置票证超时。 如果未指定，则使用在全局级别指定的票证超时值。  
  
  SSO 关联管理员可以指定允许票证和票证验证，需要在每个关联应用程序。 但是，如果 SSO 管理员指定在 SSO 系统级别票证验证是必需的 SSO 关联管理员不能将关闭此选项在关联应用程序级别。  
  
> [!IMPORTANT]
>  在使用 SSO 票证，必须确保票证超时值足够长上, 一次之间的时间兑换颁发票证之时的时间。  
  
## <a name="see-also"></a>请参阅  
 [管理用户映射](../core/managing-user-mappings.md)