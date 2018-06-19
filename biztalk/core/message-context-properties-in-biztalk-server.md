---
title: 使用 TIBCO EMS 消息上下文属性 |Microsoft 文档
description: 使用 BizTalk Server 业务流程中的 TIBCO 企业消息系统消息描述符字段
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 163ac2cf-0e2d-4780-b398-baa825f92b00
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5433e454d161c77ac140167e9af082eaee7c2032
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970435"
---
# <a name="message-context-properties-in-tibco-ems"></a>在 TIBCO EMS 消息上下文属性

## <a name="tibcoemspropertiesdll"></a>TibcoEMSProperties.dll
若要从 BizTalk Server 业务流程访问 TIBCO 企业消息系统消息描述符字段，必须添加对引用**Microsoft.BizTalk.Adapters.TibcoEMSProperties.dll**到你的项目。 此程序集位于 **\<TIBCO EMS_Adapter_installation_directory\>\bin**。 在引用此 TIBCO EMS 属性架构之后，将可以使用各种 BizTalk Server 开发工具访问其他上下文属性（例如，业务流程设计器中的消息赋值形状）。  
  
## <a name="access-context-properties"></a>访问上下文属性  
 若要访问上下文属性，需要在 TIBCO EMS 命名空间中指定一个可用上下文属性。 若要读取从绑定到 TIBCO EMS 的 BizTalk 适配器的端口接收的消息的上下文属性，可在表达式中使用下列语法：  
  
```  
Message(TibcoEMS.Property)  
```  
  
 有关详细信息，请参阅[TIBCO 企业消息服务消息描述符属性](../core/tibco-enterprise-message-service-message-descriptor-properties.md)。  
  
 在 BizTalk Server 中，消息是不可改变的。 因此，若要分配消息上下文属性值，可创建一个新消息、设置消息内容（可通过分配现有消息来实现）然后设置您需要的属性。  
  
 对于以绑定到 TIBCO EMS 的 BizTalk 适配器的发送端口为目标的消息，若要将 TIBCO EMS 上下文属性分配给此类消息，请使用消息赋值运算符，并在 TIBCO EMS 命名空间中指定可用的上下文属性之一。 语法如下：  
  
```  
Message(TibcoEMS.Property) = value;  
```  
  
## <a name="next-steps"></a>后续步骤
-   [TIBCO EMS 消息描述符属性和值](../core/tibco-enterprise-message-service-message-descriptor-properties.md)  
  
-   [教程：使用消息上下文属性](../core/tutorial-using-message-context-properties.md)