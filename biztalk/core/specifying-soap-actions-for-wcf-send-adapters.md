---
title: 指定 SOAP 操作，为 WCF 发送适配器 |Microsoft Docs
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
ms.openlocfilehash: 47781b2b8add675207136248b38b0dadfe6b5610
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023491"
---
# <a name="specifying-soap-actions-for-wcf-send-adapters"></a>为 WCF 发送适配器指定 SOAP 操作
可以设置**WCF。操作**上下文属性在 WCF 发送适配器传输属性对话框中或在业务流程**表达式**形状。 如果您设置**WCF。操作**业务流程中的上下文属性，您需要将**操作**字段留空，在 WCF 适配器传输属性对话框中的静态发送端口。 如果还在静态发送端口中指定的操作**WCF。操作**业务流程中设置的上下文属性将被重写。  
  
 此外，有两种方法来指定此属性： 单一操作格式和操作映射格式。 如果将此属性设置在单一操作格式 — 例如， http://MyService/IMyContract/MyAction1— WCF 中的 SOAP 操作发送适配器传输属性对话框中，为传出消息始终设置为此属性中指定的值。 或者，可以在业务流程中设置单一操作格式**表达式**形状。 例如，  
  
```  
OutboundMessage(WCF.Action)="http://MyService/IMyContract/MyAction1";  
```  
  
 如果采用操作映射格式设置此属性，传出的 SOAP 操作将由**BTS。操作**上下文属性。 例如，如果此属性设置为下面的 XML 格式，在 WCF 发送适配器传输属性对话框和**BTS。操作**属性设置为**Operation_1**业务流程中的发送端口，在 WCF 发送适配器将使用 http://MyService/IMyContract/MyAction1 为传出的 SOAP 操作。  
  
```  
BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
<Operation Name="Operation_1" Action="http://MyService/IMyContract/MyAction1" />  
<Operation Name="Operation_2" Action="http://MyService/IMyContract/MyAction2" />  
<Operation Name="Operation_3" Action="http://MyService/IMyContract/MyAction3" />  
</BtsActionMapping>  
```  
  
 为指定操作映射**WCF。操作**中**表达式**形状不受支持。 您需要在 WCF 传输属性对话框中指定操作映射。 然后 WCF 适配器将查找 SOAP 操作使用**BTS。操作**上下文属性，该业务流程将设置为发送消息的端口上操作的名称。  
  
 如果使用基于内容的路由 (CBR)，来路由传出消息**http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation**属性未设置，则 WCF 发送适配器会将整个操作映射字符串设置为传出 WCF 消息的操作。 若要解决此问题，可以执行下列任一操作：  
  
- 将操作字段设置为发送端口上http://MyService/IMyContract/MyAction1。  
  
- 设置**BTS。操作**管道中的上下文属性。 例如，设置的值**http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation**为 Operation1。  
  
- 将操作字段保留为空，改用传入消息中的操作。  
  
  您也可以通过 BizTalk WCF 服务使用向导来使用包含单一操作或操作映射的 WCF 服务。 有关更多详细信息，请参阅[如何使用 BizTalk WCF 服务使用向导来使用 WCF 服务](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用 WCF 适配器上下文属性配置动态发送端口](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)