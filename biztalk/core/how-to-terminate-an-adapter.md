---
title: 如何终止适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dfba2b61-b89f-41cd-a014-4e96daec6516
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd2621e15803dd5f6e8f449de530e84df1bc1b9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255989"
---
# <a name="how-to-terminate-an-adapter"></a><span data-ttu-id="c6ef7-102">如何终止适配器</span><span class="sxs-lookup"><span data-stu-id="c6ef7-102">How to Terminate an Adapter</span></span>
<span data-ttu-id="c6ef7-103">下列主题用于指导您正确关闭适配器。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-103">The following topics provide guidance on the proper shutdown of an adapter.</span></span>  
  
## <a name="terminating-an-adapter"></a><span data-ttu-id="c6ef7-104">终止适配器</span><span class="sxs-lookup"><span data-stu-id="c6ef7-104">Terminating an Adapter</span></span>  
 <span data-ttu-id="c6ef7-105">当消息引擎正在关闭它将调用**IBTTransportControl**。**终止**每个进程内适配器上。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-105">When the Messaging Engine is shutting down it calls **IBTTransportControl**.**Terminate** on each in-process adapter.</span></span> <span data-ttu-id="c6ef7-106">此方法返回后，BizTalk Server 会销毁适配器。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-106">After this method returns BizTalk Server will destroy the adapter.</span></span> <span data-ttu-id="c6ef7-107">本地适配器会立即销毁，而对托管适配器而言，由于存在 .NET 垃圾收集过程，此操作发生的时间没有那么确定。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-107">For native adapters this occurs immediately, but for managed adapters exactly when this occurs is less deterministic due to the .NET garbage-collection process.</span></span> <span data-ttu-id="c6ef7-108">适配器应阻止**终止**并执行任何必要的清理工作，直至其准备将其销毁。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-108">The adapter should block in **Terminate** and do any necessary cleanup work until it is ready to be destroyed.</span></span>  
  
## <a name="terminating-isolated-receive-adapters"></a><span data-ttu-id="c6ef7-109">终止独立的接收适配器</span><span class="sxs-lookup"><span data-stu-id="c6ef7-109">Terminating Isolated Receive Adapters</span></span>  
 <span data-ttu-id="c6ef7-110">独立接收适配器没有**终止**对其调用，因为它们没有承载 BizTalk 服务中。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-110">Isolated receive adapters do not have **Terminate** called on them because they are not hosted in the BizTalk service.</span></span> <span data-ttu-id="c6ef7-111">相反，它们应调用**IBTTransportProxy**。**TerminateIsolatedReceiver**通知他们即将关闭的消息传送引擎。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-111">Instead, they should call **IBTTransportProxy**.**TerminateIsolatedReceiver** to notify the Messaging Engine that they are about to shut down.</span></span>  
  
## <a name="clean-up-com-objects-by-using-marshalreleasecomobject"></a><span data-ttu-id="c6ef7-112">使用 Marshal.ReleaseComObject 清理 COM 对象</span><span class="sxs-lookup"><span data-stu-id="c6ef7-112">Clean Up COM Objects by Using Marshal.ReleaseComObject</span></span>  
 <span data-ttu-id="c6ef7-113">在编写使用 COM 对象的托管代码时，公共语言运行时 (CLR) 会生成用于保存对 COM 对象的引用的代理对象。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-113">When writing managed code that uses COM objects, the common language runtime (CLR) generates proxy objects that hold the references to the COM objects.</span></span> <span data-ttu-id="c6ef7-114">代理对象为托管对象，同时遵循垃圾回收的常用规则。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-114">The proxy objects are managed objects and are subject to the usual rules of garbage collection.</span></span> <span data-ttu-id="c6ef7-115">由于垃圾收集器仅可查看 .NET 运行时分配的内存，而并不会注意到 COM 对象，因而会产生问题。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-115">A problem arises in that the garbage collector only sees memory that the .NET runtimes allocated, and is not aware of the COM object.</span></span> <span data-ttu-id="c6ef7-116">因为代理对象较小，较大的 COM 对象可能会由于 CLR 垃圾收集器没有注意到它而遗留在内存中。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-116">Because the proxy objects are small, a large COM object might be left in memory because the CLR garbage collector is not aware of it.</span></span>  
  
 <span data-ttu-id="c6ef7-117">若要避免此问题，显式释放基础 COM 对象时，你已完成，特别是任何**IBTTransportBatch**对象。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-117">To avoid this problem, explicitly release underlying COM objects when you are finished with them, particularly any **IBTTransportBatch** objects.</span></span> <span data-ttu-id="c6ef7-118">执行此操作通过调用**封送**。**ReleaseComObject**。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-118">You do this by calling **Marshal**.**ReleaseComObject**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6ef7-119">**ReleaseComObject**返回剩余引用的数目和此返回值为 0 时才释放的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-119">**ReleaseComObject** returns the number of remaining references and only releases the COM object when this returned value is zero.</span></span> <span data-ttu-id="c6ef7-120">通常**ReleaseComObject**在一次循环来确保释放的对象中调用。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-120">Often **ReleaseComObject** is called in a loop to ensure that the object is released.</span></span> <span data-ttu-id="c6ef7-121">该应用程序完成后，应调用**SuppressFinalize**此对象上因为无需进行任何以完成。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-121">After that is complete, you should call **SuppressFinalize** on this object because there is nothing to finalize.</span></span> <span data-ttu-id="c6ef7-122">最后一个步骤是检查此对象是否确实为 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-122">One last step is to check whether this really is a COM object.</span></span>  
  
 <span data-ttu-id="c6ef7-123">下面的代码演示以上描述的过程：</span><span class="sxs-lookup"><span data-stu-id="c6ef7-123">The following code shows the process descrjbed above:</span></span>  
  
