---
title: "实例化隔离的适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b8359a3-b098-4bb6-87b4-d3432d2671b1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e3090252f63221547604a4fdf88388bcbf8296f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="instantiating-isolated-adapters"></a><span data-ttu-id="8e6ec-102">实例化隔离的适配器</span><span class="sxs-lookup"><span data-stu-id="8e6ec-102">Instantiating Isolated Adapters</span></span>
<span data-ttu-id="8e6ec-103">如前面所述，由 BizTalk Server 未实例化隔离的适配器。</span><span class="sxs-lookup"><span data-stu-id="8e6ec-103">As discussed earlier, isolated adapters are not instantiated by BizTalk Server.</span></span> <span data-ttu-id="8e6ec-104">而是在另一个进程中实例化并以此进程为宿主。</span><span class="sxs-lookup"><span data-stu-id="8e6ec-104">Rather, they are instantiated and hosted in another process.</span></span> <span data-ttu-id="8e6ec-105">负责创建其传输代理的适配器**QueryInterface**，为**IBTTransportProxy**，然后调用**IBTTransportProxy**。**RegisterIsolatedReceiver**注册消息引擎。</span><span class="sxs-lookup"><span data-stu-id="8e6ec-105">It is the responsibility of the adapter to create its transport proxy, **QueryInterface**, for **IBTTransportProxy**, and then call **IBTTransportProxy**.**RegisterIsolatedReceiver** to register with the Messaging Engine.</span></span>  
  
 <span data-ttu-id="8e6ec-106">重新注册需要其配置和启用的适配器传递一个接收到消息引擎的位置。</span><span class="sxs-lookup"><span data-stu-id="8e6ec-106">Registration requires that the adapter pass one of its configured and enabled receive locations to the Messaging Engine.</span></span> <span data-ttu-id="8e6ec-107">适配器的主机进程凭据必须是 BizTalk 隔离主机用户组的成员。</span><span class="sxs-lookup"><span data-stu-id="8e6ec-107">The adapter's host process credentials must be a member of the BizTalk Isolated Host Users group.</span></span> <span data-ttu-id="8e6ec-108">只需使用模拟此处是不够的除非用户是该组的成员。</span><span class="sxs-lookup"><span data-stu-id="8e6ec-108">Simply using impersonation here is insufficient unless the user is a member of that group.</span></span> <span data-ttu-id="8e6ec-109">此外，该适配器将查询以确保它具有正确**ClassID**并且为该主机实例已配置的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="8e6ec-109">In addition, the adapter is queried to ensure it has the correct **ClassID** and is running on the computer that was configured for that host instance.</span></span> <span data-ttu-id="8e6ec-110">适配器已成功向其传输代理注册后，将其配置发送给它使用通过调用的 Load 方法**IPersistPropertyBag**接口。</span><span class="sxs-lookup"><span data-stu-id="8e6ec-110">After the adapter has successfully registered with its transport proxy, its configuration is sent to it using by calling the Load method of the **IPersistPropertyBag** interface.</span></span>  
  
 <span data-ttu-id="8e6ec-111">下图说明了这一序列的 API 调用。</span><span class="sxs-lookup"><span data-stu-id="8e6ec-111">The following figure illustrates this sequence of API calls.</span></span> <span data-ttu-id="8e6ec-112">以蓝色表示接口实现的适配器。</span><span class="sxs-lookup"><span data-stu-id="8e6ec-112">The interfaces in blue are implemented by the adapter.</span></span>  
  
 ![](../core/media/isolated-adapter-init.gif "Isolated_adapter_init")  
  
 <span data-ttu-id="8e6ec-113">下面的代码片段阐释了注册 API 调用：</span><span class="sxs-lookup"><span data-stu-id="8e6ec-113">The following code fragment illustrates the registration API calls:</span></span>  
  
```  
using Microsoft.BizTalk.TransportProxy.Interop;  
using Microsoft.BizTalk.Component.Interop;  
using Microsoft.BizTalk.Message.Interop;  
  
public class MyAdapter : IBTTransport,   
 IBTTransportConfig,   
 IBTTransportControl,   
 IBaseComponent  
{  
...  
private IBTTransportProxy transportProxy;  
  
 public void Register(string uri)  
 {  
 // Create the Transport Proxy...  
 this.transportProxy =   
 (IBTTransportProxy)new BTTransportProxy();  
  
// Register on of the adapters uri’s with the TP  
 this.transportProxy.RegisterIsolatedReceiver(  
 uri,   
 (IBTTransportConfig)this );  
 }  
}  
```  
  
 <span data-ttu-id="8e6ec-114">**实现提示：**建议适配器保留工作正在进行的计数。</span><span class="sxs-lookup"><span data-stu-id="8e6ec-114">**Implementation Tip:** We recommend that the adapter keep a count of the work in progress.</span></span> <span data-ttu-id="8e6ec-115">适配器应阻止**终止**直到消息计数已达到零。</span><span class="sxs-lookup"><span data-stu-id="8e6ec-115">The adapter should block **Terminate** until the message count has reached zero.</span></span> <span data-ttu-id="8e6ec-116">在接收端此工作包括尚未发布到 BizTalk Server 任何未完成的请求。</span><span class="sxs-lookup"><span data-stu-id="8e6ec-116">On the receive side this work includes any outstanding requests that have not been published to BizTalk Server.</span></span> <span data-ttu-id="8e6ec-117">响应消息还未发送到接收适配器后**终止**已调用。</span><span class="sxs-lookup"><span data-stu-id="8e6ec-117">Response messages are not delivered to a receive adapter after **Terminate** has been called.</span></span>  
  
 <span data-ttu-id="8e6ec-118">对于发送适配器，应适当地处理正在进行的消息。</span><span class="sxs-lookup"><span data-stu-id="8e6ec-118">For send adapters, messages that are in progress should be handled appropriately.</span></span> <span data-ttu-id="8e6ec-119">这意味着应从要阻止不止一次发送消息的适配器的私有应用程序消息队列中删除已成功传递的任何消息。</span><span class="sxs-lookup"><span data-stu-id="8e6ec-119">This means any message that was successfully delivered should be deleted from the adapter's private application message queue to prevent messages from being sent more than once.</span></span>  
  
 <span data-ttu-id="8e6ec-120">后**终止**称为 the Messaging Engine 不接受请求以发布新消息，但对于请求-响应对响应消息除外。</span><span class="sxs-lookup"><span data-stu-id="8e6ec-120">After **Terminate** is called the Messaging Engine does not accept requests to publish new messages, with the exception of response messages for solicit-response pairs.</span></span>