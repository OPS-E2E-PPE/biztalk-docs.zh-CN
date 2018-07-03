---
title: 如何部署管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IReceiveLocation interface
- IReceivePort interface
- deploying, pipelines
- pipelines, deploying
- pipelines, compiling
- SendPipelineData method
- pipelines, configuring
- pipelines, code sample
- ReceivePipelineData property
- Validate method
- ISendPort interface
ms.assetid: 7a56c753-a0d4-48ed-a61d-e454bc9cd507
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23028db559864368bb091fb15abfca7e49d73808
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986318"
---
# <a name="how-to-deploy-pipelines"></a><span data-ttu-id="0bfc9-102">如何部署管道</span><span class="sxs-lookup"><span data-stu-id="0bfc9-102">How to Deploy Pipelines</span></span>
<span data-ttu-id="0bfc9-103">管道是在解决方案的生成和部署过程中进行编译和部署的。</span><span class="sxs-lookup"><span data-stu-id="0bfc9-103">Pipelines are compiled and deployed as part of the solution build and deploy process.</span></span> <span data-ttu-id="0bfc9-104">编译器将调用**验证**方法在每个组件，从而使组件返回编译错误的配置信息。</span><span class="sxs-lookup"><span data-stu-id="0bfc9-104">The compiler calls the **Validate** method on each component, allowing the components to return compile errors on the configured information.</span></span> <span data-ttu-id="0bfc9-105">在生成管道后，管道将在部署解决方案时与解决方案的其余部分部署在同一程序集中。</span><span class="sxs-lookup"><span data-stu-id="0bfc9-105">After building, the pipeline is deployed in the same assembly with the rest of the solution when the solution is deployed.</span></span>  
  
## <a name="per-instance-pipeline-configuration"></a><span data-ttu-id="0bfc9-106">基于实例的管道配置</span><span class="sxs-lookup"><span data-stu-id="0bfc9-106">Per-instance pipeline configuration</span></span>  
 <span data-ttu-id="0bfc9-107">基于实例的管道配置用于在发送端口级别或接收位置级别修改所部署管道内的管道组件的属性。</span><span class="sxs-lookup"><span data-stu-id="0bfc9-107">Per-instance pipeline configuration is used to modify properties of pipeline components within a deployed pipeline at the send port or receive location level.</span></span> <span data-ttu-id="0bfc9-108">基于实例的管道配置在只需要按实例修改少数管道组件属性时非常有用。</span><span class="sxs-lookup"><span data-stu-id="0bfc9-108">Per-instance pipeline configuration is useful when only a few pipeline component properties need to be modified per instance.</span></span> <span data-ttu-id="0bfc9-109">例如，如果您需要在多个接收位置支持不同的消息类型并且只用一个自定义 XML 接收管道，则可以使用基于实例的管道配置部署该管道并覆盖默认配置（包括指定不同的信封和文档规范名称）。</span><span class="sxs-lookup"><span data-stu-id="0bfc9-109">For example, if you need to support different message types in multiple receive locations and have a single custom XML receive pipeline, per-instance pipeline configuration enables you to deploy the pipeline and override the default configuration (including specifying different envelope and document spec names).</span></span> <span data-ttu-id="0bfc9-110">BizTalk 管理控制台支持此机制，还可以通过 BizTalk 浏览器对象模型编程来支持此机制。</span><span class="sxs-lookup"><span data-stu-id="0bfc9-110">This mechanism is supported in the BizTalk Management console and programmatically through the Explorer object model.</span></span>  
  
### <a name="per-instance-pipeline-configuration-using-biztalk-administration-console"></a><span data-ttu-id="0bfc9-111">使用 BizTalk 管理控制台进行基于实例的管道配置</span><span class="sxs-lookup"><span data-stu-id="0bfc9-111">Per-Instance Pipeline Configuration Using BizTalk Administration console</span></span>  
 <span data-ttu-id="0bfc9-112">您可以使用 BizTalk 管理控制台执行基于实例的管道配置。</span><span class="sxs-lookup"><span data-stu-id="0bfc9-112">You can perform per-instance pipeline configuration using the BizTalk Management console.</span></span> <span data-ttu-id="0bfc9-113">部署完自定义管道后，创建所需数目的接收位置或发送端口。</span><span class="sxs-lookup"><span data-stu-id="0bfc9-113">Once you have deployed your custom pipeline, create as many receive locations or send ports as required.</span></span> <span data-ttu-id="0bfc9-114">然后，对于每个接收位置或发送端口，通过“配置管道”对话框覆盖默认属性值。</span><span class="sxs-lookup"><span data-stu-id="0bfc9-114">Then for each receive location or send port, override default property values through the Configure Pipeline dialog box.</span></span> <span data-ttu-id="0bfc9-115">例如，若要指定不同的文档架构，可输入的架构名称**EnvelopeDocSpecNames**属性。</span><span class="sxs-lookup"><span data-stu-id="0bfc9-115">For example, to specify a different document schema, enter a schema name for the **EnvelopeDocSpecNames** property.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="0bfc9-116">对在接收位置或发送端口中指定的配置值，不进行验证。</span><span class="sxs-lookup"><span data-stu-id="0bfc9-116">No validation of the configuration values specified in the receive location or send port will be performed.</span></span> <span data-ttu-id="0bfc9-117">如果配置不正确，消息在运行时将无法通过管道。</span><span class="sxs-lookup"><span data-stu-id="0bfc9-117">If the configuration is incorrect, messages will fail at runtime when passing through the pipeline.</span></span>  
  
