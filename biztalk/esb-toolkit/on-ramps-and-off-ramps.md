---
title: 上渐变和关闭渐变 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0cce5d2-f16f-4bda-94ac-20c4f457cfc7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0aafa69315dba07219ad8510c77cdc9de2d4bce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294557"
---
# <a name="on-ramps-and-off-ramps"></a>上渐变和关闭渐变
在环境中其中[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]是部署，BizTalk 接收位置负责接收 ESB 要发送的消息被称为"入口。" 若要配置标准的 BizTalk 接收位置到 ESB 入口，将接收位置与作为该工具包的一部分提供的管道之一相关联，然后正确配置以确定或阅读有关路线该管道组件入站的消息，具体取决于你的方案。  
  
 "关闭负载增加"ESB 对应于 BizTalk 动态发送端口。 处理一条路线时，值将被提升到使用系统 Properties.xsd 架构的关联消息的上下文属性。 BizTalk 发布-订阅机制使用这些提升属性，以将路由任何消息通过动态发送端口 （关闭负载增加） 完成消息传递。  
  
 下表列出了上-渐变提供的[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。  
  
|Name|消息交换模式|**Description**|  
|----------|------------------------------|---------------------|  
|ESB。ItineraryServices|单向|ASMX 入口;SOAP 标头中需要 ESB 路线内容。|  
|ESB。ItineraryServices.Response|请求-响应|ASMX 入口;SOAP 标头中需要 ESB 路线内容。|  
|ESB。ItineraryServices.WCF|单向|Windows Communication Foundation (WCF) 上的负载增加;SOAP 标头中应 ESB 路线引用。|  
|ESB。ItineraryServices.Response.WCF|请求-响应|WCF 入口;SOAP 标头中应 ESB 路线引用。|  
|ESB。ItineraryServices.Generic.WCF|单向|WCF 入口;需要请求消息仅供参考。|  
|ESB。ItineraryServices.Generic.Response.WCF|请求-响应|WCF 入口;需要请求消息仅供参考。|  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]上的渐变不 ASMX 应配置为选择 ESB 路线。 有关如何选择 ESB 路线的详细信息，请参阅[使用管道组件来选择现有路线](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md)。