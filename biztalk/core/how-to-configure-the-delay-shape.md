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
# <a name="how-to-configure-the-delay-shape"></a><span data-ttu-id="1a1a7-102">如何配置延迟形状</span><span class="sxs-lookup"><span data-stu-id="1a1a7-102">How to Configure the Delay Shape</span></span>
<span data-ttu-id="1a1a7-103">![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")</span><span class="sxs-lookup"><span data-stu-id="1a1a7-103">![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")</span></span>  
<span data-ttu-id="1a1a7-104">延迟形状</span><span class="sxs-lookup"><span data-stu-id="1a1a7-104">Delay shape</span></span>  
  
 <span data-ttu-id="1a1a7-105">有两种方法来指定的超时**延迟**:</span><span class="sxs-lookup"><span data-stu-id="1a1a7-105">There are two ways to specify the timeout for a **Delay**:</span></span>  
  
- <span data-ttu-id="1a1a7-106">可以使用**System.DateTime**，这将使您的业务流程指定日期前暂停并到达时间。</span><span class="sxs-lookup"><span data-stu-id="1a1a7-106">You can use **System.DateTime**, which causes your orchestration to pause until the specified date and time is reached.</span></span>  
  
   <span data-ttu-id="1a1a7-107">System.DateTime.UtcNow.AddSeconds(60)</span><span class="sxs-lookup"><span data-stu-id="1a1a7-107">System.DateTime.UtcNow.AddSeconds(60)</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="1a1a7-108">延迟必须表示协调世界时 (UTC) 使用时**DateTime**。</span><span class="sxs-lookup"><span data-stu-id="1a1a7-108">Delays must be expressed in Coordinated Universal Time (UTC) when using **DateTime**.</span></span>  
  
- <span data-ttu-id="1a1a7-109">可以使用**System.TimeSpan**，这将导致您的业务流程来暂停指定的时间长度。</span><span class="sxs-lookup"><span data-stu-id="1a1a7-109">You can use **System.TimeSpan**, which causes your orchestration to pause for the specified length of time.</span></span>  
  
   <span data-ttu-id="1a1a7-110">System.TimeSpan(0, 1, 0)</span><span class="sxs-lookup"><span data-stu-id="1a1a7-110">System.TimeSpan(0, 1, 0)</span></span>  
  
  <span data-ttu-id="1a1a7-111">如果你**延迟**形状位于**侦听**形状，您不需要在表达式的末尾添加分号。</span><span class="sxs-lookup"><span data-stu-id="1a1a7-111">If your **Delay** shape is inside a **Listen** shape, you do not need to add a semicolon at the end of the expression.</span></span>  
  
  <span data-ttu-id="1a1a7-112">有关详细信息**System.DateTime**并**System.TimeSpan**，请参阅中"DateTime 结构"和"TimeSpan 结构"[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]组合集。</span><span class="sxs-lookup"><span data-stu-id="1a1a7-112">For more information about **System.DateTime** and **System.TimeSpan**, see "DateTime Structure" and "TimeSpan Structure" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a1a7-113">在多计算机安装环境中位置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SQL Server 安装在不同的计算机上**延迟**形状可能会早于上预期由于时间结束[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机不同步。</span><span class="sxs-lookup"><span data-stu-id="1a1a7-113">In a multiple machines installation environment where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server are installed on separated machines, the **Delay** shape may end earlier than expected because of the times on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] machines are unsynchronized.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="1a1a7-114">在任务繁忙的情况下，指定在超时**延迟**形状可能会发生晚于指定了什么。</span><span class="sxs-lookup"><span data-stu-id="1a1a7-114">Under the stress condition, the timeout specified in the **Delay** shape may occur later than what you have specified.</span></span> <span data-ttu-id="1a1a7-115">这是因为在任务繁忙的情况下存在线程资源不足。</span><span class="sxs-lookup"><span data-stu-id="1a1a7-115">This is because of the thread starvation under the stress condition.</span></span>  
  
### <a name="to-configure-a-delay-shape"></a><span data-ttu-id="1a1a7-116">配置延迟形状</span><span class="sxs-lookup"><span data-stu-id="1a1a7-116">To configure a Delay shape</span></span>  
  
1.  <span data-ttu-id="1a1a7-117">如果 BizTalk 表达式编辑器不可见，请右键单击**延迟**形状，然后单击**编辑延迟**，或在属性窗口中，单击**省略号**(**...**) 按钮**表达式**属性。</span><span class="sxs-lookup"><span data-stu-id="1a1a7-117">If BizTalk Expression Editor is not visible, right-click the **Delay** shape and click **Edit Delay**, or in the Properties window, click the **Ellipsis** (**...**) button for the **Expression** property.</span></span>  
  
2.  <span data-ttu-id="1a1a7-118">在 BizTalk 表达式编辑器中，创建一个表达式，返回**System.DateTime**对象或**System.TimeSpan**对象。</span><span class="sxs-lookup"><span data-stu-id="1a1a7-118">In BizTalk Expression Editor, create an expression that returns a **System.DateTime** object or a **System.TimeSpan** object.</span></span> <span data-ttu-id="1a1a7-119">有关详细信息，请参阅[表达式的要求和限制](../core/requirements-and-limitations-for-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="1a1a7-119">For more information, see [Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md).</span></span>