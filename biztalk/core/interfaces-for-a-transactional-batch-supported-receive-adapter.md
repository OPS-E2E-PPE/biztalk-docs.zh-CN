---
title: 批处理支持为一个事务性接口接收适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5289e8b8-4447-4196-9f7c-5e60c6598d8d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27b51a67f63f3088ce64c9db35c368289ce156d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257573"
---
# <a name="interfaces-for-a-transactional-batch-supported-receive-adapter"></a><span data-ttu-id="4bd84-102">批处理支持为一个事务性接口接收适配器</span><span class="sxs-lookup"><span data-stu-id="4bd84-102">Interfaces for a Transactional Batch-Supported Receive Adapter</span></span>
<span data-ttu-id="4bd84-103">接收适配器可在要求消息的事务性提交时创建和控制事务。</span><span class="sxs-lookup"><span data-stu-id="4bd84-103">A receive adapter creates and controls transactions when the transactional submission of messages is required.</span></span>  
  
 <span data-ttu-id="4bd84-104">一个事务性接收适配器创建，并将指针传递到 Microsoft 分布式事务处理协调器 (MSDTC) 事务**完成**方法**IBTTransportBatch**接口。</span><span class="sxs-lookup"><span data-stu-id="4bd84-104">A transactional receive adapter creates and passes a pointer to a Microsoft Distributed Transaction Coordinator (MSDTC) transaction on the **Done** method of the **IBTTransportBatch** interface.</span></span> <span data-ttu-id="4bd84-105">这确保所有批操作都在该特定事务对象的作用域中执行。</span><span class="sxs-lookup"><span data-stu-id="4bd84-105">This ensures that all batch operations are performed in the scope of that specific transaction object.</span></span> <span data-ttu-id="4bd84-106">在批提交完成后，适配器回调方法将提交或回滚该事务。</span><span class="sxs-lookup"><span data-stu-id="4bd84-106">When the batch submission completes, the adapter callback method commits or rolls back the transaction.</span></span> <span data-ttu-id="4bd84-107">它所采用的操作取决于从传输代理返回的状态，并且还可能取决于适配器执行的其他与事务相关的工作（而该工作对传输代理不可见）。</span><span class="sxs-lookup"><span data-stu-id="4bd84-107">Which action it takes depends upon the status returned from the transport proxy, and possibly upon other transaction-related work that the adapter does that is not visible to the transport proxy.</span></span> <span data-ttu-id="4bd84-108">适配器将确定事务是失败还是成功。</span><span class="sxs-lookup"><span data-stu-id="4bd84-108">The adapter determines whether the transaction failed or succeeded.</span></span> <span data-ttu-id="4bd84-109">适配器 （提交或回滚） 事务的结果回过来向报告传输代理使用**DTCCommitConfirm**方法**IBTDTCCommitConfirm**接口。</span><span class="sxs-lookup"><span data-stu-id="4bd84-109">The adapter reports the result of the transaction (commit or rollback) back to the transport proxy by using the **DTCCommitConfirm** method of the**IBTDTCCommitConfirm** interface.</span></span> <span data-ttu-id="4bd84-110">它将传递`true`成功事务或`false`失败。</span><span class="sxs-lookup"><span data-stu-id="4bd84-110">It passes in `true` for a successful transaction or `false` for a failure.</span></span>  
  
 <span data-ttu-id="4bd84-111">下图显示在创建支持事务性批的接收适配器时的对象交互。</span><span class="sxs-lookup"><span data-stu-id="4bd84-111">The following figure shows the object interactions involved in creating a transactional batch-supported receive adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter2.gif "ebiz_sdk_devadapter2")  
<span data-ttu-id="4bd84-112">接收适配器使用 DTC 事务提交一批消息的工作流</span><span class="sxs-lookup"><span data-stu-id="4bd84-112">Workflow for a receive adapter submitting a batch of messages using DTC transactions</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bd84-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4bd84-113">See Also</span></span>  
 <span data-ttu-id="4bd84-114">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="4bd84-114">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="4bd84-115">[开发接收适配器](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4bd84-115">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="4bd84-116">[实例化和初始化接收适配器](../core/instantiating-and-initializing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4bd84-116">[Instantiating and Initializing a Receive Adapter](../core/instantiating-and-initializing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="4bd84-117">[进程内的接口接收适配器](../core/interfaces-for-an-in-process-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4bd84-117">[Interfaces for an In-Process Receive Adapter](../core/interfaces-for-an-in-process-receive-adapter.md) </span></span>  
 <span data-ttu-id="4bd84-118">[一个独立的接口接收适配器](../core/interfaces-for-an-isolated-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4bd84-118">[Interfaces for an Isolated Receive Adapter](../core/interfaces-for-an-isolated-receive-adapter.md) </span></span>  
 <span data-ttu-id="4bd84-119">[批处理支持的接口接收适配器](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4bd84-119">[Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span></span>  
 [<span data-ttu-id="4bd84-120">接口同步请求-响应接收适配器</span><span class="sxs-lookup"><span data-stu-id="4bd84-120">Interfaces for a Synchronous Request-Response Receive Adapter</span></span>](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)