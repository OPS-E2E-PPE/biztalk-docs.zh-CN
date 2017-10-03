---
title: "端到端事务跟踪 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ebacd2e4-6b5c-4dc4-8361-b5b77042debc
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffa49372c54dc526f45e04317e002604ac0914d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="end-to-end-transaction-tracking"></a>端到端事务跟踪
对运算符和用户能够监视通过运行时环境的通信流相关业务可见性。 企业必须能够跟踪的进程和流经其系统在每个步骤，以确保它们播放导致收入生成其参与的事务。 AmberPoint SMS 简化了的度量和 Microsoft BizTalk Server 中的这些消息的跟踪。 系统允许用户定义新的管理单元，它们与端到端业务流程、 而不是所需以符合开发人员选择打包和部署单个服务组件的方式保持一致。 图 1 显示了用于定义管理单位的屏幕。  
  
 ![定义事务的 BizTalk](../esb-toolkit/media/ch9-biztalkdefiningtransaction.gif "Ch9 BizTalkDefiningTransaction")  
  
 **图 1**  
  
 **作为新的管理单元中定义事务**  
  
 后定义的事务，用户还可以检测和跟踪消息与使用相同的工具，提供到单个服务的可见性的每个事务相关联。 这些工具可以公开性能度量值、 监视服务级别协议针对性能和生成消息日志，如图 2 中所示。  
  
 ![BizTalk 监视](../esb-toolkit/media/ch9-biztalkmonitoring.gif "Ch9 BizTalkMonitoring")  
  
 **图 2**  
  
 **监视的管道的端到端性能**  
  
 成功的运行时管理和监视系统的主要要求是重要的业务事件，包括异常及可能会中断业务事务流的逻辑处理的应用程序错误的检测工具。 AmberPoint SMS 允许操作员和用户，以获得深入了解操作和业务事件，并监视这些事件对依赖于生成问题的服务的所有组件产生的影响。 此外，则操作员和用户可以快速诊断整个系统以确定问题的根本原因。