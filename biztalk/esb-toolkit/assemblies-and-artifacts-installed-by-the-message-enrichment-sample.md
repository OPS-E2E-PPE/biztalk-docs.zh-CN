---
title: "程序集和项目安装消息扩充示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96e67595-35b8-4bac-a429-0de76204a9a6
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b613efe730c51bdac6354f819e544a30f38d8bb
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="assemblies-and-artifacts-installed-by-the-message-enrichment-sample"></a>程序集和项目安装消息扩充示例
下表列出的程序集和消息扩充示例安装其他项目。  
  
|位置|类别|名称和版本的组件|  
|--------------|--------------|---------------------------------------|  
|BizTalk 应用程序 GlobalBank.ESB|业务流程|MessageEnrichment.Orchestrations.MessageEnricher|  
|BizTalk 应用程序 GlobalBank.ESB|发送端口|MessageEnrichment.Orchestrations_1.0.0.0_<br /><br /> MessageEnrichment.Orchestrations.MessageEnricher_RoutingPort_d98186f1038d4721|  
|BizTalk 应用程序 GlobalBank.ESB|接收端口||  
|BizTalk 应用程序 GlobalBank.ESB|接收位置||  
|BizTalk 应用程序 GlobalBank.ESB|架构|MessageEnrichment.Schema.ProcedureResultSet_dbo_GetOrderDetails 版本 1.0.0.0|  
|||MessageEnrichment.Schema.OrderDoc 版本 1.0.0.0|  
|||MessageEnrichment.Schema.InventoryOrder 版本 1.0.0.0|  
|||MessageEnrichment.Schema.TypedProcedure_dbo 版本 1.0.0.0|  
|BizTalk 应用程序 GlobalBank.ESB|管道||  
|BizTalk 应用程序 GlobalBank.ESB|Resources|MessageEnrichment.Transforms 版本 1.0.0.0|  
|||MessageEnrichment.Orchestrations 版本 1.0.0.0|  
|||MessageEnrichment.Schema 版本 1.0.0.0|  
|BizTalk 应用程序 GlobalBank.ESB|策略||  
|BizTalk 应用程序 GlobalBank.ESB|地图|MessageEnrichment.Transforms.NAOrderDocToGetOrderDetailsRequestMap 版本 1.0.0.0|  
|全局程序集缓存|程序集|MessageEnrichment.Transforms 版本 1.0.0.0|  
|||MessageEnrichment.Orchestrations 版本 1.0.0.0|  
|||MessageEnrichment.Schema 版本 1.0.0.0|  
|%Program 文件 %\\BizTalk Server\Pipeline 组件|管道组件||