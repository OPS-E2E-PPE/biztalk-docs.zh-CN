---
title: '示例 TMA: BizTalk 消息队列适配器 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security examples [TMA], MSMQ adapters
- architecture, examples
- MSMQ adapters, TMA
- DFD, MSMQ adapters
- MSMQ adapters, data flow
ms.assetid: 15b4a540-2fcd-4668-b4b4-757f23ebd83e
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec34f90e57df67c8c8a4fc84b10cdd2df8836f1f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994870"
---
# <a name="sample-tma-biztalk-message-queuing-adapter"></a>示例 TMA: BizTalk 消息队列适配器
本主题对示例结构的 BizTalk 消息队列适配器方案进行威胁模型分析 (TMA)。  
  
## <a name="step-1-collect-background-information-biztalk-message-queuing-adapter-scenario"></a>步骤 1. 收集背景信息 （BizTalk 消息队列适配器方案）  
 本部分提供示例结构的 BizTalk 消息队列适配器方案的数据流关系图 (DFD)。 下图显示了 HTTP 和 SOAP 适配器方案的示例结构：  
  
 **图 1 BizTalk 消息队列适配器方案的示例体系结构**  
  
 ![用于 BizTalk 消息队列的示例体系结构](../core/media/tdi-sec-refarch-msmq.gif "TDI_Sec_RefArch_MSMQ")  
  
 所有其他背景信息是相同的所有使用方案，以及前面所述[示例方案的背景信息](../core/background-information-for-sample-scenarios.md)。  
  
### <a name="data-flow-diagram"></a>数据流关系图  
 下图显示了使用 BizTalk 消息队列适配器时的示例结构的 DFD：  
  
 **图 2 的示例结构的 BizTalk 消息队列适配器方案的 DFD**  
  
 ![用于 BizTalk 消息队列的示例体系结构](../core/media/tdi-sec-refarch-dfd-msmq.gif "TDI_Sec_RefArch_DFD_MSMQ")  
  
 数据流如下所述：  
  
1.  合作伙伴使用消息队列或 BizTalk 消息队列发送消息。 对消息以适当的格式进行打包并发送到网络上。 如果您使用 Active Directory，则消息将通过一系列消息队列路由器，直至到达正确的目标（运行 BizTalk 消息队列接收适配器的主机实例的 BizTalk Server）。  
  
2.  BizTalk 消息队列接收适配器的进程内主机实例定期从消息队列路由器（通过防火墙 2）接收消息、进行初始处理、发送正确的网络响应（由网络协议定义），并将消息放入 MessageBox 数据库中。  
  
3.  已订阅该消息的处理主机实例将从 MessageBox 数据库中提取该消息并对其进行所需的任何其他处理，然后将该消息放回 MessageBox 数据库中。  
  
4.  具有 BizTalk 消息队列发送适配器的进程内主机实例将从 MessageBox 数据库中提取该消息。 在发送管道中对该消息完成所有最终处理，然后通过网络上的防火墙 2 发送到合作伙伴或应用程序。  
  
## <a name="step-2-create-and-analyze-the-threat-model-biztalk-message-queuing-adapter-scenario"></a>步骤 2. 创建和分析威胁模型 （BizTalk 消息队列适配器方案）  
 本部分提供对示例结构的 BizTalk 消息队列适配器方案执行 TMA 的结果。  
  
- **确定入口点、 信任边界和数据流-** 请参阅之前在步骤 1 中以及中所述的背景信息[示例方案的背景信息](../core/background-information-for-sample-scenarios.md)。  
  
- **创建的威胁的列表**我们使用以下分类 DFD 中的所有条目来识别潜在威胁的方案： **S**poofing 标识，请**T**ampering使用数据时， **R**表示拒绝，**我**表示信息泄露**D**表示拒绝服务，以及**E**表示特权提升。 下表列出了使用 BizTalk 消息队列适配器与 BizTalk Server 之间收发消息时的威胁分类：  
  
  **表 1 威胁分类列表**  
  
|威胁|Description|资产|影响|  
|------------|-----------------|-----------|------------|  
|向接收位置发送大量消息|恶意用户可能会发送大量有效或无效的消息，并导致应用程序溢出。|BizTalk Server 环境|拒绝服务|  
|消息标头在网络上以明文形式传递|当消息从队列传递到 BizTalk 消息队列接收适配器时，消息标头为明文形式，这样，恶意用户则可能会读取并篡改消息头。|消息标头|篡改数据<br /><br /> 信息泄漏|  
|未经授权的用户可与运行 BizTalk 消息队列主机的 BizTalk Server 建立网络连接。|您不能使用任意访问控制列表 (DACL) 来限制对 BizTalk 消息队列接收位置的访问权限。 因此，只要可与运行 BizTalk 消息队列接收适配器主机实例的 BizTalk Server 建立网络连接并可连接到端口 1801，任何人员均可将消息发送到 BizTalk 消息队列接收位置。|BizTalk Server 环境|抵赖<br /><br /> 篡改数据<br /><br /> 信息泄漏<br /><br /> 拒绝服务<br /><br /> 特权提升|  
|恶意用户可能会在 BizTalk Server 接收到消息前对该消息进行篡改。|恶意用户可能会在消息传输时将其截获并对其进行修改。|邮件正文|篡改数据<br /><br /> 信息泄漏|  
  