```  
if (Marshal.IsComObject (batch))  
(  
While (0 <Marshal.ReleaseComObject(batch)  
;  
GC.SuppressFinalize (batch);  
  
```  
  
 <span data-ttu-id="c6ef7-124">显式释放**IBTTransportBatch**从返回的对象**GetBatch**可以对性能的重大进步。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-124">Explicitly releasing the **IBTTransportBatch** object returned from **GetBatch** can make a significant improvement to performance.</span></span>  
  
## <a name="always-use-terminate-when-closing-an-adapter"></a><span data-ttu-id="c6ef7-125">始终使用 Terminate 关闭适配器</span><span class="sxs-lookup"><span data-stu-id="c6ef7-125">Always Use Terminate When Closing an Adapter</span></span>  
 <span data-ttu-id="c6ef7-126">BizTalk 服务器作为适配器识别你的代码，则必须实现一个接口，称为**IBTTransportControl**。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-126">For BizTalk Server to recognize your code as an adapter, you must implement an interface called **IBTTransportControl**.</span></span> <span data-ttu-id="c6ef7-127">此接口定义 BizTalk Server 如何与您的适配器进行通信，接口的定义方式如下：</span><span class="sxs-lookup"><span data-stu-id="c6ef7-127">This interface defines how BizTalk Server communicates with your adapter, and is defined as follows:</span></span>  
  
```  
public interface IBTTransportControl   
{  
void Initialize(IBTTransportProxy transportProxy);  
void Terminate();  
}  
```  
  
 <span data-ttu-id="c6ef7-128">该接口包含两种方法，**初始化**和**终止**。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-128">The interface contains two methods, **Initialize** and **Terminate**.</span></span>  
  
### <a name="initialize"></a><span data-ttu-id="c6ef7-129">“初始化”</span><span class="sxs-lookup"><span data-stu-id="c6ef7-129">Initialize</span></span>  
 <span data-ttu-id="c6ef7-130">BizTalk Server 调用**初始化**后它会加载适配器程序集的方法。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-130">BizTalk Server calls the **Initialize** method after it loads the adapter assembly.</span></span> <span data-ttu-id="c6ef7-131">执行此操作的目的在于将传输代理（BizTalk Server 的主要句柄）传入适配器。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-131">It does this to pass the transport proxy (the main handle to BizTalk Server) to the adapter.</span></span> <span data-ttu-id="c6ef7-132">实现**初始化**只需将传输代理存储在成员变量。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-132">The implementation of **Initialize** simply stores the transport proxy in a member variable.</span></span>  
  
