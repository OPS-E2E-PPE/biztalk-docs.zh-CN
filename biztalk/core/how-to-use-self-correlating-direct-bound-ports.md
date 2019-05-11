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
ms.openlocfilehash: 4fb70074983ed41bb3d5397d08156b6db1201080
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383326"
---
# <a name="how-to-use-self-correlating-direct-bound-ports"></a><span data-ttu-id="a3e56-102">如何使用自相关直接绑定端口</span><span class="sxs-lookup"><span data-stu-id="a3e56-102">How to Use Self-Correlating Direct Bound Ports</span></span>
<span data-ttu-id="a3e56-103">自相关直接绑定的端口是自引用。</span><span class="sxs-lookup"><span data-stu-id="a3e56-103">Self-correlating direct bound ports are self referential.</span></span> <span data-ttu-id="a3e56-104">这意味着自相关直接绑定的端口提供了可用于将消息发送回其封闭的业务流程到业务流程的信息。</span><span class="sxs-lookup"><span data-stu-id="a3e56-104">This means that a self-correlating direct bound port supplies the information that an orchestration can use to send messages back to its enclosing orchestration.</span></span> <span data-ttu-id="a3e56-105">使用自相关直接绑定时，业务流程引擎将生成消息的特定于业务流程实例的相关的令牌。</span><span class="sxs-lookup"><span data-stu-id="a3e56-105">When using the self-correlating direct binding, the orchestration engine generates a correlation token on a message that is particular to the orchestration instance.</span></span> <span data-ttu-id="a3e56-106">这提供了将消息返回到特定的业务流程实例，而无需使用相关集的功能。</span><span class="sxs-lookup"><span data-stu-id="a3e56-106">This provides the capability of getting messages back to a particular orchestration instance without using a correlation set.</span></span>  
  
 <span data-ttu-id="a3e56-107">例如，可以创建自相关直接绑定的端口在业务流程 A 中通过指定接收**直接**有关**端口绑定**，然后选择**自相关**端口配置向导中。</span><span class="sxs-lookup"><span data-stu-id="a3e56-107">For example, you can create a receiving self-correlating direct bound port in Orchestration A by specifying **Direct** for **Port binding** and selecting **Self Correlating** in the Port Configuration Wizard.</span></span> <span data-ttu-id="a3e56-108">然后，在业务流程 B 中，声明为发送端口业务流程的参数相同的端口类型的端口在业务流程 A 中定义为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a3e56-108">Then, in Orchestration B, you declare a port as a Send Port Orchestration Parameter of the same port type as defined in Orchestration A. To do so, do the following:</span></span>  
  
1. <span data-ttu-id="a3e56-109">在业务流程视图窗口中，右键单击**业务流程参数**，然后单击**新建端口参数**。</span><span class="sxs-lookup"><span data-stu-id="a3e56-109">In the Orchestration View window, right-click **Orchestration Parameters**, and then click **New Port Parameter**.</span></span>  
  
2. <span data-ttu-id="a3e56-110">在属性窗口中的**通信方向**，选择**发送**，并为**端口类型**，选择相同的端口类型，如业务流程 A 中定义</span><span class="sxs-lookup"><span data-stu-id="a3e56-110">In the Properties window, for **Communication Direction**, select **Send**, and for **Port Type**, select the same port type as defined in Orchestration A.</span></span>  
  
   <span data-ttu-id="a3e56-111">此声明在业务流程设计器中的端口图面上创建逻辑发送端口。</span><span class="sxs-lookup"><span data-stu-id="a3e56-111">This declaration creates a logical send port on the Port Surface in Orchestration Designer.</span></span> <span data-ttu-id="a3e56-112">业务流程 A 调用业务流程 B 使用**启动业务流程**形状并将新端口作为参数，以及其他业务流程参数，传递给业务流程 b。 业务流程 B，然后执行其业务逻辑并将消息传递的新端口上向其发送。</span><span class="sxs-lookup"><span data-stu-id="a3e56-112">Orchestration A calls Orchestration B using the **Start Orchestration** shape and passes the new port as a parameter, along with the other orchestration parameters, to Orchestration B. Orchestration B then performs its business logic and sends a message on the new port that was passed to it.</span></span> <span data-ttu-id="a3e56-113">将消息发送到接收自相关直接绑定端口的实例的业务流程的启动业务流程 b。</span><span class="sxs-lookup"><span data-stu-id="a3e56-113">The message is sent to the receiving self-correlating direct bound port of the instance of Orchestration A that started Orchestration B.</span></span>  
  
   <span data-ttu-id="a3e56-114">尽管也可以使用实现事件的上述顺序**调用业务流程**形状，它仅使用时非常有用**启动业务流程**形状。</span><span class="sxs-lookup"><span data-stu-id="a3e56-114">Although the preceding sequence of events can also be done with a **Call Orchestration** shape, it only makes sense when using a **Start Orchestration** shape.</span></span> <span data-ttu-id="a3e56-115">这是因为使用时**调用业务流程**形状，端口按引用传递。</span><span class="sxs-lookup"><span data-stu-id="a3e56-115">This is because when using a **Call Orchestration** shape, ports are passed by reference.</span></span> <span data-ttu-id="a3e56-116">该端口的极性必须在两个业务流程相同。</span><span class="sxs-lookup"><span data-stu-id="a3e56-116">The polarity of the port must be same in both of the orchestrations.</span></span> <span data-ttu-id="a3e56-117">因此，从一个业务流程中传递的端口通信方向必须与调用的业务流程中的端口引用的方向相同。</span><span class="sxs-lookup"><span data-stu-id="a3e56-117">Therefore, the communication direction of the port you pass in from one orchestration must be the same as the direction of the port reference in the called orchestration.</span></span> <span data-ttu-id="a3e56-118">但是，使用时**启动业务流程**形状，生成的业务流程异步实例化，而且不能包含**Out**或**Ref**参数;因此，自相关直接绑定的端口提供业务流程将响应返回至其进行实例化的业务流程实例的方法。</span><span class="sxs-lookup"><span data-stu-id="a3e56-118">However, when using the **Start Orchestration** shape, an asynchronous instantiation of an orchestration is generated and it cannot have **Out** or **Ref** parameters; therefore, the self-correlating direct bound port provides a way for an orchestration to respond back to the orchestration instance that instantiated it.</span></span>  
  
   <span data-ttu-id="a3e56-119">有关如何使用自相关直接绑定的端口的示例，请参阅 SDK 示例"实现分散和收集模式"网址[ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="a3e56-119">For an example of how to use self-correlating direct bound ports, see the SDK sample "Implementing Scatter and Gather Pattern" at [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3e56-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3e56-120">See Also</span></span>  
 <span data-ttu-id="a3e56-121">[如何使用 MessageBox 直接绑定端口](../core/how-to-use-messagebox-direct-bound-ports.md) </span><span class="sxs-lookup"><span data-stu-id="a3e56-121">[How to Use MessageBox Direct Bound Ports](../core/how-to-use-messagebox-direct-bound-ports.md) </span></span>  
 [<span data-ttu-id="a3e56-122">如何使用合作伙伴业务流程直接绑定端口</span><span class="sxs-lookup"><span data-stu-id="a3e56-122">How to Use Partner Orchestration Direct Bound Ports</span></span>](../core/how-to-use-partner-orchestration-direct-bound-ports.md)