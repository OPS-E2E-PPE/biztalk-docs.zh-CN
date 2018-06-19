---
title: 方案解决方案步骤 |Microsoft 文档
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
ms.openlocfilehash: dff3b2feda86ad0b8edbbded26a290c7276a63af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294837"
---
# <a name="scenario-solution-steps"></a>方案解决方案步骤
ESB 异常管理框架将为处理发票消息包含在处理期间，会导致错误的无效数据，如本主题中前面所述时出现异常提供一个简单的解决方案。 以下是你可能需要花费的一种方法：  
  
1.  将最近部署财务报告的应用程序基于 Microsoft BizTalk 到你的团队的开发人员的责任的分配。  
  
2.  新的 ESB 错误消息抵达 ESB 管理门户;该消息指示财务 Reporting BizTalk 应用程序中的业务流程中的数据完整性问题。  
  
3.  管理员或运算符来通知开发人员的新异常，或发生异常时，开发人员会自动通知。 此通知可能会出现以下原因之一：  
  
    -   它可能会导致异常超出预定义中基于事件的业务活动监视 (BAM) 的阈值。  
  
    -   它可能会导致 BizTalk 订阅存在特定的应用程序、 服务、 范围和将异常转发给开发人员的错误代码。  
  
4.  开发人员检查错误消息、 单个业务流程消息中和其持久化的上下文属性值。 开发人员可以查看此信息通过 ESB 管理门户或通过 BizTalk 订阅使用 Microsoft Outlook。  
  
5.  开发人员确定这是一种常见错误。 它将通过与财务团队，然后对系统进行重新提交需要人工干预和更正。  
  
6.  开发人员创建和部署为独立的 BizTalk 业务流程项目订阅特定的应用程序和异常类型。  
  
7.  业务流程项目从 ESB 错误消息中检索消息无效，将消息发送到更正与财务团队、 关联已更正的消息传送给业务流程，并会重新提交它。  
  
8.  一周后，开发人员导航到 ESB 管理门户，以发现无效的消息的应用程序异常趋势已降低大幅，由于部署此解决方案了。