---
title: "EnvelopeProcessing （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, envelopes
- flat files, processing
- examples, flat files
- examples, messages
- examples, envelopes
- envelopes, messages
- flat files, examples
- envelopes, examples
ms.assetid: b4cd979b-c7b4-446c-be29-c9f3169afa1f
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c2f2cd505aca89bbe72221b3a895dd21945cb5e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="envelopeprocessing-biztalk-server-sample"></a>EnvelopeProcessing （BizTalk Server 示例）
EnvelopeProcessing 示例演示如何在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管道中处理消息和消息信封。 此外，它还显示如何将平面文件消息处理成 XML 消息。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例将 EnvInput 文件夹配置为接收位置。 在将文件（如示例文件 EnvelopeProcessing_in.txt）放入此文件夹后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将按照以下步骤处理该文件内的消息：  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 从接收位置文件夹 EnvInput 检索消息文件。  
  
2.  在接收管道中，平面文件拆装器管道组件将从平面文件消息中删除标头和尾部，并将其分析成各个消息。  
  
3.  在 MessageBox 数据库中，使用订阅筛选器将消息路由到发送端口。  
  
4.  在发送端口的发送管道中，XML 组装器管道组件将消息包装在 XML 信封中，然后将其放入发送适配器文件夹 EnvOutput 中。  
  
## <a name="how-this-sample-is-designed-and-why"></a>本示例旨在如何以及为何  
 本示例的设计必须适合两个基本要求：  
  
-   接收和处理包含一个或多个采购订单的平面文件消息。  
  
-   将一个包含一个采购订单和发件人信息的 XML 消息发送到一个目录，以便由后端处理系统提取。  
  
 为满足这些要求，结合使用了平面文件/XML 架构和自定义管道。 下表对以上设计元素和其他设计元素进行了总结。  
  
|设计元素|选择的原因|  
|--------------------|--------------------------|  
|自定义接收管道|-使用平面文件拆装器和平面文件架构将传入的采购订单消息。|  
|消息标头、正文和尾部的平面文件架构|-定义的所有相同的记录和字段特性 （包括结构） 作为 XML 架构并提供一种机制，用于定义所有所需将平面文件实例消息转换为等效的 XML 实例的平面文件特征消息 （或相反）。<br />标头、 正文和预告片架构用于拆分为离散区块处理的正文。|  
|信封架构|-用于包装具有从标头信息的单个采购订单。|  
|订阅筛选器|-订阅筛选器执行实际的路由通过捕获满足基于属性的字段的一个或多个条件的消息。|  
|自定义发送管道|-使用 XML 汇编程序和信封和正文的架构的组合来将实例消息转换为 XML 格式。|  
  
 以下注意事项适用于设计本示例：  
  
-   平面文件架构 (PO.xsd) 包含描述采购订单平面文件的结构的扩展标注。 可手动创建这些文件，但大多数文件都可以使用平面文件向导生成。  
  
-   采购订单 (PO.xsd) 平面文件架构使用 elementFormDefault 值 Unqualified。 这会生成正确结果，但该结果带有其他意外 xmlns 限定。 使用 elementFormDefault 的 Qualified 值可避免此问题。  
  
-   使用标头和尾部平面文件架构从消息中分离出标题和尾部数据。 平面文件拆装器的标头、文档和尾部架构属性被分别设置为标头、采购订单和尾部架构。  
  
