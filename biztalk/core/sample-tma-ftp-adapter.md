---
title: 示例 TMA:FTP 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
- examples, FTP adapters
- security examples [TMA], FTP adapters
- FTP adapters, TMA
- DFD, FTP adapters
ms.assetid: c648f84a-c83a-44f0-adc9-a3f98b597506
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: decdff3573efbc7445ea19cd53ec257cdbc8ac7c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299822"
---
# <a name="sample-tma-ftp-adapter"></a>示例 TMA:FTP 适配器
本主题介绍对示例结构的 FTP 适配器方案进行威胁模型分析 (TMA)。  
  
 下图显示了 FTP 适配器方案的示例体系结构。  
  
 **图 1 FTP 适配器方案的示例结构**  
  
 ![示例 FTP 适配器的体系结构](../core/media/tdi-sec-refarch-ftp.gif "TDI_Sec_RefArch_FTP")  
  
## <a name="step-1-collect-background-information-ftp-adapter-scenario"></a>步骤 1. 收集背景信息 （FTP 适配器方案）  
 本部分提供对示例结构的 FTP 适配器方案的数据流关系图 (DFD)。  
  
 所有其他背景信息是相同的所有使用方案，以及前面所述[示例方案的背景信息](../core/background-information-for-sample-scenarios.md)。  
  
### <a name="data-flow-diagram"></a>数据流关系图  
 使用 FTP 适配器时，下图显示了示例结构的 dfd:。  
  
 **图 2 DFD 的示例结构的 FTP 适配器方案**  
  
 ![FTP 适配器的 DFD](../core/media/tdi-sec-refarch-dfd-ftp.gif "TDI_Sec_RefArch_DFD_FTP")  
  
 数据流如下所示：  
  
1.  合作伙伴或客户向 FTP 服务器发送消息。 消息路由到防火墙 1 的 IP 地址。  
  
2.  防火墙 1 接收该消息，并将其路由到 FTP 服务器位于 Internet 外围网络中。  
  
3.  进程内主机实例的 FTP 接收适配器定期轮询 FTP 服务器上的新消息 （通过防火墙 2)。 会在有新消息后，它将检索消息、 进行初始处理，并将该消息放在 MessageBox 数据库中。  
  
4.  已对消息的订阅的处理主机实例提取该消息从 MessageBox 数据库、 任何其他处理，并将该消息放回 MessageBox 数据库中。  
  
5.  具有 FTP 发送适配器提取该消息从 MessageBox 数据库的进程内主机实例。 该消息完成所有最终处理在发送管道中，并通过防火墙 2 然后到 FTP 服务器发送。  
  
6.  然后，FTP 服务器将通过防火墙 1 的消息路由回合作伙伴或客户。  
  
## <a name="step-2-create-and-analyze-the-threat-model-ftp-adapter-scenario"></a>步骤 2. 创建和分析威胁模型 （FTP 适配器方案）  
 本部分提供对示例结构的 FTP 适配器方案执行的 TMA 的结果。  
  
- **确定入口点、 信任边界和数据流-** 请参阅之前在步骤 1 中以及中所述的背景信息[示例方案的背景信息](../core/background-information-for-sample-scenarios.md)。  
  
- **创建一组威胁-** 我们使用以下分类 DFD 中的所有条目来识别潜在威胁的方案：**S**poofing 标识，请**T**篡改数据， **R**epudiation，**我**表示信息泄露**D**表示拒绝服务，并**E**表示特权提升。 下表列出了使用 FTP 适配器发送和接收消息与 BizTalk Server 时的各威胁分类。  
  
  **表 1 威胁分类列表**  
  
|威胁|Description|资产|影响|  
|------------|-----------------|-----------|------------|  
|FTP 协议不安全|FTP 协议用户 ID 和密码以明文形式发送。 恶意用户可以监视网络以访问凭据。 公开数据。|用户凭据|身份欺骗<br /><br /> 篡改数据<br /><br /> 信息泄露|  
|FTP 服务器容易受到未经授权的 DHCP 服务器攻击|如果 URI 不包含用户的密码，但指定处理程序，在运行时的处理程序的密码是当前发送到 FTP 服务器。 如果未授权 FTP 服务器侦听的身份验证调用，它可能会窃取密码以这种方式。 一种解决方案是启用/禁用在处理程序级别使用的密码。|FTP 服务器|身份欺骗<br /><br /> 篡改数据<br /><br /> 信息泄露|  
  
## <a name="step-3-review-threats-ftp-adapter-scenario"></a>步骤 3. 查看威胁 （FTP 适配器方案）  
 本部分提供我们的示例体系结构的 FTP 适配器方案的各威胁分类的风险分析结果。 在主要威胁模型会议后，我们对威胁进行并使用以下影响类别来划分每种威胁的风险：**D**潜在，损害**R**再现， **E**xploitability，**一个**可用户并**D**iscoverability。  
  
 下表列出了使用 FTP 适配器发送和接收消息与 BizTalk Server 时的各威胁分类的风险等级。  
  
 **表 2 威胁分类的风险等级**  
  
|威胁|影响|潜在破坏性|可再现性|可利用性指数|受影响的用户|可发现性|风险危害|  
|------------|------------|----------------------|---------------------|--------------------|--------------------|---------------------|-------------------|  
|FTP 协议不安全|身份欺骗<br /><br /> 篡改数据<br /><br /> 信息泄露|9|9|2|10|5|7|  
|FTP 服务器容易受到未经授权的 DHCP 服务器攻击|身份欺骗<br /><br /> 篡改数据<br /><br /> 信息泄露|5|5|2|10|5|5.4|  
  
## <a name="step-4-identify-mitigation-techniques-ftp-adapter-scenario"></a>步骤 4. 确定缓解措施 （FTP 适配器方案）  
 本部分介绍对示例结构的 FTP 适配器方案的各威胁分类的一些缓解措施。  
  
 下表列出了缓解措施时使用 FTP 适配器发送和接收消息与 BizTalk Server 的各威胁分类。  
  
 **表 3 缓解措施和技术**  
  
|威胁|影响|风险危害|缓解措施|  
|------------|------------|-------------------|--------------------------------------------|  
|FTP 协议不安全|身份欺骗<br /><br /> 篡改数据<br /><br /> 信息泄露|7|FTP 适配器必须使用安全的环境中并通过安全线路。|  
|FTP 服务器容易受到未经授权的 DHCP 服务器攻击|身份欺骗<br /><br /> 篡改数据<br /><br /> 信息泄露|5.4|我们建议将远程 FTP 服务器放在安全的位置。 你必须确保物理和网络安全性的最大程度减少未经授权的 DHCP 服务器攻击此服务器。|  
  
## <a name="see-also"></a>请参阅  
 [威胁模型分析](../core/threat-model-analysis.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)   
 [中小型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)