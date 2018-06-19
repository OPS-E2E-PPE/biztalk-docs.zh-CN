---
title: 创建 PeopleSoft HTTP 主机和端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP port
- HTTP host
ms.assetid: 3e1ce5fd-32ee-409f-b4c8-f2bc68470f17
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e673b2a2acdcd5248391f245ab990d424aefd298
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238109"
---
# <a name="creating-a-peoplesoft-http-host-and-port"></a><span data-ttu-id="69d5e-102">创建 PeopleSoft HTTP 主机和端口</span><span class="sxs-lookup"><span data-stu-id="69d5e-102">Creating a PeopleSoft HTTP Host and Port</span></span>
<span data-ttu-id="69d5e-103">PeopleSoft 中的消息发布体系结构称为 Integration Broker。</span><span class="sxs-lookup"><span data-stu-id="69d5e-103">The Message publication architecture in PeopleSoft is known as Integration Broker.</span></span> <span data-ttu-id="69d5e-104">Integration Broker 的主要组件如下所示：</span><span class="sxs-lookup"><span data-stu-id="69d5e-104">The main components of Integration Broker are as follows:</span></span>  
  
-   <span data-ttu-id="69d5e-105">网关</span><span class="sxs-lookup"><span data-stu-id="69d5e-105">Gateway</span></span>  
  
-   <span data-ttu-id="69d5e-106">发布节点</span><span class="sxs-lookup"><span data-stu-id="69d5e-106">Publishing node</span></span>  
  
-   <span data-ttu-id="69d5e-107">订户节点</span><span class="sxs-lookup"><span data-stu-id="69d5e-107">Subscriber node</span></span>  
  
 <span data-ttu-id="69d5e-108">这三个组件协同工作将消息发布到 HTTP 侦听器的 URL。</span><span class="sxs-lookup"><span data-stu-id="69d5e-108">All three work together to publish a message to a URL for an HTTP listener.</span></span> <span data-ttu-id="69d5e-109">您必须设置发布节点。</span><span class="sxs-lookup"><span data-stu-id="69d5e-109">You must set the Publishing node.</span></span> <span data-ttu-id="69d5e-110">PeopleSoft 有一个默认发布节点，也称为本地消息节点。</span><span class="sxs-lookup"><span data-stu-id="69d5e-110">PeopleSoft has a default publishing node, also known as local message node.</span></span> <span data-ttu-id="69d5e-111">您必须激活该节点和发布节点事务。</span><span class="sxs-lookup"><span data-stu-id="69d5e-111">You must activate the node and the transactions for the publishing node.</span></span> <span data-ttu-id="69d5e-112">您必须将订阅节点的类型设置为外部节点，然后激活该节点和事务。</span><span class="sxs-lookup"><span data-stu-id="69d5e-112">You must set the Subscription node with the type as external node, and then activate the node and the transactions.</span></span> <span data-ttu-id="69d5e-113">对于该节点，也可以将类型设置为 HTTP 并设置连接信息。</span><span class="sxs-lookup"><span data-stu-id="69d5e-113">For this node, you also set the type to be HTTP and set the connection information.</span></span>  
  
 <span data-ttu-id="69d5e-114">可使用 PeopleSoft Integration Broker 创建 PeopleSoft 用来发送事件的 PeopleSoft HTTP 主机和端口。</span><span class="sxs-lookup"><span data-stu-id="69d5e-114">You use PeopleSoft Integration Broker to create a PeopleSoft HTTP Host and Port where PeopleSoft sends events.</span></span> <span data-ttu-id="69d5e-115">请确保该消息通过使用中的过程是活动和路由[如何验证消息的活动状态](../core/how-to-verify-activity-status-of-a-message.md)。</span><span class="sxs-lookup"><span data-stu-id="69d5e-115">You make sure that the message is active and routed by using the procedure in [How to Verify Activity Status of a Message](../core/how-to-verify-activity-status-of-a-message.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69d5e-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="69d5e-116">In This Section</span></span>  
  
-   [<span data-ttu-id="69d5e-117">如何验证消息的活动状态</span><span class="sxs-lookup"><span data-stu-id="69d5e-117">How to Verify Activity Status of a Message</span></span>](../core/how-to-verify-activity-status-of-a-message.md)  
  
-   [<span data-ttu-id="69d5e-118">如何配置集成网关和 HTTP 输出连接器</span><span class="sxs-lookup"><span data-stu-id="69d5e-118">How to Configure the Integration Gateway and HTTP Output Connector</span></span>](../core/how-to-configure-the-integration-gateway-and-http-output-connector.md)  
  
-   [<span data-ttu-id="69d5e-119">如何创建新的网关节点</span><span class="sxs-lookup"><span data-stu-id="69d5e-119">How to Create a New Gateway Node</span></span>](../core/how-to-create-a-new-gateway-node.md)  
  
-   [<span data-ttu-id="69d5e-120">如何添加事务</span><span class="sxs-lookup"><span data-stu-id="69d5e-120">How to Add a Transaction</span></span>](../core/how-to-add-a-transaction.md)  
  
-   [<span data-ttu-id="69d5e-121">如何测试 HTTP 节点</span><span class="sxs-lookup"><span data-stu-id="69d5e-121">How to Test the HTTP Node</span></span>](../core/how-to-test-the-http-node.md)