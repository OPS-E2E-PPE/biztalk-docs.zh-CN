---
title: 如何配置延迟形状 |Microsoft Docs
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
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c00e002418dac53295828a4cbed632a6de0c235
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993646"
---
# <a name="how-to-configure-the-delay-shape"></a>如何配置延迟形状
![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")  
延迟形状  
  
 有两种方法来指定的超时**延迟**:  
  
- 可以使用**System.DateTime**，这将使您的业务流程指定日期前暂停并到达时间。  
  
   System.DateTime.UtcNow.AddSeconds(60)  
  
  > [!NOTE]
  >  延迟必须表示协调世界时 (UTC) 使用时**DateTime**。  
  
- 可以使用**System.TimeSpan**，这将导致您的业务流程来暂停指定的时间长度。  
  
   System.TimeSpan(0, 1, 0)  
  
  如果你**延迟**形状位于**侦听**形状，您不需要在表达式的末尾添加分号。  
  
  有关详细信息**System.DateTime**并**System.TimeSpan**，请参阅中"DateTime 结构"和"TimeSpan 结构"[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]组合集。  
  
> [!NOTE]
>  在多计算机安装环境中位置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SQL Server 安装在不同的计算机上**延迟**形状可能会早于上预期由于时间结束[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机不同步。  
> 
> [!NOTE]
>  在任务繁忙的情况下，指定在超时**延迟**形状可能会发生晚于指定了什么。 这是因为在任务繁忙的情况下存在线程资源不足。  
  
### <a name="to-configure-a-delay-shape"></a>配置延迟形状  
  
1.  如果 BizTalk 表达式编辑器不可见，请右键单击**延迟**形状，然后单击**编辑延迟**，或在属性窗口中，单击**省略号**(**...**) 按钮**表达式**属性。  
  
2.  在 BizTalk 表达式编辑器中，创建一个表达式，返回**System.DateTime**对象或**System.TimeSpan**对象。 有关详细信息，请参阅[表达式的要求和限制](../core/requirements-and-limitations-for-expressions.md)。