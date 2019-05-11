---
title: EnvelopeProcessing （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 304a19f0ab775438f01df107baf860962cf89166
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349237"
---
# <a name="envelopeprocessing-biztalk-server-sample"></a>EnvelopeProcessing （BizTalk Server 示例）
EnvelopeProcessing 示例演示如何处理消息和消息信封中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管道。 此外，它演示如何以平面文件消息加工成 XML 消息。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例将 EnvInput 文件夹配置为接收位置。 在一个文件，将示例文件 envelopeprocessing_in.txt 放，在此文件夹中，如[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理的消息在此文件中使用以下步骤：  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 从接收位置文件夹 EnvInput 检索消息文件。  

2. 在接收管道中，平面文件拆装器管道组件从平面文件消息中删除标头和尾部，并将其分析成各个消息。  

3. 在 MessageBox 数据库中，将消息路由到发送端口使用订阅筛选器。  

4. 在发送端口的发送管道中，XML 组装器管道组件将消息包装在 XML 信封中，然后将其放入发送适配器文件夹 EnvOutput。  

## <a name="how-this-sample-is-designed-and-why"></a>此示例设计方式和原因  
 此示例的设计必须适合两个基本要求：  

- 接收和处理包含一个或多个采购订单的平面文件消息。  

- 发送包含到 pickup 目录的一个采购订单和发件人信息由后端处理系统的一个 XML 消息。  

  若要满足这些要求，使用平面文件 /XML 架构和自定义管道的组合。 下表总结了这些和其他设计元素。  

|设计元素|选择的原因|  
|--------------------|--------------------------|  
|自定义接收管道|-使用平面文件拆装器和平面文件架构转换入站的采购订单消息。|  
|消息标头、 正文和尾部的平面文件架构|-定义的所有相同的记录和字段特性 （包括结构） 作为 XML 架构，并提供一种机制，用于定义所有平面文件实例消息转换为等效的 XML 实例所需的平面文件特性消息 （或相反）。<br />使用标头、 正文和尾部架构将正文拆分成进行处理的离散块。|  
|信封架构|-用于包装单个采购订单标头中的信息。|  
|订阅筛选器|-订阅筛选器执行实际的路由通过捕获符合基于属性的字段的一个或多个条件的消息。|  
|自定义发送管道|-使用 XML 组装器和信封和正文架构的组合来将实例消息转换为 XML 格式。|  

 下列注意事项适用于本示例的设计。  

-   平面文件架构 (PO.xsd) 包含描述采购订单平面文件结构的扩展的标注。 可以进行手动创建这些文件，但可以通过使用平面文件向导生成很多。  

-   采购订单 (PO.xsd) 平面文件架构使用 elementFormDefault 值 Unqualified。 这会生成正确的结果，但带有其他意外 xmlns 限定。 使用 elementformdefault 的 Qualified 值可避免此问题。  

-   标头和尾部的平面文件架构用于分离出标题和尾部消息中的数据。 平面文件拆装器标头、 文档和尾部架构属性被设置为标头，采购订单和尾部架构分别。  

-   XML 信封架构结合标头和采购订单，以生成一条 XML 消息中的元素。 标头架构将源字段升级到中的 SourceParty 字段**BTS.bts_system_properties**命名空间; 信封架构升级此相同的值，导致它降级为出站消息。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 `<Samples Path>`\Pipelines\AssemblerDisassembler\EnvelopeProcessing\  

 下表显示了本示例中的文件及其用途说明：  


|                      文件                      |                                                                                               Description                                                                                               |
|---------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                    Cleanup.bat                    |    用于取消部署程序集并从全局程序集缓存中删除。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。     |
| EnvelopeProcessing.btproj, EnvelopeProcessing.sln |                                                                               本示例的项目和解决方案文件。                                                                               |
|             EnvelopeProcessing_in.txt             |                                                                                           示例输入的文件。                                                                                            |
|          Header.xsd，PO.xsd、 Trailer.xsd          |                                                                      架构为平面文件标头、 正文和尾部，分别。                                                                      |
|                  XmlEnvelope.xsd                  |                                                                                    出站 XML 信封的架构。                                                                                    |
|    EnvReceivePipeline.btp, EnvSendPipeline.btp    | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 分别接收和发送管道使用平面文件拆装器和 XML 组装器管道组件的文件。 |
|           EnvelopeProcessingBinding.xml           |                                                                             用于如端口绑定之类的自动化设置。                                                                              |
|                     Setup.bat                     |                                                                                用于生成和初始化本示例。                                                                                |

## <a name="how-to-use-this-sample"></a>如何使用此示例  
 此示例作为基础用于平面文件处理解决方案。 您可以扩展此示例中使用以适合自己需求的设计元素的很多。 一些示例如下所示：  

-   增强示例以编写的 XML 版本除了每个采购订单的平面文件版本。 可以通过创建新的自定义发送管道并使用平面文件组装器执行此操作。 平面文件组装器，指定平面文件标头、 采购订单和尾部架构。 发送端口中使用时，它将生成标头/尾部信息的单个采购的订单。  

-   增强的从采购订单的详细信息的信封。 写入到出站消息的其他信息，"发送到"名称或其他字段中使用 Quick Promote 升级，将字段添加到信封中，然后将提升到同一个字段的信封字段。 当通过组装器处理消息时，升级的属性将降级，复制到出站消息。  

## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  

#### <a name="to-build-and-initialize-the-envelopeprocessing-sample"></a>若要生成和初始化 EnvelopeProcessing 示例  

1. 在命令窗口中，导航到以下文件夹：  

    *\<示例路径\>* \Pipelines\AssemblerDisassembler\EnvelopeProcessing  

2. 运行文件 Setup.bat，以执行以下操作：  

   - 在文件夹中创建的输入 (EnvInput) 和为本示例的输出 (EnvOutput) 文件夹：  

      *\<示例路径\>* \Pipelines\AssemblerDisassembler\EnvelopeProcessing\  

   - 编译并部署本示例的 Visual Studio 项目。  

   - 创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置、 发送和接收端口。  

      此示例将显示以下警告时创建并绑定端口：  

     ```  
     Warning: Receive handler not specified for receive location "EnvelopeProcessing_RL"; updating with first receive handler with matching transport type.  
     Warning: Host not specified for orchestration "EnvelopeProcessing"; updating with first available host.  
     ```  

      您可以放心地忽略这些警告。 （若要应对可能的命名差异在用户安装中，主机名和接收处理程序中已省略绑定文件。）  

   - 启用该接收位置，并启动发送端口。  

> [!NOTE]
>  您应确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未报告任何错误在生成和初始化过程中尝试运行此示例之前。  
> 
> [!NOTE]
>  如果你选择打开并生成本示例中的项目不运行 Setup.bat 的情况下，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。 使用此密钥对生成程序集进行签名。  
> 
> [!NOTE]
>  若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。 必须运行 Setup.bat 前运行 Cleanup.bat 时间。  

## <a name="running-this-sample"></a>运行本示例  

#### <a name="to-run-the-envelopeprocessing-sample"></a>若要运行 EnvelopeProcessing 示例  

1.  将文件 envelopeprocessing_in.txt 放的副本放到 EnvInput 文件夹下。  

2.  查看在文件夹 EnvOutput 中创建的三个.xml 文件。 这些.xml 文件的名称基于其消息 ID Guid。 它们包含从输入文件中提取和在信封中包装的消息。  

## <a name="classes-or-methods-used-in-this-sample"></a>类或方法在此示例中使用  
 配置脚本 Setup.bat 和 Cleanup.bat 依赖以下管理的 Windows Management Instrumentation (WMI) 脚本：  

- Start Send Port\StartSendPort.vbs  

- Enable Receive Location\EnableRecLoc  

- 删除发送端口 \removesendport  

  设置和清理批处理文件使用 BTSTask，如下所示：  

- **BTSTask ImportBindings**应用绑定文件并创建应用程序、 端口和绑定  

- **BTSTask RemoveApp，** 用于删除 FlatFileReceiveApplication  

## <a name="see-also"></a>请参阅  
 [Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)