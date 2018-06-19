---
title: 管道组件中的架构解析 |Microsoft 文档
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
ms.openlocfilehash: 897c25ecb64a3038a6992b9c4caf927ba3e2d805
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972955"
---
# <a name="schema-resolution-in-pipeline-components"></a><span data-ttu-id="4f404-102">管道组件中的架构解析</span><span class="sxs-lookup"><span data-stu-id="4f404-102">Schema Resolution in Pipeline Components</span></span>
<span data-ttu-id="4f404-103">管道拆装器和组装器组件使用 XSD 架构来处理消息。</span><span class="sxs-lookup"><span data-stu-id="4f404-103">Pipeline disassembler and assembler components use XSD schemas to process messages.</span></span> <span data-ttu-id="4f404-104">该架构包含升级属性、可分辨字段、平面文件消息批注和 XML 信封批注的列表等信息。</span><span class="sxs-lookup"><span data-stu-id="4f404-104">The schemas contain information such as the list of promoted properties, distinguished fields, annotations for flat file messages, and annotations for XML envelopes.</span></span>  
  
 <span data-ttu-id="4f404-105">标准拆装器和组装器组件支持使用架构类型名称和消息类型来检索部署架构。</span><span class="sxs-lookup"><span data-stu-id="4f404-105">Standard disassembler and assembler components support retrieval of deployed schemas by using the schema type name and message type.</span></span> <span data-ttu-id="4f404-106">有些组件同时使用架构类型名称和消息类型进行检索，而另一些组件（例如，平面文件拆装器）则通过架构类型进行检索。</span><span class="sxs-lookup"><span data-stu-id="4f404-106">Some components retrieve by using both the schema type name and the message type, while others (for example, the Flat File Disassembler) retrieve only by the schema type.</span></span>  
  
 <span data-ttu-id="4f404-107">接收 XML 消息的管道组件通过检查消息根元素和命名空间来确定消息类型。</span><span class="sxs-lookup"><span data-stu-id="4f404-107">Pipeline components that receive XML messages determine the message type by examining the message root element and namespace.</span></span> <span data-ttu-id="4f404-108">例如，以下 XML 的消息类型为“http://MyDocument.org#MyDocument”。</span><span class="sxs-lookup"><span data-stu-id="4f404-108">For example, the message type for the following XML is "http://MyDocument.org#MyDocument".</span></span>  
  
```  
<ns0:MyDocument xmlns:ns0="http://MyDocument.org">  
  
</ns0:MyDocument>  
```  
  
 <span data-ttu-id="4f404-109">如果架构不具有为其定义的命名空间，该消息类型是"\<**rootNode**\>"。</span><span class="sxs-lookup"><span data-stu-id="4f404-109">If a schema does not have a namespace defined for it, the message type is "\<**rootNode**\>".</span></span> <span data-ttu-id="4f404-110">例如，如果前面的示例 XML 没有命名空间，则消息类型将为“MyDocument”。</span><span class="sxs-lookup"><span data-stu-id="4f404-110">For example, if the preceding example XML had no namespace, the message type would be "MyDocument".</span></span>  
  
 <span data-ttu-id="4f404-111">标准管道组件使用此消息类型从数据库中检索相应的架构。</span><span class="sxs-lookup"><span data-stu-id="4f404-111">Standard pipeline components use the message type to retrieve the appropriate schema from the database.</span></span> <span data-ttu-id="4f404-112">默认 XML 接收和发送管道始终使用在运行时从消息 XML 内容中动态发现的消息类型来确定要加载的架构（除非管道组件设置为允许无法识别的消息）。</span><span class="sxs-lookup"><span data-stu-id="4f404-112">Default XML receive and send pipelines always determine which schema to load by using the message type dynamically discovered at runtime from the message XML content (unless the pipeline component is set to allow unrecognized messages).</span></span> <span data-ttu-id="4f404-113">XML 拆装器可以通过使用此机制来删除消息信封；但是，如果不知道要使用的信封架构，XML 拆装器无法为传出消息创建信封。</span><span class="sxs-lookup"><span data-stu-id="4f404-113">The XML Disassembler can remove the message envelope by using this mechanism; however, the XML Assembler cannot create an envelope for an outgoing message without knowing what envelope schema to use.</span></span>  
  
 <span data-ttu-id="4f404-114">在管道设计器中，可以在 XML 组装器的配置属性中指定信封架构。</span><span class="sxs-lookup"><span data-stu-id="4f404-114">You specify the envelope schema in the configuration properties for the XML Assembler from within the pipeline designer.</span></span>  
  
