---
title: "进程内的接口接收适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ed668d9-7512-4026-a8f3-df05aeed4df6
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7135471700cf640f61b56506ad159b5c47c7d877
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-an-in-process-receive-adapter"></a><span data-ttu-id="184a5-102">进程内的接口接收适配器</span><span class="sxs-lookup"><span data-stu-id="184a5-102">Interfaces for an In-Process Receive Adapter</span></span>
<span data-ttu-id="184a5-103">消息引擎实例化和配置进程内适配器，并且传入传输代理以便允许适配器访问其功能。</span><span class="sxs-lookup"><span data-stu-id="184a5-103">The Messaging Engine instantiates and configures in-process adapters, passing in the transport proxy to allow the adapter to access its functionality.</span></span> <span data-ttu-id="184a5-104">若要启用对传输代理的配置和绑定，适配器必须实现以下配置接口：</span><span class="sxs-lookup"><span data-stu-id="184a5-104">To enable configuration and binding to the transport proxy, adapters must implement the following configuration interfaces:</span></span>  
  
-   <span data-ttu-id="184a5-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="184a5-105">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="184a5-106">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="184a5-106">**IBTTransportControl**</span></span>  
  
-   <span data-ttu-id="184a5-107">**IBTTransportConfig**</span><span class="sxs-lookup"><span data-stu-id="184a5-107">**IBTTransportConfig**</span></span>  
  
-   <span data-ttu-id="184a5-108">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="184a5-108">**IBaseComponent**</span></span>  
  
 <span data-ttu-id="184a5-109">（可选） 如果适配器想要接收处理程序信息在初始化过程中它需要实现**IPersistPropertyBag**。</span><span class="sxs-lookup"><span data-stu-id="184a5-109">Optionally if the adapter wants to receive handler information during initialization it needs to implement **IPersistPropertyBag**.</span></span>  
  
 <span data-ttu-id="184a5-110">消息引擎将创建适配器的某一实例、初始化该实例并设置接收位置配置。</span><span class="sxs-lookup"><span data-stu-id="184a5-110">The Messaging Engine creates an instance of an adapter, initializes it, and sets the configuration of receive locations.</span></span> <span data-ttu-id="184a5-111">The Messaging Engine 传送给适配器上的属性包**AddReceiveEndpoint**方法调用。</span><span class="sxs-lookup"><span data-stu-id="184a5-111">The Messaging Engine passes a property bag to an adapter on the **AddReceiveEndpoint** method call.</span></span> <span data-ttu-id="184a5-112">该属性包包含接收位置和接收处理程序的配置。</span><span class="sxs-lookup"><span data-stu-id="184a5-112">The property bag contains the configuration for the receive location and receive handler.</span></span> <span data-ttu-id="184a5-113">该配置以 XML 样式的属性包形式存储于数据库中。</span><span class="sxs-lookup"><span data-stu-id="184a5-113">The configuration is stored in the database in the form of an XML-styled property bag.</span></span> <span data-ttu-id="184a5-114">消息引擎读取 XML 并从 XML 解除冻结属性包。</span><span class="sxs-lookup"><span data-stu-id="184a5-114">The Messaging Engine reads the XML and rehydrates a property bag from the XML.</span></span> <span data-ttu-id="184a5-115">在添加至少一个终结点（接收位置）后，该适配器可以开始提交消息。</span><span class="sxs-lookup"><span data-stu-id="184a5-115">After at least one endpoint (receive location) is added, the adapter can start submitting messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="184a5-116">适配器应不会阻止 Messaging Engine 如调用**IBTTransportControl.Initialize**， **IPersistPropertyBag.Load**，和**IBTTransportConfig.AddReceiveEndpoint**.</span><span class="sxs-lookup"><span data-stu-id="184a5-116">Adapters should not block Messaging Engine calls such as **IBTTransportControl.Initialize**, **IPersistPropertyBag.Load**, and **IBTTransportConfig.AddReceiveEndpoint**.</span></span> <span data-ttu-id="184a5-117">执行过多的处理中这些调用将会影响服务启动时间。</span><span class="sxs-lookup"><span data-stu-id="184a5-117">Performing excessive processing in these calls will affect service startup time.</span></span>  
  
 <span data-ttu-id="184a5-118">下图显示在创建进程内接收适配器时涉及的对象交互。</span><span class="sxs-lookup"><span data-stu-id="184a5-118">The following figure shows the object interactions involved in creating an in-process receive adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter11.gif "ebiz_sdk_devadapter11")  
<span data-ttu-id="184a5-119">进程内接收适配器的工作流</span><span class="sxs-lookup"><span data-stu-id="184a5-119">Workflow for an in-process receive adapter</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="184a5-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="184a5-120">See Also</span></span>  
 <span data-ttu-id="184a5-121">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="184a5-121">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="184a5-122">[开发接收适配器](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="184a5-122">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="184a5-123">[实例化和初始化接收适配器](../core/instantiating-and-initializing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="184a5-123">[Instantiating and Initializing a Receive Adapter](../core/instantiating-and-initializing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="184a5-124">[一个独立的接口接收适配器](../core/interfaces-for-an-isolated-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="184a5-124">[Interfaces for an Isolated Receive Adapter](../core/interfaces-for-an-isolated-receive-adapter.md) </span></span>  
 <span data-ttu-id="184a5-125">[批处理支持的接口接收适配器](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="184a5-125">[Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span></span>  
 <span data-ttu-id="184a5-126">[批处理支持为一个事务性接口接收适配器](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="184a5-126">[Interfaces for a Transactional Batch-Supported Receive Adapter](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md) </span></span>  
 [<span data-ttu-id="184a5-127">接口同步请求-响应接收适配器</span><span class="sxs-lookup"><span data-stu-id="184a5-127">Interfaces for a Synchronous Request-Response Receive Adapter</span></span>](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)