---
title: 管道工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline tools, XMLAsm.exe
- pipeline tools, FFDasm.exe
- Pipeline.exe
- FFDasm.exe
- pipeline tools, XMLDasm.exe
- pipeline tools
- XMLAsm.exe
- pipeline tools, DSDump.exe
- FFAsm.exe
- pipeline tools, FFAsm.exe
- pipeline tools, how to
- pipeline tools, about pipeline tools
- pipeline tools, Pipeline.exe
- utilities, pipeline tools
- XMLDasm.exe
ms.assetid: ca4d053a-1473-4d40-8cd0-1ed3a3af988a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5d9a2aeff4b73eebb95b8be8a76b92fb9c7848d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395758"
---
# <a name="pipeline-tools"></a>管道工具
使用 Microsoft 提供的管道工具[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]软件开发工具包 (SDK) 使您可以验证管道工作正常，而无需配置 BizTalk Server 环境，如发送/接收端口。 此外可以使用管道工具：  

-   调试服务器环境外的第三方管道组件。  

-   诊断解析引擎错误消息。  

-   尝试使用不同的架构，而无需编译、 部署、 取消部署和重新编译的负担。  

-   浏览平面文件和 XML 组装器/拆装器行为。  

-   查看拆装器输出和发现哪些消息上下文属性将升级以及它们的值。  

-   运行没有拆装器和组装器组件发送/接收管道 （例如，可以查看 S/MIME 解码器的输出）。  

-   使管道的细粒度的性能度量值本身 （而不是整个消息传送子系统）。  

## <a name="location-in-sdk"></a>在 SDK 中的位置  
 \<*Installation Path*\>\SDK\Utilities\PipelineTools  

 将管道工具用于执行、 调试和分析管道和管道组件 （即，平面文件和 XML 组装器/拆装器组件）。  

## <a name="file-inventory"></a>文件清单  
 下表列出了管道工具文件，并描述其用途。  


|   文件    |                                                                                                                                                                                                                                Description                                                                                                                                                                                                                                 |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  DSDump.exe  |                                                允许您转储文档架构结构，它是内存中轻量表示形式的一个或多个 XSD 架构，有或没有平面文件批注。 获取解析引擎错误时，此工具很有帮助如 $Root 0 美元 $ 3 个 2 美元，并且需要对其进行解码。 $ 后的数字表示基于 0 的索引或记录的文档架构中的显示方式。                                                |
|  FFAsm.exe   |                                                                                                                                     运行平面文件组装器组件，通过模拟发送管道，使您可以查看如何序列化或用户的 XML 文档组装到平面文件文档直接调用它。                                                                                                                                      |
|  FFDasm.exe  |                                                                                                                               运行平面文件拆装器组件，通过模拟接收管道，使您可以查看如何解析或拆装到一个或多个 XML 文档的用户的平面文件文档直接调用它。                                                                                                                               |
| Pipeline.exe | 运行发送或接收管道;接受一个或多个输入的文档及其部分、 XSD 架构和相关的信息;并生成输出文档后管道运行。 因此，访问包含 BizTalk 框架组装器和拆装器组件的管道，Pipeline.exe 不访问 BizTalk Server 数据库，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可能不支持在执行过程的数据库。 |
|  XMLAsm.exe  |                                                                                                                                 运行 XML 组装器组件，直接调用它，通过模拟发送管道来，可以查看如何序列化、 组装或信封用户的 XML 文档转换为输出 XML 文档。                                                                                                                                  |
| XMLDasm.exe  |                                                                                                                             运行 XML 拆装器组件，直接调用它，通过模拟接收管道来，可以查看如何分析拆装或解用户的 XML 文档到一个或多个 XML 文档。                                                                                                                              |

## <a name="usage"></a>用法  
 以下各节提供了每个文件的更详细的说明。  

### <a name="dsdumpexe"></a>DSDump.exe  
 DSDump.exe 允许您转储文档架构结构，它是一个或多个 XSD 架构、 有或没有平面文件批注的内存中轻量表示形式。  

 DSDump.exe （文档架构转储工具） 支持以下命令行参数：  

```  
DSDump.exe schemaFileName  
```  

 如果成功，DSDump 打印到控制台的文档架构。  

### <a name="ffasmexe"></a>FFAsm.exe  
 FFAsm.exe （平面文件组装器） 支持以下命令行参数：  

