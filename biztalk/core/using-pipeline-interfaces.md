---
title: 使用管道接口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bb88d0d-23ab-4fdb-bcd2-56050456cf69
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c365a8d7bdf37564d3d9b2dceac1c8615e126ebc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289141"
---
# <a name="using-pipeline-interfaces"></a>使用管道接口
管道组件一种 .NET 或 COM 组件，它实现一组预定义的接口以便与 BizTalk 消息引擎交互。 根据组件的功能，必须实现不同接口。 本主题介绍这些接口及其一些方法。  
  
> [!WARNING]
>  如果您在使用 COM 构建自定义管道组件，则必须配置您的组件以便使用多线程单元 (MTA) 模型。 如果没有这样做，则组件的调用将失败并且具有 E_NOINTERFACE 错误。  
  
## <a name="ipipelinecontext"></a>IPipelineContext  
 可以使用所有管道组件**IPipelineContext**用于访问所有文档处理特定接口的方法。 **IPipelineContext**接口提供了以下功能：  
  
-   允许组件检索环境管道和阶段设置。  
  
-   允许组件检索消息和消息工厂。 使用这些工厂，组件可以创建执行组件所需的不同对象。  
  
-   允许组件检索文档规范。 文档规范是 XSD 架构以及附加的批注。  
  
## <a name="ibasecomponent"></a>IBaseComponent  
 所有管道组件都需要实现此接口，以便提供有关组件的基本信息。  
  
## <a name="icomponent"></a>为 IComponent  
 除组装器和拆装器之外的所有管道组件都实现此接口，以便从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 引擎获取消息以供处理并将已处理的消息传递回引擎。  
  
 **执行。** 由引擎调用以便将输入消息传递到组件并从组件检索已处理的消息的方法。  
  
## <a name="ipropertybag-ipersistpropertybag"></a>IPropertyBag、IPersistPropertyBag  
 管道组件需要实现**IPersistPropertyBag**接收其配置信息。 此接口和**IPropertyBag**是标准的接口。 有关这些接口的详细信息，请参考 Microsoft .NET Framework 软件开发工具包 (SDK) 文档。  
  
## <a name="idisassemblercomponent"></a>IDisassemblerComponent  
 拆装组件是一种管道组件，它在输入端接收单个消息并在输出端生成零个或多个消息。 拆装组件用于将消息交换拆分成单个文档。 反汇编程序组件必须实现的方法**IDisassemblerComponent**要获取来自消息接口[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档以进行处理并传递反汇编回[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
|方法|Description|  
|------------|-----------------|  
|**反汇编**|执行传入文档的反汇编**pInMsg**。|  
|**GetNext**|从拆装器执行导致的消息集获取下一个消息。 返回**NULL**如果没有更多的消息。|  
  
 如果您在编写将支持可恢复交换处理的拆装器组件，则必须执行以下操作：  
  
1.  通过在 VirtualStream() 中包装输入流，使输入流可查找。  
  
2.  在 GetNext() 中，具有可确定何时消息出错的逻辑。 如果某一消息是错误的，则设置 BTS.MessageDestination = "SuspendQueue" 并在 GetNext() 中返回该消息。  
  
3.  如果消息是正确的，则设置 BTS.SuspendMessageOnRoutingFailure = True 并在 GetNext() 中返回该消息。  
  
## <a name="iassemblercomponent"></a>IAssemblerComponent  
 组装组件一种管道组件，它在输入端接收若干消息，在输出端生成一个消息。 组装组件用于将若干单独的文档收集到消息交换批中。  
  
> [!NOTE]
>  在此版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，未采用组装功能，因此，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 始终将一个文档传递到组件输入。  
  
 汇编程序组件实现**IAssemblerComponent**由调用的方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在运行时引擎。  
  
|方法|Description|  
|------------|-----------------|  
|**AddDocument**|将文档添加**pInMsg**到将包含在该交换的消息的列表。|  
|**将组合**|从以前方法所添加的消息生成交换。 返回指向已组装消息的指针。|  
  
## <a name="iprobemessage"></a>IProbeMessage  
 任何管道组件 （常规、 组装，或分解） 可以实现**IProbeMessage**是否需要探测功能的消息。 探测组件用于中具有的管道阶段**匹配**执行模式。 在此类阶段，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到组件时，会发送消息和**探测**方法检查以确定该组件是否识别的消息的格式的消息的开头。  
  
|方法|Description|  
|------------|-----------------|  
|**探测**|此方法采用**pInMsg**消息，并返回**True**如果识别此格式或**False**否则为。|  
  
## <a name="inameditem"></a>INamedItem  
 这是用于从托管代码和非托管代码访问文档架构的帮助程序接口。  
  
## <a name="inameditemlist"></a>INamedItemList  
 这是用于从托管代码和非托管代码访问文档架构的帮助程序接口。  
  
## <a name="idocumentspec"></a>IDocumentSpec  
 管道组件可以使用的方法**IDocumentSpec**接口以执行特定于文档的操作，例如，将内容属性移到上下文并返回，访问文档架构中，依次类推。  
  
|方法|Description|  
|------------|-----------------|  
|**DocType**|返回当前文档的类型。|  
|**DocSpecName**|返回当前文档的规范名称。|  
|**GetSchemaCollection**|返回当前文档的文档架构列表。|  
|**GetBodyPath**|将 XPath 返回到文档中正文部分开始的节点。|  
|**GetDistinguishedPropertyAnnotationEnumerator**|返回所有可分辨字段属性批注的字典枚举数。|  
|**GetPropertyAnnotationEnumerator**|返回所有属性批注的枚举数。|  
  
## <a name="icomponentui"></a>IComponentUI  
 管道组件必须实现此接口，以便用于管道设计器环境。  
  
|方法|Description|  
|------------|-----------------|  
|**图标**|提供与此组件关联的图标。|  
|**验证**|管道设计器在管道编译前调用此方法，以便确认所有配置属性均正确设置。|  
  
 **图标**属性返回**IntPtr**。 下面的 C# 示例演示如何返回**IntPtr**。  
  
```csharp  
static   ResourceManager resManager = new ResourceManager("ResourceManager", Assembly.GetExecutingAssembly());  
...  
[Browsable(false)]  
public IntPtr Icon  
{  
   get  
   {  
      return ((Bitmap)resManager.GetObject("MyIcon")).GetHicon();  
   }  
}  
```  
  
 有关详细信息，请参阅**IComponentUI 接口 (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 
  
## <a name="see-also"></a>另请参阅  
 [开发自定义管道组件](../core/developing-custom-pipeline-components.md)   
 [CustomComponent （BizTalk Server 示例）](../core/customcomponent-biztalk-server-sample.md)