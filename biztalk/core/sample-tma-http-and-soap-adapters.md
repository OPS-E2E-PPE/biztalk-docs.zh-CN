---
title: 示例 TMA:HTTP 和 SOAP 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e07bd1d90fbf423fcba38dde75696c3825293d20
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399530"
---
# <a name="sample-tma-http-and-soap-adapters"></a>示例 TMA:HTTP 和 SOAP 适配器
本主题介绍威胁模型分析 (TMA) 的 HTTP 和 SOAP (Web services) 适配器方案的示例体系结构。 下图显示了 HTTP 和 SOAP 适配器方案的示例体系结构。  
  
 **图 1 的 HTTP/SOAP 适配器方案的示例结构**  
  
 ![示例 HTTP 或 SOAP 适配器的体系结构](../core/media/tdi-sec-refarch-http.gif "TDI_Sec_RefArch_HTTP")  
  
## <a name="step-1-collect-background-information-http-and-soap-adapters-scenario"></a>步骤 1. 收集背景信息 （HTTP 和 SOAP 适配器方案）  
 本部分提供了数据的数据流关系图 (DFD) 的 HTTP 和 SOAP (Web services) 适配器方案的示例结构。  
  
 所有其他背景信息是相同的所有使用方案，以及前面所述[示例方案的背景信息](../core/background-information-for-sample-scenarios.md)。  
  
### <a name="data-flow-diagram"></a>数据流关系图  
 下图显示了示例结构的 dfd:，当您使用的 HTTP 和 SOAP (Web services) 适配器。  
  
 **图 2 DFD 的示例结构的 HTTP/SOAP 适配器方案**  
  
 ![对示例结构的 DFD](../core/media/tdi-sec-refarch-dfd-http.gif "TDI_Sec_RefArch_DFD_HTTP")  
  
 数据流如下所示：  
  
1.  合作伙伴或客户发送一条消息通过 HTTP、 HTTPS 或 Web 服务。 消息路由到防火墙 1 的 IP 地址。  
  
2.  防火墙 1 中继通过防火墙 2 使用反向代理的消息。  
  
3.  防火墙 2 路由到运行独立主机的实例的 HTTP 或 SOAP 接收适配器的 BizTalk Server 消息。 独立的主机处理消息，并将其放入 MessageBox 数据库。  
  
4.  已对消息的订阅的处理主机实例提取该消息从 MessageBox 数据库、 任何其他处理，并将该消息放回 MessageBox 数据库中。  
  
5.  具有 HTTP 或 SOAP 发送适配器将消息从 MessageBox 数据库提取的独立主机的实例。 消息完成所有最终处理在发送管道中，并且发送回合作伙伴或客户。  
  
6.  当消息发送到合作伙伴或客户，它会路由通过防火墙 2 和防火墙 1 使用反向代理。  
  
## <a name="step-2-create-and-analyze-the-threat-model-http-and-soap-adapters-scenario"></a>步骤 2. 创建和分析威胁模型 （HTTP 和 SOAP 适配器方案）  
 本部分提供的结果执行 TMA 的 HTTP 和 SOAP (Web services) 适配器方案的示例结构。  
  
- **确定入口点、 信任边界和数据流-** 请参阅之前在步骤 1 中所述的背景信息和[示例方案的背景信息](../core/background-information-for-sample-scenarios.md)。  
  
- **创建一组威胁-** 我们使用以下分类 DFD 中的所有条目来识别潜在威胁的方案：**S**poofing 标识，请**T**篡改数据， **R**epudiation，**我**表示信息泄露**D**表示拒绝服务，并**E**表示特权提升。 下表列出了使用 HTTP 和 SOAP 适配器发送和接收消息与 BizTalk Server 时的各威胁分类。  
  
  **表 1 威胁列表**  
  
