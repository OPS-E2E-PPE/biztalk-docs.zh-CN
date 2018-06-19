---
title: 单一登录支持 SOAP 适配器 |Microsoft 文档
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
ms.openlocfilehash: 7b6e604eaf7e1b0a9b6144dc20f8bdd59d03932f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277549"
---
# <a name="single-sign-on-support-for-the-soap-adapter"></a>SOAP 适配器的的单一登录支持
可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台来配置企业单一登录 (SSO)，以便与 SOAP 接收位置或发送端口结合使用。 本主题将介绍 SSO 与 SOAP 适配器的协同工作机制。  
  
 **用于 SOAP 的单一登录支持接收位置**  
  
 SOAP 接收位置支持两个版本的 SSO-[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]企业 SSO 和 Microsoft SharePoint 门户服务器 SSO。 运行 BizTalk Web Services 发布向导可启用对 SharePoint Portal Server SSO 的支持。 有关启用 SharePoint 门户服务器 SSO 的详细信息，请参阅[发布 Web 服务](../core/publishing-web-services.md)。 通过使用 SOAP 接收位置的属性页可启用 BizTalk 企业单一登录。 有关为 SOAP 接收位置启用企业 SSO 的详细信息，请参阅[如何配置 SOAP 接收位置](../core/how-to-configure-a-soap-receive-location.md)。  
  
 **企业 SSO 支持用于 SOAP 接收位置**  
  
 Internet 信息服务 (IIS) 接收来自 Web 客户端的 SOAP 请求，然后 IIS 对用户进行验证，并将安全标识符传递到 SOAP 适配器。 如果 IIS 验证方法为摘要验证、基本验证或集成 Windows 身份验证，则 SOAP 适配器将调用 SSO 凭据存储来根据经过验证的用户获取加密票证。 此票证已存储为**SSOTicket**消息的上下文属性中的属性。  
  
 在直通方案中，BizTalk 消息引擎将把消息引入 MessageBox 数据库中。 发送适配器从 MessageBox 数据库接收消息时，它使用加密票证和应用程序名来调用 RedeemTicket 方法，以从 SSO 存储中检索应用程序的安全凭据。 然后，发送适配器将使用外部凭据连接该应用程序并处理请求。 有关关联应用程序的详细信息，请参阅[SSO Affiliate 应用程序](../core/sso-affiliate-applications.md)。  
  
 在业务流程调用发送适配器的方案中，BizTalk 消息引擎将把消息发送到 MessageBox 数据库。 业务流程应确保同时**SSOTicket**上下文属性和**Microsoft.BizTalk.XLANGs.BTXEngine.OriginatorSID**包含票证的消息的上下文属性维护。 从 MessageBox 数据库中接收此消息时，适配器将使用加密票证调用 RedeemTicket 方法，以便从 SSO 存储中检索后端凭据。 设计该业务流程的用户应专门将此属性复制到消息中。  
  
 **SharePoint Portal Server SSO Support for SOAP 接收位置**  
  
 在与 SharePoint Portal Server 集成时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 仅支持通过 SOAP 适配器使用 Microsoft SharePoint Portal Server SSO。 SharePoint Portal Server 创建 SSO 票证，并以 SOAP 请求的 SOAP 标头形式将其发送到 BizTalk Server。 当 SOAP 适配器收到包含 SSO 票证请求时，将被视为票证**SSOTicket**消息的上下文属性中的属性。 这一相同的属性将包含企业 SSO 票证。 只能将一个 SSO 票证与 BizTalk 消息相关联。  
  
 在直通和业务流程方案中，从 SharePoint Portal Server 接收到的 SSO 票证的处理方式与 SOAP 适配器使用企业 SSO 创建的票证的处理方式是一样的。 当发送适配器收到消息时，它将调用**RedeemTicket**具有的加密方法票证生成该 SharePoint Portal Server。 发送端口不需要考虑是否存在不同的 SSO 票证。 **RedeemTicket**方法将确定哪些 SSO 系统生成的票证和兑换从的适当位置。  
  
 **结合使用的企业 SSO 和 SharePoint Portal Server SSO**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 支持同时使用这两种 SSO 系统。 API 可以区分每种 SSO 生成的票证，并在相应的 SSO 数据库中兑换这些票证。 如果同时使用这两个 SSO 系统，则以下规则可确定 SOAP 接收哪些 SSO 票证位置提升到**SSOTicket**上下文属性：  
  
-   如果未启用任何 SSO，则不升级票证。  
  
-   如果启用企业 SSO，但未启用 SharePoint Portal Server SSO，则检索并升级企业 SSO 票证。  
  
-   如果启用 SharePoint Portal Server SSO，但未启用企业 SSO，则升级现有的 SharePoint Portal Server SSO 票证。  
  
-   如果同时启用了企业 SSO 和 SharePoint Portal Server SSO：  
  
    -   如果接收到 SharePoint Portal Server SSO 票证，则升级该票证。  
  
    -   如果未接收到 SharePoint Portal Server SSO 票证，则检索并升级企业 SSO 票证。  
  
 **SOAP 发送适配器的的单一登录支持**  
  
 如果启用了 SSO，当 SOAP 发送端口收到的消息**Secure**属性 (**SSOTicket**)，它调用的 SSO 服务器验证和兑换关联应用程序的票证。 关联应用程序的管理应用程序、关联管理员或 SSO 管理员可调用 SSO 以兑换票证。 然后，SSO 将对票证进行解密，并获取后端凭据。 传递和业务流程方案都是相同的 SOAP 发送端口，如主题的"企业 SSO 支持的 SOAP 接收位置"部分中所述[SOAP 适配器的单一登录支持](../core/single-sign-on-support-for-the-soap-adapter.md)。  
  
 默认情况下，SOAP 发送端口不启用 SSO。 有关为 SOAP 发送端口启用 SSO 的详细信息，请参阅[如何配置 SOAP 发送端口](../core/how-to-configure-a-soap-send-port.md)。