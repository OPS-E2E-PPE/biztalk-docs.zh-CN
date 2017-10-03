---
title: "程序集和项目安装异常管理示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af580992-73d4-4b16-a1cc-fa819b441fca
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65bcb2681cceb450995b18b7dc00d3d8f5a44d30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="assemblies-and-artifacts-installed-by-the-exception-management-samples"></a>程序集和项目安装异常管理示例
下表列出的程序集和 ESB 异常管理示例安装其他项目。  
  
|位置|类别|名称和版本的组件|  
|--------------|--------------|---------------------------------------|  
|BizTalk 应用程序 GlobalBank.ESB|业务流程|GlobalBank.ESB.ExceptionHandling.Processes.EAIProcess|  
|||GlobalBank.ESB.ExceptionHandling.Handlers.EAIGenericHandler|  
|||GlobalBank.ESB.ExceptionHandling.Handlers.EAIProcessHandler|  
|BizTalk 应用程序 GlobalBank.ESB|发送端口|EAIProcessHandler.RepairSubmit|  
|||EAIGenericHandler.PostTmpMsg|  
|||EAIProcess.PostApproval|  
|||EAIProcessHandler.PostDecline|  
|||所有。Exceptions_FILE （引用 GlobalFaultProcessor 管道）|  
|BizTalk 应用程序 GlobalBank.ESB|接收端口|EAIProcess.RequestPort|  
|BizTalk 应用程序 GlobalBank.ESB|接收位置|EAIProcess.RequestPort_FILE|  
|||EAIProcess.ReSubmit_HTTP|  
|BizTalk 应用程序 GlobalBank.ESB|架构|GlobalBank.ESB.ExceptionHandling.Schemas.System_Properties 版本 2.0.0.0|  
|||GlobalBank.ESB.ExceptionHandling.Schemas.Request 版本 2.0.0.0|  
|||GlobalBank.ESB.ExceptionHandling.Schemas.RequestDenied 版本 2.0.0.0|  
|BizTalk 应用程序 GlobalBank.ESB|管道|GlobalBank.ESB.ExceptionHandling.Pipelines.GlobalFaultProcessor 版本 2.0.0.0|  
|BizTalk 应用程序 GlobalBank.ESB|Resources|GlobalBank.ESB.ExceptionHandling.Handlers 版本 2.0.0.0|  
|||GlobalBank.ESB.ExceptionHandling.Processes 版本 2.0.0.0|  
|||GlobalBank.ESB.ExceptionHandling.Schemas 版本 2.0.0.0|  
|||GlobalBank.ESB.ExceptionHandling.Pipelines 版本 2.0.0.0|  
|BizTalk 应用程序 GlobalBank.ESB|策略||  
|BizTalk 应用程序 GlobalBank.ESB|地图|GlobalBank.ESB.ExceptionHandling.Schemas.MapToReqDenied 版本 2.0.0.0|  
|全局程序集缓存|程序集|GlobalBank.ESB.ExceptionHandling.Handlers 版本 2.0.0.0|  
|||GlobalBank.ESB.ExceptionHandling.Processes 版本 2.0.0.0|  
|||GlobalBank.ESB.ExceptionHandling.Schemas 版本 2.0.0.0|  
|||GlobalBank.ESB.ExceptionHandling.Pipelines 版本 2.0.0.0|  
|%Program 文件 %\\[!INCLUDE[prague](../includes/prague-md.md)]\Pipeline 组件|管道组件||