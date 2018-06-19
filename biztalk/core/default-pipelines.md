---
title: 默认管道 |Microsoft 文档
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
ms.openlocfilehash: 8ceb3f06f2e2b57ec37bc4a95a385574de594940
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239301"
---
# <a name="default-pipelines"></a>默认管道
默认情况下，在创建新应用程序时将创建和部署默认管道。这些管道将显示在每个 BizTalk 项目的 \References 文件夹下的 Microsoft.BizTalk.DefaultPipelines 程序集中。 在管道设计器中不能修改默认管道。 在 BizTalk 浏览器中配置发送端口或接收位置时，可以选择这些管道。 本主题对这些默认管道以及何时使用这些管道进行了说明。  
  
> [!NOTE]
>  XML 接收管道和 XML 发送管道不支持大于 4GB 的 XML 文档。  
  
## <a name="passthrureceive-pipeline"></a>PassThruReceive 管道  
 直通接收管道不包含任何组件。 该管道用于不需要处理任何消息负载的简单直通方案。 在消息的源和目标已知，并且不需对消息进行验证、编码或拆装时，通常使用此管道。 此管道通常与直通发送管道一起使用。  
  
 由于直通接收管道不包含拆装器，因此不能用于向业务流程路由消息。  
  
> [!NOTE]
>  直通接收管道不支持属性升级。  
  
## <a name="passthrutransmit-pipeline"></a>PassThruTransmit 管道  
 直通发送管道不包含任何组件。 如果向目标发送消息前不需处理任何文档，则通常使用此管道。  
  
## <a name="xmlreceive-pipeline"></a>XMLReceive 管道  
 XML 接收管道包括以下阶段：  
  
-   **解码。** Empty  
  
-   **反汇编。** 包含 XML 拆装器组件  
  
-   **验证。** Empty  
  
-   **ResolveParty。** 运行参与方解析组件，该组件可以将证书主题或源安全 ID 解析为参与方 ID。  
  
## <a name="xmltransmit-pipeline"></a>XMLTransmit 管道  
 XML 发送管道包括以下阶段：  
  
-   **预先组建。** Empty  
  
-   **组建。** 包含 XML 组装器组件  
  
-   **编码。** Empty  
  
## <a name="see-also"></a>另请参阅  
 [类型的管道](../core/types-of-pipelines.md)   
 [类型的管道组件](../core/types-of-pipeline-components.md)   
 [管道模板](../core/pipeline-templates.md)   
 [管道组件](../core/pipeline-components.md)   
 [有关管道、 阶段和组件](../core/about-pipelines-stages-and-components.md)