---
title: 消息转换模式 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aef41642-d33b-4878-be65-ef336530647f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: badfb450b51aebbdf81b2beccdeac98fc549bcb0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294813"
---
# <a name="message-transformation-patterns"></a>消息转换模式
消息转换模式定义转换以进行其他处理，或以匹配的消息将发送到服务的预期的文档格式的消息的经验证的的准则。 一条消息可能需要转换，因为收到的消息的结构不在预期的标准，或者必须将消息从非标准的格式转换为 XML。  
  
## <a name="message-translator"></a>消息转换器  
 该消息转换器模式定义为使用不兼容的数据格式的系统之间的通信的解决方案。 例如，客户端应用程序可能会发送平面文件请求消息必须转换为 XML 中，然后才能进行其他处理。 有关此模式的详细说明，请参阅[消息转换器](http://go.microsoft.com/fwlink/?LinkId=186845)([http://go.microsoft.com/fwlink/?LinkId=186845](http://go.microsoft.com/fwlink/?LinkId=186845)) 上的企业集成模式站点。  
  
 此模式在路线设计器中的实现是的组合[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]转换服务和单个冲突解决程序。 路线转换服务负责将使用定义所需的转换的项目的冲突解决程序属性的消息。 解析程序实现负责提供可以根据解析程序配置静态还是动态，定义的转换设置。  
  
 有关消息转换器模式的示例实现，请参阅以下资源：  
  
-   [安装和运行路线上负载增加示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
-   [如何： 转换消息和使用请求-响应消息交换模式的服务终结点的路由](../esb-toolkit/transform-message-and-route-to-service-endpoint-using-request-response-message.md)  
  
## <a name="normalizer"></a>规范化器  
 规范化器模式是数据模型转换模式的扩展。 此模式中不同的格式定义就是从多个源收到的消息在语义上等效，但消息到达的解决方案。 有关此模式的详细说明，请参阅[规范化器](http://go.microsoft.com/fwlink/?LinkId=186847)([http://go.microsoft.com/fwlink/?LinkId=186847](http://go.microsoft.com/fwlink/?LinkId=186847)) 上的企业集成模式站点。  
  
 此模式在路线设计器中的实现是的组合[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]转换服务和单个冲突解决程序。 路线转换服务负责将使用定义所需的转换的项目的冲突解决程序属性的消息。 解析程序实现负责动态解析具有指定类型的消息的适当 Microsoft BizTalk 映射。  
  
 规范化器模式的示例实现，请参阅[安装和运行路线上负载增加示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。  
  
## <a name="content-enricher"></a>内容 Enricher  
 该内容 Enricher 模式定义收到的消息可能不包括所需的目标系统上以适当地处理消息的所有数据的解决方案。 例如，发送服务可能包括邮政编码没有冗余状态代码，但接收服务期望消息，其中包含一个状态代码和邮政编码;接收服务可以处理收到的消息之前需要额外的数据。 有关此模式的详细说明，请参阅[内容 Enricher](http://go.microsoft.com/fwlink/?LinkId=186848) ([http://go.microsoft.com/fwlink/?LinkId=186848](http://go.microsoft.com/fwlink/?LinkId=186848)) 上的企业集成模式站点。  
  
 有关内容 Enricher 模式的示例实现，请参阅[安装和运行消息扩充示例](../esb-toolkit/installing-and-running-the-message-enrichment-sample.md)应用程序。