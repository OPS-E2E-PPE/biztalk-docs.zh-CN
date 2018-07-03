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
ms.openlocfilehash: 0e1ae40e43924faca6a5154b2b62a154fea1ea9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012710"
---
# <a name="sso-tickets"></a>SSO 票证
在企业环境中，用户需要与各种各样的系统和应用程序进行交互，很可能会出现环境不通过多个进程、产品和计算机维护用户上下文的情况。 此用户上下文对于提供单一登录功能至关重要，因为需要确认原始请求的发起人。 为了克服此问题，企业单一登录 (SSO) 提供了 SSO 票证（不是 Kerberos 票证），应用程序可以使用该票证获取与发出原始请求的用户相对应的凭据。 默认情况下，不启用 SSO 票证。 有关启用票证的详细信息，请参阅[如何配置 SSO 票证](../core/how-to-configure-the-sso-tickets.md)。  
  
 当经过验证的 Windows 用户发出请求时，SSO 系统将颁发票证。 SSO 系统可为发出请求的用户或远程用户颁发票证。 票证包含当前用户加密的域和用户名以及票证到期时间。 SSO 系统颁发票证之后，默认情况下该票证将在两分钟内到期。 SSO 管理员可以修改票证的到期时间。 SSO 管理员还可以在关联应用程序级别上设置票证超时。 有关详细信息，请参阅[如何配置 SSO 票证](../core/how-to-configure-the-sso-tickets.md)。  
  
 在应用程序验证原始请求方的标识之后，该应用程序将兑换票证以获取发起请求关联应用程序的用户的凭据。 应用程序可以通过以下两种方式之一从 SSO 系统兑换票证：  
  
- **只兑换。** 当应用程序发起兑换票证的请求时，该请求必须包含要连接到的关联应用程序的名称以及票证本身。 只有特定关联应用程序的应用程序管理员、SSO 关联管理员或 SSO 管理员才能够兑换票证。 应使用**只兑换**颁发票证的应用程序和兑换票证的应用程序之间的受信任的子系统时。 只有指定关联应用程序的应用程序管理员才能够为用户兑换票证。  
  
- **验证并兑换。** 票证包含 SSO 系统为其执行凭据查找的用户的有关信息。 在这种情况下，在系统兑换票证之前，SSO 服务将验证原始消息的发件人和票证的用户是否相同。 Microsoft BizTalk Server 适配器方案就利用了此机制。  
  
  SSO 管理员可针对每个关联应用程序禁用票证超时。 尽管在以前的版本中并不建议这样做，但此版本支持针对每个关联应用程序使用票证超时。 通过此选项，您可以在关联应用程序级别上设置票证超时。 如果未指定此选项，则使用在全局级别上指定的票证超时。  
  
  SSO 关联管理员可指定允许票证，并指定需要基于每个关联应用程序进行票证验证。 不过，如果 SSO 管理员在 SSO 系统级别上指定需要对票证进行验证，则 SSO 关联管理员将不能在关联应用程序级别上禁用此选项。  
  
> [!IMPORTANT]
>  在使用 SSO 票证时，必须确保票证超时值足够长，以便可以从颁发票证之时延续到兑换票证之时。  
  
## <a name="see-also"></a>请参阅  
 [管理用户映射](../core/managing-user-mappings.md)