## <a name="how-schemas-are-resolved"></a><span data-ttu-id="4f404-115">架构的解析方式</span><span class="sxs-lookup"><span data-stu-id="4f404-115">How Schemas Are Resolved</span></span>  
 <span data-ttu-id="4f404-116">假设您没有在 XmlDisassembler 中直接指定架构，则架构将以下列方式进行解析：</span><span class="sxs-lookup"><span data-stu-id="4f404-116">Assuming you are not specifying the schema directly in the XmlDisassembler, schemas will be resolved in the following manner:</span></span>  
  
1.  <span data-ttu-id="4f404-117">首先，系统使用根节点名称和命名空间（例如 http://MyNamespace#MyRoot）对已部署架构进行非限定搜索。</span><span class="sxs-lookup"><span data-stu-id="4f404-117">First, an unqualified search on the deployed schemas is made using the root node name and namespace (for example, http://MyNamespace#MyRoot).</span></span> <span data-ttu-id="4f404-118">如果找到唯一的匹配架构，则对该架构进行解析。</span><span class="sxs-lookup"><span data-stu-id="4f404-118">If a unique match is found the schema is resolved.</span></span> <span data-ttu-id="4f404-119">如果找到仅版本号不同的多个匹配架构，并且只有一个匹配架构是活动的，则使用该版本的架构，并对其进行解析。</span><span class="sxs-lookup"><span data-stu-id="4f404-119">If multiple matches are found and differ only by version number and only one is active, that version is used and the schema is resolved.</span></span> <span data-ttu-id="4f404-120">如果同一架构在多个应用程序中处于活动状态，则将找到多个活动架构，在这种情况下，将执行下面的步骤 2 继续进行搜索。</span><span class="sxs-lookup"><span data-stu-id="4f404-120">If the same schema is active in multiple applications, multiple active schemas will be found and the search will continue with step 2 below.</span></span>  
  
2.  <span data-ttu-id="4f404-121">如果有多个步骤 1 的匹配项不能解决，搜索是由管道执行中的程序集限定的。</span><span class="sxs-lookup"><span data-stu-id="4f404-121">If there are multiple matches that step 1 cannot resolve, the search is qualified by the assembly the pipeline is executing in.</span></span> <span data-ttu-id="4f404-122">如果在同一程序集中中找到唯一架构管道执行在中，则架构处于已解决状态。</span><span class="sxs-lookup"><span data-stu-id="4f404-122">If a unique schema is found within the same assembly the pipeline is executing in, then the schema is resolved.</span></span>  
  
3.  <span data-ttu-id="4f404-123">如果仍没有匹配架构，则发布服务器将用于解析架构。</span><span class="sxs-lookup"><span data-stu-id="4f404-123">If there are still no matches, then the publisher is used to resolve the schema.</span></span> <span data-ttu-id="4f404-124">通过根节点、命名空间和公钥标记来缩小搜索范围。</span><span class="sxs-lookup"><span data-stu-id="4f404-124">The search is narrowed by using the root node, namespace, and public key token.</span></span> <span data-ttu-id="4f404-125">如果使用这种搜索找到了唯一架构，则此架构将被解析。</span><span class="sxs-lookup"><span data-stu-id="4f404-125">If a unique schema is found using this search, the schema is resolved.</span></span>  
  
4.  <span data-ttu-id="4f404-126">架构无法解析。</span><span class="sxs-lookup"><span data-stu-id="4f404-126">Schema cannot be resolved.</span></span> <span data-ttu-id="4f404-127">此时将返回一个错误，通知您找不到唯一架构。</span><span class="sxs-lookup"><span data-stu-id="4f404-127">An error is returned noting that no unique schema can be found.</span></span>  
  
 <span data-ttu-id="4f404-128">其他注意事项，包括对架构解析的 SQL Server 排序规则和区分大小写的影响，请参阅[Namespace 管理](../core/namespace-management.md)。</span><span class="sxs-lookup"><span data-stu-id="4f404-128">For other considerations including the effect of SQL Server collation and case-sensitivity on schema resolution, see [Namespace Management](../core/namespace-management.md).</span></span>  
  
 <span data-ttu-id="4f404-129">若要在 XML 组装器中创建信封或在平面文件组装器中创建头部和尾部，可执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="4f404-129">To create an envelope in the XML Assembler or a header and trailer in the Flat File Assembler, you may do one of the following:</span></span>  
  
