---
title: 端到端事务跟踪 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebacd2e4-6b5c-4dc4-8361-b5b77042debc
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7d19c4ce9bc30d60144ed69fc14f2323b4379d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306192"
---
# <a name="end-to-end-transaction-tracking"></a>端到端事务跟踪
业务可见性与操作员和用户的能力，若要监视的流量通过在运行时环境的流。 企业必须能够跟踪的进程和事务中通过他们在每个步骤以确保它们完成的贡献创收到其相应的系统。 AmberPoint SMS 简化了度量和 Microsoft BizTalk Server 中的这些消息的跟踪。 系统允许用户定义新的管理单元的端到端业务流程，而不是要求开发人员选择用来打包和部署单个服务组件的方式符合与保持一致。 图 1 显示了用于定义管理单位的屏幕。  
  
 ![BizTalk 定义事务](../esb-toolkit/media/ch9-biztalkdefiningtransaction.gif "Ch9-BizTalkDefiningTransaction")  
  
 **图 1**  
  
 **定义一个事务作为一个新的管理单元**  
  
 定义的事务之后, 用户还可以检测和跟踪消息与使用相同的工具提供可见性，单个服务的每个事务相关联。 这些工具可以公开性能指标、 监视服务级别协议，对性能和生成消息日志，如图 2 中所示。  
  
 ![BizTalk 监视](../esb-toolkit/media/ch9-biztalkmonitoring.gif "Ch9-BizTalkMonitoring")  
  
 **图 2**  
  
 **监视管道的端到端性能**  
  
 成功运行时管理和监视系统的一个主要要求是重要的业务事件，如异常和可能会中断业务事务流的逻辑处理的应用程序错误的检测。 AmberPoint SMS 允许操作员和用户，以获得深入了解操作和业务事件并监视这些事件对生成问题的服务所依赖的所有组件的影响。 此外，操作员和用户可以快速解决整个系统识别问题的根本原因。