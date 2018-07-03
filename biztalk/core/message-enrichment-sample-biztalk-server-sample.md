---
title: 消息充实示例 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41ed707-dbdb-46b7-97a6-86fdbc8ad285
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01fa66b344548654a4d2e2e2f2b8700b604ec0e7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998502"
---
# <a name="message-enrichment-sample-biztalk-server-sample"></a>消息收集示例（BizTalk Server 示例）
消息收集示例演示如何将 X12 文档和 EDIFACT 文档的交换标头附加到事务集消息中。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例演示如何将针对 EDIFACT 的 UNA、UNB 和 UNG 标头及针对 X12 的 ISA 标头附加到事务集。 具体而言，本示例执行下列操作：  
  
1.  将测试消息放入 \Message Enrichment\In 文件夹时，接收端口将提取和处理该消息，然后将其放入 MessageBox 中。  
  
2.  MessageEnrichmentOrchestration 将从 MessageBox 中提取该测试消息，因为该业务流程基于在其接收形状上设置的筛选器表达式订阅消息。  
  
3.  业务流程从消息的上下文属性中读取交换标头。  
  
    > [!NOTE]
    >  因为 UNA 和 UNG 标头在 EDIFACT 消息中不是必需部分，所以在消息的上下文属性中可能会缺失此类标头。  
  
4.  业务流程将交换标头和消息正文写入单个新消息中。  
  
5.  业务流程将在 ReceivePortNameCorrelationType 相关类型中设置的其他属性升级到该消息中。 利用这些属性，业务流程的用户可以选择订阅时所需属性的列表。 这些属性是在构造消息形状中编写的。 并非所有写入原始消息的上下文属性都将写入新消息。  
  
6.  业务流程将新消息放入 MessageBox 中。  
  
7.  发送端口提取新消息，并通过 FILE 适配器将其发送至 \Message Enrichment\Out 文件夹。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 此示例位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹： [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\Message Enrichment。  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|Cleanup.bat|取消部署示例方案。 为了成功完成此操作，绝对不能存在活动的业务流程实例。 否则，操作将失败。|  
|MessageEnrichment.sln|包含 MessageEnrichment 和 MessageEnrichmentLibrary 项目。|  
|Setup.bat|部署包含接收端口、发送端口和业务流程的示例方案。|  
|EDIFACT_example.edi|一条 EDIFACT 输入消息。|  
|X12_example.edi|一条 X12 输入消息。|  
|MessageEnrichment.btproj|包含 MessageEnrichment 业务流程和架构的项目。|  
|MessageEnrichmentBindings.xml|包含业务流程、端口和参与方的绑定的文件。|  
|MessageEnrichmentOrchestration.odx|将标头附加到消息的业务流程。|  
|MessageEnrichmentOrchestration.odx.cs|将标头附加到消息的业务流程代码。|  
|EFACT_D98B_APERAK.xsd|输入消息的 EDIFACT 架构。|  
|Enriched_EFACT_D98B_APERAK.xsd|输出消息的 EDIFACT 架构。|  
|X12_00401_864.xsd|输入消息的 X12 架构。|  
|Enriched_X12_00401_864.xsd|输出消息的 X12 架构。|  
|Headers.xsd|要添加到输入消息的标头的架构。|  
|MessageEnrichmentLibrary.csproj|包含 Headers.cs、OrchestrationUtilities.cs 和 ParseHeaders.cs 文件的项目。|  
|Headers.cs|包括表示标头数据的类。|  
|OrchestrationUtilities.cs|包含业务流程使用的实用工具方法。|  
|ParseHeaders.cs|包含新消息中使用的 UNA 默认值。 这些值取自 ParseHeaders.cs 中的 SerializeEDIFACTHeaders 方法。|  
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
 可将本示例作为演示将交换标头附加到 EDI 事务集消息所需操作的可运行示例。  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化本示例  
 若要生成并初始化消息收集示例，您需要为本示例生成并部署 BizTalk 项目、配置接收端口和位置，并配置两个不同的发送端口。  
  
#### <a name="to-build-and-deploy-the-biztalk-project-for-this-sample"></a>为本示例生成并部署 BizTalk 项目  
  
1. 使用 Notepad.Exe，打开[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\MessageEnrichment\  
   MessageEnrichment\properties\AssemblyInfo.cs 并在文件底部添加以下行：  
  
   ```  
   [assembly: Microsoft.XLANGs.BaseTypes.BizTalkAssembly(typeof(Microsoft.BizTalk.XLANGs.BTXEngine.BTXService))]  
   ```  
  
2. 保存修改的 AssemblyInfo.cs 文件，然后退出记事本。  
  
3. 在命令窗口中，转至以下文件夹：  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\Message Enrichment  
  
4. 运行**Setup.bat**，该文件将执行以下操作：  
  
   -   创建接收 (**中**) 和发送 (**出**) \MessageEnrichment 文件夹中的以下示例的文件夹。  
  
   -   将密钥对写入 MessageEnrichmentLibrary\testkey.snk。  
  
   -   生成并部署 MessageEnrichmentLibrary.btproj 项目。  
  
   -   生成并部署 MessageEnrichment.btproj 项目。  
  
   -   读取 MessageEnrichmentBindings.xml 中的绑定信息。  
  
       > [!NOTE]
       >  此项目的绑定需要将 BizTalk 主机标记为受信任的身份验证。  为了将此绑定与不受信任的主机一起使用，请修改 MessageEnrichmentBindings.xml 并将 HostTrusted=”true” 条目更改为 HostTrusted=”false”。  
  
   -   更新业务流程绑定。  
  
   -   更新发送端口、发送端口组和接收端口。  
  
   -   更新参与方和登记。  
  
   -   启动发送端口。  
  
   -   启用接收位置。  
  
   -   登记并启动业务流程。  
  
   BizTalk Server 现在便可使用本示例。  
  
## <a name="running-this-sample"></a>运行本示例  
 使用以下过程运行消息收集示例。  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1.  将 \MessageEnrichment\Instances 文件夹中的 EDIFACT_examples.edi 文件复制到 \MessageEnrichment\In 文件夹中。  
  
2.  验证 EDIFACT_examples.edi 文件是否已从 \MessageEnrichment\In 文件夹中消失，并显示在 \MessageEnrichment\Out 文件夹中。  
  
3.  打开 \MessageEnrichment\Out 文件夹中的文件。 验证该文件是否为 \MessageEnrichment\Instances 文件夹中的 EDIFACT_examples.edi 文件的 XML 表示形式，并且包含与 EDIFACT_examples.edi 文件相同的内容。不过与之不同的是，该输出文件包含 EDIFACT UNA、UNB 和 UNG 标头。  
  
4.  针对 \MessageEnrichment\Instances 文件夹中的 X12_examples.edi 文件，请重复步骤 1 至 2。  
  
5.  打开 \MessageEnrichment\Out 文件夹中的新文件。 验证该文件是否为 \MessageEnrichment\Instances 文件夹中的 X12_examples.edi 文件的 XML 表示形式，并且包含与 X12_examples.edi 文件相同的内容。不过与之不同的是，该输出文件包含 X12 ISA 标头。  
  
## <a name="classes-or-methods-used-in-this-sample"></a>本示例中使用的类或方法  
 InclusionThresholdSetting  
  
## <a name="see-also"></a>请参阅  
 [EDI 和 AS2（BizTalk Server 示例文件夹）](../core/edi-and-as2-biztalk-server-samples-folder.md)