---
title: 示例 TMA:企业单一登录 |Microsoft Docs
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
ms.openlocfilehash: 9c87a27ced896214e361d6056da2e1b5e13c0883
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393912"
---
# <a name="sample-tma-enterprise-single-sign-on"></a>示例 TMA:企业单一登录
本主题介绍对示例结构的企业单一登录方案进行威胁模型分析 (TMA)。  
  
 下图显示了基本示例结构，其中包括企业单一登录方案。  
  
 **图 1 包含企业单一登录方案的基本示例结构**  
  
 ![基本结构组件](../core/media/tdi-sec-refarch.gif "TDI_Sec_RefArch_")  
  
## <a name="step-1-collect-background-information-enterprise-single-sign-on-scenario"></a>步骤 1. 收集背景信息 （企业单一登录方案）  
 本部分提供 Windows 凭据映射到用来连接到后端网络的凭据时使用企业单一登录方案的数据流关系图 (DFD)。  
  
 所有其他背景信息是相同的所有使用方案，以及前面所述[示例方案的背景信息](../core/background-information-for-sample-scenarios.md)。  
  
### <a name="data-flow-diagram"></a>数据流关系图  
 下图显示了企业单一登录方案的 dfd:。  
  
 **图 2 DFD 企业单一登录方案**  
  
 ![企业单一登录的 dfd:&#45;上](../core/media/tdi-sec-refarch-dfd-sso.gif "TDI_Sec_RefArch_DFD_SSO")  
  
 数据流如下所示：  
  
1.  用户或应用程序登录使用 Windows 凭据。  
  
2.  企业单一登录使用 Windows 凭据来请求后端网络的凭据。  
  
3.  企业单一登录将映射到存储在 SSO 数据库中的后端凭据的 Windows 凭据。  
  
4.  企业单一登录检索后端凭据，并使用它们来连接到后端网络的应用程序的用户。  
  
## <a name="step-2-create-and-analyze-the-threat-model-enterprise-single-sign-on-scenario"></a>步骤 2. 创建和分析威胁模型 （企业单一登录方案）  
 本部分提供执行 TMA 的企业单一登录方案的示例体系结构的结果。  
  
- **确定入口点、 信任边界和数据流**-请参阅之前在步骤 1 中以及中所述的背景信息[示例方案的背景信息](../core/background-information-for-sample-scenarios.md)。  
  
- **创建一组威胁**-我们使用以下分类 DFD 中的所有条目来识别潜在威胁的方案：**S**poofing 标识，请**T**篡改数据， **R**epudiation，**我**表示信息泄露**D**表示拒绝服务，并**E**表示特权提升。 下表列出了使用企业单一登录 (SSO) 来发送和接收消息与 BizTalk Server 时的各威胁分类。  
  
  **表 1 威胁分类列表**  
  
|威胁|Description|资产|影响|  
|------------|-----------------|-----------|------------|  
|主密钥服务器是单点故障|如果恶意用户威胁主密钥服务器，SSO 计算机将无法加密的凭据 （它将能够继续解密凭据）。|BizTalk Server 和 SSO 环境|拒绝服务|  
|恶意用户可以欺骗客户端或服务器|如果客户端或服务器运行 Windows 时不使用 NTLM 身份验证的情况下，恶意用户可以欺骗客户端或服务器。|BizTalk Server 和 SSO 环境|身份欺骗<br /><br /> 篡改数据<br /><br /> 否认性<br /><br /> 信息泄露<br /><br /> 拒绝服务<br /><br /> 特权提升|  
|恶意用户可能篡改数据，因为从一台服务器传输到另一个|服务器之间的通信是以明文形式和传输时，恶意用户可能可以读取数据。|数据|篡改数据<br /><br /> 信息泄露|  
  
## <a name="step-3-review-threats-enterprise-single-sign-on-scenario"></a>步骤 3. 查看威胁 （企业单一登录方案）  
 本部分提供我们的企业单一登录 (SSO) 方案的参考体系结构的各威胁分类的风险分析结果。 在主要威胁模型会议后，我们对威胁进行并使用以下影响类别来划分每种威胁的风险：**D**潜在，损害**R**再现， **E**xploitability，**一个**可用户并**D**iscoverability。  
  
 下表列出了当使用企业单一登录来发送和接收消息与 BizTalk Server 时的各威胁分类的风险等级。  
  
 **表 2 威胁分类的风险评级**  
  
|威胁|影响|潜在破坏性|可再现性|可利用性指数|受影响的用户|可发现性|风险危害|  
|------------|------------|----------------------|---------------------|--------------------|--------------------|---------------------|-------------------|  
|主密钥服务器是单点故障|拒绝服务|2|3|2|1|2|2|  
|恶意用户可以欺骗客户端或服务器|身份欺骗<br /><br /> 篡改数据<br /><br /> 否认性<br /><br /> 信息泄露<br /><br /> 拒绝服务<br /><br /> 特权提升|3|2|2|2|1|2|  
|恶意用户可能篡改数据，因为从一台服务器传输到另一个|篡改数据<br /><br /> 信息泄露|3|1|1|2|1|1.6|  
  
## <a name="step-4-identify-mitigation-techniques-enterprise-single-sign-on-scenario"></a>步骤 4. 确定缓解措施 （企业单一登录方案）  
 本部分介绍对示例结构的企业单一登录方案的各威胁分类的一些缓解措施。  
  
 下表列出了缓解措施时使用企业单一登录的各威胁分类。  
  
 **表 3 缓解措施和技术**  
  
|威胁|影响|风险危害|缓解措施|  
|------------|------------|-------------------|--------------------------------------------|  
|主密钥服务器是单点故障|拒绝服务|2|对于在主密钥服务器使用主动-被动群集配置。<br /><br /> 有关群集主密钥服务器的详细信息，请参阅[为企业单一登录的高可用性](../core/high-availability-for-enterprise-single-sign-on.md)。|  
|恶意用户可以欺骗客户端或服务器|身份欺骗<br /><br /> 篡改数据<br /><br /> 否认性<br /><br /> 信息泄露<br /><br /> 拒绝服务<br /><br /> 特权提升|2|如果你的网络支持 Kerberos 身份验证，则应注册所有 SSO 服务器。 使用主密钥服务器和 SSO 数据库之间的 Kerberos 身份验证时，你必须配置 SSO 数据库所在的 SQL Server 上的服务主体名称 (SPN)。<br /><br /> 有关如何配置服务主体名称的详细信息，请参阅 Microsoft TechNet 网站上的[ http://go.microsoft.com/fwlink/?LinkId=61374 ](http://go.microsoft.com/fwlink/?LinkId=61374)。|  
|恶意用户可能篡改数据，因为从一台服务器传输到另一个|篡改数据<br /><br /> 信息泄露|1.6|所有 SSO 服务器和 SSO 数据库之间使用 Internet 协议安全性 (IPsec) 或安全套接字层 (SSL)。<br /><br /> 有关 SSL 的详细信息，请参阅 Microsoft 帮助和支持网站上的[ http://go.microsoft.com/fwlink/?LinkID=189708 ](http://go.microsoft.com/fwlink/?LinkID=189708)。<br /><br /> 有关如何为所有 SSO 服务器和 SSO 数据库之间使用 SSL 的详细信息，请参阅[如何为 SSO 启用 SSL](../core/how-to-enable-ssl-for-sso.md)。|  
  
## <a name="see-also"></a>请参阅  
 [威胁模型分析](../core/threat-model-analysis.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)   
 [中小型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)