```  
usage: ffasm document... [-dm documentMask...]-bs bodySchema [ -hs headerSchema ] [ -ts trailerSchema ] [ -c ] [ -d ] [ -sb ] [ -m filenamemask ] [ -en encoding ] [ -v ]  

where:  
  document           XML document(s)  
  documentMask       XML document(s) file mask, e.g., c:\\documents\\*.xml  
  bodySchema         Flat File body schema  
  headerSchema       Flat File header schema  
  trailerSchema      Flat File trailer schema  
  -c                 Display assembled FF message on the console  
  -d                 Demote properties  
  -sb                Set body schema(s) as design-time property  
  -m                 Output file name mask (default is %MessageID%)  
  encoding           Output message encoding name (e.g. windows-1252) or   
                         code page (e.g. 936)  
  -v                 Verbose mode  

file name macros:  
  %MessageID%        FF message identifier (Guid)  
  %MessagePartID%    FF message part identifier (Guid)  

```  

 例如，如果你想要将三个输入的 XML 文档组装到一个具有标头和属性降级的单个平面文件文档，使用以下命令：  

```  
FFAsm.exe file_in1.xml file_in2.xml file_in3.xml –hs myHeaderSchema.xsd –bs myBodySchema.xsd -d  
```  

### <a name="ffdasmexe"></a>FFDasm.exe  
 FFDasm.exe （平面文件反汇编程序） 支持以下命令行参数：  

```  
usage: ffdasm document -bs bodySchema [ -hs headerSchema ] [ -ts trailerSchema ] [ -s ] [ -c ] [ -p ] [ -m filenamemask ] [ -en encoding ] [ -v ]  

where:  
  document           Flat File document  
  bodySchema         Flat File body schema  
  headerSchema       Flat File header schema  
  trailerSchema      Flat File trailer schema  
  -s                 Validate document structure  
  -c                 Display disassembled XML message on the console  
  -p                 Display promoted properties on the console  
  encoding           Input message body part encoding name (e.g. windows-1252) or code page (e.g., 396)  
  -m                 Output file name mask (default is %MessageID%)  
  -v                 Verbous mode  

file name macros:  
  %MessageID%        XML message identifier (Guid)  
  %MessagePartID%    XML message part identifier (Guid)  

```  

 例如，如果你想要拆装平面文件文档包含头部、 正文和尾部，并将结果显示到控制台，使用以下命令：  

```  
FFDasm.exe file_in.txt –hs myHeaderSchema.xsd –bs myBodySchema.xsd –ts myTrailerSchema.xsd –c  
```  

### <a name="pipelineexe"></a>Pipeline.exe  
 Pipeline.exe （管道工具） 支持以下命令行参数：  