-   XML 信封架构结合标头和采购订单中的元素生成单个 XML 消息。 标头架构提升到 SourceParty 字段源字段**BTS.bts_system_properties**命名空间; 信封架构提升此相同的值，从而可以降级到出站消息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 `<Samples Path>`\Pipelines\AssemblerDisassembler\EnvelopeProcessing\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存中删除这些程序集。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|EnvelopeProcessing.btproj、EnvelopeProcessing.sln|本示例的项目文件和解决方案文件。|  
|EnvelopeProcessing_in.txt|示例输入文件。|  
|Header.xsd, PO.xsd、Trailer.xsd|分别为平面文件标头、正文和尾部的架构。|  
|XmlEnvelope.xsd|出站 XML 信封的架构。|  
|EnvReceivePipeline.btp、EnvSendPipeline.btp|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 分别使用平面文件拆装器和 XML 组装器管道组件接收和发送管道文件。|  
|EnvelopeProcessingBinding.xml|用于如端口绑定之类的自动化设置。|  
|Setup.bat|用于生成和初始化本示例。|  
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
 可将本示例用作您自己的平面文件处理解决方案的基础， 并可根据自己的需要扩展本示例中用到的诸多设计元素。 以下是一些示例：  
  
-   增强示例以在 XML 版本之外还编写每个采购订单的平面文件版本。 这可以通过创建新的自定义发送管道和使用平面文件组装器来实现。 在平面文件组装器中，指定平面文件标头、采购订单和尾部架构。 当用于发送端口中时，这将生成带有标头/尾部信息的单个采购订单。  
  
-   使用采购订单中的更多信息增强信封。 若要将其他信息写入出站消息，请使用 Quick Promote 升级“发送到”名称或其他字段，将字段添加到信封中，然后将信封字段升级为相同字段。 当通过组装器处理消息时，将对升级的属性降级并将其复制到出站消息中。  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
  
#### <a name="to-build-and-initialize-the-envelopeprocessing-sample"></a>生成和初始化 EnvelopeProcessing 示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     *\<示例路径\>*\Pipelines\AssemblerDisassembler\EnvelopeProcessing  
  
2.  运行 Setup.bat 文件，该文件将执行以下操作：  
  
    -   在下面的文件夹中，为本示例创建输入 (EnvInput) 和输出 (EnvOutput) 文件夹：  
  
         *\<示例路径\>*\Pipelines\AssemblerDisassembler\EnvelopeProcessing\  
  
    -   为本示例编译并部署 Visual Studio 项目。  
  
    -   创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置、发送和接收端口。  
  
         本示例在创建和绑定端口时将显示以下警告：  
  
        ```  
        Warning: Receive handler not specified for receive location "EnvelopeProcessing_RL"; updating with first receive handler with matching transport type.  
        Warning: Host not specified for orchestration "EnvelopeProcessing"; updating with first available host.  
        ```  
  
         可以安全地忽略这些警告。 （考虑可能命名在用户安装中，主机名的差异和接收处理程序省略了从绑定文件。）  
  
    -   启用接收位置并启动发送端口。  
  
> [!NOTE]
>  在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。  
  
> [!NOTE]
>  如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat，必须首先创建强名称密钥对使用.NET Framework 强名称工具 (sn.exe)。 使用此密钥对生成的程序集进行签名。  
  
> [!NOTE]
>  若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。 在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-the-envelopeprocessing-sample"></a>运行 EnvelopeProcessing 示例  
  
1.  将 EnvelopeProcessing_in.txt 文件的副本放到 EnvInput 文件夹下。  
  
2.  查看在文件夹 EnvOutput 中创建的三个 .xml 文件。 这些 .xml 文件的名称基于其消息 ID GUID。 它们包含从输入文件提取和在信封中包装的消息。  
  
## <a name="classes-or-methods-used-in-this-sample"></a>本示例中使用的类或方法  
 配置脚本 Setup.bat 和 Cleanup.bat 依赖于以下 Windows 管理规范 (WMI) 管理脚本：  
  
-   启动发送端口\StartSendPort.vbs  
  
-   启用接收位置\EnableRecLoc  
  
-   删除发送端口\RemoveSendPort  
  
 安装和清除批处理文件使用以下 BTSTask：  
  
-   **BTSTask ImportBindings**应用绑定文件并创建应用程序、 端口和绑定  
  
-   **BTSTask RemoveApp**删除 FlatFileReceiveApplication  
  
## <a name="see-also"></a>另请参阅  
 [Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)