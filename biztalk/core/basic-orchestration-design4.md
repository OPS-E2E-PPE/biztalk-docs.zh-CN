---
title: 基本业务流程 Design4 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, design
ms.assetid: 53f90bba-5786-49ca-b4d0-21601ec04045
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01c2bf6a1a3fc74b27a0dadd7ce7ad0185a51a12
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529147"
---
# <a name="basic-orchestration-design"></a>基本业务流程设计
创建基本业务流程时，您在您的业务流程的接收端口接收 XML。 将 XML 然后发送到后端系统进行处理。 在后端系统中，可能会发生异常，无法停止业务流程。 生成的异常提供了业务流程未完成的信息。  
  
 发生错误时，调用将被挂起。 在事件查看器日志，可以查看错误和失败的原因。  
  
 若要防止业务流程进入挂起的状态并将重定向错误，可以创建一个 CatchExpression。 若要捕获由后端生成的异常并帮助找到问题的原因，您可以在业务流程中使用作用域形状。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk Server 的异常处理](../core/using-biztalk-server-exception-handling4.md)