---
title: 接收适配器的进程内的接口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ed668d9-7512-4026-a8f3-df05aeed4df6
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d608f9e511b1a3cb0ba94f30fbe3cd1eb7c9e87
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965862"
---
# <a name="interfaces-for-an-in-process-receive-adapter"></a><span data-ttu-id="ed64d-102">接收适配器的进程内的接口</span><span class="sxs-lookup"><span data-stu-id="ed64d-102">Interfaces for an In-Process Receive Adapter</span></span>
<span data-ttu-id="ed64d-103">消息引擎实例化和配置进程内适配器，并且传入传输代理以便允许适配器访问其功能。</span><span class="sxs-lookup"><span data-stu-id="ed64d-103">The Messaging Engine instantiates and configures in-process adapters, passing in the transport proxy to allow the adapter to access its functionality.</span></span> <span data-ttu-id="ed64d-104">若要启用对传输代理的配置和绑定，适配器必须实现以下配置接口：</span><span class="sxs-lookup"><span data-stu-id="ed64d-104">To enable configuration and binding to the transport proxy, adapters must implement the following configuration interfaces:</span></span>  
  
- <span data-ttu-id="ed64d-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="ed64d-105">**IBTTransport**</span></span>  
  
- <span data-ttu-id="ed64d-106">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="ed64d-106">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="ed64d-107">**IBTTransportConfig**</span><span class="sxs-lookup"><span data-stu-id="ed64d-107">**IBTTransportConfig**</span></span>  
  
- <span data-ttu-id="ed64d-108">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="ed64d-108">**IBaseComponent**</span></span>  
  
  <span data-ttu-id="ed64d-109">（可选） 如果适配器想要接收处理程序信息在初始化过程中它需要实现**IPersistPropertyBag**。</span><span class="sxs-lookup"><span data-stu-id="ed64d-109">Optionally if the adapter wants to receive handler information during initialization it needs to implement **IPersistPropertyBag**.</span></span>  
  
  <span data-ttu-id="ed64d-110">消息引擎将创建适配器的某一实例、初始化该实例并设置接收位置配置。</span><span class="sxs-lookup"><span data-stu-id="ed64d-110">The Messaging Engine creates an instance of an adapter, initializes it, and sets the configuration of receive locations.</span></span> <span data-ttu-id="ed64d-111">消息引擎将属性包传递给适配器**AddReceiveEndpoint**方法调用。</span><span class="sxs-lookup"><span data-stu-id="ed64d-111">The Messaging Engine passes a property bag to an adapter on the **AddReceiveEndpoint** method call.</span></span> <span data-ttu-id="ed64d-112">该属性包包含接收位置和接收处理程序的配置。</span><span class="sxs-lookup"><span data-stu-id="ed64d-112">The property bag contains the configuration for the receive location and receive handler.</span></span> <span data-ttu-id="ed64d-113">该配置以 XML 样式的属性包形式存储于数据库中。</span><span class="sxs-lookup"><span data-stu-id="ed64d-113">The configuration is stored in the database in the form of an XML-styled property bag.</span></span> <span data-ttu-id="ed64d-114">消息引擎读取 XML 并从 XML 解除冻结属性包。</span><span class="sxs-lookup"><span data-stu-id="ed64d-114">The Messaging Engine reads the XML and rehydrates a property bag from the XML.</span></span> <span data-ttu-id="ed64d-115">在添加至少一个终结点（接收位置）后，该适配器可以开始提交消息。</span><span class="sxs-lookup"><span data-stu-id="ed64d-115">After at least one endpoint (receive location) is added, the adapter can start submitting messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed64d-116">适配器应不会阻止消息引擎调用如**IBTTransportControl.Initialize**， **ipersistpropertybag.load 这样**，和**IBTTransportConfig.AddReceiveEndpoint**.</span><span class="sxs-lookup"><span data-stu-id="ed64d-116">Adapters should not block Messaging Engine calls such as **IBTTransportControl.Initialize**, **IPersistPropertyBag.Load**, and **IBTTransportConfig.AddReceiveEndpoint**.</span></span> <span data-ttu-id="ed64d-117">执行过多的处理中这些调用将会影响服务启动时间。</span><span class="sxs-lookup"><span data-stu-id="ed64d-117">Performing excessive processing in these calls will affect service startup time.</span></span>  
  
 <span data-ttu-id="ed64d-118">下图显示在创建进程内接收适配器时涉及的对象交互。</span><span class="sxs-lookup"><span data-stu-id="ed64d-118">The following figure shows the object interactions involved in creating an in-process receive adapter.</span></span>  
  
 <span data-ttu-id="ed64d-119">![](../core/media/ebiz-sdk-devadapter11.gif "ebiz_sdk_devadapter11")</span><span class="sxs-lookup"><span data-stu-id="ed64d-119">![](../core/media/ebiz-sdk-devadapter11.gif "ebiz_sdk_devadapter11")</span></span>  
<span data-ttu-id="ed64d-120">进程内接收适配器的工作流</span><span class="sxs-lookup"><span data-stu-id="ed64d-120">Workflow for an in-process receive adapter</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed64d-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed64d-121">See Also</span></span>  
 <span data-ttu-id="ed64d-122">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="ed64d-122">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="ed64d-123">[开发接收适配器](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="ed64d-123">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="ed64d-124">[实例化和初始化接收适配器](../core/instantiating-and-initializing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="ed64d-124">[Instantiating and Initializing a Receive Adapter](../core/instantiating-and-initializing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="ed64d-125">[接口独立接收适配器](../core/interfaces-for-an-isolated-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="ed64d-125">[Interfaces for an Isolated Receive Adapter](../core/interfaces-for-an-isolated-receive-adapter.md) </span></span>  
 <span data-ttu-id="ed64d-126">[接收适配器的支持批的接口](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="ed64d-126">[Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span></span>  
 <span data-ttu-id="ed64d-127">[接收适配器的接口的事务性批处理支持](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="ed64d-127">[Interfaces for a Transactional Batch-Supported Receive Adapter](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md) </span></span>  
 [<span data-ttu-id="ed64d-128">同步请求-响应接收适配器的接口</span><span class="sxs-lookup"><span data-stu-id="ed64d-128">Interfaces for a Synchronous Request-Response Receive Adapter</span></span>](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)