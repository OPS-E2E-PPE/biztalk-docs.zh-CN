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
ms.openlocfilehash: 26c2398840eb44fcaf8dd42259704d860d7466ea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331595"
---
# <a name="interfaces-for-a-synchronous-send-adapter"></a><span data-ttu-id="a8b43-102">发送适配器的同步接口</span><span class="sxs-lookup"><span data-stu-id="a8b43-102">Interfaces for a Synchronous Send Adapter</span></span>
<span data-ttu-id="a8b43-103">阻止传入消息引擎在执行发送操作时调用线程时，适配器将消息以同步方式发送。</span><span class="sxs-lookup"><span data-stu-id="a8b43-103">An adapter sends messages synchronously when it blocks the incoming Messaging Engine calling thread while performing its send operation.</span></span> <span data-ttu-id="a8b43-104">若要能够同步发送消息，适配器必须实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="a8b43-104">To be able to send messages synchronously, an adapter needs to implement the following interfaces:</span></span>  
  
- <span data-ttu-id="a8b43-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="a8b43-105">**IBTTransport**</span></span>  
  
- <span data-ttu-id="a8b43-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="a8b43-106">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="a8b43-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="a8b43-107">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="a8b43-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="a8b43-108">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="a8b43-109">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="a8b43-109">**IBTTransmitter**</span></span>  
  
  <span data-ttu-id="a8b43-110">在同步发送中，适配器将消息发送时阻塞**TransmitMessage**，和传输成功返回后 `True.`</span><span class="sxs-lookup"><span data-stu-id="a8b43-110">In a synchronous send, the adapter sends the message while blocking **TransmitMessage**, and after successful transmission returns `True.`</span></span>  
  
  <span data-ttu-id="a8b43-111">下图显示了对象交互涉及创建同步发送适配器。</span><span class="sxs-lookup"><span data-stu-id="a8b43-111">The following figure shows the object interactions involved in creating a synchronous send adapter.</span></span>  
  
  <span data-ttu-id="a8b43-112">![](../core/media/ebiz-sdk-devadapter4.gif "ebiz_sdk_devadapter4")</span><span class="sxs-lookup"><span data-stu-id="a8b43-112">![](../core/media/ebiz-sdk-devadapter4.gif "ebiz_sdk_devadapter4")</span></span>  
  <span data-ttu-id="a8b43-113">以同步方式发送一条消息的工作流</span><span class="sxs-lookup"><span data-stu-id="a8b43-113">Workflow for sending a message synchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8b43-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8b43-114">See Also</span></span>  
 <span data-ttu-id="a8b43-115">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="a8b43-115">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="a8b43-116">[开发发送适配器](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a8b43-116">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="a8b43-117">[实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a8b43-117">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="a8b43-118">[发送适配器的异步接口](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a8b43-118">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="a8b43-119">[同步的支持批的发送适配器的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a8b43-119">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="a8b43-120">[异步的支持批的发送适配器的的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a8b43-120">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="a8b43-121">[事务性异步的支持批的发送适配器的接口](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a8b43-121">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="a8b43-122">要求-响应发送适配器的接口</span><span class="sxs-lookup"><span data-stu-id="a8b43-122">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)