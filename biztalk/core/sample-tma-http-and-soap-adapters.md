---
title: "示例 TMA: HTTP 和 SOAP 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, examples
- DFD, HTTP adapters
- security examples [TMA], SOAP adapters
- SOAP adapters, examples
- security examples [TMA], HTTP adapters
- examples, HTTP adapters
- DFD, SOAP adapter
- examples, SOAP adapters
- SOAP adapters, TMA
- HTTP adapters, TMA
ms.assetid: d9a40cff-92a1-4bc9-ae45-3a5857f70222
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fedbdd03e79a0a9250b184695806813f2805e34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sample-tma-http-and-soap-adapters"></a>示例 TMA: HTTP 和 SOAP 适配器
本主题对示例结构的 HTTP 和 SOAP (Web Services) 适配器方案进行威胁模型分析 (TMA)。 下图显示了 HTTP 和 SOAP 适配器方案的示例结构：  
  
 **图 1 的 HTTP/SOAP 适配器方案的示例体系结构**  
  
 ![示例体系结构为 HTTP 或 SOAP 适配器](../core/media/tdi-sec-refarch-http.gif "TDI_Sec_RefArch_HTTP")  
  
## <a name="step-1-collect-background-information-http-and-soap-adapters-scenario"></a>步骤 1. 收集背景信息 （HTTP 和 SOAP 适配器方案）  
 本部分针对 HTTP 和 SOAP （Web 服务） 提供数据流关系图 (DFD) 示例体系结构的适配器方案。  
  
 所有其他背景信息是相同的所有我们使用方案，以及前面所述[示例方案的背景信息](../core/background-information-for-sample-scenarios.md)。  
  
### <a name="data-flow-diagram"></a>数据流关系图  
 当你使用的 HTTP 和 SOAP （Web 服务） 时下, 图显示示例体系结构 DFD 适配器。  
  
 **图 2 DFD 的 HTTP/SOAP 适配器方案示例体系结构**  
  
 ![示例体系结构的 DFD](../core/media/tdi-sec-refarch-dfd-http.gif "TDI_Sec_RefArch_DFD_HTTP")  
  
 数据流如下所述：  
  
1.  合作伙伴或客户发送任何消息通过 HTTP、 HTTPS 或 Web 服务。 该消息随后路由到防火墙 1 的 IP 地址。  
  
2.  防火墙 1 中继通过使用反向代理的防火墙 2 的消息。  
  
3.  防火墙 2 路由到 HTTP 或 SOAP 接收适配器的运行实例的一个独立主机 BizTalk Server 消息。 隔离的主机处理消息，并将其放在 MessageBox 数据库中。  
  
4.  已订阅该消息的处理主机实例将从 MessageBox 数据库中提取该消息并对其进行所需的任何其他处理，然后将该消息放回 MessageBox 数据库中。  
  
5.  具有 HTTP 或 SOAP 发送适配器的独立主机实例将从 MessageBox 数据库中提取该消息。 在发送管道中对该消息完成所有最终处理，然后将其发送回合作伙伴或客户。  
  
6.  消息在发送到合作伙伴或客户时是使用反向代理通过防火墙 2 和防火墙 1 来路由的。  
  
## <a name="step-2-create-and-analyze-the-threat-model-http-and-soap-adapters-scenario"></a>步骤 2. 创建和分析威胁模型 （HTTP 和 SOAP 适配器方案）  
 本部分提供对示例结构的 HTTP 和 SOAP (Web Services) 适配器方案执行 TMA 的结果。  
  
-   **标识入口点、 信任边界和数据的流-**请参阅之前在步骤 1 中所述的背景信息和[示例方案的背景信息](../core/background-information-for-sample-scenarios.md)。  
  
-   **创建标识的威胁的列表**我们使用以下分类 DFD 中的所有条目来识别潜在威胁的方案： **S**哄骗标识， **T**篡改数据， **R**epudiation，**我**璝泄露**D**的服务，用以和**E**提升特权。 下表列出了使用 HTTP 和 SOAP 适配器与 BizTalk Server 之间收发消息时的威胁分类：  
  
 **表 1 的威胁的列表**  
  
