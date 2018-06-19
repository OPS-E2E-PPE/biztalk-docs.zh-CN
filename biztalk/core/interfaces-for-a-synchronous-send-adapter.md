---
title: 异步接口发送适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e1b397a-3a35-4447-8522-d8a5f39a42d7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1012b52bf5c6ab564cc219926b97445e43f60dd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256909"
---
# <a name="interfaces-for-a-synchronous-send-adapter"></a><span data-ttu-id="5e7f6-102">同步发送适配器的接口</span><span class="sxs-lookup"><span data-stu-id="5e7f6-102">Interfaces for a Synchronous Send Adapter</span></span>
<span data-ttu-id="5e7f6-103">执行发送操作时，如果阻止了传入消息引擎调用线程，则适配器将会同步发送消息。</span><span class="sxs-lookup"><span data-stu-id="5e7f6-103">An adapter sends messages synchronously when it blocks the incoming Messaging Engine calling thread while performing its send operation.</span></span> <span data-ttu-id="5e7f6-104">为了能够同步发送消息，适配器需要实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="5e7f6-104">To be able to send messages synchronously, an adapter needs to implement the following interfaces:</span></span>  
  
-   <span data-ttu-id="5e7f6-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="5e7f6-105">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="5e7f6-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="5e7f6-106">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="5e7f6-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="5e7f6-107">**IBTTransportControl**</span></span>  
  
-   <span data-ttu-id="5e7f6-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="5e7f6-108">**IPersistPropertyBag**</span></span>  
  
-   <span data-ttu-id="5e7f6-109">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="5e7f6-109">**IBTTransmitter**</span></span>  
  
 <span data-ttu-id="5e7f6-110">在同步发送，该适配器将消息发送时阻止**TransmitMessage**，并返回成功传输之后`True.`</span><span class="sxs-lookup"><span data-stu-id="5e7f6-110">In a synchronous send, the adapter sends the message while blocking **TransmitMessage**, and after successful transmission returns `True.`</span></span>  
  
 <span data-ttu-id="5e7f6-111">下图显示了创建同步发送适配器所涉及的对象交互。</span><span class="sxs-lookup"><span data-stu-id="5e7f6-111">The following figure shows the object interactions involved in creating a synchronous send adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter4.gif "ebiz_sdk_devadapter4")  
<span data-ttu-id="5e7f6-112">同步发送消息的工作流</span><span class="sxs-lookup"><span data-stu-id="5e7f6-112">Workflow for sending a message synchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e7f6-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e7f6-113">See Also</span></span>  
 <span data-ttu-id="5e7f6-114">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="5e7f6-114">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="5e7f6-115">[开发发送适配器](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5e7f6-115">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="5e7f6-116">[实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5e7f6-116">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="5e7f6-117">[异步接口发送适配器](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5e7f6-117">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="5e7f6-118">[同步的批处理支持发送适配器的的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5e7f6-118">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="5e7f6-119">[异步批处理支持发送适配器的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5e7f6-119">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="5e7f6-120">[事务异步批处理支持发送适配器的的接口](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5e7f6-120">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="5e7f6-121">适配器发送的请求作出响应的接口</span><span class="sxs-lookup"><span data-stu-id="5e7f6-121">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)