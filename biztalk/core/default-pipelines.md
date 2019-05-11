---
title: 默认管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, PassThruTransmit
- pipelines, PassThruReceive
- pipelines, XMLTransmit
- pipelines, StsReceive
- pipelines, StsSend
- pipelines, StsFileReceive
- Microsoft.BizTalk.KwTpm.StsDefaultPipelines.EnvSchema XML envelope
- pipelines, XMLReceive
- pipelines, backward compatibility
- Microsoft.BizTalk.DefaultPipelines assembly
- pipelines, default
ms.assetid: 7d82bb2c-c7f1-44a1-9e1b-89b0bb806845
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a49e806bf8d38c7b2018f583e443589065be71a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389709"
---
# <a name="default-pipelines"></a>默认管道
当您创建新的应用程序，默认管道创建和部署默认情况下，显示在中每个 BizTalk 项目的 \References 文件夹下的 Microsoft.BizTalk.DefaultPipelines 程序集。 不能在管道设计器中修改默认管道。 这些管道配置的发送端口时，可以选择，或接收位置在 BizTalk 浏览器。 本主题介绍默认管道以及何时使用它们。  
  
> [!NOTE]
>  XML 接收管道和 XML 发送管道不支持大于 4gb 的 XML 文档。  
  
## <a name="passthrureceive-pipeline"></a>PassThruReceive 管道  
 直通接收管道不包含任何组件。 需要处理任何消息负载时，它用于简单直通方案。 当源和目标的消息已知的并且需要对消息进行任何验证，编码或拆装时，通常使用此管道。 此管道通常与直通发送管道结合使用。  
  
 因为它不包含拆装器，则无法将消息路由到业务流程使用直通接收管道。  
  
> [!NOTE]
>  直通接收管道不支持属性升级。  
  
## <a name="passthrutransmit-pipeline"></a>PassThruTransmit 管道  
 传递发送管道不包含任何组件。 将消息发送到目标之前需要处理任何文档时，通常使用此管道。  
  
## <a name="xmlreceive-pipeline"></a>XMLReceive 管道  
 XML 接收管道包括以下阶段：  
  
-   **解码。** Empty  
  
-   **反汇编。** 包含 XML 拆装器组件  
  
-   **验证。** Empty  
  
-   **解析参与方。** 运行参与方解析组件，证书使用者或源安全 ID 解析为参与方 id。  
  
## <a name="xmltransmit-pipeline"></a>XMLTransmit 管道  
 XML 发送管道包括以下阶段：  
  
-   **预组装。** Empty  
  
-   **组装。** 包含 XML 组装器组件  
  
-   **对进行编码。** Empty  
  
## <a name="see-also"></a>请参阅  
 [类型的管道](../core/types-of-pipelines.md)   
 [类型的管道组件](../core/types-of-pipeline-components.md)   
 [管道模板](../core/pipeline-templates.md)   
 [管道组件](../core/pipeline-components.md)   
 [关于管道、阶段和组件](../core/about-pipelines-stages-and-components.md)