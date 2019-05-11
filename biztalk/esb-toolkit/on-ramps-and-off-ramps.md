---
title: 接入和接出点 |Microsoft Docs
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
ms.openlocfilehash: 528a8a42319fce4dbfc6507ec4d0658092e44963
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400055"
---
# <a name="on-ramps-and-off-ramps"></a>接入和接出点
在环境中其中[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]是部署，BizTalk 接收位置负责接收发往 ESB 的消息被称为"好帮手。" 若要配置 ESB 接入点的标准 BizTalk 接收位置，将接收位置与作为该工具包的一部分提供的管道之一相关联，然后正确配置该管道中，以确定或阅读有关路线的组件入站的消息，具体取决于你的方案。  
  
 ESB"关闭入口"对应于 BizTalk 动态发送端口。 处理一条路线时，值将被提升到使用系统 Properties.xsd 架构相关联的消息的上下文属性。 BizTalk 的发布-订阅机制使用这些升级属性，以通过动态将消息路由发送端口 （关闭接入点） 以完成消息传递。  
  
 下表列出了接入所提供的[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。  
  
|“属性”|消息交换模式|**说明**|  
|----------|------------------------------|---------------------|  
|ESB.ItineraryServices|单向|ASMX 接入点;ESB 路线内容需要 SOAP 标头。|  
|ESB.ItineraryServices.Response|请求-响应|ASMX 接入点;ESB 路线内容需要 SOAP 标头。|  
|ESB.ItineraryServices.WCF|单向|Windows Communication Foundation (WCF) 的途径;SOAP 标头中要求 ESB 路线引用。|  
|ESB.ItineraryServices.Response.WCF|请求-响应|WCF 的途径;SOAP 标头中要求 ESB 路线引用。|  
|ESB.ItineraryServices.Generic.WCF|单向|WCF 的途径;预期请求消息仅供参考。|  
|ESB.ItineraryServices.Generic.Response.WCF|请求-响应|WCF 的途径;预期请求消息仅供参考。|  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] 接入不应配置 ASMX 选择 ESB 行程。 有关如何选择 ESB 路线的详细信息，请参阅[使用管道组件来选择现有路线](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md)。