---
title: '示例 TMA: Enterprise 上单一登录 |Microsoft 文档'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security examples [TMA], SSO
- architecture, examples
- SSO, examples
- SSO, TMA
- DFD, SSO
- examples, SSO
- examples, TMA
ms.assetid: c2c15b1b-54f3-4d1a-b3d8-6679abd41ccb
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb57e7b22680844e3ddb18481aa76002df78b013
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22273189"
---
# <a name="sample-tma-enterprise-single-sign-on"></a>示例 TMA: Enterprise 上单一登录
本主题对示例结构的企业单一登录方案进行威胁模型分析 (TMA)。  
  
 下图显示基示例体系结构，其中包括企业单一登录方案。  
  
 **图 1 基示例体系结构，包括企业单一登录方案**  
  
 ![基本体系结构组件](../core/media/tdi-sec-refarch.gif "TDI_Sec_RefArch_")  
  
## <a name="step-1-collect-background-information-enterprise-single-sign-on-scenario"></a>步骤 1. 收集背景信息 （企业单一登录方案）  
 本部分提供在将 Windows 凭据映射到用来连接到后端网络的凭据时使用企业单一登录方案的数据的流关系图 (DFD)。  
  
 所有其他背景信息是相同的所有我们使用方案，以及前面所述[示例方案的背景信息](../core/background-information-for-sample-scenarios.md)。  
  
