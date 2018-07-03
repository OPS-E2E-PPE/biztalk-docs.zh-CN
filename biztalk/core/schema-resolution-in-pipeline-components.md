---
title: 管道组件中的架构解析 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, schema resolution
- pipeline components, schema resolution
- schemas, pipeline components
ms.assetid: 35a79a6f-788b-4ca1-8483-36dcba5ae580
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c269ff3a7a5d973356754a222699c93179c90362
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984782"
---
# <a name="schema-resolution-in-pipeline-components"></a>管道组件中的架构解析
管道拆装器和组装器组件使用 XSD 架构来处理消息。 该架构包含升级属性、可分辨字段、平面文件消息批注和 XML 信封批注的列表等信息。  
  
 标准拆装器和组装器组件支持使用架构类型名称和消息类型来检索部署架构。 有些组件同时使用架构类型名称和消息类型进行检索，而另一些组件（例如，平面文件拆装器）则通过架构类型进行检索。  
  
 接收 XML 消息的管道组件通过检查消息根元素和命名空间来确定消息类型。 例如，下面的 XML 的消息类型是"<http://MyDocument.org#MyDocument>"。  
  
```  
<ns0:MyDocument xmlns:ns0="http://MyDocument.org">  
  
</ns0:MyDocument>  
```  
  
 如果架构不具有为其定义的命名空间，则消息类型是"\<**rootNode**\>"。 例如，如果前面的示例 XML 没有命名空间，则消息类型将为“MyDocument”。  
  
 标准管道组件使用此消息类型从数据库中检索相应的架构。 默认 XML 接收和发送管道始终使用在运行时从消息 XML 内容中动态发现的消息类型来确定要加载的架构（除非管道组件设置为允许无法识别的消息）。 XML 拆装器可以通过使用此机制来删除消息信封；但是，如果不知道要使用的信封架构，XML 拆装器无法为传出消息创建信封。  
  
 在管道设计器中，可以在 XML 组装器的配置属性中指定信封架构。  
  
## <a name="how-schemas-are-resolved"></a>架构的解析方式  
 假设您没有在 XmlDisassembler 中直接指定架构，则架构将以下列方式进行解析：  
  
1. 首先，使用的根节点名称和命名空间进行非限定的搜索上所部署的架构 (例如， http://MyNamespace#MyRoot)。 如果找到唯一的匹配架构，则对该架构进行解析。 如果找到仅版本号不同的多个匹配架构，并且只有一个匹配架构是活动的，则使用该版本的架构，并对其进行解析。 如果同一架构在多个应用程序中处于活动状态，则将找到多个活动架构，在这种情况下，将执行下面的步骤 2 继续进行搜索。  
  
2. 如果有多个匹配项的步骤 1 无法解析，搜索进行限定。 在执行管道的程序集。 如果在同一程序集中找到了唯一架构，在执行管道，则架构将被解析。  
  
3. 如果仍没有匹配架构，则发布服务器将用于解析架构。 通过根节点、命名空间和公钥标记来缩小搜索范围。 如果使用这种搜索找到了唯一架构，则此架构将被解析。  
  
4. 架构无法解析。 此时将返回一个错误，通知您找不到唯一架构。  
  
   有关其他注意事项，包括对架构解析 SQL Server 排序规则和区分大小写的影响，请参阅[Namespace 管理](../core/namespace-management.md)。  
  
   若要在 XML 组装器中创建信封或在平面文件组装器中创建头部和尾部，可执行以下操作之一：  
  
- 创建一个自定义发送管道，并在 XML 组装器的配置属性中指定信封的架构。 此操作在管道设计器中完成。  
  
- 在 BizTalk Server 管理控制台中，为发送端口的发送管道属性指定 XMLTransmit。 请单击省略号以配置管道属性，并在 EnvelopeDocSpecNames 属性中指定信封的架构。  
  
  如果数据库中有意或无意地部署了同一架构的多个版本（例如，采用并行部署，或者多个方案不具有唯一的消息类型），则按消息类型来解析架构可能无法工作。 如果按消息类型解析架构失败，则会向事件日志中添加“架构不明确”错误。 若要确保成功地按消息类型解析架构，请执行以下操作之一：  
  
- 在与自定义管道相同的 BizTalk 项目中定义架构。  
  
- 使用与包含管道的程序集相同的密钥对包含架构的程序集进行签名。  
  
- 在管道组件中显式指定架构（消息类型名称在 BizTalk 管理数据库中应是唯一的）。  
  
> [!IMPORTANT]
>  如果同一程序集中的架构共享消息类型，则由于模糊解析的限制，不得在同一管道组件程序集中包括这些架构；而只能引用管道组件程序集外部的架构。 如果架构和管道组件位于同一程序集中，即使在自定义管道的管道组件中显式指定了架构类型名称，也无法进行模糊解析。  
  
> [!NOTE]
>  使用自定义管道组件**IPipelineContext**获取部署的架构应仅当架构类型名称未指定组件在运行时，获取按架构类型并获取按消息类型仅架构如果该组件运行时的架构类型信息不可用。  
  
## <a name="see-also"></a>请参阅  
 [管道组件](../core/pipeline-components.md)