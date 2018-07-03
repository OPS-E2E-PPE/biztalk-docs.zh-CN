---
title: 如何使用自相关直接绑定端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: feb651fa-3e35-4598-b229-335448f6919c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eaad102db33b4967c89cb78f944b93a688e4c213
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982318"
---
# <a name="how-to-use-self-correlating-direct-bound-ports"></a><span data-ttu-id="2dff1-102">如何使用自相关直接绑定端口</span><span class="sxs-lookup"><span data-stu-id="2dff1-102">How to Use Self-Correlating Direct Bound Ports</span></span>
<span data-ttu-id="2dff1-103">自相关直接绑定端口是自引用的。</span><span class="sxs-lookup"><span data-stu-id="2dff1-103">Self-correlating direct bound ports are self referential.</span></span> <span data-ttu-id="2dff1-104">这表明自相关直接绑定端口提供了可用于将消息发送回其封闭业务流程的信息。</span><span class="sxs-lookup"><span data-stu-id="2dff1-104">This means that a self-correlating direct bound port supplies the information that an orchestration can use to send messages back to its enclosing orchestration.</span></span> <span data-ttu-id="2dff1-105">使用自相关直接绑定时，业务流程引擎对特定于业务流程实例的消息生成一个相关标记。</span><span class="sxs-lookup"><span data-stu-id="2dff1-105">When using the self-correlating direct binding, the orchestration engine generates a correlation token on a message that is particular to the orchestration instance.</span></span> <span data-ttu-id="2dff1-106">这提供了在不使用相关集的情况下将消息返回到特定业务流程实例的能力。</span><span class="sxs-lookup"><span data-stu-id="2dff1-106">This provides the capability of getting messages back to a particular orchestration instance without using a correlation set.</span></span>  
  
 <span data-ttu-id="2dff1-107">例如，可以创建自相关直接绑定的端口在业务流程 A 中通过指定接收**直接**有关**端口绑定**，然后选择**自相关**端口配置向导中。</span><span class="sxs-lookup"><span data-stu-id="2dff1-107">For example, you can create a receiving self-correlating direct bound port in Orchestration A by specifying **Direct** for **Port binding** and selecting **Self Correlating** in the Port Configuration Wizard.</span></span> <span data-ttu-id="2dff1-108">然后，在业务流程 B 中，将某个端口声明为业务流程 A 中定义的具有相同端口类型的发送端口业务流程参数。为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2dff1-108">Then, in Orchestration B, you declare a port as a Send Port Orchestration Parameter of the same port type as defined in Orchestration A. To do so, do the following:</span></span>  
  
1. <span data-ttu-id="2dff1-109">在业务流程视图窗口中，右键单击**业务流程参数**，然后单击**新建端口参数**。</span><span class="sxs-lookup"><span data-stu-id="2dff1-109">In the Orchestration View window, right-click **Orchestration Parameters**, and then click **New Port Parameter**.</span></span>  
  
2. <span data-ttu-id="2dff1-110">在属性窗口中的**通信方向**，选择**发送**，并为**端口类型**，选择相同的端口类型，如业务流程 A 中定义</span><span class="sxs-lookup"><span data-stu-id="2dff1-110">In the Properties window, for **Communication Direction**, select **Send**, and for **Port Type**, select the same port type as defined in Orchestration A.</span></span>  
  
   <span data-ttu-id="2dff1-111">该声明将在业务流程设计器中的端口图面上创建一个逻辑发送端口。</span><span class="sxs-lookup"><span data-stu-id="2dff1-111">This declaration creates a logical send port on the Port Surface in Orchestration Designer.</span></span> <span data-ttu-id="2dff1-112">业务流程 A 调用业务流程 B 使用**启动业务流程**形状并将新端口作为参数，以及其他业务流程参数，传递给业务流程 b。 业务流程 B，然后执行其业务逻辑并将消息传递的新端口上向其发送。</span><span class="sxs-lookup"><span data-stu-id="2dff1-112">Orchestration A calls Orchestration B using the **Start Orchestration** shape and passes the new port as a parameter, along with the other orchestration parameters, to Orchestration B. Orchestration B then performs its business logic and sends a message on the new port that was passed to it.</span></span> <span data-ttu-id="2dff1-113">此消息发送到启动了业务流程 B 的业务流程 A 实例的用于接收的自相关直接绑定端口。</span><span class="sxs-lookup"><span data-stu-id="2dff1-113">The message is sent to the receiving self-correlating direct bound port of the instance of Orchestration A that started Orchestration B.</span></span>  
  
   <span data-ttu-id="2dff1-114">尽管也可以使用实现事件的上述顺序**调用业务流程**形状，它仅使用时非常有用**启动业务流程**形状。</span><span class="sxs-lookup"><span data-stu-id="2dff1-114">Although the preceding sequence of events can also be done with a **Call Orchestration** shape, it only makes sense when using a **Start Orchestration** shape.</span></span> <span data-ttu-id="2dff1-115">这是因为使用时**调用业务流程**形状，端口按引用传递。</span><span class="sxs-lookup"><span data-stu-id="2dff1-115">This is because when using a **Call Orchestration** shape, ports are passed by reference.</span></span> <span data-ttu-id="2dff1-116">端口的极性在这两个业务流程中必须相同。</span><span class="sxs-lookup"><span data-stu-id="2dff1-116">The polarity of the port must be same in both of the orchestrations.</span></span> <span data-ttu-id="2dff1-117">因此，从一个业务流程中传入的端口的通信方向必须与所调用业务流程中端口引用的方向相同。</span><span class="sxs-lookup"><span data-stu-id="2dff1-117">Therefore, the communication direction of the port you pass in from one orchestration must be the same as the direction of the port reference in the called orchestration.</span></span> <span data-ttu-id="2dff1-118">但是，使用时**启动业务流程**形状，生成的业务流程异步实例化，而且不能包含**Out**或**Ref**参数;因此，自相关直接绑定的端口提供业务流程将响应返回至其进行实例化的业务流程实例的方法。</span><span class="sxs-lookup"><span data-stu-id="2dff1-118">However, when using the **Start Orchestration** shape, an asynchronous instantiation of an orchestration is generated and it cannot have **Out** or **Ref** parameters; therefore, the self-correlating direct bound port provides a way for an orchestration to respond back to the orchestration instance that instantiated it.</span></span>  
  
   <span data-ttu-id="2dff1-119">有关如何使用自相关直接绑定的端口的示例，请参阅 SDK 示例"实现分散和收集模式"网址[ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="2dff1-119">For an example of how to use self-correlating direct bound ports, see the SDK sample "Implementing Scatter and Gather Pattern" at [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dff1-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="2dff1-120">See Also</span></span>  
 <span data-ttu-id="2dff1-121">[如何使用 MessageBox 直接绑定端口](../core/how-to-use-messagebox-direct-bound-ports.md) </span><span class="sxs-lookup"><span data-stu-id="2dff1-121">[How to Use MessageBox Direct Bound Ports](../core/how-to-use-messagebox-direct-bound-ports.md) </span></span>  
 [<span data-ttu-id="2dff1-122">如何使用合作伙伴业务流程直接绑定端口</span><span class="sxs-lookup"><span data-stu-id="2dff1-122">How to Use Partner Orchestration Direct Bound Ports</span></span>](../core/how-to-use-partner-orchestration-direct-bound-ports.md)