### <a name="per-instance-pipeline-configuration-using-the-explorer-object-model"></a><span data-ttu-id="0bfc9-118">使用 BizTalk 浏览器对象模型进行基于实例的管道配置</span><span class="sxs-lookup"><span data-stu-id="0bfc9-118">Per-Instance Pipeline Configuration Using the Explorer Object Model</span></span>  
 <span data-ttu-id="0bfc9-119">在读取定义管道组件基于实例的配置的 XML 文件后，该文件中的属性将覆盖在管道文件中设置的属性。</span><span class="sxs-lookup"><span data-stu-id="0bfc9-119">When the XML file describing the per-instance configuration of the pipeline components is read, it overrides the properties set in the pipeline file.</span></span>  
  
 <span data-ttu-id="0bfc9-120">基于实例的管道配置是使用 BizTalk 浏览器对象模型进行设置的。</span><span class="sxs-lookup"><span data-stu-id="0bfc9-120">Per-instance pipeline configuration is set by using the BizTalk Explorer object model.</span></span> <span data-ttu-id="0bfc9-121">BizTalk 浏览器对象模型提供了**ReceivePipelineData**上的属性**IReceiveLocation**并**ISendPort**接口来设置的配置接收管道组件。</span><span class="sxs-lookup"><span data-stu-id="0bfc9-121">The BizTalk Explorer object model provides the **ReceivePipelineData** property on the **IReceiveLocation** and **ISendPort** interfaces for setting the configuration of receive pipeline components.</span></span> <span data-ttu-id="0bfc9-122">BizTalk 浏览器对象模型还提供了**SendPipelineData**方法**ireceiveport 接口**并**ISendPort**设置配置的发送接口管道组件。</span><span class="sxs-lookup"><span data-stu-id="0bfc9-122">The BizTalk Explorer object model also provides the **SendPipelineData** method on the **IReceivePort** and **ISendPort** interfaces for setting configuration of send pipeline components.</span></span>  
  
 <span data-ttu-id="0bfc9-123">基于实例的管道配置不支持以下操作：</span><span class="sxs-lookup"><span data-stu-id="0bfc9-123">Per-instance pipeline configuration does not support the following:</span></span>  
  
- <span data-ttu-id="0bfc9-124">重排管道内的阶段</span><span class="sxs-lookup"><span data-stu-id="0bfc9-124">Rearranging stages within the pipeline</span></span>  
  
- <span data-ttu-id="0bfc9-125">添加或删除阶段</span><span class="sxs-lookup"><span data-stu-id="0bfc9-125">Adding or removing stages</span></span>  
  
- <span data-ttu-id="0bfc9-126">重排阶段内的组件</span><span class="sxs-lookup"><span data-stu-id="0bfc9-126">Rearranging components within stages</span></span>  
  
- <span data-ttu-id="0bfc9-127">添加或删除组件</span><span class="sxs-lookup"><span data-stu-id="0bfc9-127">Adding or removing components</span></span>  
  
  <span data-ttu-id="0bfc9-128">只支持在管道组件的配置中进行的更改。</span><span class="sxs-lookup"><span data-stu-id="0bfc9-128">The only supported changes are in the configuration of pipeline components.</span></span> <span data-ttu-id="0bfc9-129">管道组件基于实例的配置将覆盖通用管道组件配置。</span><span class="sxs-lookup"><span data-stu-id="0bfc9-129">Per-instance configuration of a pipeline component overrides the common pipeline component configuration.</span></span> <span data-ttu-id="0bfc9-130">如果在基于实例的管道配置中未指定某个组件参数，则使用该参数的通用配置（与管道设计器中的配置一样）。</span><span class="sxs-lookup"><span data-stu-id="0bfc9-130">If a parameter of a component is not specified in per-instance pipeline configuration, the common configuration for that parameter (as configured in Pipeline Designer) is used.</span></span>  
  
  <span data-ttu-id="0bfc9-131">下面列出了一个基于实例配置数据的示例：</span><span class="sxs-lookup"><span data-stu-id="0bfc9-131">The following is an example of per-instance configuration data.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<Root xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
    <Stages>  
        <Stage CategoryId="9d0e4103-4cce-4536-83fa-4a5040674ad6">  
            <Components>  
                <Component Name=Microsoft Microsoft.BizTalk.Component.MIME_SMIME_Decoder>  
                    <Properties>  
                        <AllowNonMIMEMessage vt=11>true</AllowNonMIMEMessage>  
                    </Properties>  
                </Component>  
            </Components>  
        </Stage>  
        <Stage CategoryId="9d0e4105-4cce-4536-83fa-4a5040674ad6">  
            <Components>  
                <Component Name=Microsoft.BizTalk.Component.XmlDasmComp>  
                    <Properties>  
                        <EnvelopeSpecNames vt=8>MySchemas.EnvelopeSpecNames</EnvelopeSpecNames>  
                        <AllowUnrecognizedMessage vt=11>false</AllowUnrecognizedMessage>  
                    </Properties>  
                </Component>  
            </Components>  
        </Stage>  
        <Stage CategoryId="9d0e410d-4cce-4536-83fa-4a5040674ad6" ExecutionSequence="2">  
            <Components>  
                 <Component Name=Microsoft.BizTalk.Component.XmlValidator >  
                    <Properties>  
                        <DocumentSpecName vt=8>MySchemas.DocspecName</DocumentSpecName>  
                    </Properties>  
                </Component>  
            </Components>  
        </Stage>  
    </Stages>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0bfc9-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="0bfc9-132">See Also</span></span>  
 [<span data-ttu-id="0bfc9-133">开发自定义管道组件</span><span class="sxs-lookup"><span data-stu-id="0bfc9-133">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)