|威胁|Description|资产|影响|  
|------------|-----------------|-----------|------------|  
|发送无限大的消息|恶意用户可以发送无限大的消息。|BizTalk Server 环境|拒绝服务|  
|发送大量消息，以接收位置|恶意用户可以发送大量有效或无效的消息和填满该应用程序。|BizTalk Server 环境|拒绝服务|  
|通过 HTTP 读取消息正文|恶意用户可以截获的消息，因为它从发送方传递到防火墙 1，并可以读取该消息。|消息负载|信息泄露|  
|从消息中读取用户凭据|如果使用基本身份验证，并且该消息包含用户凭据，恶意用户可以获得凭据的访问权限，并使用它们来访问该应用程序。|用户凭据|信息泄露<br /><br /> 提升权限|  
  
## <a name="step-3-review-threats-http-and-soap-adapters-scenario"></a>步骤 3. 查看威胁 （HTTP 和 SOAP 适配器方案）  
 本部分提供我们的 HTTP 和 SOAP （Web 服务） 的各威胁分类的风险分析结果适配器方案的示例结构。 在主要威胁模型会议后，我们对威胁进行并使用以下影响类别来划分每种威胁的风险：**D**潜在，损害**R**再现， **E**xploitability，**一个**可用户并**D**iscoverability。  
  
 下表列出了使用 HTTP 和 SOAP 适配器发送和接收消息与 BizTalk Server 时的各威胁分类的风险等级。  
  
 **表 2 威胁的风险等级**  
  
|威胁|影响|潜在破坏性|可再现性|可利用性指数|受影响的用户|可发现性|风险危害|  
|------------|------------|----------------------|---------------------|--------------------|--------------------|---------------------|-------------------|  
|发送无限大的消息|拒绝服务|2|3|2|3|2|2.4|  
|发送大量消息，以接收位置|拒绝服务|3|3|1|3|3|2.6|  
|通过 HTTP 读取消息正文|信息泄露|3|3|2|3|3|2.8|  
|从消息中读取用户凭据|信息泄露<br /><br /> 提升权限|3|3|2|3|2|2.6|  
  
## <a name="step-4-identify-mitigation-techniques-http-and-soap-adapters-scenario"></a>步骤 4. 确定缓解措施 （HTTP 和 SOAP 适配器方案）  
 本部分介绍一些缓解措施的相应威胁分类的 HTTP 和 SOAP (Web services) 适配器方案的示例结构。  
  
 下表列出了缓解措施时使用 HTTP 和 SOAP 适配器发送和接收消息与 BizTalk Server 的各威胁分类。  
  
 **表 3 缓解措施和技术**  
  
|威胁|影响|风险危害|缓解措施|  
|------------|------------|-------------------|--------------------------------------------|  
|发送无限大的消息|拒绝服务|2.4|限制每个 URL 的传入消息的最大大小，并拒绝超过该最大的消息。<br /><br /> 有关详细信息，请参阅[缓解拒绝的服务攻击](../core/mitigating-denial-of-service-attacks.md)。|  
|发送大量消息，以接收位置|拒绝服务|2.6|SOAP 适配器充分利用 HTTP 发送和接收来自 BizTalk Server 之间的消息。 因此，必须遵循安全建议来帮助安全 Internet 信息服务 (IIS)。 如果使用 IIS，请确保您遵循有关如何配置应用程序隔离的 IIS 建议。<br /><br /> 有关详细信息，请参阅 Microsoft TechNet 网站上的[ http://go.microsoft.com/fwlink/?LinkId=60951 ](http://go.microsoft.com/fwlink/?LinkId=60951)。<br /><br /> 使用客户端身份验证和参与方解析限制为仅显示那些是有效且获得授权正在处理的消息数。|  
|通过 HTTP 读取消息正文|信息泄露|2.8|我们建议使用 S/MIME 以帮助保护发往和从 BizTalk Server 消息的内容。<br /><br /> 我们建议使用安全套接字层 (SSL) 来帮助保护到和从 BizTalk Server 和 BizTalk Server 组件分布在您的环境之间的数据传输。|  
|从消息中读取用户凭据|信息泄露<br /><br /> 提升权限|2.6|当您使用基本身份验证，或在消息级别未使用加密时，我们建议使用 SSL 来接收和发送消息，以确保未经授权的人员无法读取用户凭据。|  
  
## <a name="see-also"></a>请参阅  
 [威胁模型分析](../core/threat-model-analysis.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)   
 [中小型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)