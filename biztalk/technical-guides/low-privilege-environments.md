---
title: "低特权环境 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: abdc45d0-b63a-4b6c-80c4-1f8e87644cd9
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d43f363bd96dd8e3109a8ce21b9565fb43e5f9bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="low-privilege-environments"></a>低特权环境
附带的多个工作流[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包需要提升的权限才能执行某些操作。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包，可在低特权环境中执行基本的监视功能。 有两个管理角色： BizTalk 服务器管理员和 BizTalk Server 运算符。 BizTalk Server 管理员是高权限角色，有权访问配置数据和跟踪数据。 BizTalk 服务器管理员可以执行所有关键管理任务，此类登记和启动项目。 BizTalk Server 操作员是低权限角色，仅有权执行监视操作和排除故障操作。 有关详细信息，请参阅[最低安全用户权限](http://technet.microsoft.com/library/aa559845\(BTS.80\).aspx)。  
  
 使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包：  
  
-   BizTalk Server Operators 组的成员可以执行以下操作：  
  
    -   监视 BizTalk Server 以查找错误，挂起 messages\instances，查看配置的查询。  
  
    -   监视 BizTalk Server 安装和项目。  
  
    -   查看服务状态和消息流。  
  
    -   启动或停止应用程序和项目比如业务流程、 发送端口或发送处于登记状态的端口组。  
  
    -   启用或禁用接收位置。 在默认为 60 秒的下一缓存刷新间隔之前，更改不会生效。 缓存刷新间隔是在 BizTalk Server 组级别进行设置的。  
  
-   BizTalk Server Operators 组的成员不能执行以下操作：  
  
    -   修改 BizTalk Server 的配置。  
  
    -   查看分类为个人身份信息 (PII) 的消息上下文属性或消息正文。  
  
    -   修改消息路由的过程（例如向正在运行的系统添加新的订阅或从中删除订阅），包括将消息发布到 BizTalk Server 运行时的能力。  
  
> [!NOTE]  
>  若要执行的管理包，如重新启动 BTSNTSvc.exe 服务提供的所有监视任务，你必须是 BizTalk 服务器上的本地管理员组的成员。  
  
## <a name="in-this-section"></a>在本节中  
  
-   [监视](../technical-guides/monitoring.md)  
  
-   [发现](../technical-guides/discoveries.md)