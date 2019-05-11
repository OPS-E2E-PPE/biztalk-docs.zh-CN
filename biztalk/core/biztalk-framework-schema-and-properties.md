---
title: BizTalk 框架架构和属性 |Microsoft Docs
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
ms.openlocfilehash: 96aa2417e089d6ce2453b69af240e7c0056f2692
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358040"
---
# <a name="biztalk-framework-schema-and-properties"></a>BizTalk 框架架构和属性
**http://schemas.microsoft.com/BizTalk/2003/btf2-properties**命名空间包含可用于设置 BizTalk 框架拆装器管道组件的消息和部分上下文属性的属性。 BizTalk 框架拆装器管道组件使用这些属性创建的消息中生成适当的标头。 下表介绍了 BizTalk 框架属性。  

## <a name="properties-list"></a>属性列表  

|“属性”|类型|Description|  
|----------|----------|-----------------|  
|**IsReliable**|xs:boolean|指示从目标收到确认之前，是否应重新发送 BizTalk 框架消息。 此属性是由 BizTalk 框架组件在内部设置，引擎使用。 不要更改你的代码中此属性的值。|  
|**PassAckThrough**|xs:boolean|指示是否应通过 BizTalk 框架拆装器管道组件而不是已使用传递的确认消息。|  
|**eps_to_address**|xs:string|指定的目标地址。|  
|**eps_to_address_type**|xs:string|指定目标地址类型。|  
|**eps_from_address**|xs:string|指定的源地址。|  
|**eps_from_address_type**|xs:string|指定源地址类型。|  
|**prop_identity**|xs:string|唯一标识 BizTalk 框架文档的日志记录、 跟踪、 错误处理或其他文档处理和相关要求一个 URI 引用。|  
|**prop_sentAt**|xs:string|BizTalk 框架文档的发送时间戳。|  
|**prop_topic**|xs:string|一个唯一标识 BizTalk 框架文档的全部用途的 URI 引用。|  
|**svc_deliveryRctRqt_sendTo_address**|xs:string|指定应发送到 BizTalk 框架文档的送达回执的地址。|  
|**svc_deliveryRctRqt_sendTo_address_type**|xs:string|指定应发送 BizTalk 框架文档的送达回执地址类型。|  
|**svc_deliveryRctRqt_sendBy**|xs:dateTime|由 BizTalk 框架文档的送达回执必须接收指定的时间 （以分钟为单位）。|  
|**svc_commitmentRctRqt_sendTo_address**|xs:string|指定的收件人的发件人请求的处理的决策通知应发送到的地址。|  
|**svc_commitmentRctRqt_sendTo_address_type**|xs:string|指定的收件人的发件人请求的处理的决策通知应发送到的地址的类型。|  
|**svc_commitmentRctRqt_sendBy**|xs:dateTime|指定按其必须由发件人收到 BizTalk 框架文档的承诺回执的时间 （以分钟为单位）。|  
|**prc_type**|xs:string|提供指定业务流程的 BizTalk 框架消息处理中涉及的类型的 URI 引用。|  
|**prc_instance**|xs:string|提供唯一标识 BizTalk 框架文档关联的业务流程的特定实例的 URI 引用。|  
|**deliveryRct_receivedAt**|xs:dateTime|指定由此回执确认的文档的接收时间戳。 接收时间戳可能反映收到第一个副本的时间或在其收到确认副本的时间。|  
|**deliveryRct_identity**|xs:string|指定由送达回执确认的 BizTalk 框架文档的标识。|  
|**commitmentRct_identity**|xs:string|指定由提交回执确认的 BizTalk 框架文档的标识。|  
|**commitmentRct_decidedAt**|xs:string|指定由此回执确认的文档处理决定时间戳。|  
|**commitmentRct_decision**|xs:string|指定实际的决策，使用正值或负值的可能的值。|  
|**commitmentRct_commitmentCode**|xs:QName|指定限定的名称 （XSD)，指定有关处理决策的更具体状态。|  

## <a name="see-also"></a>请参阅  
- **消息上下文属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
- [配置本地管道组件](../core/configuring-native-pipeline-components.md)