|威胁|Description|资产|影响|  
|------------|-----------------|-----------|------------|  
|发送无限大的消息|恶意用户可能会发送无限大的消息。|BizTalk Server 环境|拒绝服务|  
|向接收位置发送大量消息|恶意用户可能会发送大量有效或无效的消息，并导致应用程序溢出。|BizTalk Server 环境|拒绝服务|  
|通过 HTTP 读取消息正文|恶意用户可能会在消息从发送程序传递到防火墙 1 时将其截获并进行读取。|消息负载|信息泄漏|  
|从消息中读取用户凭据|如果使用基本验证，而且消息包含用户凭据，则恶意用户可能会访问这些凭据，并使用其访问应用程序。|用户凭据|信息泄漏<br /><br /> 特权提升|  
  
## <a name="step-3-review-threats-http-and-soap-adapters-scenario"></a>步骤 3. 查看威胁 （HTTP 和 SOAP 适配器方案）  
 本部分提供对示例结构的 HTTP 和 SOAP (Web Services) 适配器方案的相应威胁分类的风险分析结果。 后会议的主要威胁模型，我们查看威胁和以下影响类别用于确定对每种威胁的风险： **D**amage 潜在， **R**eproducibility， **E**xploitability， **A**ffected 用户和**D**iscoverability。  
  
 下表列出了使用 HTTP 和 SOAP 适配器与 BizTalk Server 之间收发消息时的各威胁分类的风险等级：  
  
 **表 2 的威胁的风险评分**  
  
|威胁|影响|潜在损害|可再现性|可利用性|受影响的用户|可发现性|风险度|  
|------------|------------|----------------------|---------------------|--------------------|--------------------|---------------------|-------------------|  
|发送无限大的消息|拒绝服务|2|3|2|3|2|2.4|  
|向接收位置发送大量消息|拒绝服务|3|3|1|3|3|2.6|  
|通过 HTTP 读取消息正文|信息泄漏|3|3|2|3|3|2.8|  
|从消息中读取用户凭据|信息泄漏<br /><br /> 特权提升|3|3|2|3|2|2.6|  
  
## <a name="step-4-identify-mitigation-techniques-http-and-soap-adapters-scenario"></a>步骤 4. 标识缓解技术 （HTTP 和 SOAP 适配器方案）  
 本部分介绍对示例结构的 HTTP 和 SOAP (Web Services) 适配器方案的相应威胁分类的一些缓解措施。  
  
 下表列出了使用 HTTP 和 SOAP 适配器与 BizTalk Server 之间收发消息时的各威胁分类的缓解措施：  
  
 **表 3 缓解技术和技术**  
  
|威胁|影响|风险度|缓解措施|  
|------------|------------|-------------------|--------------------------------------------|  
|发送无限大的消息|拒绝服务|2.4|限制每个 URL 的传入消息的最大大小，并拒绝超过该最大大小的消息。<br /><br /> 有关详细信息，请参阅[减少拒绝的服务攻击](../core/mitigating-denial-of-service-attacks.md)。|  
|向接收位置发送大量消息|拒绝服务|2.6|SOAP 适配器充分利用 HTTP 与 BizTalk Server 之间收发消息。 因此，您必须遵循安全建议来帮助确保 Internet 信息服务 (IIS) 的安全。 如果使用 IIS，请确保您遵循有关如何配置应用程序隔离的 IIS 建议。<br /><br /> 有关详细信息，请参阅 Microsoft TechNet 网站， [http://go.microsoft.com/fwlink/?LinkId=60951](http://go.microsoft.com/fwlink/?LinkId=60951)。<br /><br /> 使用客户端验证和参与方解析限制处理的消息数，以便仅包括有效且经过授权的消息。|  
|通过 HTTP 读取消息正文|信息泄漏|2.8|建议您使用 S/MIME 以帮助确保与 BizTalk Server 之间收发的消息内容的安全。<br /><br /> 建议您使用安全套接字层 (SSL) 来帮助确保与 BizTalk Server 之间的数据传输以及您所在环境中 BizTalk Server 分布组件相互之间的数据传输的安全。|  
|从消息中读取用户凭据|信息泄漏<br /><br /> 特权提升|2.6|如果使用基本验证或在消息层未使用加密，则建议您使用 SSL 收发消息，以确保未经授权的人员无法读取用户凭据。|  
  
## <a name="see-also"></a>另请参阅  
 [威胁模型分析](../core/threat-model-analysis.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)   
 [对于小型和中型公司示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)