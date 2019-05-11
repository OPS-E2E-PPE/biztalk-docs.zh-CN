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
ms.openlocfilehash: d987164eeb855bfc991e9b4f1b0c8b444b99407b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325120"
---
# <a name="message-enrichment-sample-biztalk-server-sample"></a>消息充实示例 （BizTalk Server 示例）
消息收集示例演示如何将交换标头附加到事务集消息的 X12 和 EDIFACT 文档。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 此示例演示如何将对于 EDIFACT，UNA、 UNB 和 UNG 标头和对于 X12，ISA 标头附加到事务集。 具体而言，此示例执行以下任务：  
  
1.  将测试消息放到 enrichment\in 文件夹时，接收端口获取、 处理它，并将其放入 MessageBox。  
  
2.  MessageEnrichmentOrchestration 选取测试消息从 MessageBox，因为其订阅的消息根据其接收形状上设置筛选器表达式。  
  
3.  业务流程从消息上下文属性中读取交换标头。  
  
    > [!NOTE]
    >  UNA 和 UNG 标头是消息的可选的 EDIFACT 消息，因此可能会丢失上下文属性中。  
  
4.  业务流程将交换标头和消息正文写入到一条新消息。  
  
5.  业务流程将在 ReceivePortNameCorrelationType 相关类型到消息上设置其他属性。 这些行为允许业务流程的用户选择所需订阅的属性的列表。 这些属性是在构造消息形状中编写的。 并非所有已写入到原始消息的上下文属性写入到新消息。  
  
6.  业务流程将新消息放入 MessageBox。  
  
7.  发送端口提取新消息并将其通过文件适配器发送至 \message enrichment\out 文件夹。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 此示例位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹：[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\Message Enrichment。  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|Cleanup.bat|取消部署示例方案。 为了使它成功必须是业务流程没有活动实例。 否则，它将失败。|  
|MessageEnrichment.sln|包含 MessageEnrichment 和 MessageEnrichmentLibrary 项目。|  
|Setup.bat|将部署包含接收端口、 发送端口和业务流程的示例方案。|  
|EDIFACT_example.edi|输入的 EDIFACT 消息。|  
|X12_example.edi|输入 X12 消息。|  
|MessageEnrichment.btproj|包含 MessageEnrichment 业务流程和架构的项目。|  
|MessageEnrichmentBindings.xml|包含该业务流程、 端口和参与方绑定的文件。|  
|MessageEnrichmentOrchestration.odx|将标头附加到消息的业务流程。|  
|MessageEnrichmentOrchestration.odx.cs|将标头附加到消息的业务流程代码。|  
|EFACT_D98B_APERAK.xsd|输入消息的 EDIFACT 架构。|  
|Enriched_EFACT_D98B_APERAK.xsd|输出消息的 EDIFACT 架构。|  
|X12_00401_864.xsd|X12 输入消息的架构。|  
|Enriched_X12_00401_864.xsd|X12 输出消息的架构。|  
|Headers.xsd|添加到输入消息的标头的架构。|  
|MessageEnrichmentLibrary.csproj|包含 Headers.cs、 OrchestrationUtilities.cs 和 ParseHeaders.cs 文件的项目。|  
|Headers.cs|包括表示标头数据的类。|  
|OrchestrationUtilities.cs|包括使用业务流程的实用工具方法。|  
|ParseHeaders.cs|包括新的消息中使用的 UNA 默认值。 这些值取自 ParseHeaders.cs 中的 SerializeEDIFACTHeaders 方法。|  
  
## <a name="how-to-use-this-sample"></a>如何使用此示例  
 本示例用作将交换标头附加到 EDI 事务集消息所必需的操作的可运行示例。  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 生成并初始化消息收集示例，您需要生成和部署本示例中，在 BizTalk 项目配置接收端口和位置，并配置两个不同的发送端口。  
  
#### <a name="to-build-and-deploy-the-biztalk-project-for-this-sample"></a>若要生成和部署此示例的 BizTalk 项目  
  
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
  
   -   密钥对写入 messageenrichmentlibrary\testkey.snk。  
  
   -   生成并部署 MessageEnrichmentLibrary.btproj 项目。  
  
   -   生成并部署 MessageEnrichment.btproj 项目。  
  
   -   读取 MessageEnrichmentBindings.xml 中的绑定信息。  
  
       > [!NOTE]
       >  此项目的绑定需要的 BizTalk 主机标记为受信任的身份验证。  若要使用这与不受信任的主机，修改 MessageEnrichmentBindings.xml 并更改 HostTrusted ="true"条目为 HostTrusted ="false"。  
  
   -   更新业务流程绑定。  
  
   -   更新发送端口、 发送端口组和接收端口。  
  
   -   更新参与方和登记。  
  
   -   启动发送端口。  
  
   -   启用接收位置。  
  
   -   登记并启动业务流程。  
  
   现在便可使用本示例 BizTalk Server。  
  
## <a name="running-this-sample"></a>运行本示例  
 使用以下过程运行消息收集示例。  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1.  将 \MessageEnrichment\Instances 文件夹中的 EDIFACT_examples.edi 文件复制到 \MessageEnrichment\In 文件夹。  
  
2.  验证 EDIFACT_examples.edi 文件将从 \MessageEnrichment\In 文件夹中消失，并且会显示在 \MessageEnrichment\Out 文件夹。  
  
3.  打开 \MessageEnrichment\Out 文件夹中的文件。 验证它的 XML 表示形式 EDIFACT_examples.edi 文件在 \MessageEnrichment\Instances 文件夹中，并且是与输出文件包含 EDIFACT UNA、 UNB 和 UNG 标头的 EDIFACT_examples.edi 文件具有相同的内容。  
  
4.  针对 \MessageEnrichment\Instances 文件夹中的 X12_examples.edi 文件重复步骤 1 和 2。  
  
5.  打开 \MessageEnrichment\Out 文件夹中的新文件。 验证它是否的 XML 表示形式 X12_examples.edi 文件在 \MessageEnrichment\Instances 文件夹中，并且是与输出文件包含 X12 的 X12_examples.edi 文件具有相同内容 ISA 标头。  
  
## <a name="classes-or-methods-used-in-this-sample"></a>类或方法在此示例中使用  
 None  
  
## <a name="see-also"></a>请参阅  
 [EDI 和 AS2（BizTalk Server 示例文件夹）](../core/edi-and-as2-biztalk-server-samples-folder.md)