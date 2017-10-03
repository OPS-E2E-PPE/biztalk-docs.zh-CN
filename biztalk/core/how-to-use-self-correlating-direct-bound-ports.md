---
title: "如何使用自关联直接绑定端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: feb651fa-3e35-4598-b229-335448f6919c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b866d1042aed8abbb6441822e6bc7eda62254881
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-self-correlating-direct-bound-ports"></a><span data-ttu-id="e8935-102">如何使用自关联 Direct 绑定端口</span><span class="sxs-lookup"><span data-stu-id="e8935-102">How to Use Self-Correlating Direct Bound Ports</span></span>
<span data-ttu-id="e8935-103">自相关直接绑定端口是自引用的。</span><span class="sxs-lookup"><span data-stu-id="e8935-103">Self-correlating direct bound ports are self referential.</span></span> <span data-ttu-id="e8935-104">这表明自相关直接绑定端口提供了可用于将消息发送回其封闭业务流程的信息。</span><span class="sxs-lookup"><span data-stu-id="e8935-104">This means that a self-correlating direct bound port supplies the information that an orchestration can use to send messages back to its enclosing orchestration.</span></span> <span data-ttu-id="e8935-105">使用自相关直接绑定时，业务流程引擎对特定于业务流程实例的消息生成一个相关标记。</span><span class="sxs-lookup"><span data-stu-id="e8935-105">When using the self-correlating direct binding, the orchestration engine generates a correlation token on a message that is particular to the orchestration instance.</span></span> <span data-ttu-id="e8935-106">这提供了在不使用相关集的情况下将消息返回到特定业务流程实例的能力。</span><span class="sxs-lookup"><span data-stu-id="e8935-106">This provides the capability of getting messages back to a particular orchestration instance without using a correlation set.</span></span>  
  
 <span data-ttu-id="e8935-107">例如，你可以创建自通过指定相关业务流程 A 中的直接绑定的端口接收**直接**为**端口绑定**并选择**自助关联**在端口配置向导。</span><span class="sxs-lookup"><span data-stu-id="e8935-107">For example, you can create a receiving self-correlating direct bound port in Orchestration A by specifying **Direct** for **Port binding** and selecting **Self Correlating** in the Port Configuration Wizard.</span></span> <span data-ttu-id="e8935-108">然后，在业务流程 B 中，将某个端口声明为业务流程 A 中定义的具有相同端口类型的发送端口业务流程参数。为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e8935-108">Then, in Orchestration B, you declare a port as a Send Port Orchestration Parameter of the same port type as defined in Orchestration A. To do so, do the following:</span></span>  
  
1.  <span data-ttu-id="e8935-109">在业务流程视图窗口中，右键单击**业务流程参数**，然后单击**新端口参数**。</span><span class="sxs-lookup"><span data-stu-id="e8935-109">In the Orchestration View window, right-click **Orchestration Parameters**, and then click **New Port Parameter**.</span></span>  
  
2.  <span data-ttu-id="e8935-110">在属性窗口中，为**通信方向**，选择**发送**，和**端口类型**，选择相同的端口类型，如业务流程 A.中定义</span><span class="sxs-lookup"><span data-stu-id="e8935-110">In the Properties window, for **Communication Direction**, select **Send**, and for **Port Type**, select the same port type as defined in Orchestration A.</span></span>  
  
 <span data-ttu-id="e8935-111">该声明将在业务流程设计器中的端口图面上创建一个逻辑发送端口。</span><span class="sxs-lookup"><span data-stu-id="e8935-111">This declaration creates a logical send port on the Port Surface in Orchestration Designer.</span></span> <span data-ttu-id="e8935-112">业务流程 B 使用 orchestration A 调用**启动 Orchestration**形状并将新的端口作为参数，以及其他业务流程参数，传递给业务流程。 业务流程 B，然后执行其业务逻辑并向其传递的新端口上的消息发送。</span><span class="sxs-lookup"><span data-stu-id="e8935-112">Orchestration A calls Orchestration B using the **Start Orchestration** shape and passes the new port as a parameter, along with the other orchestration parameters, to Orchestration B. Orchestration B then performs its business logic and sends a message on the new port that was passed to it.</span></span> <span data-ttu-id="e8935-113">此消息发送到启动了业务流程 B 的业务流程 A 实例的用于接收的自相关直接绑定端口。</span><span class="sxs-lookup"><span data-stu-id="e8935-113">The message is sent to the receiving self-correlating direct bound port of the instance of Orchestration A that started Orchestration B.</span></span>  
  
 <span data-ttu-id="e8935-114">尽管也可以通过实现事件的上述顺序**调用 Orchestration**形状，它仅时有意义使用**启动 Orchestration**形状。</span><span class="sxs-lookup"><span data-stu-id="e8935-114">Although the preceding sequence of events can also be done with a **Call Orchestration** shape, it only makes sense when using a **Start Orchestration** shape.</span></span> <span data-ttu-id="e8935-115">这是因为使用时**调用 Orchestration**形状，端口按引用传递。</span><span class="sxs-lookup"><span data-stu-id="e8935-115">This is because when using a **Call Orchestration** shape, ports are passed by reference.</span></span> <span data-ttu-id="e8935-116">端口的极性在这两个业务流程中必须相同。</span><span class="sxs-lookup"><span data-stu-id="e8935-116">The polarity of the port must be same in both of the orchestrations.</span></span> <span data-ttu-id="e8935-117">因此，从一个业务流程中传入的端口的通信方向必须与所调用业务流程中端口引用的方向相同。</span><span class="sxs-lookup"><span data-stu-id="e8935-117">Therefore, the communication direction of the port you pass in from one orchestration must be the same as the direction of the port reference in the called orchestration.</span></span> <span data-ttu-id="e8935-118">但是，当使用**启动 Orchestration**形状，生成的业务流程异步实例化，而且不能包含**出**或**Ref**参数;因此，自关联直接绑定的端口提供为业务流程重新对其进行实例化的业务流程实例作出响应的方法。</span><span class="sxs-lookup"><span data-stu-id="e8935-118">However, when using the **Start Orchestration** shape, an asynchronous instantiation of an orchestration is generated and it cannot have **Out** or **Ref** parameters; therefore, the self-correlating direct bound port provides a way for an orchestration to respond back to the orchestration instance that instantiated it.</span></span>  
  
 <span data-ttu-id="e8935-119">如何使用自关联直接绑定的端口的示例，请参阅"实现的散点图和收集模式"中的 SDK 示例在[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="e8935-119">For an example of how to use self-correlating direct bound ports, see the SDK sample "Implementing Scatter and Gather Pattern" at [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8935-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8935-120">See Also</span></span>  
 <span data-ttu-id="e8935-121">[如何直接使用 MessageBox 绑定端口](../core/how-to-use-messagebox-direct-bound-ports.md) </span><span class="sxs-lookup"><span data-stu-id="e8935-121">[How to Use MessageBox Direct Bound Ports](../core/how-to-use-messagebox-direct-bound-ports.md) </span></span>  
 [<span data-ttu-id="e8935-122">如何直接使用合作伙伴业务流程绑定端口</span><span class="sxs-lookup"><span data-stu-id="e8935-122">How to Use Partner Orchestration Direct Bound Ports</span></span>](../core/how-to-use-partner-orchestration-direct-bound-ports.md)