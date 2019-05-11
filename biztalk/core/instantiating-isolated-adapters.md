---
title: 实例化独立的适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b8359a3-b098-4bb6-87b4-d3432d2671b1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89f534ab91f940a179c765fba6f109a9da6df5ae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331835"
---
# <a name="instantiating-isolated-adapters"></a><span data-ttu-id="aabd6-102">实例化独立的适配器</span><span class="sxs-lookup"><span data-stu-id="aabd6-102">Instantiating Isolated Adapters</span></span>
<span data-ttu-id="aabd6-103">如前面所述，独立的适配器是通过 BizTalk Server 未实例化。</span><span class="sxs-lookup"><span data-stu-id="aabd6-103">As discussed earlier, isolated adapters are not instantiated by BizTalk Server.</span></span> <span data-ttu-id="aabd6-104">相反，它们是实例化，在另一个进程中托管。</span><span class="sxs-lookup"><span data-stu-id="aabd6-104">Rather, they are instantiated and hosted in another process.</span></span> <span data-ttu-id="aabd6-105">若要创建其传输代理的适配器负责**QueryInterface**，对于**IBTTransportProxy**，然后调用**IBTTransportProxy**。**RegisterIsolatedReceiver**向消息引擎注册。</span><span class="sxs-lookup"><span data-stu-id="aabd6-105">It is the responsibility of the adapter to create its transport proxy, **QueryInterface**, for **IBTTransportProxy**, and then call **IBTTransportProxy**.**RegisterIsolatedReceiver** to register with the Messaging Engine.</span></span>  
  
 <span data-ttu-id="aabd6-106">注册需要适配器传递一个其配置和启用的接收到消息引擎的位置。</span><span class="sxs-lookup"><span data-stu-id="aabd6-106">Registration requires that the adapter pass one of its configured and enabled receive locations to the Messaging Engine.</span></span> <span data-ttu-id="aabd6-107">适配器的主机进程凭据必须是 BizTalk Isolated Host Users 组的成员。</span><span class="sxs-lookup"><span data-stu-id="aabd6-107">The adapter's host process credentials must be a member of the BizTalk Isolated Host Users group.</span></span> <span data-ttu-id="aabd6-108">只需在此处使用模拟是不够的除非用户是该组的成员。</span><span class="sxs-lookup"><span data-stu-id="aabd6-108">Simply using impersonation here is insufficient unless the user is a member of that group.</span></span> <span data-ttu-id="aabd6-109">此外，查询该适配器以确保它具有正确**ClassID**和已配置为该主机实例的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="aabd6-109">In addition, the adapter is queried to ensure it has the correct **ClassID** and is running on the computer that was configured for that host instance.</span></span> <span data-ttu-id="aabd6-110">向其传输代理，该适配器已成功注册后，将其配置发送给它使用通过调用 Load 方法**IPersistPropertyBag**接口。</span><span class="sxs-lookup"><span data-stu-id="aabd6-110">After the adapter has successfully registered with its transport proxy, its configuration is sent to it using by calling the Load method of the **IPersistPropertyBag** interface.</span></span>  
  
 <span data-ttu-id="aabd6-111">下图说明了这一序列的 API 调用。</span><span class="sxs-lookup"><span data-stu-id="aabd6-111">The following figure illustrates this sequence of API calls.</span></span> <span data-ttu-id="aabd6-112">蓝色的接口由适配器实现。</span><span class="sxs-lookup"><span data-stu-id="aabd6-112">The interfaces in blue are implemented by the adapter.</span></span>  
  
 <span data-ttu-id="aabd6-113">![](../core/media/isolated-adapter-init.gif "Isolated_adapter_init")</span><span class="sxs-lookup"><span data-stu-id="aabd6-113">![](../core/media/isolated-adapter-init.gif "Isolated_adapter_init")</span></span>  
  
 <span data-ttu-id="aabd6-114">下面的代码段演示如何注册 API 调用：</span><span class="sxs-lookup"><span data-stu-id="aabd6-114">The following code fragment illustrates the registration API calls:</span></span>  
  
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
  
 <span data-ttu-id="aabd6-115">**实现提示：** 我们建议适配器对正在进行的工作的计数。</span><span class="sxs-lookup"><span data-stu-id="aabd6-115">**Implementation Tip:** We recommend that the adapter keep a count of the work in progress.</span></span> <span data-ttu-id="aabd6-116">适配器应该一直阻止**Terminate**直到消息计数归零。</span><span class="sxs-lookup"><span data-stu-id="aabd6-116">The adapter should block **Terminate** until the message count has reached zero.</span></span> <span data-ttu-id="aabd6-117">在接收端这项工作包括尚未发布到 BizTalk Server 的任何未完成请求。</span><span class="sxs-lookup"><span data-stu-id="aabd6-117">On the receive side this work includes any outstanding requests that have not been published to BizTalk Server.</span></span> <span data-ttu-id="aabd6-118">响应消息不传送给接收适配器后**Terminate**已调用。</span><span class="sxs-lookup"><span data-stu-id="aabd6-118">Response messages are not delivered to a receive adapter after **Terminate** has been called.</span></span>  
  
 <span data-ttu-id="aabd6-119">对于发送适配器，应适当地处理正在进行中的消息。</span><span class="sxs-lookup"><span data-stu-id="aabd6-119">For send adapters, messages that are in progress should be handled appropriately.</span></span> <span data-ttu-id="aabd6-120">这意味着应从要阻止消息多次发送适配器的专用应用程序消息队列中删除已成功传递任何消息。</span><span class="sxs-lookup"><span data-stu-id="aabd6-120">This means any message that was successfully delivered should be deleted from the adapter's private application message queue to prevent messages from being sent more than once.</span></span>  
  
 <span data-ttu-id="aabd6-121">之后**Terminate**调用消息引擎不接受请求发布新消息，但要求-响应对的响应消息除外。</span><span class="sxs-lookup"><span data-stu-id="aabd6-121">After **Terminate** is called the Messaging Engine does not accept requests to publish new messages, with the exception of response messages for solicit-response pairs.</span></span>