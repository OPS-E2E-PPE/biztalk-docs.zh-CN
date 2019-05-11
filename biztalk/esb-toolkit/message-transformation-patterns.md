---
title: 消息转换模式 |Microsoft Docs
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
ms.openlocfilehash: 87df85f41e15857cf73e82e437009574861345df
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395903"
---
# <a name="message-transformation-patterns"></a>消息转换模式
消息转换模式定义用于转换消息以进行其他处理，或以匹配所需的文档格式将向其发送消息的服务的经验证指导原则。 一条消息可能需要转换，因为收到的消息的结构不在预期的标准或因为必须将消息从非标准格式转换为 XML。  
  
## <a name="message-translator"></a>消息转换器  
 消息转换器模式定义为使用不兼容的数据格式的系统之间的通信的解决方案。 例如，客户端应用程序可能会发送平面文件的请求消息必须转换为 XML，然后才能进行其他处理。 此模式的详细说明，请参阅[消息转换器](http://go.microsoft.com/fwlink/?LinkId=186845)([http://go.microsoft.com/fwlink/?LinkId=186845](http://go.microsoft.com/fwlink/?LinkId=186845)) 企业集成模式站点上。  
  
 在路线设计器中此模式的实现是一系列[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]转换服务和单个冲突解决程序。 路线转换服务负责转换使用定义的转换所需的项目的冲突解决程序属性的消息。 解析程序实现负责提供转换设置，具体取决于冲突解决程序配置静态或动态，进行定义。  
  
 消息转换器模式的实现示例，请参阅以下资源：  
  
-   [安装和运行路线接入点示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
-   [如何：转换消息并使用请求-响应消息交换模式的服务终结点的路由](../esb-toolkit/transform-message-and-route-to-service-endpoint-using-request-response-message.md)  
  
## <a name="normalizer"></a>规范化器  
 规范化器模式是数据模型转换模式的扩展。 此模式中不同的格式定义的解决方案，从多个源接收的消息在语义上等效，但消息到达。 此模式的详细说明，请参阅[规范化器](http://go.microsoft.com/fwlink/?LinkId=186847)([http://go.microsoft.com/fwlink/?LinkId=186847](http://go.microsoft.com/fwlink/?LinkId=186847)) 企业集成模式站点上。  
  
 在路线设计器中此模式的实现是一系列[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]转换服务和单个冲突解决程序。 路线转换服务负责转换使用定义的转换所需的项目的冲突解决程序属性的消息。 解析程序实现负责动态解析具有指定类型的消息的相应 Microsoft BizTalk 映射。  
  
 规范化器模式的实现示例，请参阅[安装和运行路线接入点示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。  
  
## <a name="content-enricher"></a>内容扩充器添加  
 内容扩充器添加模式定义收到的消息可能不包括所需的目标系统来适当地处理该消息的所有数据的解决方案。 例如，发送服务可能包括 ZIP 代码而无需是冗余的状态代码，但接收服务需要一条消息，包括状态代码和邮政编码;接收服务可以处理收到的消息之前，其他数据是必需的。 此模式的详细说明，请参阅[内容扩充器添加](http://go.microsoft.com/fwlink/?LinkId=186848)([http://go.microsoft.com/fwlink/?LinkId=186848](http://go.microsoft.com/fwlink/?LinkId=186848)) 企业集成模式站点上。  
  
 有关内容扩充器添加模式的实现示例，请参阅[安装和运行消息充实示例](../esb-toolkit/installing-and-running-the-message-enrichment-sample.md)应用程序。