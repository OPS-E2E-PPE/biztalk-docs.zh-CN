---
title: 基本业务流程 Design1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, design
ms.assetid: fd2e1d89-6230-4634-8a33-1cda26fd55f5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bfe5f4bce42fbffb7a0496b296f95b20be429d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358382"
---
# <a name="basic-orchestration-design"></a>基本业务流程设计
创建基本业务流程时，您在业务流程的接收端口接收 XML。 将 XML 发送到后端系统进行处理。 在后端系统中，异常可能会发生的无法停止业务流程并生成错误。 生成，该异常提供业务流程未完成的信息。  
  
 ![](../core/media/jdeoneworld-01.gif "JdeOneWorld_01")  
异常处理  
  
 发生错误时，调用将被挂起。 在事件查看器日志，可以查看错误和失败的原因。  
  
 若要防止业务流程进入挂起的状态并将重定向错误，可以创建一个 CatchExpression。 若要捕获由后端系统中，生成的异常并帮助查找问题的原因，您可以使用**作用域**形状在业务流程中的。  
  
 ![](../core/media/jdeoneworld-02.gif "JdeOneWorld_02")  
异常处理总计  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk Server 的异常处理](../core/using-biztalk-server-exception-handling1.md)