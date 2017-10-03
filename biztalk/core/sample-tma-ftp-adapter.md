---
title: "示例 TMA: FTP 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, examples
- examples, FTP adapters
- security examples [TMA], FTP adapters
- FTP adapters, TMA
- DFD, FTP adapters
ms.assetid: c648f84a-c83a-44f0-adc9-a3f98b597506
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b88f01eadc2fcadf6592e61b38203bb09e69b547
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sample-tma-ftp-adapter"></a>示例 TMA: FTP 适配器
本主题对示例结构的 FTP 适配器方案进行威胁模型分析 (TMA)。  
  
 下图显示了 FTP 适配器方案的示例结构：  
  
 **对于 FTP 适配器方案图 1 示例体系结构**  
  
 ![示例体系结构为 FTP 适配器](../core/media/tdi-sec-refarch-ftp.gif "TDI_Sec_RefArch_FTP")  
  
## <a name="step-1-collect-background-information-ftp-adapter-scenario"></a>步骤 1. 收集背景信息 （FTP 适配器方案）  
 本部分提供了示例结构的 FTP 适配器方案的数据流关系图 (DFD)。  
  
 所有其他背景信息是相同的所有我们使用方案，以及前面所述[示例方案的背景信息](../core/background-information-for-sample-scenarios.md)。  
  
### <a name="data-flow-diagram"></a>数据流关系图  
 下图显示使用 FTP 适配器时示例结构的 DFD：  
  
 **图 2 DFD FTP 适配器方案的示例体系结构**  
  
 ![为 FTP 适配器 DFD](../core/media/tdi-sec-refarch-dfd-ftp.gif "TDI_Sec_RefArch_DFD_FTP")  
  
 数据流如下所述：  
  
1.  合作伙伴或客户向 FTP 服务器发送消息。 该消息随后路由到防火墙 1 的 IP 地址。  
  
2.  防火墙 1 接收该消息，然后将其路由到位于 Internet 外围网络中的 FTP 服务器。  
  
3.  FTP 接收适配器的进程内主机实例（通过防火墙 2）定期轮询 FTP 服务器以获取新消息。 找到一条新消息之后，它将检索消息，执行任何初始处理，并且将消息放入 MessageBox 数据库。  
  
4.  已订阅该消息的处理主机实例将从 MessageBox 数据库中提取该消息并对其进行所需的任何其他处理，然后将该消息放回 MessageBox 数据库中。  
  
5.  具有 FTP 发送适配器的进程内主机实例将从 MessageBox 数据库中提取该消息。 在发送管道中对该消息完成所有最终处理，然后通过防火墙 2 将其发送到 FTP 服务器。  
  
6.  之后，FTP 服务器将通过防火墙 1 将该消息路由回合作伙伴或客户。  
  
## <a name="step-2-create-and-analyze-the-threat-model-ftp-adapter-scenario"></a>步骤 2. 创建和分析的威胁模型 （FTP 适配器方案）  
 本部分提供对示例结构的 FTP 适配器方案执行 TMA 的结果。  
  
-   **标识入口点、 信任边界和数据的流-**请参阅前面的步骤 1 和中所述的背景信息[示例方案的背景信息](../core/background-information-for-sample-scenarios.md)。  
  
-   **创建标识的威胁的列表**我们使用以下分类 DFD 中的所有条目来识别潜在威胁的方案： **S**哄骗标识， **T**篡改数据， **R**epudiation，**我**璝泄露**D**的服务，用以和**E**提升特权。 下表列出了使用 FTP 适配器与 BizTalk Server 之间收发消息时的威胁分类：  
  
 **表 1 的标识的威胁的列表**  
  
|威胁|Description|资产|影响|  
|------------|-----------------|-----------|------------|  
|FTP 协议不安全|FTP 协议用户 ID 和密码以明文形式发送。 恶意用户可能会监视网络以访问凭据。 数据是公开的。|用户凭据|身份欺骗<br /><br /> 篡改数据<br /><br /> 信息泄漏|  
|FTP 服务器容易受到未经授权的 DHCP 服务器攻击|如果 URI 不包含用户密码，而该密码是在处理程序中指定的，则当前在运行时会将处理程序中的密码发送到 FTP 服务器。 如果存在监听身份验证呼叫的未授权 FTP 服务器，则该服务器可能会以此方式盗取密码。 此问题的一个解决方案是启用/禁用在处理程序级别使用密码。|FTP 服务器|身份欺骗<br /><br /> 篡改数据<br /><br /> 信息泄漏|  
  
## <a name="step-3-review-threats-ftp-adapter-scenario"></a>步骤 3. 查看威胁 （FTP 适配器方案）  
 本部分提供对示例结构的 FTP 适配器方案的相应威胁分类的风险分析结果。 后会议的主要威胁模型，我们查看威胁和使用的已用以下影响类别，以确定对每种威胁的风险： **D**amage 潜在， **R**eproducibility， **E**xploitability， **A**ffected 用户和**D**iscoverability。  
  
 下表列出了使用 FTP 适配器与 BizTalk Server 之间收发消息时的各威胁分类的风险等级：  
  
 **表 2 的标识的威胁的风险级别**  
  
|威胁|影响|潜在损害|可再现性|可利用性|受影响的用户|可发现性|风险度|  
|------------|------------|----------------------|---------------------|--------------------|--------------------|---------------------|-------------------|  
|FTP 协议不安全|身份欺骗<br /><br /> 篡改数据<br /><br /> 信息泄漏|9|9|2|10|5|7|  
|FTP 服务器容易受到未经授权的 DHCP 服务器攻击|身份欺骗<br /><br /> 篡改数据<br /><br /> 信息泄漏|5|5|2|10|5|5.4|  
  
## <a name="step-4-identify-mitigation-techniques-ftp-adapter-scenario"></a>步骤 4. 标识缓解技术 （FTP 适配器方案）  
 本部分介绍对示例结构的 FTP 适配器方案的相应威胁分类的一些缓解措施。  
  
 下表列出了使用 FTP 适配器与 BizTalk Server 之间收发消息时的各威胁分类的缓解措施：  
  
 **表 3 缓解技术和技术**  
  
|威胁|影响|风险度|缓解措施|  
|------------|------------|-------------------|--------------------------------------------|  
|FTP 协议不安全|身份欺骗<br /><br /> 篡改数据<br /><br /> 信息泄漏|7|必须在安全的环境中通过安全线路使用 FTP 适配器。|  
|FTP 服务器容易受到未经授权的 DHCP 服务器攻击|身份欺骗<br /><br /> 篡改数据<br /><br /> 信息泄漏|5.4|建议您将远程 FTP 服务器放在安全的位置中。 您必须确保此服务器的物理安全和网络安全，以便将未经授权的 DHCP 服务器攻击减到最少。|  
  
## <a name="see-also"></a>另请参阅  
 [威胁模型分析](../core/threat-model-analysis.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)   
 [对于小型和中型公司示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)