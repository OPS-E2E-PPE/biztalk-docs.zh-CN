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
ms.openlocfilehash: 9eebb3e1cb4c33d49bacb1353ada164932dae003
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396915"
---
# <a name="schema-resolution-in-pipeline-components"></a>管道组件中的架构解析
管道拆装器和组装器组件使用 XSD 架构来处理消息。 该架构包含升级的属性、 可分辨的字段、 平面文件消息批注和 XML 信封批注列表等信息。  
  
 标准拆装器和组装器组件使用的架构类型名称和消息类型支持检索已部署的架构。 某些组件使用的架构类型名称和消息类型，而其他人 （例如，平面文件反汇编程序） 检索只能由架构类型检索。  
  
 接收 XML 消息的管道组件通过检查消息根元素和命名空间来确定消息类型。 例如，下面的 XML 的消息类型是"<http://MyDocument.org#MyDocument>"。  
  
```  
<ns0:MyDocument xmlns:ns0="http://MyDocument.org">  
  
</ns0:MyDocument>  
```  
  
 如果架构不具有为其定义的命名空间，则消息类型是"\<**rootNode**\>"。 例如，如果前面的示例 XML 没有命名空间，消息类型将为"MyDocument"。  
  
 标准管道组件使用的消息类型来从数据库中检索相应的架构。 默认 XML 接收和发送管道始终确定要使用的消息类型动态加载的架构在运行时发现从消息 XML 内容 （除非管道组件设置为允许无法识别的消息）。 XML 拆装器可以通过使用此机制; 中删除消息信封但是，XML 组装器无法创建无需知道要使用的信封架构为传出消息信封。  
  
 从在 XML 组装器管道设计器中，可以配置属性中指定信封架构。  
  
## <a name="how-schemas-are-resolved"></a>如何解决架构  
 假设并不在 XmlDisassembler 中直接指定架构，将按以下方式解析架构：  
  
1. 首先，使用的根节点名称和命名空间进行非限定的搜索上所部署的架构 (例如， http://MyNamespace#MyRoot)。 如果找到唯一匹配的架构会得到解决。 如果发现了多个匹配项，并且差异仅在于版本号，并且只有一个处于活动状态，将使用该版本和架构将被解析。 如果多个应用程序中处于活动状态相同的架构，将找到多个活动架构，并搜索将使用下面的步骤 2。  
  
2. 如果有多个匹配项的步骤 1 无法解析，搜索进行限定。 在执行管道的程序集。 如果在同一程序集中找到了唯一架构，在执行管道，则架构将被解析。  
  
3. 如果仍有没有匹配项，则发布服务器用于解析架构。 通过使用根节点、 命名空间和公钥标记缩小搜索范围。 如果使用此搜索找到了唯一架构，则架构将被解析。  
  
4. 无法解析架构。 注意不到唯一架构可在返回错误。  
  
   有关其他注意事项，包括对架构解析 SQL Server 排序规则和区分大小写的影响，请参阅[Namespace 管理](../core/namespace-management.md)。  
  
   若要在 XML 组装器或标头和尾部平面文件组装器中的创建一个信封，可能会执行下列任一操作：  
  
- 创建自定义发送管道和 XML 组装器的配置属性中指定信封的架构。 这是从管道设计器中。  
  
- 在 BizTalk Server 管理控制台为发送端口的发送管道属性中指定 XMLTransmit。 单击省略号以配置管道属性，并在 EnvelopeDocSpecNames 属性中指定信封的架构。  
  
  如果同一架构的多个版本有意或无意地部署 （适用于示例中的，通过并行部署中或多个方案，如果不具有唯一的消息类型） 在数据库中，按消息类型解析架构可能无法工作。 如果按消息类型解析架构失败，"架构不明确"错误添加到事件日志。 若要确保按消息类型的架构解析成功，请执行以下操作：  
  
- 在自定义管道相同的 BizTalk 项目中定义架构。  
  
- 使用与包含管道的程序集相同的密钥进行签名的程序集使用的架构。  
  
- （消息类型名称应是唯一的整个 BizTalk 管理数据库） 的管道组件中显式指定架构。  
  
> [!IMPORTANT]
>  当在同一程序集中的架构共享消息类型时，您不能包含架构中由于模糊解析; 的限制相同管道组件程序集相反，引用外部的管道组件程序集的架构。 多义性解析无法正常工作时的架构和管道组件是在同一程序集中，即使在自定义管道的管道组件中显式指定架构类型名称。  
  
> [!NOTE]
>  使用自定义管道组件**IPipelineContext**获取部署的架构应仅当架构类型名称未指定组件在运行时，获取按架构类型并获取按消息类型仅架构如果该组件运行时的架构类型信息不可用。  
  
## <a name="see-also"></a>请参阅  
 [管道组件](../core/pipeline-components.md)