```  
usage: pipeline ( pipeline[.btp] | -pt pipelineTypeName [ -an assemblyName ] ) -d document... [ -part part... ] [ -s schema[.xsd][:namespace.type]... ] [ -proj project[.btproj] ] [ -p ] [ -c ] [ -t ] [ -m filenamemask ] [ -pm partfilenamemask ] [ -en encoding ] [ -v ]  

where:  
  pipeline                Pipeline file name  
  pipelineTypeName     Compiled pipeline assembly qualified type name (e.g.   
"MyPipelines.ReceivePipeline, MyPipelines,   
Version=1.0.0.0, Culture=neutral,   
PublicKeyToken=e03965cb5971ad66" or full name (e.g.   
"MyPipelines.ReceivePipeline") if assembly name is   
specified  
  assemblyName         Compiled pipeline assembly file name (e.g.   
MyPipelines.dll) or name (e.g. "MyPipelines,   
Version=1.0.0.0, Culture=neutral,   
PublicKeyToken=e03965cb5971ad66")  
  document             Input document(s)  
  part                 Input document's part  
  schema               Schema file name  
  namespace            Schema namespace (as in BizTalk project system)  
  type                 Schema type (as in BizTalk project system)  
  project              BizTalk project file  
  -p                   Display promoted context properties for receive and   
send pipelines, and promote context properties for   
send pipelines  
  -c                      Display output document on the console  
  -t                      Display elapsed time of components execution  
  filenamemask         Output message file name mask (default is   
Message_%MessageID%.out)  
  partfilenamemask     Output part file name mask (default is   
Part_%MessagePartID%.out)  
  encoding             Output message encoding name (e.g. windows-1252)   
or code page (e.g. 936)  
  -v                   Verbous mode  

note:  
You can specify namespace and type for schemas either using namespace.type notation in schema file reference or by using BizTalk project file.  

file name macros:  
  %MessageID%           Message identifier (Guid)  
  %MessagePartID%       Message part identifier (Guid)  
  %MessageNumber%       Message number  

```  

 例如，如果你想要从 receivepipeline.btp (具有 XML 拆装器和 XML 验证器组件） 运行接收管道使用 mySchema.xsd 和显示到控制台，结果，请使用以下命令：  

```  
Pipeline.exe ReceivePipeline.btp –d file_in.xml –s MySchema.xsd:MyProject.MySchema -c  

```  

 \- 或 -  

```  
Pipeline.exe ReceivePipeline.btp –d file_in.xml –s MySchema.xsd –proj MyProject.btproj -c  

```  

 在第一个示例中，限定的类型名称 (**MyProject.MySchema**) 架构是包含作为命令行参数。 在第二个示例中，从指定的 BizTalk 项目文件中获取该架构。  

 此外可以从编译运行管道[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目文件，如下面的示例 （管道由其程序集限定类型名称引用） 中所示：  

```  
Pipeline.exe -pt "TestBtsProject.ReceivePipeline, TestBtsProject, Version=1.0.0.0, Culture=neutral, PublicKeyToken=e03965cb5971ad66" -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c  
```  

 在以下示例中，管道引用由其类型名称和程序集文件名分别：  

```  
Pipeline.exe -pt TestBtsProject.ReceivePipeline –an TestBtsProject.dll -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c   
```  

 下面的示例演示其程序集名称所引用的管道：  

```  
Pipeline.exe -pt TestBtsProject.ReceivePipeline –an "TestBtsProject, Version=1.0.0.0, Culture=neutral, PublicKeyToken=e03965cb5971ad66" -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c  
```  

 Pipeline.exe 运行时使用你用于启动其任何凭据。 它不使用的普通帐户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机实例下运行，您可能不能运行包含需要数据库访问权限组件的管道。 请确保具有所需的所有权限的帐户下运行 Pipeline.exe。  

 仅应使用 Pipeline.exe 来验证没有第三方自定义组件的自定义管道。 如果使用 pipeline.exe 来验证与第三方自定义组件的自定义管道，Pipeline.exe 将生成所需的输出。 但是，如果在部署具有第三方自定义组件的相同自定义管道使用管道在接收或发送端口，然后使用 Pipeline.exe 将消息提交到管道，管道将失败，BizTalk Server 将返回错误。  

### <a name="xmlasmexe"></a>XMLAsm.exe  
 XMLAsm.exe （XML 组装器工具） 支持以下命令行参数：  

```  
usage: xmlasm document...[-dm documentmask...] -ds documentSchema... [ -es envelopeSchema... ] [ -c ] [ -d ] [ -sd ] [ -m filenamemask ] [ -v ]  

where:  
  document           XML document(s)  
  documentMask       XML document(s) file mask, e.g., c:\\documents\\*.xml  
  documentSchema     XML document schema(s)  
  envelopeSchema     XML envelope schema(s)  
  -c                 Display assembled XML message on the console  
  -d                 Demote properties  
  -sd                Set document schema(s) as design-time property  
  -d                 Demote properties  
  -m                 Output file name mask (default is %MessageID%)  
  -v                 Verbous mode  

file name macros:  
  %MessageID%        XML message identifier (Guid)  
  %MessagePartID%    XML message part identifier (Guid)  

```  

 例如，如果你想要将两个输入的 XML 文档组装到一个具有信封的单个 XML 文档并将结果显示到控制台，使用以下命令：  

```  
FFAsm.exe file_in1.xml file_in2.xml–es myEnvelopeSchema.xsd –ds myBodySchema.xsd –c  
```  

### <a name="xmldasmexe"></a>XMLDasm.exe  
 XMLDasm.exe 支持以下命令行参数：  

```  
usage: xmldasm document -ds documentSchema... [ -es envelopeSchema... ] [ -s ] [ -c ] [ -p ] [ -sd ] [ -se ] [ -m filenamemask ] [ -en encoding ] [ -v ]  

where:  
  document           XML document  
  documentSchema     XML document schema(s)  
  envelopeSchema     XML envelope schema(s)  
  -s                 Validate document structure  
  -c                 Display disassembled XML message on the console  
  -p                 Display promoted properties on the console  
  -sd                Set document schema(s) as design-time property  
  -se                Set envelope schema(s) as design-time property  
  -m                 Output file name mask (default is %MessageID%)  
  encoding           Input message body part encoding name (e.g., windows-1252) or code page (e.g., 936)  
  -v                 Verbous mode  

file name macros:  
  %MessageID%        XML message identifier (Guid)  
  %MessagePartID%    XML message part identifier (Guid)  
  %MessageNumber%    XML message number  

```  

 例如，如果您希望拆装具有两个嵌套信封的 XML 文档并将结果显示到控制台，请使用以下命令：  

```  
XmlDasm.exe file_in.txt –ds myDocumentSchema.xsd –es myEnvelopeSchema1.xsd –es myEnvelopeSchema2.xsd –c  
```  

## <a name="see-also"></a>请参阅  
 [SDK 中的实用工具](../core/utilities-in-the-sdk.md)