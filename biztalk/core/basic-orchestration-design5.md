---
title: 基本业务流程 Design5 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, design
- exception handling, orchestration design
ms.assetid: 0941d617-e30c-4ca7-852f-193e16781ca7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 224b8e507fc9319a2a4b66006914b3ebc27a8421
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230845"
---
# <a name="basic-orchestration-design"></a>基本业务流程设计
当您在 PeopleSoft Enterprise 的 BizTalk 适配器中创建基本业务流程时，将在该业务流程的接收端口中接收 XML， 然后将 XML 发送到后端系统以供处理。 在后端系统中，可能会发生异常，将停止业务流程，并生成错误。 生成的错误提供了业务流程未完成的相关信息， 但这并不能帮助确定错误起因。  
  
 ![](../core/media/siebeladapter-15-exceptionhandling-start.gif "SiebelAdapter_15_ExceptionHandling_Start")  
异常处理  
  
 出现故障时，调用将被挂起。 在审核日志中，该调用设置为“失败”。 在审核日志中右键单击“失败”，失败的调用将打开一个弹出消息。 单击报告选项后，后端系统将显示出错误以及失败原因。  
  
 若要防止业务流程进入挂起状态和重定向错误，您可创建一个 CatchExpression。 若要捕获由后端生成的异常并帮助找到错误起因，可以在业务流程中使用作用域形状。  
  
 ![](../core/media/siebeladapter-16-exceptionhandling-total.gif "SiebelAdapter_16_ExceptionHandling_Total")  
异常处理总计  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling2.md)