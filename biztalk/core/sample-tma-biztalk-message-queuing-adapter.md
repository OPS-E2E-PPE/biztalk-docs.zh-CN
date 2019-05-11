---
title: 示例 TMA:BizTalk 消息队列适配器 |Microsoft Docs
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
ms.openlocfilehash: 27187bcb688ed50d6935fb7dd386cdaad6f59ede
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393880"
---
# <a name="sample-tma-biztalk-message-queuing-adapter"></a>示例 TMA:BizTalk 消息队列适配器
本主题介绍对示例结构的 BizTalk 消息队列适配器方案进行威胁模型分析 (TMA)。  
  
## <a name="step-1-collect-background-information-biztalk-message-queuing-adapter-scenario"></a>步骤 1. 收集背景信息 （BizTalk 消息队列适配器方案）  
 本部分提供对示例结构的 BizTalk 消息队列适配器方案的数据流关系图 (DFD)。 下图显示了 HTTP 和 SOAP 适配器方案的示例体系结构。  
  
 **图 1 BizTalk 消息队列适配器方案的示例体系结构**  
  
 ![用于 BizTalk 消息队列的示例体系结构](../core/media/tdi-sec-refarch-msmq.gif "TDI_Sec_RefArch_MSMQ")  
  
 所有其他背景信息是相同的所有使用方案，以及前面所述[示例方案的背景信息](../core/background-information-for-sample-scenarios.md)。  
  
### <a name="data-flow-diagram"></a>数据流关系图  
 使用 BizTalk 消息队列适配器时，下图显示了示例结构的 dfd:。  
  
 **图 2 的示例结构的 BizTalk 消息队列适配器方案的 DFD**  
  
 ![用于 BizTalk 消息队列的示例体系结构](../core/media/tdi-sec-refarch-dfd-msmq.gif "TDI_Sec_RefArch_DFD_MSMQ")  
  
 数据流如下所示：  
  
1.  合作伙伴发送使用消息队列或 BizTalk 消息队列的消息。 将消息以适当的格式打包并在网络上发送。 如果使用 Active Directory，则消息将通过一系列消息队列路由器，直至到达正确的目标 （BizTalk Server 运行主机实例的 BizTalk 消息队列接收适配器）。  
  
2.  进程内主机实例定期 BizTalk 消息队列接收适配器从消息队列路由器 （通过防火墙 2) 接收消息、 进行初始处理、 发送正确的网络响应所定义的网络协议并将该消息放入 MessageBox 数据库。  
  
3.  已对消息的订阅的处理主机实例提取该消息从 MessageBox 数据库、 任何其他处理，并将该消息放回 MessageBox 数据库中。  
  
4.  具有 BizTalk 消息队列发送适配器的进程内主机实例中提取消息从 MessageBox 数据库。 消息完成所有最终处理在发送管道中，并且然后通过防火墙 2 通过网络发送到合作伙伴或应用程序。  
  
## <a name="step-2-create-and-analyze-the-threat-model-biztalk-message-queuing-adapter-scenario"></a>步骤 2. 创建和分析威胁模型 （BizTalk 消息队列适配器方案）  
 本部分提供对示例结构的 BizTalk 消息队列适配器方案执行的 TMA 的结果。  
  
- **确定入口点、 信任边界和数据流-** 请参阅之前在步骤 1 中以及中所述的背景信息[示例方案的背景信息](../core/background-information-for-sample-scenarios.md)。  
  
- **创建一组威胁-** 我们使用以下分类 DFD 中的所有条目来识别潜在威胁的方案：**S**poofing 标识，请**T**篡改数据， **R**epudiation，**我**表示信息泄露**D**表示拒绝服务，并**E**表示特权提升。 下表列出了使用 BizTalk 消息队列适配器发送和接收消息与 BizTalk Server 时的各威胁分类。  
  
  **表 1 威胁分类列表**  
  
|威胁|Description|资产|影响|  
|------------|-----------------|-----------|------------|  
|发送大量消息，以接收位置|恶意用户可以发送大量有效或无效的消息和填满该应用程序。|BizTalk Server 环境|拒绝服务|  
|在网络上以明文形式传输消息标头|随着从队列消息传递到 BizTalk 消息队列接收适配器，消息标头为明文形式，并且恶意用户可能可以读取并篡改标头。|消息标头|篡改数据<br /><br /> 信息泄露|  
|未经授权的用户可以对运行 BizTalk 消息队列主机的 BizTalk 服务器进行网络连接|不能使用任意访问列表 (DACL) 来限制对 BizTalk 消息队列访问接收位置。 因此，可以对运行 BizTalk 消息队列的主机实例的 BizTalk 服务器进行网络连接的任何人都接收适配器和端口 1801年可以发送到 BizTalk 消息队列的消息的接收位置。|BizTalk Server 环境|否认性<br /><br /> 篡改数据<br /><br /> 信息泄露<br /><br /> 拒绝服务<br /><br /> 特权提升|  
|恶意用户可能篡改该消息，BizTalk Server 接收它之前|恶意用户可以在传输时截获消息并对其进行修改。|消息正文|篡改数据<br /><br /> 信息泄露|  
  
