---
title: 收集异常并将消息路由的修复和重新提交 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a61658a-0bac-4802-b506-02e61a3d2a9b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88e76164a26e1dfd227d7fea79cfa8106825f25d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302141"
---
# <a name="collecting-exceptions-and-routing-messages-for-repair-and-resubmit"></a>收集异常并将消息路由的修复和重新提交
在此用例，自定义异常处理程序选取通过 Web 服务收到的错误消息，并将其路由到与附带的 InfoPath 模板兼容的格式中的磁盘文件[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。 用户可以使用 Microsoft InfoPath 打开文件，编辑消息内容，并重新提交邮件以进行处理，如图 1 中所示。  
  
 ![收集异常修复](../esb-toolkit/media/ch3-collectingexceptionsrepair.gif "Ch3-CollectingExceptionsRepair")  
  
 **图 1**  
  
 **用于修复和重新提交消息路由**  
  
 中包含的修复和重新提交自定义异常处理程序示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。 当业务流程中的进程时遇到错误，异常处理程序，业务流程生成和发布到 ESB 的错误消息。 此错误消息包括，在其负载中，消息 （包括它们与 BizTalk Server 相关的上下文属性），是正在处理"时出现异常，并由 BizTalk 业务流程引擎捕获当前异常。 发布到 ESB 的错误消息后，它是到订阅的业务流程 （自定义异常处理程序），提取并检查未送达的消息和系统异常的对象，并将未送达的消息路由到文件文件夹中，从中取消排队用户可以编辑使用 InfoPath 的消息，并将其重新提交到 BizTalk Server 进行处理。  
  
 有关详细信息，请参阅[运行修复和重新提交自定义异常处理程序示例](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md)。