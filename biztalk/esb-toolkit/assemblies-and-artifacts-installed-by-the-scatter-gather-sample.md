---
title: "程序集和项目安装散播-聚集示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61f5f10e-c38b-4887-b2db-f568a28d1d4d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e62dd1701284fec27084bbdaf5aab19d6dca64a4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="assemblies-and-artifacts-installed-by-the-scatter-gather-sample"></a>程序集和项目安装散播-聚集示例
下表列出的程序集和 ESB 散播-聚集示例安装其他项目。  
  
|位置|类别|名称和版本的组件|  
|--------------|--------------|---------------------------------------|  
|BizTalk 应用程序 GlobalBank.ESB|业务流程|GlobalBank.ESB.ScatterGather.Processes.Broker|  
|||GlobalBank.ESB.ScatterGather.Processes.ServiceDispatcher|  
|BizTalk 应用程序 GlobalBank.ESB|发送端口|GlobalBank.ESB.ScatterGather.Processes_2.0.0.0_<br /><br /> GlobalBank.ESB.ScatterGather.Processes.ServiceDispatcher_ServiceRequestPort_d98186f1038d4721|  
|BizTalk 应用程序 GlobalBank.ESB|接收端口||  
|BizTalk 应用程序 GlobalBank.ESB|接收位置||  
|BizTalk 应用程序 GlobalBank.ESB|架构|GlobalBank.ESB.ScatterGather.Schemas.RequestMetaData 版本 2.0.0.0|  
|||GlobalBank.ESB.ScatterGather.Schemas.AggregatedResponse 版本 2.0.0.0|  
|||GlobalBank.ESB.ScatterGather.Schemas.ServiceResponse 版本 2.0.0.0|  
|||GlobalBank.ESB.ScatterGather.Schemas.ServicePayload 版本 2.0.0.0|  
|BizTalk 应用程序 GlobalBank.ESB|管道|GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline 版本 2.0.0.0|  
|BizTalk 应用程序 GlobalBank.ESB|Resources|GlobalBank.ESB.ScatterGather.Processes 版本 2.0.0.0|  
|||GlobalBank.ESB.ScatterGather.Schemas 版本 2.0.0.0|  
|BizTalk 应用程序 GlobalBank.ESB|策略|ResolveEndPointScatterGather<br /><br /> ResolveMapScatterGather|  
|BizTalk 应用程序 GlobalBank.ESB|地图||  
|全局程序集缓存|程序集|GlobalBank.ESB.ScatterGather.Processes 版本 2.0.0.0|  
|||GlobalBank.ESB.ScatterGather.Schemas 版本 2.0.0.0|  
|%Program 文件 %\\BizTalk Server\Pipeline 组件|管道组件||