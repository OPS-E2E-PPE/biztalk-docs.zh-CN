---
title: 方案解决方案步骤 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77751c15-9b67-4587-8bc8-2be65f13d339
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebd2f7623487670041ed2684fc096b669eaef1a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394021"
---
# <a name="scenario-solution-steps"></a>方案解决方案步骤
ESB 异常管理框架提供用于处理异常时的发票消息包含无效数据的处理过程中，将导致错误，如本主题中前面所述的一个简单的解决方案。 下面是可能需要一种方法：  
  
1.  将最近部署财务报告的应用程序基于 Microsoft BizTalk 为你的团队的开发人员的责任分配。  
  
2.  新的 ESB 故障消息到达时在 ESB 管理门户中;该消息指示的财务报告 BizTalk 应用程序中的业务流程中的数据完整性问题。  
  
3.  发生异常时自动通知注册开发人员或管理员或操作员通知的新异常，开发人员。 此通知可能是由于以下原因之一：  
  
    -   它可能会导致异常超出预定义在基于事件的业务活动监视 (BAM) 的阈值。  
  
    -   它可能会导致 BizTalk 订阅存在特定的应用程序、 服务、 范围和错误代码，它将异常转发给开发人员。  
  
4.  开发人员检查错误消息、 单个业务流程消息和其持久化的上下文属性值。 开发人员可以查看此信息通过 ESB 管理门户或通过 BizTalk 订阅使用 Microsoft Outlook。  
  
5.  开发人员确定，这是一种常见错误。 只有财务团队，然后重新提交到系统，它将需要手动干预和更正。  
  
6.  开发人员创建和部署为独立的 BizTalk 业务流程项目的订阅的特定应用程序和异常类型。  
  
7.  业务流程项目从 ESB 错误消息中检索无效的消息、 将消息发送到更正财务团队、 关联回业务流程中，更正后的消息并将其重新提交。  
  
8.  一周后，开发人员将导航到 ESB 管理门户来发现由于此解决方案已部署，极大地降低无效消息的应用程序异常趋势。