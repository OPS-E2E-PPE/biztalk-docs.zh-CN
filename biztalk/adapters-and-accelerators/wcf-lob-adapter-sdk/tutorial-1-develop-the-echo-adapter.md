---
title: "教程 1： 开发 Echo 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ffb0df3c-cd07-4bcf-af69-971065081fd6
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 484452dc4ee624f4fa41e9387098f6f792c1de28
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-1-develop-the-echo-adapter"></a>教程 1： 开发 Echo 适配器
在本教程中，你将开发功能的适配器使用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 适配器模拟虚构的业务线系统，用于说明的许多 WCF LOB 适配器 SDK 包括关键功能的操作：  
  
-   同步入站  
  
-   同步出站  
  
-   元数据浏览  
  
-   元数据搜索  
  
-   元数据解析  
  
 本部分包含 echo 适配器支持的各种功能。 它们是消息交换、 操作元数据、 连接属性和适配器属性。  
  
## <a name="message-exchange-patterns"></a>消息交换模式  
 Echo 适配器支持以下两个消息交换模式：  
  
-   同步的出站，即，使用客户端将通过该适配器 WCF 请求消息发送到目标系统中，并且将等待接收来自通过适配器的目标系统的 WCF 响应消息。 这是适配器的最常见的消息交换模式。 若要支持同步的出站，实现`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`接口。  
  
-   也就是说，同步入站数据或从目标系统通过适配器的事件使用的客户端侦听。 若要支持同步入站，实现`Microsoft.ServiceModel.Channels.Common.IInboundHandler`接口。  
  
 有关消息交换模式的详细信息，请参阅[体系结构概述](architecture-overview-of-the-wcf-lob-adapter-sdk.md)。  
  
> [!NOTE]
>  [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]显示为在 UI 中的数据流的消息交换模式。  
  
## <a name="metadata-support"></a>元数据支持  
 Echo 适配器支持元数据浏览、 搜索和解析功能。 通常情况下，浏览和搜索从 LOB 系统检索操作。 为 echo 适配器 LOB 系统是一组预定义的操作，如下所示：  
  
```  
EchoMainCategory  
        Echo/EchoStrings  
        Echo/EchoGreetings  
        Echo/EchoCustomGreetingFromFile  
        Echo/OnReceiveEcho  
```  
  
 以下是每个操作的定义：  
  
|**名称**|**操作定义**|**Description**|**方向**|  
|--------------|------------------------------|---------------------|-------------------|  
|EchoMainCategory|类别|对操作进行分类。|N/A|  
|Echo/EchoStrings|字符串 [] EchoStrings(string data)|将传入的字符串回显到调用的客户端按指定的次数。|出站|  
|Echo/EchoGreetings|问候语 [] EchoGreetings(Greeting greeting)|回显传入问候语对象指定大量的时间，以调用的客户端。|出站|  
|Echo/EchoCustomGreetingFromFile|CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath)|通过从文件读取其实例回显问候语对象。 从预定义的 XSD 文件中获取问候语对象的元数据。|出站|  
|Echo/OnReceiveEcho|void OnReceiveEcho （Uri 路径，长时间内容）|回显的位置和长度的指定文件夹中删除的文件。|入站|  
  
## <a name="adapter-properties"></a>适配器属性  
 适配器公开以下适配器属性。  
  
|**名称**|**类别**|**数据类型**|**Description**|  
|--------------|------------------|-------------------|---------------------|  
|Count|杂项|System.Int32|用于回显的输入指定次数的调用的客户端。<br /><br /> 默认值 = 5|  
|EnableConnectionPooling|杂项|System.Boolean|用于启用或禁用连接池的适配器。<br /><br /> 默认值 = true，这意味着，运行时引擎中启用连接池[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。|  
|InboundFileFilter|入站|System.String|用于仅入站的方案和 FileSystemWatcher 用于监视扩展的文件。<br /><br /> 默认值 = *.txt|  
|InboundFileSystemWatcherFolder|入站|System.String|用于设置文件为 FileSystemWatcher 引发到适配器的通知的放置位置的文件夹。<br /><br /> 默认值 = c:\inbound\watcher。|  
  
## <a name="connection-properties"></a>连接属性  
 Echo 适配器公开以下连接属性。  
  
|**名称**|**数据类型**|**Description**|  
|--------------|-------------------|---------------------|  
|应用程序|System.String|LOB 系统中的应用程序名称。 此属性是用于说明目的。 Echo 适配器不涉及任何 LOB 系统。<br /><br /> 默认值 = lobapplication|  
|EnableAuthentication|System.Boolean|为 true 时，该适配器将需要在用户名字段中的客户端凭据值。<br /><br /> 默认值 = false|  
|Hostname|System.String|服务器名称的 LOB 系统的驻留位置。 此属性是用于说明目的。 Echo 适配器不涉及任何 LOB 系统。<br /><br /> 默认值 = lobhostname|  
  
## <a name="interface-implementation"></a>接口实现  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]定义的类和接口必须实现以支持特定功能的适配器的集合。 下表描述这些类和接口、 及其说明，以及何时实现它们。  
  
|**类/接口**|**何时实现**|**Description**|  
|--------------------------|---------------------------|---------------------|  
|Microsoft.ServiceModel.Channels.Common.IConnection|如果你需要定义目标系统的连接。|定义连接到目标系统。|  
|Microsoft.ServiceModel.Channels.Common.IConnectionFactory|如果你需要创建到目标系统的连接。|创建连接到目标系统。|  
|Microsoft.ServiceModel.Channels.Common.ConnectionUri|如果你需要管理连接 Uri。<br /><br /> 如果你需要对其进行分类中的连接属性[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]工具。|管理目标系统的连接 Uri。|  
|Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler|你的适配器必须支持元数据解析功能。|解析操作和类型的元数据。|  
|Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler|如果你的适配器支持元数据搜索功能。|搜索目标系统中的操作。|  
|Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler|你的适配器必须支持浏览功能|浏览目标系统中的操作。|  
|Microsoft.ServiceModel.Channels.Common.IOutboundHandler|如果你的适配器通常需要支持出站的功能。|将传入的 WCF 请求消息转换成目标系统消息，调用目标系统的特定函数，然后将响应转换为传出的 WCF 响应消息。|  
|Microsoft.ServiceModel.Channels.Common.IInboundHandler|如果你的适配器支持入站的功能。|侦听数据和/或从目标系统的事件。|  
  
 若要简化适配器开发过程，使用[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]生成你的适配器项目，这将创建一组的适配器功能定制的派生类。  
  
 若要自定义的适配器和连接的属性，通过[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]工具，来修改以下文件由生成[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]。  
  
-   {Projectname}BindingElement.cs  
  
-   {Projectname}BindingElementExtensionElement.cs  
  
-   {Projectname}ConnectionUri.cs  
  
 有关如何执行此操作的详细信息，请参阅[步骤 2： 对适配器和连接属性进行分类](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)。  
  
## <a name="see-also"></a>另请参阅  
 [若要了解 WCF LOB 适配器 SDK 的教程](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorials-to-learn-the-wcf-lob-adapter-sdk.md)