---
title: 基本业务流程 Design5 |Microsoft Docs
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
ms.openlocfilehash: 96606eac3ed552dfb07d82630d1ae82830b040c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358323"
---
# <a name="basic-orchestration-design"></a>基本业务流程设计
当 PeopleSoft Enterprise 的 BizTalk 适配器中创建基本业务流程时，请插入您的业务流程的接收端口接收 XML。 将 XML 然后发送到后端系统进行处理。 在后端系统中，可能会发生异常，将停止业务流程并生成错误。 生成的错误提供了业务流程未完成的信息。 这不是有帮助的调试错误的原因。  
  
 ![](../core/media/siebeladapter-15-exceptionhandling-start.gif "SiebelAdapter_15_ExceptionHandling_Start")  
异常处理  
  
 在发生错误时调用将被挂起。 在审核日志中，在调用设置为失败。 在审核日志中右键单击失败时，失败的调用将打开一个弹出消息。 当您单击报告选项时，将显示容错域和后端系统从失败的原因。  
  
 若要防止业务流程进入挂起的状态并将重定向错误，可以创建一个 CatchExpression。 若要捕获由后端生成的异常并帮助找到错误的原因，您可以在业务流程中使用作用域形状。  
  
 ![](../core/media/siebeladapter-16-exceptionhandling-total.gif "SiebelAdapter_16_ExceptionHandling_Total")  
异常处理总计  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk Server 的异常处理](../core/using-biztalk-server-exception-handling2.md)