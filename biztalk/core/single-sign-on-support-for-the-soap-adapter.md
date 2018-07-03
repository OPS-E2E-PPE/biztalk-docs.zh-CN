---
title: 单一登录 SOAP 适配器的支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, SOAP adapters
- SOAP adapters, SharePoint Portal Server
- SOAP adapters, SSO
- SharePoint Portal server
ms.assetid: c7bf755c-c37d-4b19-9817-a7f42e1e9656
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a95673e0f8d7f8a49ba0ad6d5ba6760a6db4b524
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966702"
---
# <a name="single-sign-on-support-for-the-soap-adapter"></a>SOAP 适配器的单一登录支持
可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台来配置企业单一登录 (SSO)，以便与 SOAP 接收位置或发送端口结合使用。 本主题将介绍 SSO 与 SOAP 适配器的协同工作机制。  
  
 **接收位置的 SOAP 的单一登录支持**  
  
 SOAP 接收位置支持两个版本的 SSO —[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]企业 SSO 和 Microsoft SharePoint Portal Server SSO。 运行 BizTalk Web Services 发布向导可启用对 SharePoint Portal Server SSO 的支持。 有关启用 SharePoint Portal Server SSO 的详细信息，请参阅[发布 Web Services](../core/publishing-web-services.md)。 通过使用 SOAP 接收位置的属性页可启用 BizTalk 企业单一登录。 有关为 SOAP 接收位置启用企业 SSO 的详细信息，请参阅[如何配置 SOAP 接收位置](../core/how-to-configure-a-soap-receive-location.md)。  
  
 **企业 SSO 支持对 SOAP 接收位置**  
  
 Internet 信息服务 (IIS) 接收来自 Web 客户端的 SOAP 请求，然后 IIS 对用户进行验证，并将安全标识符传递到 SOAP 适配器。 如果 IIS 验证方法为摘要验证、基本验证或集成 Windows 身份验证，则 SOAP 适配器将调用 SSO 凭据存储来根据经过验证的用户获取加密票证。 此票证将被视为**SSOTicket**消息上下文属性中的属性。  
  
 在直通方案中，BizTalk 消息引擎将把消息引入 MessageBox 数据库中。 发送适配器从 MessageBox 数据库接收消息时，它使用加密票证和应用程序名来调用 RedeemTicket 方法，以从 SSO 存储中检索应用程序的安全凭据。 然后，发送适配器将使用外部凭据连接该应用程序并处理请求。 有关关联应用程序的详细信息，请参阅[SSO 关联应用程序](../core/sso-affiliate-applications.md)。  
  
 在业务流程调用发送适配器的方案中，BizTalk 消息引擎将把消息发送到 MessageBox 数据库。 业务流程应确保同时**SSOTicket**上下文属性和**Microsoft.BizTalk.XLANGs.BTXEngine.OriginatorSID**是包含该票证在消息上下文属性维护。 从 MessageBox 数据库中接收此消息时，适配器将使用加密票证调用 RedeemTicket 方法，以便从 SSO 存储中检索后端凭据。 设计该业务流程的用户应专门将此属性复制到消息中。  
  
 **SharePoint Portal Server SSO 支持对 SOAP 接收位置**  
  
 在与 SharePoint Portal Server 集成时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 仅支持通过 SOAP 适配器使用 Microsoft SharePoint Portal Server SSO。 SharePoint Portal Server 创建 SSO 票证，并以 SOAP 请求的 SOAP 标头形式将其发送到 BizTalk Server。 当 SOAP 适配器收到包含 SSO 票证请求时，该票证存储作为**SSOTicket**消息上下文属性中的属性。 这一相同的属性将包含企业 SSO 票证。 只能将一个 SSO 票证与 BizTalk 消息相关联。  
  
 在直通和业务流程方案中，从 SharePoint Portal Server 接收到的 SSO 票证的处理方式与 SOAP 适配器使用企业 SSO 创建的票证的处理方式是一样的。 当发送适配器收到消息时，它将调用**RedeemTicket**方法使用加密票证生成该 SharePoint Portal Server。 发送端口不需要考虑是否存在不同的 SSO 票证。 **RedeemTicket**方法将确定哪种 SSO 系统生成票证，并从相应的位置兑换。  
  
 **组合使用企业 SSO 和 SharePoint Portal Server SSO**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 支持同时使用这两种 SSO 系统。 API 可以区分每种 SSO 生成的票证，并在相应的 SSO 数据库中兑换这些票证。 如果同时使用这两种 SSO 系统，下列规则确定哪种 SSO 票证 SOAP 接收位置将提升为**SSOTicket**上下文属性：  
  
- 如果未启用任何 SSO，则不升级票证。  
  
- 如果启用企业 SSO，但未启用 SharePoint Portal Server SSO，则检索并升级企业 SSO 票证。  
  
- 如果启用 SharePoint Portal Server SSO，但未启用企业 SSO，则升级现有的 SharePoint Portal Server SSO 票证。  
  
- 如果同时启用了企业 SSO 和 SharePoint Portal Server SSO：  
  
  -   如果接收到 SharePoint Portal Server SSO 票证，则升级该票证。  
  
  -   如果未接收到 SharePoint Portal Server SSO 票证，则检索并升级企业 SSO 票证。  
  
  **SOAP 发送适配器的单一登录支持**  
  
  如果启用 SSO，则当 SOAP 发送端口收到的消息**Secure**属性 (**SSOTicket**)，它将调用 SSO 服务器以验证并兑换票证关联应用程序。 关联应用程序的管理应用程序、关联管理员或 SSO 管理员可调用 SSO 以兑换票证。 然后，SSO 将对票证进行解密，并获取后端凭据。 直通和业务流程方案是相同的 SOAP 发送端口，如本主题的"企业 SSO 支持的 SOAP 接收位置"部分中所述[SOAP 适配器的单一登录支持](../core/single-sign-on-support-for-the-soap-adapter.md)。  
  
  默认情况下，SOAP 发送端口不启用 SSO。 有关为 SOAP 发送端口启用 SSO 的详细信息，请参阅[如何配置 SOAP 发送端口](../core/how-to-configure-a-soap-send-port.md)。