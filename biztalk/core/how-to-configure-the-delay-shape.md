---
title: 如何配置延迟形状 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Delay shape [Orchestration Designer], configuring
- Delay shape [Orchestration Designer]
- Delay shape [Orchestration Designer], timeouts
- Delay shape [Orchestration Designer], about Delay shape
- configuring [Orchestration Designer], Delay shapes
ms.assetid: 727be28d-932a-41d5-af3f-3ee6f7129a17
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b76448398facd3af7f3b9712491f9895ffb406d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-configure-the-delay-shape"></a>如何配置延迟形状
![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")  
延迟形状  
  
 有两种方法指定的超时 **延迟**:  
  
-   你可以使用 **System.DateTime**, ，这将导致您的业务流程暂停到指定的日期和时间为止。  
  
     System.DateTime.UtcNow.AddSeconds(60)  
  
    > [!NOTE]
    >  延迟必须表示以协调世界时 (UTC) 时使用 **DateTime**。  
  
-   你可以使用 **System.TimeSpan**, ，这将导致您的业务流程暂停指定的时间长度。  
  
     System.TimeSpan(0, 1, 0)  
  
 如果你 **延迟** 形状位于 **侦听** 形状，则你不需要表达式的末尾添加分号。  
  
 有关详细信息 **System.DateTime** 和 **System.TimeSpan**, ，请参阅"DateTime 结构"和"TimeSpan 结构" [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 组合集合。  
  
> [!NOTE]
>  在多个机安装环境其中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 分隔机上安装 SQL Server 和 **延迟** 形状可能最终会早于由于时间应在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 机均未同步。  
  
> [!NOTE]
>  低于压力条件中，指定在超时 **延迟** 形状以后比你指定的内容可能会出现。 这是因为在任务繁忙的情况下存在线程资源不足。  
  
### <a name="to-configure-a-delay-shape"></a>配置延迟形状  
  
1.  如果 BizTalk 表达式编辑器不可见，请右键单击 **延迟** 的形状，然后单击 **编辑延迟**, ，或在属性窗口中，单击 **省略号** (**...**) 按钮 **表达式** 属性。  
  
2.  在 BizTalk 表达式编辑器中，创建一个表达式，返回 **System.DateTime** 对象或 **System.TimeSpan** 对象。 有关详细信息，请参阅[表达式的要求和限制](../core/requirements-and-limitations-for-expressions.md)。