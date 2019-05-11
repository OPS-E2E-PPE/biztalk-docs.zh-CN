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
ms.openlocfilehash: 1a222f41d28b57053c192db3235e2fa7f4f710ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381732"
---
# <a name="interfaces-for-an-in-process-receive-adapter"></a><span data-ttu-id="64ce3-102">接收适配器的进程内的接口</span><span class="sxs-lookup"><span data-stu-id="64ce3-102">Interfaces for an In-Process Receive Adapter</span></span>
<span data-ttu-id="64ce3-103">消息引擎实例化和配置进程内适配器，并且传入传输代理以便允许适配器访问其功能。</span><span class="sxs-lookup"><span data-stu-id="64ce3-103">The Messaging Engine instantiates and configures in-process adapters, passing in the transport proxy to allow the adapter to access its functionality.</span></span> <span data-ttu-id="64ce3-104">若要启用配置和绑定到传输代理，适配器必须实现以下配置接口：</span><span class="sxs-lookup"><span data-stu-id="64ce3-104">To enable configuration and binding to the transport proxy, adapters must implement the following configuration interfaces:</span></span>  
  
- <span data-ttu-id="64ce3-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="64ce3-105">**IBTTransport**</span></span>  
  
- <span data-ttu-id="64ce3-106">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="64ce3-106">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="64ce3-107">**IBTTransportConfig**</span><span class="sxs-lookup"><span data-stu-id="64ce3-107">**IBTTransportConfig**</span></span>  
  
- <span data-ttu-id="64ce3-108">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="64ce3-108">**IBaseComponent**</span></span>  
  
  <span data-ttu-id="64ce3-109">（可选） 如果适配器想要接收处理程序信息在初始化过程中它需要实现**IPersistPropertyBag**。</span><span class="sxs-lookup"><span data-stu-id="64ce3-109">Optionally if the adapter wants to receive handler information during initialization it needs to implement **IPersistPropertyBag**.</span></span>  
  
  <span data-ttu-id="64ce3-110">消息引擎创建的适配器实例，初始化它，并设置的配置接收位置。</span><span class="sxs-lookup"><span data-stu-id="64ce3-110">The Messaging Engine creates an instance of an adapter, initializes it, and sets the configuration of receive locations.</span></span> <span data-ttu-id="64ce3-111">消息引擎将属性包传递给适配器**AddReceiveEndpoint**方法调用。</span><span class="sxs-lookup"><span data-stu-id="64ce3-111">The Messaging Engine passes a property bag to an adapter on the **AddReceiveEndpoint** method call.</span></span> <span data-ttu-id="64ce3-112">属性包包含接收位置和接收处理程序的配置。</span><span class="sxs-lookup"><span data-stu-id="64ce3-112">The property bag contains the configuration for the receive location and receive handler.</span></span> <span data-ttu-id="64ce3-113">配置存储在数据库中的 XML 样式的属性包形式。</span><span class="sxs-lookup"><span data-stu-id="64ce3-113">The configuration is stored in the database in the form of an XML-styled property bag.</span></span> <span data-ttu-id="64ce3-114">消息引擎读取 XML 并解除冻结从 XML 属性包。</span><span class="sxs-lookup"><span data-stu-id="64ce3-114">The Messaging Engine reads the XML and rehydrates a property bag from the XML.</span></span> <span data-ttu-id="64ce3-115">至少一个终结点后 （接收位置） 添加，适配器可以开始提交消息。</span><span class="sxs-lookup"><span data-stu-id="64ce3-115">After at least one endpoint (receive location) is added, the adapter can start submitting messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64ce3-116">适配器应不会阻止消息引擎调用如**IBTTransportControl.Initialize**， **ipersistpropertybag.load 这样**，和**IBTTransportConfig.AddReceiveEndpoint**.</span><span class="sxs-lookup"><span data-stu-id="64ce3-116">Adapters should not block Messaging Engine calls such as **IBTTransportControl.Initialize**, **IPersistPropertyBag.Load**, and **IBTTransportConfig.AddReceiveEndpoint**.</span></span> <span data-ttu-id="64ce3-117">执行过多的处理中这些调用将会影响服务启动时间。</span><span class="sxs-lookup"><span data-stu-id="64ce3-117">Performing excessive processing in these calls will affect service startup time.</span></span>  
  
 <span data-ttu-id="64ce3-118">下图显示了接收适配器创建过程中涉及的对象交互。</span><span class="sxs-lookup"><span data-stu-id="64ce3-118">The following figure shows the object interactions involved in creating an in-process receive adapter.</span></span>  
  
 <span data-ttu-id="64ce3-119">![](../core/media/ebiz-sdk-devadapter11.gif "ebiz_sdk_devadapter11")</span><span class="sxs-lookup"><span data-stu-id="64ce3-119">![](../core/media/ebiz-sdk-devadapter11.gif "ebiz_sdk_devadapter11")</span></span>  
<span data-ttu-id="64ce3-120">工作流的进程内接收适配器</span><span class="sxs-lookup"><span data-stu-id="64ce3-120">Workflow for an in-process receive adapter</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64ce3-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="64ce3-121">See Also</span></span>  
 <span data-ttu-id="64ce3-122">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="64ce3-122">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="64ce3-123">[开发接收适配器](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="64ce3-123">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="64ce3-124">[实例化和初始化接收适配器](../core/instantiating-and-initializing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="64ce3-124">[Instantiating and Initializing a Receive Adapter](../core/instantiating-and-initializing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="64ce3-125">[接口独立接收适配器](../core/interfaces-for-an-isolated-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="64ce3-125">[Interfaces for an Isolated Receive Adapter](../core/interfaces-for-an-isolated-receive-adapter.md) </span></span>  
 <span data-ttu-id="64ce3-126">[接收适配器的支持批的接口](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="64ce3-126">[Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span></span>  
 <span data-ttu-id="64ce3-127">[接收适配器的接口的事务性批处理支持](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="64ce3-127">[Interfaces for a Transactional Batch-Supported Receive Adapter](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md) </span></span>  
 [<span data-ttu-id="64ce3-128">同步请求-响应接收适配器的接口</span><span class="sxs-lookup"><span data-stu-id="64ce3-128">Interfaces for a Synchronous Request-Response Receive Adapter</span></span>](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)