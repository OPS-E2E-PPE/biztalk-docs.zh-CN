---
title: OrderBroker 和 OrderManager 之间的通信 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, publishing [MessageBox database]
- MessageBox database, publishing
ms.assetid: 1b77dcd2-f7a5-4013-b9a2-c06ace161792
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f438b0dfe744aae5867943f4b1493bb163994f4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231869"
---
# <a name="communication-between-orderbroker-and-ordermanager"></a><span data-ttu-id="625d9-102">OrderBroker 和 OrderManager 之间的通信</span><span class="sxs-lookup"><span data-stu-id="625d9-102">Communication between OrderBroker and OrderManager</span></span>
<span data-ttu-id="625d9-103">顺序 broker 和顺序 manager 业务流程 (**OrderBroker**， **OrderManager**) 通过 MessageBox 数据库，而不是直接合作伙伴绑定进行通信。</span><span class="sxs-lookup"><span data-stu-id="625d9-103">The order broker and the order manager orchestrations (**OrderBroker**, **OrderManager**) communicate through the MessageBox database rather than being direct partner bound.</span></span> <span data-ttu-id="625d9-104">这可确保，在以便它们，如有必要，可以在不同的 BizTalk 组和地理位置的位置所在松散耦合的代理和管理器。</span><span class="sxs-lookup"><span data-stu-id="625d9-104">This ensures that the broker and manager are loosely coupled so that they can, if necessary, be located in separate BizTalk groups and in geographically-separated locations.</span></span> <span data-ttu-id="625d9-105">分隔这种方式的业务流程需要仅管理配置，并不需要的任何代码更改。</span><span class="sxs-lookup"><span data-stu-id="625d9-105">Separating the orchestrations this way requires only administrative configuration and does not require any code changes.</span></span>  
  
 <span data-ttu-id="625d9-106">在解决方案中为当前配置，顺序 broker 将消息标记为特定的顺序管理器，并将它们发送到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="625d9-106">In the solution as presently configured, the order broker marks messages for a particular order manager and sends them to the MessageBox.</span></span> <span data-ttu-id="625d9-107">反过来，订单管理器为适用于它的消息筛选器，并从 MessageBox 所需的这些消息。</span><span class="sxs-lookup"><span data-stu-id="625d9-107">In turn, the order manager filters for messages intended for it and takes those messages from the MessageBox.</span></span> <span data-ttu-id="625d9-108">这种间接方式 — 通过 MessageBox 通信，而不是直接绑定-可以轻松地移动到单独的组的代理和管理器。</span><span class="sxs-lookup"><span data-stu-id="625d9-108">This indirection—communicating through the MessageBox rather than direct binding—makes it easy to move the broker and manager to separate groups.</span></span>  
  
 <span data-ttu-id="625d9-109">如果没有负责维护的代理和管理器的不同组，或者如果它们需要处于不同的地理位置，设计可以轻松地适应这。</span><span class="sxs-lookup"><span data-stu-id="625d9-109">If there are different groups responsible for maintaining the broker and manager or if they need to be in geographically separate locations, the design makes it easy to accommodate this.</span></span> <span data-ttu-id="625d9-110">你需要执行操作的只是将业务流程移到不同的 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="625d9-110">All you need to do is move the orchestrations to different BizTalk groups.</span></span> <span data-ttu-id="625d9-111">业务流程都位于不同的组后，重新连接它们只需创建端口。</span><span class="sxs-lookup"><span data-stu-id="625d9-111">After the orchestrations are in separate groups, reconnecting them only requires creating ports.</span></span> <span data-ttu-id="625d9-112">在顺序 broker 组中，你必须创建具有相同筛选器设置为顺序管理器中，但，将消息转发到新组发送端口。</span><span class="sxs-lookup"><span data-stu-id="625d9-112">In the order broker group, you must create a send port that has the same filter as the order manager, but that forwards the message to the new group.</span></span> <span data-ttu-id="625d9-113">在订单管理器组中，你必须创建接收端口接收消息并将其放在 MessageBox 数据库中。</span><span class="sxs-lookup"><span data-stu-id="625d9-113">In the order manager group, you must create a receive port that receives the message and puts it in the MessageBox database.</span></span>  
  
 <span data-ttu-id="625d9-114">你可以通过导出创建 MSI 文件，每个代理和管理器用于移动应用程序。</span><span class="sxs-lookup"><span data-stu-id="625d9-114">You can move the applications by exporting them to create MSI files, one each for the broker and manager.</span></span> <span data-ttu-id="625d9-115">有关导出应用程序的详细信息，请参阅[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="625d9-115">For more information about exporting applications, see [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="625d9-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="625d9-116">See Also</span></span>  
 [<span data-ttu-id="625d9-117">实现突出显示的业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="625d9-117">Implementation Highlights of the Business Process Management Solution</span></span>](../core/implementation-highlights-of-the-business-process-management-solution.md)