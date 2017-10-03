---
title: "基本业务流程 Design1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: orchestrations, design
ms.assetid: fd2e1d89-6230-4634-8a33-1cda26fd55f5
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d302428cd713b826e7c4629ea75eb6f6268d7400
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="basic-orchestration-design"></a>基本业务流程设计
创建基本业务流程时，将在您的业务流程的接收端口接收 XML。 将 XML 发送到后端系统以供处理。 在后端系统中，可能会出现停止业务流程并生成错误的异常。 生成的异常提供了业务流程未完成的相关信息。  
  
 ![](../core/media/jdeoneworld-01.gif "JdeOneWorld_01")  
异常处理  
  
 出现错误时，调用将被挂起。 在事件查看器日志中，您可以查看该故障的错误和原因。  
  
 若要防止业务流程进入挂起状态和重定向错误，您可创建一个 CatchExpression。 若要捕获由后端系统中，所生成的异常并帮助查找问题的原因，你可以使用**作用域**业务流程中的形状。  
  
 ![](../core/media/jdeoneworld-02.gif "JdeOneWorld_02")  
异常处理总计  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling1.md)