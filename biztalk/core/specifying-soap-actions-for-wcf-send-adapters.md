---
title: 指定的 SOAP 操作，wcf 发送适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send adapters, mapping
- send adapters, WCF services
- mapping, send adapters
- mapping, WCF send adapters
ms.assetid: fa9878eb-65b5-4ccc-b727-ff7e09ba6302
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 385e92f7801dc2512fbd038bd0b005d95c503e57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276637"
---
# <a name="specifying-soap-actions-for-wcf-send-adapters"></a>为 WCF 发送适配器指定 SOAP 操作
你可以设置**WCF。操作**WCF 发送适配器传输属性对话框中或业务流程中的上下文属性**表达式**形状。 如果你设置**WCF。操作**业务流程中的上下文属性，您需要离开**操作**字段保留为空白中静态发送端口的 WCF 适配器传输属性对话框。 如果你还在静态发送端口中，指定操作**WCF。操作**将替代在业务流程中设置的上下文属性。  
  
 此外，有两种方法来指定此属性： 单个操作格式和操作映射格式。 如果采用单一操作格式设置此属性（例如 http://MyService/IMyContract/MyAction1），则传出消息的“WCF 发送适配器传输属性”对话框中的 SOAP 操作将始终设置为在此属性中指定的值。 或者，可以在业务流程中设置的单个操作格式**表达式**形状。 例如：  
  
```  
OutboundMessage(WCF.Action)="http://MyService/IMyContract/MyAction1";  
```  
  
 如果在操作映射格式设置此属性，传出的 SOAP 操作由**BTS。操作**上下文属性。 例如，如果此属性设置为 WCF 中的以下 XML 格式发送适配器传输属性对话框中和**BTS。操作**属性设置为**Operation_1**在发送端口业务流程中，WCF 发送适配器使用 http://MyService/IMyContract/MyAction1 传出的 SOAP 操作的。  
  
```  
BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
<Operation Name="Operation_1" Action="http://MyService/IMyContract/MyAction1" />  
<Operation Name="Operation_2" Action="http://MyService/IMyContract/MyAction2" />  
<Operation Name="Operation_3" Action="http://MyService/IMyContract/MyAction3" />  
</BtsActionMapping>  
```  
  
 指定操作映射**WCF。操作**中**表达式**形状不支持。 您需要在 WCF 传输属性对话框中指定操作映射。 然后 WCF 适配器将通过查找的 SOAP 操作**BTS。操作**上下文属性，业务流程将设置为发送消息所在的端口上操作的名称。  
  
 如果使用基于内容的路由 (CBR) 其中路由传出消息**http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation**属性未设置，WCF 发送适配器将设置整个操作映射连接到传出的 WCF 消息的操作字符串。 若要解决此问题，你可以执行下列其中一项：  
  
-   将发送端口上的操作字段设置为 http://MyService/IMyContract/MyAction1。  
  
-   设置**BTS。操作**在管道中的上下文属性。 例如，设置的值**http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation**到 Operation1。  
  
-   将操作字段保留为空，改用传入消息中的操作。  
  
 您也可以通过 BizTalk WCF 服务使用向导来使用包含单一操作或操作映射的 WCF 服务。 有关更多详细信息，请参阅[如何使用 BizTalk WCF 服务使用向导来使用 WCF 服务](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)。  
  
## <a name="see-also"></a>另请参阅  
 [配置动态发送端口使用 WCF 适配器上下文属性](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)