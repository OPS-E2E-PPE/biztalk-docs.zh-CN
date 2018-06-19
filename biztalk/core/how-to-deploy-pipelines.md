---
title: 如何部署管道 |Microsoft 文档
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
ms.openlocfilehash: db6047752c45a2f72b615102e14a4e66839e3e81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249597"
---
# <a name="how-to-deploy-pipelines"></a>如何部署管道
管道是在解决方案的生成和部署过程中进行编译和部署的。 编译器调用**验证**允许要返回的组件的各个组件上的方法编译错误的配置信息。 在生成管道后，管道将在部署解决方案时与解决方案的其余部分部署在同一程序集中。  
  
## <a name="per-instance-pipeline-configuration"></a>基于实例的管道配置  
 基于实例的管道配置用于在发送端口级别或接收位置级别修改所部署管道内的管道组件的属性。 基于实例的管道配置在只需要按实例修改少数管道组件属性时非常有用。 例如，如果您需要在多个接收位置支持不同的消息类型并且只用一个自定义 XML 接收管道，则可以使用基于实例的管道配置部署该管道并覆盖默认配置（包括指定不同的信封和文档规范名称）。 BizTalk 管理控制台支持此机制，还可以通过 BizTalk 浏览器对象模型编程来支持此机制。  
  
### <a name="per-instance-pipeline-configuration-using-biztalk-administration-console"></a>使用 BizTalk 管理控制台进行基于实例的管道配置  
 您可以使用 BizTalk 管理控制台执行基于实例的管道配置。 部署完自定义管道后，创建所需数目的接收位置或发送端口。 然后，对于每个接收位置或发送端口，通过“配置管道”对话框覆盖默认属性值。 例如，若要指定不同的文档架构，可输入的架构名称**EnvelopeDocSpecNames**属性。  
  
> [!WARNING]
>  对在接收位置或发送端口中指定的配置值，不进行验证。 如果配置不正确，消息在运行时将无法通过管道。  
  
### <a name="per-instance-pipeline-configuration-using-the-explorer-object-model"></a>使用 BizTalk 浏览器对象模型进行基于实例的管道配置  
 在读取定义管道组件基于实例的配置的 XML 文件后，该文件中的属性将覆盖在管道文件中设置的属性。  
  
 基于实例的管道配置是使用 BizTalk 浏览器对象模型进行设置的。 BizTalk 资源管理器对象模型提供**ReceivePipelineData**属性**IReceiveLocation**和**ISendPort**设置的配置的接口接收管道组件。 BizTalk 资源管理器对象模型还提供了**SendPipelineData**方法**IReceivePort**和**ISendPort**的发送设置配置的接口管道组件。  
  
 基于实例的管道配置不支持以下操作：  
  
-   重排管道内的阶段  
  
-   添加或删除阶段  
  
-   重排阶段内的组件  
  
-   添加或删除组件  
  
 只支持在管道组件的配置中进行的更改。 管道组件基于实例的配置将覆盖通用管道组件配置。 如果在基于实例的管道配置中未指定某个组件参数，则使用该参数的通用配置（与管道设计器中的配置一样）。  
  
 下面列出了一个基于实例配置数据的示例：  
  
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
  
## <a name="see-also"></a>另请参阅  
 [开发自定义管道组件](../core/developing-custom-pipeline-components.md)