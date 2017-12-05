---
title: "收集异常和修复，重新提交路由消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a61658a-0bac-4802-b506-02e61a3d2a9b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a1d080cc3b87cf371729c51e1b1f26e07ae521e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="collecting-exceptions-and-routing-messages-for-repair-and-resubmit"></a>收集异常和修复，重新提交路由消息
在使用此种情况下，自定义异常处理程序选取通过 Web 服务收到的错误消息，并将它路由到中随附的 InfoPath 模板与兼容的格式为磁盘文件[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。 用户可以使用 Microsoft InfoPath 打开文件，编辑消息内容，然后重新提交以进行处理，该消息，如图 1 中所示。  
  
 ![收集异常修复](../esb-toolkit/media/ch3-collectingexceptionsrepair.gif "Ch3 CollectingExceptionsRepair")  
  
 **图 1**  
  
 **路由修复并重新提交一条的消息**  
  
 修复和重新提交自定义异常处理程序示例随附[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。 当业务流程中的进程时遇到错误，异常处理程序，业务流程生成和发布 ESB 错误消息。 此错误消息包括，在其负载中，消息 （包括其与 BizTalk Server 相关的上下文属性），处于"航班"时出现异常，由 BizTalk 业务流程引擎捕获当前异常。 发布 ESB 错误消息后，它是与订阅业务流程 （自定义异常处理程序），提取和检查正在进行的消息和系统异常对象，并从中将正在进行的消息路由到文件文件夹中，取消排队用户可以编辑使用 InfoPath 的消息，并将其重新提交给 BizTalk Server 进行处理。  
  
 有关详细信息，请参阅[运行修复和重新提交自定义异常处理程序示例](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md)。