## <a name="step-3-review-threats-biztalk-message-queuing-adapter-scenario"></a>步骤 3. 查看威胁 （BizTalk 消息队列适配器方案）  
 本部分提供对示例结构的 BizTalk 消息队列适配器方案的相应威胁分类的风险分析结果。 在主要威胁模型会议后，我们对威胁进行，并使用以下影响类别来划分每种威胁的风险： **D**潜在，损害**R**再现， **E**xploitability， **A**可用户并**D**iscoverability。  
  
 下表列出了使用 BizTalk 消息队列适配器与 BizTalk Server 之间收发消息时的各威胁分类的风险等级：  
  
 **表 2 威胁分类的风险等级**  
  
|威胁|影响|潜在损害|可再现性|可利用性|受影响的用户|可发现性|风险度|  
|------------|------------|----------------------|---------------------|--------------------|--------------------|---------------------|-------------------|  
|向接收位置发送大量消息|拒绝服务|8|7|7|7|5|6.8|  
|消息标头在网络上以明文形式传递|篡改数据<br /><br /> 信息泄漏|8|10|8|3|5|6.8|  
|未经授权的用户可与运行 BizTalk 消息队列主机的 BizTalk Server 建立网络连接。|抵赖<br /><br /> 篡改数据<br /><br /> 信息泄漏<br /><br /> 拒绝服务<br /><br /> 特权提升|8|10|9|9|9|9|  
|恶意用户可能会在 BizTalk Server 接收到消息前对该消息进行篡改。|篡改数据<br /><br /> 信息泄漏|5|7|6|5|7|6|  
  
## <a name="step-4-identify-mitigation-techniques-biztalk-message-queuing-adapter-scenario"></a>步骤 4. 确定缓解措施 （BizTalk 消息队列适配器方案）  
 本部分介绍对示例结构的 BizTalk 消息队列适配器方案的相应威胁分类的一些缓解措施。  
  
 下表列出了使用 BizTalk 消息队列适配器与 BizTalk Server 之间收发消息时的各威胁分类的缓解措施：  
  
 **表 3 缓解措施和技术**  
  
|威胁|影响|风险度|缓解措施|  
|------------|------------|-------------------|--------------------------------------------|  
|向接收位置发送大量消息|拒绝服务|6.8|在要求验证模式下使用 BizTalk 消息队列适配器。 设置**要求 MSMQ 身份验证**接收位置上的标志和**身份验证必需 （删除消息）** 接收端口上。<br /><br /> 将 BizTalk 消息队列配置为要求进行基于证书的验证。 此操作发生在适配器级别，并且与 BizTalk 管道的参与方解析组件不同。 如果配置了此功能，则会在传入消息中包括公用证书。 这是对 BizTalk 消息队列唯一可用的客户端验证模式。 若要使用此客户端验证模式，则必须安装带有 Active Directory 集成模式的 BizTalk 消息队列。 当使用此功能时，请记住选择**要求进行身份验证**复选框上的属性对话框的 BizTalk 消息队列接收位置。|  
|消息标头在网络上以明文形式传递|篡改数据<br /><br /> 信息泄漏|6.8|在服务器间传递消息时使用 Internet 协议安全性 (IPsec) 帮助保护消息正文和消息标头。|  
|未经授权的用户可与运行 BizTalk 消息队列主机的 BizTalk Server 建立网络连接。|抵赖<br /><br /> 篡改数据<br /><br /> 信息泄漏<br /><br /> 拒绝服务<br /><br /> 特权提升|9|创建带有参与方解析管道组件的自定义管道，然后配置该参与方解析组件以使用发件人 ID (SID) 来解析参与方。 设置**通过证书解析参与方**属性设置为**False**，并**通过 SID 解析参与方**属性设置为**True**。 有关详细信息，请参阅[参与方解析管道组件](../core/party-resolution-pipeline-component.md)。<br /><br /> 在接收端口上设置**身份验证**属性设置为**必需 （删除消息）**。|  
|恶意用户可能会在 BizTalk Server 接收到消息前对该消息进行篡改。|篡改数据<br /><br /> 信息泄漏|6|使用协议级别验证，以确保消息在传输中不会被篡改。 若要使用协议级别验证，则电子商务域中必须具有消息队列路由器。 请按照以下步骤配置 BizTalk Server：<br /><br /> -在**BizTalk 消息传送**页的配置管理器中，提供路由器的名称。<br />-对于接收端口设置**身份验证**属性设置为**必需 （删除消息）** 或**必需 （保留消息）**。<br />-对于发送处理程序，在**常规**选项卡上，在**MSMQ 路由器**名称框中，键入消息队列路由器的名称。<br />-对于该发送端口，选择**使用 MSMQ 身份验证**。|  
  
## <a name="see-also"></a>请参阅  
 [威胁模型分析](../core/threat-model-analysis.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)   
 [中小型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)