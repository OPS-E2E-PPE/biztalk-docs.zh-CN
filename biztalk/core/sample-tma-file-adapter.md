---
title: 示例 TMA:文件适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
- DFD, File adapters
- File adapters, TMA
- examples, File adapters
- security examples [TMA], File adapters
ms.assetid: bcb862c0-fe02-4335-8b59-242d28049e3f
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d22d7bfc496921b9d564dc673755f2b52009e27
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309572"
---
# <a name="sample-tma-file-adapter"></a>示例 TMA:文件适配器
本主题介绍对示例结构的文件适配器方案进行威胁模型分析 (TMA)。 下图显示了文件适配器方案的示例体系结构。  
  
 **图 1 示例文件适配器方案的体系结构**  
  
 ![示例文件适配器的体系结构](../core/media/tdi-sec-refarch-file.gif "TDI_Sec_RefArch_File")  
  
## <a name="step-1-collect-background-information-file-adapter-scenario"></a>步骤 1. 收集背景信息 （文件适配器方案）  
 本部分提供对示例结构的文件适配器方案的数据流关系图 (DFD)。  
  
 所有其他背景信息是相同的所有使用方案，以及前面所述[示例方案的背景信息](../core/background-information-for-sample-scenarios.md)。  
  
### <a name="data-flow-diagram"></a>数据流关系图  
 使用文件适配器时，下图显示了示例结构的 dfd:。  
  
 **图 2 DFD 的示例结构的文件适配器方案**  
  
 ![DFD 的示例体系结构](../core/media/tdi-sec-refarch-dfd-file.gif "TDI_Sec_RefArch_DFD_FILE_")  
  
 数据流如下所示：  
  
1.  合作伙伴将一条消息 （通过防火墙 1) 放在 intranet 外围网络中的文件服务器中。  
  
2.  进程内主机实例的文件接收适配器定期轮询新消息 （通过防火墙 2) 的文件服务器。 会在有新消息后，它将检索消息、 进行初始处理，并将该消息放在 MessageBox 数据库中。  
  
3.  已对消息的订阅的处理主机实例提取该消息从 MessageBox 数据库、 任何其他处理，并将该消息放回 MessageBox 数据库中。  
  
4.  发送适配器提取该消息具有文件的进程内主机实例将从 MessageBox 数据库。 该消息完成所有最终处理，发送管道中，通过防火墙 2 然后到文件服务器发送。  
  
5.  合作伙伴将提取来自文件服务器的消息。  
  
## <a name="step-2-create-and-analyze-the-threat-model-file-adapter-scenario"></a>步骤 2. 创建和分析威胁模型 （文件适配器方案）  
 本部分提供对示例结构的文件适配器方案执行的 TMA 的结果。  
  
- **确定入口点、 信任边界和数据流-** 请参阅之前在"收集背景信息文件适配器方案的"和"适用于所有方案的背景信息。"中介绍的背景信息  
  
- **创建一组威胁-** 我们使用以下分类 DFD 中的所有条目来识别潜在威胁的方案：**S**poofing 标识，请**T**篡改数据， **R**epudiation，**我**表示信息泄露**D**表示拒绝服务，并**E**表示特权提升。 下表列出了使用文件适配器发送和接收消息与 BizTalk Server 时的各威胁分类。  
  
  **表 1 列表标识的威胁**  
  
|威胁|Description|资产|影响|  
|------------|-----------------|-----------|------------|  
|未经授权的用户可以从文件放置文件夹中检索消息|如果你尚未设置加强的任意访问列表 (Dacl) 的文件夹，文件适配器使用，未经授权的用户可以在该文件中存放消息接收位置，或提取从文件发送位置的消息。|消息正文|篡改数据<br /><br /> 信息泄露|  
|未经授权的用户可以将消息提交给 BizTalk Server|如果用户从其 BizTalk Server 将提取的消息的 file 文件夹具有写权限，未经授权的用户可以将消息提交给 BizTalk Server。|消息正文|拒绝服务<br /><br /> 特权提升|  
  
## <a name="step-3-review-threats-file-adapter-scenario"></a>步骤 3. 查看威胁 （文件适配器方案）  
 本部分提供有关文件适配器方案的示例体系结构的各威胁分类的风险分析的结果。 在主要威胁模型会议后，我们对威胁进行并使用以下影响类别来划分每种威胁的风险：**D**潜在，损害**R**再现， **E**xploitability，**一个**可用户并**D**iscoverability。  
  
 下表列出了使用文件适配器发送和接收消息与 BizTalk Server 时的各威胁分类的风险等级。  
  
 **表 2 威胁分类的风险等级**  
  
|威胁|影响|潜在破坏性|可再现性|可利用性指数|受影响的用户|可发现性|风险危害|  
|------------|------------|----------------------|---------------------|--------------------|--------------------|---------------------|-------------------|  
|未经授权的用户可以从文件放置文件夹中检索消息|篡改数据<br /><br /> 信息泄露|4|7|5|4|6|5.2|  
|未经授权的用户可以将消息提交给 BizTalk Server|拒绝服务<br /><br /> 特权提升|4|7|5|4|5|5.2|  
  
## <a name="step-4-identify-mitigation-techniques-file-adapter-scenario"></a>步骤 4. 确定缓解措施 （文件适配器方案）  
 本部分介绍对示例结构的文件适配器方案的各威胁分类的一些缓解措施。  
  
 下表列出了缓解措施时使用文件适配器发送和接收消息与 BizTalk Server 的各威胁分类。  
  
 **表 3 缓解措施和技术**  
  
|威胁|影响|风险危害|缓解措施|  
|------------|------------|-------------------|--------------------------------------------|  
|未经授权的用户可以从文件放置文件夹中检索消息|篡改数据<br /><br /> 信息泄露|5.2|对于从该 BizTalk Server 将提取的消息的文件夹，使用加强的任意访问列表 (DACL)，如下所示：<br /><br /> -对于运行接收适配器的主机的主机实例的服务帐户，设置读取、 写入、 删除文件，和删除子文件夹和文件权限从中文件接收位置提取消息的目录。<br />-对于外部用户或应用程序将文件放入此文件夹中，将设置写入权限。<br />-对于 BizTalk Administrators 组中，设置完全控制。<br /><br /> 对于到 BizTalk Server 将删除消息的文件夹，使用强 DACL，如下所示：<br /><br /> -对于运行发送适配器的主机的主机实例的服务帐户，将设置写入权限。<br />-对于外部用户或应用程序将文件放入此文件夹中，设置的读取权限。<br />-对于 BizTalk Administrators 组中，设置完全控制。|  
|未经授权的用户可以将消息提交给 BizTalk Server|拒绝服务<br /><br /> 特权提升|5.2|加强的 Dacl 中设置接收位置的存放目录如先前所述。|  
  
## <a name="see-also"></a>请参阅  
 [威胁模型分析](../core/threat-model-analysis.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)   
 [中小型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)