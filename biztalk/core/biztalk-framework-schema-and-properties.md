---
title: BizTalk Framework 架构和属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8986e4a7-0c0a-415f-8a74-4fca71d3f1b5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 992f0fb9c66ee00cf425609db4231a57bf5782c4
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
ms.locfileid: "22232717"
---
# <a name="biztalk-framework-schema-and-properties"></a>BizTalk 框架架构和属性
**http://schemas.microsoft.com/BizTalk/2003/btf2-properties**命名空间包含可用于设置 BizTalk Framework 反汇编程序管道组件的消息和一部分上下文属性的属性。 BizTalk 框架拆装器管道组件使用这些属性在所创建消息中生成适当的标头。 下表对这些 BizTalk 框架属性进行了说明：  

## <a name="properties-list"></a>属性列表  
|名称|类型|Description|  
|----------|----------|-----------------|  
|**IsReliable**|xs:boolean|指示在收到目标的确认前是否应重新发送 BizTalk 框架消息。 此属性由 BizTalk 框架组件内部设置，供引擎使用。 请不要通过代码更改此属性的值。|  
|**PassAckThrough**|xs:boolean|指示确认消息是否应直接通过 BizTalk 框架拆装器管道组件而不被使用。|  
|**eps_to_address**|xs:string|指定目标地址。|  
|**eps_to_address_type**|xs:string|指定目标地址类型。|  
|**eps_from_address**|xs:string|指定源地址。|  
|**eps_from_address_type**|xs:string|指定源地址类型。|  
|**prop_identity**|xs:string|唯一标识 BizTalk 框架文档的 URI 引用，用于记录、跟踪、错误处理或其他文档处理和相关要求。|  
|**prop_sentAt**|xs:string|BizTalk 框架文档的发送时间戳。|  
|**prop_topic**|xs:string|唯一标识 BizTalk 框架文档的全部用途的 URI 引用。|  
|**svc_deliveryRctRqt_sendTo_address**|xs:string|指定应向其发送 BizTalk 框架文档的送达回执的地址。|  
|**svc_deliveryRctRqt_sendTo_address_type**|xs:string|指定应向其发送 BizTalk Framework 文档的送达回执的地址类型。|  
|**svc_deliveryRctRqt_sendBy**|xs:dateTime|指定必须在多长时间内收到 BizTalk 框架文档的送达回执（以分钟计）。|  
|**svc_commitmentRctRqt_sendTo_address**|xs:string|指定收件人对发件人请求的处理决策通知应发送到的地址。|  
|**svc_commitmentRctRqt_sendTo_address_type**|xs:string|指定收件人对发件人请求的处理决策通知应发送到的地址的类型。|  
|**svc_commitmentRctRqt_sendBy**|xs:dateTime|指定发件人必须在多长时间内收到 BizTalk 框架文档的提交回执（以分钟计）。|  
|**prc_type**|xs:string|提供指定处理 BizTalk 框架消息时涉及的业务流程类型的 URI 引用。|  
|**prc_instance**|xs:string|提供唯一标识与 BizTalk 框架文档关联的特定业务流程实例的 URI 引用。|  
|**deliveryRct_receivedAt**|xs:dateTime|指定此回执确认的文档的接收时间戳。 接收时间戳可能反映收到第一个副本的时间或收到确认副本的时间。|  
|**deliveryRct_identity**|xs:string|指定由送达回执确认的 BizTalk 框架文档的标识。|  
|**commitmentRct_identity**|xs:string|指定由提交回执确认的 BizTalk 框架文档的标识。|  
|**commitmentRct_decidedAt**|xs:string|指定由此回执确认的文档的处理决定时间戳。|  
|**commitmentRct_decision**|xs:string|指定实际的决策，可能为肯定值或否定值。|  
|**commitmentRct_commitmentCode**|xs:QName|指定限定名称（XSD 格式），用于指定有关处理决策的更具体的状态。|  
  
## <a name="see-also"></a>另请参阅  
-  **消息上下文属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
-  [配置本地管道组件](../core/configuring-native-pipeline-components.md)