## <a name="step-3-review-threats-biztalk-message-queuing-adapter-scenario"></a>步骤 3. 查看威胁 （BizTalk 消息队列适配器方案）  
 本部分提供有关对示例结构的 BizTalk 消息队列适配器方案的各威胁分类的风险分析的结果。 在主要威胁模型会议后，我们对威胁进行并使用以下影响类别来划分每种威胁的风险：**D**潜在，损害**R**再现， **E**xploitability，**一个**可用户并**D**iscoverability。  
  
 下表列出了使用 BizTalk 消息队列适配器发送和接收消息与 BizTalk Server 时的各威胁分类的风险等级。  
  
 **表 2 威胁分类的风险等级**  
  
|威胁|影响|潜在破坏性|可再现性|可利用性指数|受影响的用户|可发现性|风险危害|  
|------------|------------|----------------------|---------------------|--------------------|--------------------|---------------------|-------------------|  
|发送大量消息，以接收位置|拒绝服务|8|7|7|7|5|6.8|  
|在网络上以明文形式传输消息标头|篡改数据<br /><br /> 信息泄露|8|10|8|3|5|6.8|  
|未经授权的用户可以对运行 BizTalk 消息队列主机的 BizTalk 服务器进行网络连接|否认性<br /><br /> 篡改数据<br /><br /> 信息泄露<br /><br /> 拒绝服务<br /><br /> 特权提升|8|10|9|9|9|9|  
|恶意用户可能篡改该消息，BizTalk Server 接收它之前|篡改数据<br /><br /> 信息泄露|5|7|6|5|7|6|  
  
## <a name="step-4-identify-mitigation-techniques-biztalk-message-queuing-adapter-scenario"></a>步骤 4. 确定缓解措施 （BizTalk 消息队列适配器方案）  
 本部分介绍对示例结构的 BizTalk 消息队列适配器方案的各威胁分类的一些缓解措施。  
  
 下表列出了缓解措施时使用的 BizTalk 消息队列适配器发送和接收消息与 BizTalk Server 的各威胁分类。  
  
 **表 3 缓解措施和技术**  
  
|威胁|影响|风险危害|缓解措施|  
|------------|------------|-------------------|--------------------------------------------|  
|发送大量消息，以接收位置|拒绝服务|6.8|在身份验证要求模式下使用 BizTalk 消息队列适配器。 设置**要求 MSMQ 身份验证**接收位置上的标志和**身份验证必需 （删除消息）** 接收端口上。<br /><br /> 配置 BizTalk 消息队列需要基于证书的身份验证。 此行为在适配器级别进行，并且不同于 BizTalk 管道的参与方解析组件。 如果配置，是包含在传入消息的公用证书。 这是可用于 BizTalk 消息队列的唯一客户端身份验证模式。 若要使用此客户端身份验证模式，您必须安装 BizTalk 消息队列与 Active Directory 集成模式。 当使用此功能时，请记住选择**要求进行身份验证**复选框上的属性对话框的 BizTalk 消息队列接收位置。|  
|在网络上以明文形式传输消息标头|篡改数据<br /><br /> 信息泄露|6.8|使用 Internet 协议安全 (IPsec) 来帮助保护消息正文和消息标头，在一台服务器间传递到另一个。|  
|未经授权的用户可以对运行 BizTalk 消息队列主机的 BizTalk 服务器进行网络连接|否认性<br /><br /> 篡改数据<br /><br /> 信息泄露<br /><br /> 拒绝服务<br /><br /> 特权提升|9|创建包含参与方解析管道组件的自定义管道，然后配置要使用发件人 ID (SID) 来解析参与方的参与方解析组件。 设置**通过证书解析参与方**属性设置为**False**，并**通过 SID 解析参与方**属性设置为**True**。 有关详细信息，请参阅[参与方解析管道组件](../core/party-resolution-pipeline-component.md)。<br /><br /> 在接收端口上设置**身份验证**属性设置为**必需 （删除消息）**。|  
|恶意用户可能篡改该消息，BizTalk Server 接收它之前|篡改数据<br /><br /> 信息泄露|6|使用协议级别身份验证来确保消息未篡改在传输过程中。 若要使用协议级别身份验证，必须在电子商务域中具有消息队列路由器。 配置 BizTalk Server 按如下所示：<br /><br /> -在**BizTalk 消息传送**页的配置管理器中，提供路由器的名称。<br />-对于接收端口设置**身份验证**属性设置为**必需 （删除消息）** 或**必需 （保留消息）**。<br />-对于发送处理程序，在**常规**选项卡上，在**MSMQ 路由器**名称框中，键入消息队列路由器的名称。<br />-对于该发送端口，选择**使用 MSMQ 身份验证**。|  
  
## <a name="see-also"></a>请参阅  
 [威胁模型分析](../core/threat-model-analysis.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)   
 [中小型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)