-   <span data-ttu-id="4f404-130">创建一个自定义发送管道，并在 XML 组装器的配置属性中指定信封的架构。</span><span class="sxs-lookup"><span data-stu-id="4f404-130">Create a custom send pipeline and specify the schemas for the envelope in the configuration properties for the XML Assembler.</span></span> <span data-ttu-id="4f404-131">此操作在管道设计器中完成。</span><span class="sxs-lookup"><span data-stu-id="4f404-131">This is done from within the pipeline designer.</span></span>  
  
-   <span data-ttu-id="4f404-132">在 BizTalk Server 管理控制台中，为发送端口的发送管道属性指定 XMLTransmit。</span><span class="sxs-lookup"><span data-stu-id="4f404-132">In the BizTalk Server Administration console specify XMLTransmit for the Send pipeline property on a send port.</span></span> <span data-ttu-id="4f404-133">请单击省略号以配置管道属性，并在 EnvelopeDocSpecNames 属性中指定信封的架构。</span><span class="sxs-lookup"><span data-stu-id="4f404-133">Click the ellipsis to configure the pipeline properties and specify the schema for the envelope in the EnvelopeDocSpecNames property.</span></span>  
  
 <span data-ttu-id="4f404-134">如果数据库中有意或无意地部署了同一架构的多个版本（例如，采用并行部署，或者多个方案不具有唯一的消息类型），则按消息类型来解析架构可能无法工作。</span><span class="sxs-lookup"><span data-stu-id="4f404-134">Schema resolution by message type may not work if several versions of the same schema are intentionally or accidentally deployed in the database (for example, in a side-by-side deployment or if multiple scenarios do not have unique message types).</span></span> <span data-ttu-id="4f404-135">如果按消息类型解析架构失败，则会向事件日志中添加“架构不明确”错误。</span><span class="sxs-lookup"><span data-stu-id="4f404-135">If schema resolution by message type fails, a "schema ambiguity" error is added to the event log.</span></span> <span data-ttu-id="4f404-136">若要确保成功地按消息类型解析架构，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="4f404-136">To ensure that schema resolution by message type succeeds, do one of the following:</span></span>  
  
-   <span data-ttu-id="4f404-137">在与自定义管道相同的 BizTalk 项目中定义架构。</span><span class="sxs-lookup"><span data-stu-id="4f404-137">Define the schemas in the same BizTalk project as your custom pipeline.</span></span>  
  
-   <span data-ttu-id="4f404-138">使用与包含管道的程序集相同的密钥对包含架构的程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="4f404-138">Sign the assembly with the schemas with the same key as the assembly containing the pipelines.</span></span>  
  
-   <span data-ttu-id="4f404-139">在管道组件中显式指定架构（消息类型名称在 BizTalk 管理数据库中应是唯一的）。</span><span class="sxs-lookup"><span data-stu-id="4f404-139">Explicitly specify schemas in pipeline components (message type names should be unique across the BizTalk Management database).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4f404-140">如果同一程序集中的架构共享消息类型，则由于模糊解析的限制，不得在同一管道组件程序集中包括这些架构；而只能引用管道组件程序集外部的架构。</span><span class="sxs-lookup"><span data-stu-id="4f404-140">When schemas in the same assembly share a message type, you must not include the schemas in the same pipeline component assembly due to the limitations of ambiguity resolution; instead, reference schemas that are external to the pipeline component assembly.</span></span> <span data-ttu-id="4f404-141">如果架构和管道组件位于同一程序集中，即使在自定义管道的管道组件中显式指定了架构类型名称，也无法进行模糊解析。</span><span class="sxs-lookup"><span data-stu-id="4f404-141">Ambiguity resolution does not work when schemas and pipeline components are in the same assembly, even if schema type names are explicitly specified in pipeline components in custom pipelines.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f404-142">使用的自定义管道组件**IPipelineContext**以获取已部署的架构应仅当架构类型名称未指定组件在运行时，获取由架构类型的架构并获取消息类型仅通过架构如果运行组件时，架构类型信息不可用。</span><span class="sxs-lookup"><span data-stu-id="4f404-142">Custom pipeline components that use **IPipelineContext** to obtain deployed schemas should obtain schemas by schema type only if the schema type name is not specified for the component at run time, and obtain schemas by message type only if the schema type information is not available when the component is run.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f404-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f404-143">See Also</span></span>  
 [<span data-ttu-id="4f404-144">管道组件</span><span class="sxs-lookup"><span data-stu-id="4f404-144">Pipeline Components</span></span>](../core/pipeline-components.md)