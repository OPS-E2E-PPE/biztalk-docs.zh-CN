---
title: 使用 TIBCO EMS 消息上下文属性 |Microsoft Docs
description: 使用 BizTalk Server 业务流程中的 TIBCO Enterprise Message System 消息描述符字段
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
ms.openlocfilehash: 6c4c095969483905cf30403e4831e4f2df8296b7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394575"
---
# <a name="message-context-properties-in-tibco-ems"></a>在 TIBCO EMS 的消息上下文属性

## <a name="tibcoemspropertiesdll"></a>TibcoEMSProperties.dll
若要从 BizTalk Server 业务流程访问 TIBCO 企业消息系统消息描述符字段，必须添加对的引用**Microsoft.BizTalk.Adapters.TibcoEMSProperties.dll**到你的项目。 此程序集位于 **\<TIBCO EMS_Adapter_installation_directory\>\bin**。 在引用此 TIBCO EMS 属性架构之后，可以通过各种 BizTalk Server 开发工具 （例如，业务流程设计器中的消息赋值形状） 访问其他上下文属性。  
  
## <a name="access-context-properties"></a>访问上下文属性  
 若要访问上下文属性，指定一个可用上下文属性在 TIBCO EMS 命名空间中。 若要读取从端口绑定到的 BizTalk 适配器 TIBCO EMS 接收的消息的上下文属性，请在表达式中使用以下语法：  
  
```  
Message(TibcoEMS.Property)  
```  
  
 有关详细信息，请参阅[TIBCO Enterprise Message Service 消息描述符属性](../core/tibco-enterprise-message-service-message-descriptor-properties.md)。  
  
 在 BizTalk Server 中，消息是不可变的。 因此，若要将分配消息上下文属性值，请创建新的消息、 设置消息内容 （可通过分配现有的消息），然后设置所需的属性。  
  
 若要将 TIBCO EMS 上下文属性分配到发往 TIBCO ems 绑定到的 BizTalk 适配器的发送端口的消息，请使用消息赋值运算符，并在 TIBCO EMS 命名空间中指定一个可用上下文属性。 语法如下：  
  
```  
Message(TibcoEMS.Property) = value;  
```  
  
## <a name="next-steps"></a>后续步骤
-   [TIBCO EMS 消息描述符属性和值](../core/tibco-enterprise-message-service-message-descriptor-properties.md)  
  
-   [教程：使用消息上下文属性](../core/tutorial-using-message-context-properties.md)