### <a name="data-flow-diagram"></a>数据流关系图  
 下图显示为企业单一登录方案 DFD。  
  
 **图 2 DFD 为企业单一登录方案**  
  
 ![DFD 上的企业单一登录 &#45;](../core/media/tdi-sec-refarch-dfd-sso.gif "TDI_Sec_RefArch_DFD_SSO")  
  
 数据流如下所述：  
  
1.  用户或应用程序登录使用 Windows 凭据。  
  
2.  企业单一登录使用的 Windows 凭据来请求为后端网络凭据。  
  
3.  企业单一登录将映射到 SSO 数据库中存储的后端凭据的 Windows 凭据。  
  
4.  企业单一登录检索后端凭据，并使用它们来将用户或应用程序到后端网络连接。  
  
## <a name="step-2-create-and-analyze-the-threat-model-enterprise-single-sign-on-scenario"></a>步骤 2. 创建和分析的威胁模型 （企业单一登录方案）  
 本部分提供了我们的示例体系结构的企业单一登录方案未 TMA 的结果。  
  
-   **标识入口点、 信任边界和数据的流**-请参阅前面的步骤 1 和中所述的背景信息[示例方案的背景信息](../core/background-information-for-sample-scenarios.md)。  
  
-   **创建的标识的威胁列表**-我们使用以下分类 DFD 中的所有条目来识别潜在威胁的方案： **S**哄骗标识， **T**篡改数据， **R**epudiation，**我**璝泄露**D**的服务，用以和**E**提升特权。 下表列出了当你使用企业单一登录 (SSO) 来发送和接收消息与 BizTalk Server 我们标识的威胁。  
  
 **表 1 的标识的威胁的列表**  
  
|威胁|Description|资产|影响|  
|------------|-----------------|-----------|------------|  
|主密钥服务器是单点故障|如果恶意用户威胁的主密钥服务器，SSO 计算机将无法加密的凭据 （它位于能够继续解密凭据）。|BizTalk Server 和 SSO 环境|拒绝服务|  
|恶意用户可以欺骗客户端或服务器|如果客户端或服务器运行 Windows 时未 NTLM 身份验证，恶意用户可以欺骗客户端或服务器。|BizTalk Server 和 SSO 环境|身份欺骗<br /><br /> 篡改数据<br /><br /> 抵赖<br /><br /> 信息泄漏<br /><br /> 拒绝服务<br /><br /> 特权提升|  
|从一台服务器路由到另一个，恶意用户可以篡改数据|服务器之间的通信是以明文形式，并传播时，恶意用户可能可以读取的数据。|data|篡改数据<br /><br /> 信息泄漏|  
  
## <a name="step-3-review-threats-enterprise-single-sign-on-scenario"></a>步骤 3. 查看威胁 （企业单一登录方案）  
 本部分提供了我们所做的有关参考体系结构企业单一登录 (SSO) 方案，我们识别的威胁的风险分析的结果。 后会议的主要威胁模型，我们查看威胁和使用的已用以下影响类别，以确定对每种威胁的风险： **D**amage 潜在， **R**eproducibility， **E**xploitability， **A**ffected 用户和**D**iscoverability。  
  
 下表列出了当你使用企业单一登录来发送和接收消息与 BizTalk Server 我们标识的威胁的风险级别。  
  
 **表 2 的标识的威胁的风险等级**  
  
|威胁|影响|潜在损害|可再现性|可利用性|受影响的用户|可发现性|风险度|  
|------------|------------|----------------------|---------------------|--------------------|--------------------|---------------------|-------------------|  
|主密钥服务器是单点故障|拒绝服务|2|3|2|1|2|2|  
|恶意用户可以欺骗客户端或服务器|身份欺骗<br /><br /> 篡改数据<br /><br /> 抵赖<br /><br /> 信息泄漏<br /><br /> 拒绝服务<br /><br /> 特权提升|3|2|2|2|1|2|  
|从一台服务器路由到另一个，恶意用户可以篡改数据|篡改数据<br /><br /> 信息泄漏|3|1|1|2|1|1.6|  
  
## <a name="step-4-identify-mitigation-techniques-enterprise-single-sign-on-scenario"></a>步骤 4. 标识缓解技术 （企业单一登录方案）  
 本节提供一些缓解技术进行我们已识别为企业单一登录方案示例体系结构的威胁。  
  
 下表列出缓解技术和技术的企业单一登录使用时，我们识别威胁。  
  
 **表 3 缓解技术和技术**  
  
|威胁|影响|风险度|缓解措施|  
|------------|------------|-------------------|--------------------------------------------|  
|主密钥服务器是单点故障|拒绝服务|2|为主密钥服务器使用主动-被动群集配置。<br /><br /> 有关群集的主密钥服务器的详细信息，请参阅[为企业单一登录的高可用性](../core/high-availability-for-enterprise-single-sign-on.md)。|  
|恶意用户可以欺骗客户端或服务器|身份欺骗<br /><br /> 篡改数据<br /><br /> 抵赖<br /><br /> 信息泄漏<br /><br /> 拒绝服务<br /><br /> 特权提升|2|如果您的网络支持 Kerberos 验证，则应注册所有 SSO 服务器。 当你使用主密钥服务器与 SSO 数据库之间的 Kerberos 身份验证时，你必须在 SSO 数据库所在的 SQL Server 上配置服务主体名称 (SPN)。<br /><br /> 有关如何配置服务主体名称的详细信息，请参阅 Microsoft TechNet 网站，网址[http://go.microsoft.com/fwlink/?LinkId=61374](http://go.microsoft.com/fwlink/?LinkId=61374)。|  
|从一台服务器路由到另一个，恶意用户可以篡改数据|篡改数据<br /><br /> 信息泄漏|1.6|所有 SSO 服务器与 SSO 数据库之间使用 Internet 协议安全性 (IPsec) 或安全套接字层 (SSL)。<br /><br /> 有关 SSL 的详细信息，请参阅以下 Microsoft 帮助和支持 Web 站点[http://go.microsoft.com/fwlink/?LinkID=189708](http://go.microsoft.com/fwlink/?LinkID=189708)。<br /><br /> 有关如何使用所有 SSO 服务器与 SSO 数据库之间的 SSL 的详细信息，请参阅[如何为 SSO 启用 SSL](../core/how-to-enable-ssl-for-sso.md)。|  
  
## <a name="see-also"></a>另请参阅  
 [威胁模型分析](../core/threat-model-analysis.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)   
 [对于小型和中型公司示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)