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
ms.openlocfilehash: edc30a99c0a037d23bc7d1ef7476edfdf159a339
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385289"
---
# <a name="how-to-deploy-pipelines"></a>如何部署管道
管道进行编译和部署为解决方案生成的一部分并部署过程。 编译器将调用**验证**方法在每个组件，从而使组件返回编译错误的配置信息。 生成后, 管道部署解决方案的其余部分的同一个程序集中时部署解决方案。  
  
## <a name="per-instance-pipeline-configuration"></a>每个实例的管道配置  
 每个实例的管道配置用于修改发送端口处部署管道内的管道组件的属性或接收位置级别。 仅几个管道组件属性需要修改每个实例时，每个实例的管道配置非常有用。 例如，如果你需要支持不同的消息类型中存在多个接收位置并具有一个自定义 XML 接收管道，每个实例的管道配置使你能够部署管道和重写默认配置 （包括指定不同的信封和文档规范名称）。 在 BizTalk 管理控制台中，以编程方式通过资源管理器对象模型支持此机制。  
  
### <a name="per-instance-pipeline-configuration-using-biztalk-administration-console"></a>每个实例管道配置使用 BizTalk 管理控制台  
 您还可以使用 BizTalk 管理控制台的每个实例的管道配置。 部署自定义管道后，创建许多接收位置或根据需要发送端口。 然后对于每个接收位置或发送端口，覆盖通过配置管道对话框中的默认属性值。 例如，若要指定不同的文档架构，可输入的架构名称**EnvelopeDocSpecNames**属性。  
  
> [!WARNING]
>  未验证的配置值指定在接收位置或发送端口将执行。 如果配置不正确，通过管道传递时，在运行时将失败消息。  
  
### <a name="per-instance-pipeline-configuration-using-the-explorer-object-model"></a>使用资源管理器对象模型的每个实例的管道配置  
 描述管道组件的每个实例配置的 XML 文件中读取时，它将覆盖在管道文件中设置的属性。  
  
 使用 BizTalk 浏览器对象模型可设置每个实例的管道配置。 BizTalk 浏览器对象模型提供了**ReceivePipelineData**上的属性**IReceiveLocation**并**ISendPort**接口来设置的配置接收管道组件。 BizTalk 浏览器对象模型还提供了**SendPipelineData**方法**ireceiveport 接口**并**ISendPort**设置配置的发送接口管道组件。  
  
 每个实例的管道配置不支持以下方案：  
  
- 重新排列管道内的阶段  
  
- 添加或删除阶段  
  
- 重排阶段内的组件  
  
- 添加或删除组件  
  
  在管道组件的配置中是唯一受支持的更改。 管道组件的每个实例配置将覆盖通用管道组件配置。 如果某个组件参数未指定每个实例的管道配置中，使用该参数 （如管道设计器中） 的常见配置。  
  
  下面是每个实例配置数据的示例。  
  
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
  
## <a name="see-also"></a>请参阅  
 [开发自定义管道组件](../core/developing-custom-pipeline-components.md)