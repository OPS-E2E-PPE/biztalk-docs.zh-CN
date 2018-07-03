---
title: 发送适配器的同步接口 |Microsoft Docs
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
ms.openlocfilehash: 1602d19bc5b97231a25f5449f5837fce153c037d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008838"
---
# <a name="interfaces-for-a-synchronous-send-adapter"></a><span data-ttu-id="e4def-102">同步发送适配器的接口</span><span class="sxs-lookup"><span data-stu-id="e4def-102">Interfaces for a Synchronous Send Adapter</span></span>
<span data-ttu-id="e4def-103">执行发送操作时，如果阻止了传入消息引擎调用线程，则适配器将会同步发送消息。</span><span class="sxs-lookup"><span data-stu-id="e4def-103">An adapter sends messages synchronously when it blocks the incoming Messaging Engine calling thread while performing its send operation.</span></span> <span data-ttu-id="e4def-104">为了能够同步发送消息，适配器需要实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="e4def-104">To be able to send messages synchronously, an adapter needs to implement the following interfaces:</span></span>  
  
- <span data-ttu-id="e4def-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="e4def-105">**IBTTransport**</span></span>  
  
- <span data-ttu-id="e4def-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="e4def-106">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="e4def-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="e4def-107">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="e4def-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="e4def-108">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="e4def-109">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="e4def-109">**IBTTransmitter**</span></span>  
  
  <span data-ttu-id="e4def-110">在同步发送中，适配器将消息发送时阻塞**TransmitMessage**，和传输成功返回后 `True.`</span><span class="sxs-lookup"><span data-stu-id="e4def-110">In a synchronous send, the adapter sends the message while blocking **TransmitMessage**, and after successful transmission returns `True.`</span></span>  
  
  <span data-ttu-id="e4def-111">下图显示了创建同步发送适配器所涉及的对象交互。</span><span class="sxs-lookup"><span data-stu-id="e4def-111">The following figure shows the object interactions involved in creating a synchronous send adapter.</span></span>  
  
  <span data-ttu-id="e4def-112">![](../core/media/ebiz-sdk-devadapter4.gif "ebiz_sdk_devadapter4")</span><span class="sxs-lookup"><span data-stu-id="e4def-112">![](../core/media/ebiz-sdk-devadapter4.gif "ebiz_sdk_devadapter4")</span></span>  
  <span data-ttu-id="e4def-113">同步发送消息的工作流</span><span class="sxs-lookup"><span data-stu-id="e4def-113">Workflow for sending a message synchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4def-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4def-114">See Also</span></span>  
 <span data-ttu-id="e4def-115">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="e4def-115">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="e4def-116">[开发发送适配器](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="e4def-116">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="e4def-117">[实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="e4def-117">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="e4def-118">[发送适配器的异步接口](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="e4def-118">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="e4def-119">[同步的支持批的发送适配器的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="e4def-119">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="e4def-120">[异步的支持批的发送适配器的的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="e4def-120">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="e4def-121">[事务性异步的支持批的发送适配器的接口](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="e4def-121">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="e4def-122">要求-响应发送适配器的接口</span><span class="sxs-lookup"><span data-stu-id="e4def-122">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)