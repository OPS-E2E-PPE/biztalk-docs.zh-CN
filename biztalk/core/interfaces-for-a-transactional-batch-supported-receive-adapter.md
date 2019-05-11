---
title: 接收适配器的接口的事务性批处理支持 |Microsoft Docs
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
ms.openlocfilehash: f46c7662fac5010c4f1effe56016fe2f5c5d5e8f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331558"
---
# <a name="interfaces-for-a-transactional-batch-supported-receive-adapter"></a><span data-ttu-id="647f5-102">接收适配器的接口的事务性批处理支持</span><span class="sxs-lookup"><span data-stu-id="647f5-102">Interfaces for a Transactional Batch-Supported Receive Adapter</span></span>
<span data-ttu-id="647f5-103">一个接收适配器创建和所需的消息的事务性提交时，控制事务。</span><span class="sxs-lookup"><span data-stu-id="647f5-103">A receive adapter creates and controls transactions when the transactional submission of messages is required.</span></span>  
  
 <span data-ttu-id="647f5-104">事务性接收适配器创建并将指针传递到 Microsoft 分布式事务处理协调器 (MSDTC) 的事务**完成**方法**IBTTransportBatch**接口。</span><span class="sxs-lookup"><span data-stu-id="647f5-104">A transactional receive adapter creates and passes a pointer to a Microsoft Distributed Transaction Coordinator (MSDTC) transaction on the **Done** method of the **IBTTransportBatch** interface.</span></span> <span data-ttu-id="647f5-105">这可确保在该特定事务对象的作用域中执行所有批处理操作的。</span><span class="sxs-lookup"><span data-stu-id="647f5-105">This ensures that all batch operations are performed in the scope of that specific transaction object.</span></span> <span data-ttu-id="647f5-106">中的批提交完成后，适配器回调方法将提交或回滚事务。</span><span class="sxs-lookup"><span data-stu-id="647f5-106">When the batch submission completes, the adapter callback method commits or rolls back the transaction.</span></span> <span data-ttu-id="647f5-107">所需的操作取决于状态返回从传输代理，并且可能在其他与事务相关的工作时适配器执行看不到传输代理。</span><span class="sxs-lookup"><span data-stu-id="647f5-107">Which action it takes depends upon the status returned from the transport proxy, and possibly upon other transaction-related work that the adapter does that is not visible to the transport proxy.</span></span> <span data-ttu-id="647f5-108">适配器可以确定事务是失败还是成功。</span><span class="sxs-lookup"><span data-stu-id="647f5-108">The adapter determines whether the transaction failed or succeeded.</span></span> <span data-ttu-id="647f5-109">适配器事务 （commit 或 rollback） 的结果返回到传输代理通过报告**DTCCommitConfirm**方法**IBTDTCCommitConfirm**接口。</span><span class="sxs-lookup"><span data-stu-id="647f5-109">The adapter reports the result of the transaction (commit or rollback) back to the transport proxy by using the **DTCCommitConfirm** method of the**IBTDTCCommitConfirm** interface.</span></span> <span data-ttu-id="647f5-110">它将传入`true`对于成功的事务或`false`失败。</span><span class="sxs-lookup"><span data-stu-id="647f5-110">It passes in `true` for a successful transaction or `false` for a failure.</span></span>  
  
 <span data-ttu-id="647f5-111">下图显示了接收适配器创建事务的支持批的涉及到的对象交互。</span><span class="sxs-lookup"><span data-stu-id="647f5-111">The following figure shows the object interactions involved in creating a transactional batch-supported receive adapter.</span></span>  
  
 <span data-ttu-id="647f5-112">![](../core/media/ebiz-sdk-devadapter2.gif "ebiz_sdk_devadapter2")</span><span class="sxs-lookup"><span data-stu-id="647f5-112">![](../core/media/ebiz-sdk-devadapter2.gif "ebiz_sdk_devadapter2")</span></span>  
<span data-ttu-id="647f5-113">接收适配器提交一批消息使用 DTC 事务的工作流</span><span class="sxs-lookup"><span data-stu-id="647f5-113">Workflow for a receive adapter submitting a batch of messages using DTC transactions</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="647f5-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="647f5-114">See Also</span></span>  
 <span data-ttu-id="647f5-115">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="647f5-115">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="647f5-116">[开发接收适配器](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="647f5-116">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="647f5-117">[实例化和初始化接收适配器](../core/instantiating-and-initializing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="647f5-117">[Instantiating and Initializing a Receive Adapter](../core/instantiating-and-initializing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="647f5-118">[接收适配器的进程内的接口](../core/interfaces-for-an-in-process-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="647f5-118">[Interfaces for an In-Process Receive Adapter](../core/interfaces-for-an-in-process-receive-adapter.md) </span></span>  
 <span data-ttu-id="647f5-119">[接口独立接收适配器](../core/interfaces-for-an-isolated-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="647f5-119">[Interfaces for an Isolated Receive Adapter](../core/interfaces-for-an-isolated-receive-adapter.md) </span></span>  
 <span data-ttu-id="647f5-120">[接收适配器的支持批的接口](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="647f5-120">[Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span></span>  
 [<span data-ttu-id="647f5-121">同步请求-响应接收适配器的接口</span><span class="sxs-lookup"><span data-stu-id="647f5-121">Interfaces for a Synchronous Request-Response Receive Adapter</span></span>](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)