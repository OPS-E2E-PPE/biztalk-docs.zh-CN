---
title: 单一登录的 WCF 适配器的支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF adapters, Single Sign-On
- Single Sign-On, WCF adapters
ms.assetid: 70a33d87-50bd-41de-9084-68dd66b0dbf9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aebbe98182d1bc2e97b2ee46245a6d23bfdbe719
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399259"
---
# <a name="single-sign-on-support-for-the-wcf-adapters"></a>WCF 适配器的单一登录支持
用于 WCF 接收位置或发送端口使用 BizTalk 管理控制台，可以配置企业单一登录 (SSO)。 本主题介绍 SSO 与 WCF 适配器的工作方式。  
  
 在企业环境中，其中用户与各种系统和应用程序交互，则很可能在环境不维护通过多个进程、 产品和计算机的用户上下文。 此用户上下文至关重要提供单一登录功能，因为它不需要验证原始请求的发起人。 若要解决此问题的企业单一登录 (SSO) 提供了应用程序可用于获取向发出原始请求的用户相对应的凭据的 SSO 票证 （不 Kerberos 票证）。  
  
 当接收适配器收到一条消息时，适配器可以从 SSO 服务器请求 SSO 票证。 此加密的票证包含[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]发出请求，并在超时期限的用户的标识。 获取该票证后，它是作为属性添加到传入的消息。 当发送适配器传送消息时，适配器将联系 SSO 服务器发放的 SSO 票证和关联应用程序名称为其适配器尝试检索凭据。 SSO 服务器查找目标关联应用程序的用户凭据，然后将凭据返回给发送适配器，用它来将正确验证的消息发送到关联应用程序。  
  
## <a name="single-sign-on-support-for-the-wcf-receive-locations"></a>接收位置的 WCF 的单一登录支持  
 与用于接收位置的 WCF 适配器的类型结合使用的应用的安全设置决定了 WCF 接收适配器是否能够发放 SSO 票证。 为 WCF 接收适配器发放 SSO 令牌，WCF 客户端必须发送适配器可以模拟的凭据。 模拟是服务器应用程序的客户端标识的能力。 该凭据必须映射为有效[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]正确的模拟的用户帐户。  
  
> [!NOTE]
>  有关安全设置和不要求客户端发送凭据进行模拟的 WCF 适配器，可以使用任何类型的客户端发送的自定义接收管道组件中的凭据发放 SSO 票证。 接收管道组件的有关如何处理中的 SSO 票证的详细信息，请参阅中包含的示例管道组件 inpipelinecomp，该示例[面向服务的解决方案的文件清单](../core/file-inventory-for-the-service-oriented-solution.md)。  
  
 **单一登录支持 Wcf-basichttp 接收位置**  
  
 Wcf-basichttp 接收适配器可从仅在下表中所示的安全配置中的 SSO 服务器发放 SSO 票证。  
  
> [!NOTE]
>  有关将证书映射到更多信息[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]用户帐户，请参阅"将证书映射到用户帐户"，网址[ http://go.microsoft.com/fwlink/?LinkId=87478 ](http://go.microsoft.com/fwlink/?LinkId=87478)。  
  
|安全模式|传输客户端凭据类型|消息客户端凭据类型|  
|-------------------|--------------------------------------|------------------------------------|  
|Transport|基本|不可用|  
|Transport|摘要|不可用|  
|Transport|Ntlm|不可用|  
|Transport|Windows|不可用|  
|Transport|证书|不可用|  
|消息|不可用|UserName|  
|消息|不可用|证书|  
|TransportWithMessageCredential|不可用|证书|  
|TransportWithMessageCredential|不可用|UserName|  
|TransportCredentialOnly|基本|不可用|  
|TransportCredentialOnly|摘要|不可用|  
|TransportCredentialOnly|Ntlm|不可用|  
|TransportCredentialOnly|Windows|不可用|  
|TransportCredentialOnly|证书|不可用|  
  
 **接收位置的 WCF-WSHttp 的单一登录支持**  
  
 Wcf-wshttp 接收适配器可从仅在下表中所示的安全配置中的 SSO 服务器发放 SSO 票证。  
  
|安全模式|传输客户端凭据类型|消息客户端凭据类型|  
|-------------------|--------------------------------------|------------------------------------|  
|Transport|基本|不可用|  
|Transport|摘要|不可用|  
|Transport|Ntlm|不可用|  
|Transport|Windows|不可用|  
|Transport|证书|不可用|  
|消息|不可用|UserName|  
|消息|不可用|Windows|  
|消息|不可用|证书|  
|TransportWithMessageCredential|不可用|Windows|  
|TransportWithMessageCredential|不可用|证书|  
|TransportWithMessageCredential|不可用|UserName|  
  
 **接收位置的 WCF NetTcp 的单一登录支持**  
  
 Wcf-nettcp 接收适配器可从仅在下表中所示的安全配置中的 SSO 服务器发放 SSO 票证。  
  
|安全模式|传输客户端凭据类型|消息客户端凭据类型|  
|-------------------|--------------------------------------|------------------------------------|  
|Transport|Windows|不可用|  
|Transport|证书|不可用|  
|消息|不可用|证书|  
|消息|不可用|Windows|  
|消息|不可用|UserName|  
|TransportWithMessageCredential|不可用|证书|  
|TransportWithMessageCredential|不可用|Windows|  
|TransportWithMessageCredential|不可用|UserName|  
  
 S**ingle Wcf-netnamedpipe 接收位置的单一登录支持**  
  
 Wcf-netnamedpipe 接收适配器可从仅在下表中所示的安全配置中的 SSO 服务器发放 SSO 票证。  
  
|安全模式|传输客户端凭据类型|消息客户端凭据类型|  
|-------------------|--------------------------------------|------------------------------------|  
|Transport|不可用|不可用|  
  
 **单一登录支持 Wcf-custom 和 Wcf-customisolated 接收位置**  
  
 对于 Wcf-custom 和 Wcf-customisolated 接收位置以发放 SSO 票证，接收位置中使用的安全设置需要 WCF 客户端发送可以通过 Windows Communication Foundation 模拟的凭据。 WCF 支持模拟的各种类型的客户端凭据。 有关 WCF 支持模拟的凭据类型的详细信息，请参阅"委派和模拟使用 WCF"网址[ http://go.microsoft.com/fwlink/?LinkId=87476 ](http://go.microsoft.com/fwlink/?LinkId=87476)。  
  
## <a name="single-sign-on-support-for-the-wcf-send-ports"></a>WCF 发送端口的单一登录支持  
 对于 WCF 发送端口，可以指定要用于仅在下表中所示的安全配置中的 SSO 关联应用程序名称。  
  
|安全模式|传输客户端凭据类型|消息客户端凭据类型|  
|-------------------|--------------------------------------|------------------------------------|  
|Transport|摘要|不可用|  
|Transport|基本|不可用|  
|消息|不可用|UserName|  
  
> [!NOTE]
>  为使 WCF 发送端口验证和兑换 SSO 票证正确**SSOTicket**并**OriginatorSID**上下文属性必须是要发送的消息中。 使用单一登录启用接收位置可以将这些属性从发件人的提升[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]帐户。  
  
## <a name="see-also"></a>请参阅  
 [企业单一登录](../core/enterprise-single-sign-on2.md)