---
title: 单一登录支持个 WCF 适配器 |Microsoft 文档
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
ms.openlocfilehash: 712aa01190762d6c6f74604a5f48c19fe42531d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280053"
---
# <a name="single-sign-on-support-for-the-wcf-adapters"></a>WCF 适配器的单一登录支持
可以使用 BizTalk Server 管理控制台来配置企业单一登录 (SSO)，以便与 WCF 接收位置或发送端口结合使用。 本主题介绍 SSO 与 WCF 适配器的协同工作机制。  
  
 在企业环境中，用户需要与各种各样的系统和应用程序进行交互，可能会出现环境无法在多个进程、产品和计算机间维护用户上下文的情况。 此用户上下文至关重要提供单一登录功能，因为它是需要验证谁启动了原始请求。 为了克服此问题，企业单一登录 (SSO) 提供了 SSO 票证（不是 Kerberos 票证），应用程序可以使用该票证获取与发出原始请求的用户相对应的凭据。  
  
 当接收适配器获得消息后，适配器可以从 SSO 服务器请求一个 SSO 票证。 此加密的票证包含[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]进行请求和超时期限的用户标识。 在获取该票证后，会将其作为属性添加到传入消息中。 当发送适配器传送消息时，适配器使用发放的 SSO 票证和关联应用程序名称（该适配器将试图检索该关联应用程序的凭据）联系 SSO 服务器。 SSO 服务器查找目标关联应用程序的用户凭据，然后将凭据返回给发送适配器，发送适配器使用该凭据将正确验证的消息发送给关联应用程序。  
  
## <a name="single-sign-on-support-for-the-wcf-receive-locations"></a>WCF 接收位置的单一登录支持  
 所应用的安全设置与用于接收位置的 WCF 适配器的类型共同决定了 WCF 接收适配器是否能够发放 SSO 票证。 若要 WCF 接收适配器发放 SSO 令牌，WCF 客户端必须发送一个适配器可以模拟的凭据。 模拟是服务器应用程序承担客户端的身份的能力。 凭据必须映射到有效[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]正确模拟的用户帐户。  
  
> [!NOTE]
>  对于不要求客户端发送凭据进行模拟的安全设置和 WCF 适配器，可以使用客户端在自定义接收管道组件中发送的任何类型的凭据发放 SSO 票证。 接收管道组件的有关如何处理在 SSO 票证的详细信息，请参阅包含在中示例管道组件 InPipelineComp，[服务面向解决方案的文件清单](../core/file-inventory-for-the-service-oriented-solution.md)。  
  
 **有关 WCF BasicHttp 的单一登录支持接收位置**  
  
 WCF-BasicHttp 接收适配器仅在下表所示的安全配置下，才可从 SSO 服务器发放 SSO 票证。  
  
> [!NOTE]
>  有关映射到证书的详细信息[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]用户帐户，请参阅"将证书映射到用户帐户"，网址[http://go.microsoft.com/fwlink/?LinkId=87478](http://go.microsoft.com/fwlink/?LinkId=87478)。  
  
|安全模式|传输客户端凭据类型|消息客户端凭据类型|  
|-------------------|--------------------------------------|------------------------------------|  
|Transport|基本|N/A|  
|Transport|摘要|N/A|  
|Transport|Ntlm|N/A|  
|Transport|Windows|N/A|  
|Transport|证书|N/A|  
|消息|N/A|UserName|  
|消息|N/A|证书|  
|TransportWithMessageCredential|N/A|证书|  
|TransportWithMessageCredential|N/A|UserName|  
|TransportCredentialOnly|基本|N/A|  
|TransportCredentialOnly|摘要|N/A|  
|TransportCredentialOnly|Ntlm|N/A|  
|TransportCredentialOnly|Windows|N/A|  
|TransportCredentialOnly|证书|N/A|  
  
 **有关 WCF WSHttp 的单一登录支持接收位置**  
  
 WCF-WSHttp 接收适配器仅在下表所示的安全配置下，才可从 SSO 服务器发放 SSO 票证。  
  
|安全模式|传输客户端凭据类型|消息客户端凭据类型|  
|-------------------|--------------------------------------|------------------------------------|  
|Transport|基本|N/A|  
|Transport|摘要|N/A|  
|Transport|Ntlm|N/A|  
|Transport|Windows|N/A|  
|Transport|证书|N/A|  
|消息|N/A|UserName|  
|消息|N/A|Windows|  
|消息|N/A|证书|  
|TransportWithMessageCredential|N/A|Windows|  
|TransportWithMessageCredential|N/A|证书|  
|TransportWithMessageCredential|N/A|UserName|  
  
 **有关 WCF NetTcp 的单一登录支持接收位置**  
  
 WCF-NetTcp 接收适配器仅在下表所示的安全配置下，才可从 SSO 服务器发放 SSO 票证。  
  
|安全模式|传输客户端凭据类型|消息客户端凭据类型|  
|-------------------|--------------------------------------|------------------------------------|  
|Transport|Windows|N/A|  
|Transport|证书|N/A|  
|消息|N/A|证书|  
|消息|N/A|Windows|  
|消息|N/A|UserName|  
|TransportWithMessageCredential|N/A|证书|  
|TransportWithMessageCredential|N/A|Windows|  
|TransportWithMessageCredential|N/A|UserName|  
  
 S**ingle 上登录支持 WCF NetNamedPipe 接收位置**  
  
 WCF-NetNamedPipe 接收适配器仅在下表所示的安全配置下，才可从 SSO 服务器发放 SSO 票证。  
  
|安全模式|传输客户端凭据类型|消息客户端凭据类型|  
|-------------------|--------------------------------------|------------------------------------|  
|Transport|N/A|N/A|  
  
 **WCF 自定义和 WCF CustomIsolated 的单一登录支持接收位置**  
  
 若要 WCF-Custom 和 WCF-CustomIsolated 接收位置发放 SSO 票证，接收位置中使用的安全设置需要 WCF 客户端发送可以被 Windows Communication Foundation 模拟的凭据。 WCF 支持模拟各种类型的客户端凭据。 WCF 支持模拟的凭据类型有关的详细信息，请参阅"委派和模拟与 WCF"网址[http://go.microsoft.com/fwlink/?LinkId=87476](http://go.microsoft.com/fwlink/?LinkId=87476)。  
  
## <a name="single-sign-on-support-for-the-wcf-send-ports"></a>WCF 发送端口的单一登录支持  
 对于 WCF 发送端口，只有在下表所示的安全配置下，才能指定一个用于 SSO 的关联应用程序名称。  
  
|安全模式|传输客户端凭据类型|消息客户端凭据类型|  
|-------------------|--------------------------------------|------------------------------------|  
|Transport|摘要|N/A|  
|Transport|基本|N/A|  
|消息|N/A|UserName|  
  
> [!NOTE]
>  WCF 将发送端口以验证并正确，兑换的 SSO 票证**SSOTicket**和**OriginatorSID**上下文属性必须在要发送的消息中可用。 已启用单一登录的接收位置可以从发件人的 [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] 帐户升级这些属性。  
  
## <a name="see-also"></a>另请参阅  
 [企业单一登录](../core/enterprise-single-sign-on2.md)