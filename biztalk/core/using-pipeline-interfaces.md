---
title: 使用管道接口 |Microsoft Docs
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
ms.openlocfilehash: a9d76df29720f33d8c7433bc34f9be239cfee0a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395395"
---
# <a name="using-pipeline-interfaces"></a>使用管道接口
管道组件是实现一组预定义的接口，以便与 BizTalk 消息引擎进行交互的.NET 或 COM 组件。 具体取决于组件的功能，必须实现不同的接口。 本主题介绍这些接口及其一些方法。  
  
> [!WARNING]
>  如果要构建使用 COM 的自定义管道组件，必须配置您的组件以使用多线程单元 (MTA) 模型。 如果不这样做，则组件的调用将失败具有 E_NOINTERFACE 错误。  
  
## <a name="ipipelinecontext"></a>IPipelineContext  
 所有管道组件可以都使用**IPipelineContext**方法来访问文档的所有特定于处理的接口。 **IPipelineContext**接口提供以下功能：  
  
-   允许组件检索环境管道和阶段设置。  
  
-   允许组件检索消息和消息工厂。 使用这些工厂，组件可以创建所需的组件的执行的各种对象。  
  
-   允许组件检索文档规范。 文档规范是 XSD 架构以及附加的批注。  
  
## <a name="ibasecomponent"></a>IBaseComponent  
 所有管道组件都需要实现此接口可提供有关组件的基本信息。  
  
## <a name="icomponent"></a>IComponent  
 所有管道组件除组装器和拆装器实现此接口可获取来自消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]引擎进行处理和传递处理的消息返回给引擎。  
  
 **执行。** 方法由引擎调用将传递给该组件的输入的消息并从组件中检索已处理的消息。  
  
## <a name="ipropertybag-ipersistpropertybag"></a>IPropertyBag、 IPersistPropertyBag  
 管道组件需要实现**IPersistPropertyBag**接收其配置信息。 此接口和**IPropertyBag**是标准接口。 有关这些接口的详细信息，请参阅 Microsoft.NET Framework 软件开发工具包 (SDK) 文档。  
  
## <a name="idisassemblercomponent"></a>IDisassemblerComponent  
 拆装组件是接收输入一条消息，并生成输出的零个或多个消息的管道组件。 拆装组件用于拆分成单个文档的消息交换。 拆装器组件必须实现的方法**IDisassemblerComponent**接口，用于获取来自消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进行处理，并将传递已拆装的文档返回到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
|方法|Description|  
|------------|-----------------|  
|**反汇编**|执行传入文档的拆装**pInMsg**。|  
|**GetNext**|获取下一条消息由拆装器执行导致的消息集。 返回**NULL**如果没有更多的消息。|  
  
 如果你正在编写将支持可恢复交换处理的拆装器组件，必须执行以下操作：  
  
1.  通过将它们放置在 virtualstream （），使输入的流可查找。  
  
2.  在 getnext （），具有逻辑来确定消息无效。 如果消息是错误的则设置 BTS。MessageDestination ="SuspendQueue"并在 getnext （） 中返回该消息。  
  
3.  如果消息是很好，设置 BTS。SuspendMessageOnRoutingFailure = True，并在 getnext （） 中返回消息。  
  
## <a name="iassemblercomponent"></a>IAssemblerComponent  
 组装组件是接收输入的多条消息，并生成输出一条消息的管道组件。 组装组件用于到消息交换批中收集的各个文档。  
  
> [!NOTE]
>  在此版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，未采用组装功能，因此[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]始终将一个文档传递到组件输入。  
  
 组装器组件实现**IAssemblerComponent**方法调用的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在运行时引擎。  
  
|方法|Description|  
|------------|-----------------|  
|**AddDocument**|将该文档添加**pInMsg**到将交换中包含的消息的列表。|  
|**组合**|生成从上一个方法已添加的消息交换。 返回一个指向已组装消息。|  
  
## <a name="iprobemessage"></a>IProbeMessage  
 任何管道组件 （一般、 组装或拆装） 都可以实现**IProbeMessage**如果它要求消息探测功能。 探测组件用于具有的管道阶段**第一个匹配**执行模式。 在此类阶段[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将消息提供给组件，并**探测**方法将检查消息以确定组件是否识别消息格式的开始。  
  
|方法|Description|  
|------------|-----------------|  
|**Probe**|此方法采用**pInMsg**消息，并返回**True**如果识别格式或**False**否则为。|  
  
## <a name="inameditem"></a>INamedItem  
 这是一个帮助器界面，用于从托管和非托管代码访问文档架构。  
  
## <a name="inameditemlist"></a>INamedItemList  
 这是一个帮助器界面，用于从托管和非托管代码访问文档架构。  
  
## <a name="idocumentspec"></a>IDocumentSpec  
 管道组件可以使用的方法**IDocumentSpec**接口来执行特定于文档的操作，例如，将内容属性移到上下文并返回，访问文档架构中，依次类推。  
  
|方法|Description|  
|------------|-----------------|  
|**DocType**|返回当前文档的类型。|  
|**DocSpecName**|返回当前文档的规范名称。|  
|**GetSchemaCollection**|返回当前文档的文档架构的列表。|  
|**GetBodyPath**|正文部分开始的位置将 XPath 返回到文档中的节点。|  
|**GetDistinguishedPropertyAnnotationEnumerator**|返回所有可分辨的字段属性批注的字典枚举器。|  
|**GetPropertyAnnotationEnumerator**|返回所有属性批注的枚举器。|  
  
## <a name="icomponentui"></a>IComponentUI  
 管道组件必须实现此接口，以便用于在管道设计器环境。  
  
|方法|Description|  
|------------|-----------------|  
|**图标**|提供了与此组件关联的图标。|  
|**验证**|管道设计器之前调用此方法以验证正确设置所有配置属性的管道编译。|  
  
 **图标**属性将返回**IntPtr**。 以下C#的示例演示如何返回**IntPtr**。  
  
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
  
## <a name="see-also"></a>请参阅  
 [开发自定义管道组件](../core/developing-custom-pipeline-components.md)   
 [CustomComponent（BizTalk Server 示例）](../core/customcomponent-biztalk-server-sample.md)