### <a name="terminate"></a><span data-ttu-id="c6ef7-133">Terminate</span><span class="sxs-lookup"><span data-stu-id="c6ef7-133">Terminate</span></span>  
 <span data-ttu-id="c6ef7-134">BizTalk Server 调用**终止**在服务关闭让适配器时间才能完成的所有批执行的方法。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-134">BizTalk Server calls the **Terminate** method on service shutdown to give the adapter time to finish the execution of all batches.</span></span> <span data-ttu-id="c6ef7-135">这可使的实现**终止**复杂得多的方法。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-135">This makes the implementation of the **Terminate** method much more involved.</span></span>  
  
 <span data-ttu-id="c6ef7-136">适配器不应返回从**终止**调用，直到它具有任何挂起的工作已完成。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-136">The adapter should not return from a **Terminate** call until any pending work it has is complete.</span></span> <span data-ttu-id="c6ef7-137">在 BizTalk Server 调用**终止**，适配器应尝试停止所有当前的任务并不会启动任何新的。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-137">When BizTalk Server calls **Terminate**, the adapter should try to stop all its current tasks and not start any new ones.</span></span>  
  
 <span data-ttu-id="c6ef7-138">因为**终止**称为的关闭服务，一部分的服务控制管理器终止这一过程，如果适配器永远块以**终止**。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-138">Because **Terminate** is called as part of the service shutdown, the service control manager ends the process if the adapter perpetually blocks in **Terminate**.</span></span> <span data-ttu-id="c6ef7-139">在这种情况下，在服务控制管理器停止 BizTalk Server 服务时，您会看到其发出的警告。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-139">In this case, you see the warning from the service control manager as it stops the BizTalk Server service.</span></span> <span data-ttu-id="c6ef7-140">如果可能，请避免以此方式提前终止适配器。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-140">If possible, avoid terminating the adapter prematurely like this.</span></span> <span data-ttu-id="c6ef7-141">如果适配器没有正确处理此终止过程，且在该过程开始关闭时还有线程在运行，则在关闭时可能有时会发现来自 BizTalk Server 的访问冲突。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-141">If the adapter does not handle the termination process appropriately, and still has threads running when the process starts to shut down, then you may occasionally see an access violation from BizTalk Server on shutdown.</span></span>  
  
 <span data-ttu-id="c6ef7-142">因为 BizTalk Server 接口的异步性，在承受负载的情况下可能还有很多批以及线程需要执行。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-142">Because of the asynchronous nature of the interface to BizTalk Server, it is likely that under load there will be many batches and therefore threads still being executed.</span></span> <span data-ttu-id="c6ef7-143">**终止**调用应为实现适配器计算机然后再继续 BizTalk 服务器已成功执行每个批处理结束等待。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-143">The **Terminate** call should be implemented to wait on the conclusion of every batch the adapter has successfully executed on BizTalk Server before proceeding.</span></span> <span data-ttu-id="c6ef7-144">批处理结束处于有信号状态的**BatchComplete** BizTalk Server 中的回调。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-144">The conclusion of the batch is signaled by the **BatchComplete** callback from BizTalk Server.</span></span> <span data-ttu-id="c6ef7-145">**终止**调用应等待每个挂起**BatchComplete**发生。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-145">The **Terminate** call should wait on every pending **BatchComplete** to happen.</span></span> <span data-ttu-id="c6ef7-146">不过，批的执行必须成功。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-146">However, the execution of the batch must be successful.</span></span> <span data-ttu-id="c6ef7-147">也就是说，调用**IBTTransportBatch**::**完成**一定不能失败。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-147">That is, the call to **IBTTransportBatch**::**Done** must not fail.</span></span> <span data-ttu-id="c6ef7-148">如果调用**IBTTransportBatch**::**完成**失败，没有批处理回调。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-148">If the call to **IBTTransportBatch**::**Done** fails, there is no batch callback.</span></span>  
  
 <span data-ttu-id="c6ef7-149">在您发现必须向适配器添加同步代码时，实现就变得相当简单了。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-149">After you realize that you have to add synchronization code to your adapter, the implementation is fairly straightforward.</span></span>  
  
 <span data-ttu-id="c6ef7-150">一个简单方法是实现具有的复合的同步对象**输入**和**保留**对于工作线程的方法和一个**终止**方法时阻止线程是仍处于受保护的执行。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-150">One simple approach is to implement a compound synchronization object with **enter** and **leave** methods for the worker threads and a **terminate** method that blocks while a thread is still within the protected execution.</span></span> <span data-ttu-id="c6ef7-151">(顺便说一下，解决方案是非常相似的熟悉的多个读取器、 单编写器结构中的工作线程可以被想象成读取器和**终止**为编写器的方法。)</span><span class="sxs-lookup"><span data-stu-id="c6ef7-151">(Incidentally, the solution is very similar to the familiar multiple-reader, single-writer structure where the worker threads can be thought of as readers and the **terminate** method as the writer.)</span></span>  
  
 <span data-ttu-id="c6ef7-152">**终止**方法是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c6ef7-152">The **terminate** method is as follows:</span></span>  
  
```  
void terminate ()  
{  
this.control.Terminate();  
}  
```  
  
 <span data-ttu-id="c6ef7-153">对于每一工作线程：</span><span class="sxs-lookup"><span data-stu-id="c6ef7-153">For each worker thread:</span></span>  
  
```  
If (!this.control.Enter())  
return; // we can’t enter because Terminate has been called  
try  
{  
//  create and fill batch  
batch.Done();  
}  
catch (Exception)  
{  
//  we are not expecting a callback  
This.control.Leave();  
}  
```  
  
 <span data-ttu-id="c6ef7-154">在来自 BizTalk Server 的回调中：</span><span class="sxs-lookup"><span data-stu-id="c6ef7-154">In the callback from BizTalk Server:</span></span>  
  
```  
batchComplete (…)  
{  
//  the callback from BizTalk Server  
//  process results  
this.control.Leave();  
}  
```  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c6ef7-155">附带了在基适配器示例中，显示这个同步机制在此处所述的示例代码 ControlledTermination.cs。</span><span class="sxs-lookup"><span data-stu-id="c6ef7-155"> ships with sample code ControlledTermination.cs in the Base Adapter sample, showing the synchronization mechanism described here.</span></span>