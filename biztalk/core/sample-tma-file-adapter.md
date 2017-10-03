---
title: "示例 TMA： 文件适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, examples
- DFD, File adapters
- File adapters, TMA
- examples, File adapters
- security examples [TMA], File adapters
ms.assetid: bcb862c0-fe02-4335-8b59-242d28049e3f
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b0a5bfe1cce0db07ef26a8d71cc6795cd49202f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sample-tma-file-adapter"></a>示例 TMA： 文件适配器
本主题对示例结构的文件适配器方案进行威胁模型分析 (TMA)。 下图显示了文件适配器方案的示例结构：  
  
 **图 1 文件适配器方案示例体系结构**  
  
 ![示例文件适配器的体系结构](../core/media/tdi-sec-refarch-file.gif "TDI_Sec_RefArch_File")  
  
## <a name="step-1-collect-background-information-file-adapter-scenario"></a>步骤 1. 收集背景信息 （文件适配器方案）  
 本部分提供了示例结构的文件适配器方案的数据流关系图 (DFD)。  
  
 所有其他背景信息是相同的所有我们使用方案，以及前面所述[示例方案的背景信息](../core/background-information-for-sample-scenarios.md)。  
  
### <a name="data-flow-diagram"></a>数据流关系图  
 下图显示了使用文件适配器时示例结构的 DFD：  
  
 **图 2 DFD 文件适配器方案中的示例体系结构**  
  
 ![体系结构的示例性 DFD](../core/media/tdi-sec-refarch-dfd-file.gif "TDI_Sec_RefArch_DFD_FILE_")  
  
 数据流如下所述：  
  
1.  合作伙伴将一条消息 （通过防火墙 1) 将放置在 intranet 外围网络中的文件服务器中。  
  
2.  一个进程内主机的实例为 File 接收适配器定期轮询新消息 （通过防火墙 2) 的文件服务器。 找到一条新消息之后，它将检索消息，执行任何初始处理，并且将消息放入 MessageBox 数据库。  
  
3.  已订阅该消息的处理主机实例将从 MessageBox 数据库中提取该消息并对其进行所需的任何其他处理，然后将该消息放回 MessageBox 数据库中。  
  
4.  具有发送适配器选取该消息从 MessageBox 数据库文件的进程内主机实例。 消息经历发送管道中的任何最终处理，并通过防火墙 2 然后到文件服务器发送。  
  
5.  合作伙伴选取该消息从文件服务器。  
  
## <a name="step-2-create-and-analyze-the-threat-model-file-adapter-scenario"></a>步骤 2. 创建和分析的威胁模型 （文件适配器方案）  
 本部分提供了我们的示例体系结构的文件适配器方案未 TMA 的结果。  
  
-   **标识入口点、 信任边界和数据的流-**请参阅"收集背景信息的文件适配器方案"和"对于所有方案的背景信息。"中前面所述的背景信息  
  
-   **创建标识的威胁的列表**我们使用以下分类 DFD 中的所有条目来识别潜在威胁的方案： **S**哄骗标识， **T**篡改数据， **R**epudiation，**我**璝泄露**D**的服务，用以和**E**提升特权。 下表列出了当你使用文件适配器发送和接收消息与 BizTalk Server 我们标识的威胁。  
  
 **表 1 列表标识的威胁**  
  
|威胁|Description|资产|影响|  
|------------|-----------------|-----------|------------|  
|未经授权的用户可以从文件放置文件夹中检索消息|如果你尚未设置强随机访问列表 (Dacl) 为文件夹文件适配器使用，未经授权的用户都可以删除文件中的消息接收位置，或选取从文件发送位置的消息。|邮件正文|篡改数据<br /><br /> 信息泄漏|  
|未经授权的用户可将消息提交给 BizTalk Server|如果用户到从中 BizTalk Server 选取消息文件文件夹具有写入权限，未经授权的用户可以提交给 BizTalk Server 的消息。|邮件正文|拒绝服务<br /><br /> 特权提升|  
  
## <a name="step-3-review-threats-file-adapter-scenario"></a>步骤 3. 查看威胁 （文件适配器方案）  
 本部分提供了我们所做的我们的示例体系结构的文件适配器方案标识的威胁的风险分析的结果。 后会议的主要威胁模型，我们查看威胁和以下影响类别用于确定对每种威胁的风险： **D**amage 潜在， **R**eproducibility， **E**xploitability， **A**ffected 用户和**D**iscoverability。  
  
 下表列出了当你使用文件适配器发送和接收消息与 BizTalk Server 我们标识的威胁的风险级别。  
  
 **表 2 的标识的威胁的风险级别**  
  
|威胁|影响|潜在损害|可再现性|可利用性|受影响的用户|可发现性|风险度|  
|------------|------------|----------------------|---------------------|--------------------|--------------------|---------------------|-------------------|  
|未经授权的用户可以从文件放置文件夹中检索消息|篡改数据<br /><br /> 信息泄漏|4|7|5|4|6|5.2|  
|未经授权的用户可将消息提交给 BizTalk Server|拒绝服务<br /><br /> 特权提升|4|7|5|4|5|5.2|  
  
## <a name="step-4-identify-mitigation-techniques-file-adapter-scenario"></a>步骤 4. 标识缓解技术 （文件适配器方案）  
 本节提供一些缓解技术进行我们已识别为文件适配器方案示例体系结构的威胁。  
  
 下表列出缓解技术和技术的使用文件适配器发送和接收消息与 BizTalk Server 时，我们识别威胁。  
  
 **表 3 缓解技术和技术**  
  
|威胁|影响|风险度|缓解措施|  
|------------|------------|-------------------|--------------------------------------------|  
|未经授权的用户可以从文件放置文件夹中检索消息|篡改数据<br /><br /> 信息泄漏|5.2|对于从其 BizTalk Server 选取消息的文件夹，使用强随机访问列表 (DACL)，如下所示：<br /><br /> -对于运行接收适配器的主机的主机实例的服务帐户，设置读取、 写入、 删除文件，和删除消息从其选取文件接收位置的目录的子文件夹和文件权限。<br />-对于外部用户或应用程序将文件放置到此文件夹中，设置写入权限。<br />-对于 BizTalk 管理员组中，设置完全控制。<br /><br /> 对于到 BizTalk Server 中删除消息的文件夹，使用强 DACL，如下所示：<br /><br /> -对于运行发送适配器的主机的主机实例的服务帐户，设置写入权限。<br />-对于外部用户或应用程序将文件放置到此文件夹中，设置的读取权限。<br />-对于 BizTalk 管理员组中，设置完全控制。|  
|未经授权的用户可将消息提交给 BizTalk Server|拒绝服务<br /><br /> 特权提升|5.2|设置强 Dacl 中接收位置投递目录如前面所述。|  
  
## <a name="see-also"></a>另请参阅  
 [威胁模型分析](../core/threat-model-analysis.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)   
 [对于小型和中型公司示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)