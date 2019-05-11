---
title: 如何终止适配器 |Microsoft Docs
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
ms.openlocfilehash: ce8e6fcf862ba52c1ae742ff48ff985ef801c0b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383762"
---
# <a name="how-to-terminate-an-adapter"></a><span data-ttu-id="73d6c-102">如何终止适配器</span><span class="sxs-lookup"><span data-stu-id="73d6c-102">How to Terminate an Adapter</span></span>
<span data-ttu-id="73d6c-103">以下主题提供有关正确关闭适配器的指导。</span><span class="sxs-lookup"><span data-stu-id="73d6c-103">The following topics provide guidance on the proper shutdown of an adapter.</span></span>  
  
## <a name="terminating-an-adapter"></a><span data-ttu-id="73d6c-104">终止适配器</span><span class="sxs-lookup"><span data-stu-id="73d6c-104">Terminating an Adapter</span></span>  
 <span data-ttu-id="73d6c-105">消息引擎即将关闭时它将调用**IBTTransportControl**。**终止**上每个进程内适配器。</span><span class="sxs-lookup"><span data-stu-id="73d6c-105">When the Messaging Engine is shutting down it calls **IBTTransportControl**.**Terminate** on each in-process adapter.</span></span> <span data-ttu-id="73d6c-106">此方法返回后，BizTalk Server 会销毁适配器。</span><span class="sxs-lookup"><span data-stu-id="73d6c-106">After this method returns BizTalk Server will destroy the adapter.</span></span> <span data-ttu-id="73d6c-107">发生这种情况立即，而对托管适配器完全的本机适配器在这种情况是由于.NET 垃圾回收进程不太确定的。</span><span class="sxs-lookup"><span data-stu-id="73d6c-107">For native adapters this occurs immediately, but for managed adapters exactly when this occurs is less deterministic due to the .NET garbage-collection process.</span></span> <span data-ttu-id="73d6c-108">适配器应该一直阻止**Terminate**并执行所有必需的清理工作，直到准备好销毁。</span><span class="sxs-lookup"><span data-stu-id="73d6c-108">The adapter should block in **Terminate** and do any necessary cleanup work until it is ready to be destroyed.</span></span>  
  
## <a name="terminating-isolated-receive-adapters"></a><span data-ttu-id="73d6c-109">终止独立接收适配器</span><span class="sxs-lookup"><span data-stu-id="73d6c-109">Terminating Isolated Receive Adapters</span></span>  
 <span data-ttu-id="73d6c-110">独立接收适配器不具有**Terminate**因为它们没有驻留在 BizTalk 服务中对其调用。</span><span class="sxs-lookup"><span data-stu-id="73d6c-110">Isolated receive adapters do not have **Terminate** called on them because they are not hosted in the BizTalk service.</span></span> <span data-ttu-id="73d6c-111">相反，它们应调用**IBTTransportProxy**。**TerminateIsolatedReceiver**通知消息引擎它们即将关闭。</span><span class="sxs-lookup"><span data-stu-id="73d6c-111">Instead, they should call **IBTTransportProxy**.**TerminateIsolatedReceiver** to notify the Messaging Engine that they are about to shut down.</span></span>  
  
## <a name="clean-up-com-objects-by-using-marshalreleasecomobject"></a><span data-ttu-id="73d6c-112">使用 Marshal.ReleaseComObject 清理 COM 对象</span><span class="sxs-lookup"><span data-stu-id="73d6c-112">Clean Up COM Objects by Using Marshal.ReleaseComObject</span></span>  
 <span data-ttu-id="73d6c-113">编写使用 COM 对象的托管的代码时，公共语言运行时 (CLR) 生成保存到 COM 对象的引用的代理对象。</span><span class="sxs-lookup"><span data-stu-id="73d6c-113">When writing managed code that uses COM objects, the common language runtime (CLR) generates proxy objects that hold the references to the COM objects.</span></span> <span data-ttu-id="73d6c-114">代理对象是托管的对象，可能会有所垃圾回收的常用规则。</span><span class="sxs-lookup"><span data-stu-id="73d6c-114">The proxy objects are managed objects and are subject to the usual rules of garbage collection.</span></span> <span data-ttu-id="73d6c-115">出现问题的因为垃圾回收器只能看到.NET 运行时分配，并不知道的 COM 对象的内存。</span><span class="sxs-lookup"><span data-stu-id="73d6c-115">A problem arises in that the garbage collector only sees memory that the .NET runtimes allocated, and is not aware of the COM object.</span></span> <span data-ttu-id="73d6c-116">因为代理对象较小，大型的 COM 对象可能保留在内存中因为 CLR 垃圾回收器不是意识到这一点。</span><span class="sxs-lookup"><span data-stu-id="73d6c-116">Because the proxy objects are small, a large COM object might be left in memory because the CLR garbage collector is not aware of it.</span></span>  
  
 <span data-ttu-id="73d6c-117">若要避免此问题，显式释放底层的 COM 对象时，你已完成，特别是任何**IBTTransportBatch**对象。</span><span class="sxs-lookup"><span data-stu-id="73d6c-117">To avoid this problem, explicitly release underlying COM objects when you are finished with them, particularly any **IBTTransportBatch** objects.</span></span> <span data-ttu-id="73d6c-118">执行此操作通过调用**封送**。**ReleaseComObject**。</span><span class="sxs-lookup"><span data-stu-id="73d6c-118">You do this by calling **Marshal**.**ReleaseComObject**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73d6c-119">**ReleaseComObject**返回剩余引用数，并仅在返回值为零，此发布的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="73d6c-119">**ReleaseComObject** returns the number of remaining references and only releases the COM object when this returned value is zero.</span></span> <span data-ttu-id="73d6c-120">通常**ReleaseComObject**在一个循环，以便确保在释放的对象中调用。</span><span class="sxs-lookup"><span data-stu-id="73d6c-120">Often **ReleaseComObject** is called in a loop to ensure that the object is released.</span></span> <span data-ttu-id="73d6c-121">该应用程序完成后，应调用**SuppressFinalize**此对象上因为不需要完成。</span><span class="sxs-lookup"><span data-stu-id="73d6c-121">After that is complete, you should call **SuppressFinalize** on this object because there is nothing to finalize.</span></span> <span data-ttu-id="73d6c-122">最后一步是检查是否确实为 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="73d6c-122">One last step is to check whether this really is a COM object.</span></span>  
  
 <span data-ttu-id="73d6c-123">下面的代码演示以上描述的过程：</span><span class="sxs-lookup"><span data-stu-id="73d6c-123">The following code shows the process descrjbed above:</span></span>  
  
```  
if (Marshal.IsComObject (batch))  
(  
While (0 <Marshal.ReleaseComObject(batch)  
;  
GC.SuppressFinalize (batch);  
  
```  
  
 <span data-ttu-id="73d6c-124">显式释放**IBTTransportBatch**从返回的对象**GetBatch**可以使性能得到显著提高。</span><span class="sxs-lookup"><span data-stu-id="73d6c-124">Explicitly releasing the **IBTTransportBatch** object returned from **GetBatch** can make a significant improvement to performance.</span></span>  
  
## <a name="always-use-terminate-when-closing-an-adapter"></a><span data-ttu-id="73d6c-125">始终使用 Terminate 关闭适配器</span><span class="sxs-lookup"><span data-stu-id="73d6c-125">Always Use Terminate When Closing an Adapter</span></span>  
 <span data-ttu-id="73d6c-126">若要将你的代码识别为适配器的 BizTalk server，必须实现一个接口，称为**IBTTransportControl**。</span><span class="sxs-lookup"><span data-stu-id="73d6c-126">For BizTalk Server to recognize your code as an adapter, you must implement an interface called **IBTTransportControl**.</span></span> <span data-ttu-id="73d6c-127">此接口定义 BizTalk Server 如何与您的适配器，并按以下方式定义：</span><span class="sxs-lookup"><span data-stu-id="73d6c-127">This interface defines how BizTalk Server communicates with your adapter, and is defined as follows:</span></span>  
  
```  
public interface IBTTransportControl   
{  
void Initialize(IBTTransportProxy transportProxy);  
void Terminate();  
}  
```  
  
 <span data-ttu-id="73d6c-128">此接口包含两个方法，**初始化**并**终止**。</span><span class="sxs-lookup"><span data-stu-id="73d6c-128">The interface contains two methods, **Initialize** and **Terminate**.</span></span>  
  
### <a name="initialize"></a><span data-ttu-id="73d6c-129">“初始化”</span><span class="sxs-lookup"><span data-stu-id="73d6c-129">Initialize</span></span>  
 <span data-ttu-id="73d6c-130">BizTalk Server 调用**初始化**方法后它会加载适配器程序集。</span><span class="sxs-lookup"><span data-stu-id="73d6c-130">BizTalk Server calls the **Initialize** method after it loads the adapter assembly.</span></span> <span data-ttu-id="73d6c-131">这样做可传递到适配器的传输代理 （BizTalk Server 的主要句柄）。</span><span class="sxs-lookup"><span data-stu-id="73d6c-131">It does this to pass the transport proxy (the main handle to BizTalk Server) to the adapter.</span></span> <span data-ttu-id="73d6c-132">实现**初始化**只需将传输代理存储在成员变量。</span><span class="sxs-lookup"><span data-stu-id="73d6c-132">The implementation of **Initialize** simply stores the transport proxy in a member variable.</span></span>  
  
### <a name="terminate"></a><span data-ttu-id="73d6c-133">终止</span><span class="sxs-lookup"><span data-stu-id="73d6c-133">Terminate</span></span>  
 <span data-ttu-id="73d6c-134">BizTalk Server 调用**Terminate**在服务关闭以给予适配器时间来完成的所有批处理执行的方法。</span><span class="sxs-lookup"><span data-stu-id="73d6c-134">BizTalk Server calls the **Terminate** method on service shutdown to give the adapter time to finish the execution of all batches.</span></span> <span data-ttu-id="73d6c-135">这样的实现**Terminate**变得更为复杂的方法。</span><span class="sxs-lookup"><span data-stu-id="73d6c-135">This makes the implementation of the **Terminate** method much more involved.</span></span>  
  
 <span data-ttu-id="73d6c-136">适配器不应返回从**Terminate**调用，直到它具有任何挂起的工作已完成。</span><span class="sxs-lookup"><span data-stu-id="73d6c-136">The adapter should not return from a **Terminate** call until any pending work it has is complete.</span></span> <span data-ttu-id="73d6c-137">当 BizTalk Server 调用**Terminate**，适配器应尝试停止所有当前任务并不会启动任何新的。</span><span class="sxs-lookup"><span data-stu-id="73d6c-137">When BizTalk Server calls **Terminate**, the adapter should try to stop all its current tasks and not start any new ones.</span></span>  
  
 <span data-ttu-id="73d6c-138">因为**Terminate**称为作为服务关闭的一部分，服务控制管理器结束进程，如果适配器永久阻止**终止**。</span><span class="sxs-lookup"><span data-stu-id="73d6c-138">Because **Terminate** is called as part of the service shutdown, the service control manager ends the process if the adapter perpetually blocks in **Terminate**.</span></span> <span data-ttu-id="73d6c-139">在这种情况下，您看到从服务控制管理器警告，因为它将停止 BizTalk Server 服务。</span><span class="sxs-lookup"><span data-stu-id="73d6c-139">In this case, you see the warning from the service control manager as it stops the BizTalk Server service.</span></span> <span data-ttu-id="73d6c-140">如果可能，避免终止以此方式提前适配器。</span><span class="sxs-lookup"><span data-stu-id="73d6c-140">If possible, avoid terminating the adapter prematurely like this.</span></span> <span data-ttu-id="73d6c-141">如果适配器不会适当地处理终止进程，并且还有线程在运行时该过程开始关闭的情况下，然后可能会在关闭偶尔会看到从 BizTalk Server 的访问冲突。</span><span class="sxs-lookup"><span data-stu-id="73d6c-141">If the adapter does not handle the termination process appropriately, and still has threads running when the process starts to shut down, then you may occasionally see an access violation from BizTalk Server on shutdown.</span></span>  
  
 <span data-ttu-id="73d6c-142">由于 BizTalk Server 接口的异步性质，很可能，在负载下将有多批以及线程需要执行。</span><span class="sxs-lookup"><span data-stu-id="73d6c-142">Because of the asynchronous nature of the interface to BizTalk Server, it is likely that under load there will be many batches and therefore threads still being executed.</span></span> <span data-ttu-id="73d6c-143">**Terminate**应实现调用要等待的适配器已成功执行 BizTalk Server 在继续之前每个批处理结束。</span><span class="sxs-lookup"><span data-stu-id="73d6c-143">The **Terminate** call should be implemented to wait on the conclusion of every batch the adapter has successfully executed on BizTalk Server before proceeding.</span></span> <span data-ttu-id="73d6c-144">通过发出信号批已经结束**BatchComplete**从 BizTalk Server 的回调。</span><span class="sxs-lookup"><span data-stu-id="73d6c-144">The conclusion of the batch is signaled by the **BatchComplete** callback from BizTalk Server.</span></span> <span data-ttu-id="73d6c-145">**Terminate**调用应等待每个挂起**BatchComplete**发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="73d6c-145">The **Terminate** call should wait on every pending **BatchComplete** to happen.</span></span> <span data-ttu-id="73d6c-146">但是，必须成功执行批处理。</span><span class="sxs-lookup"><span data-stu-id="73d6c-146">However, the execution of the batch must be successful.</span></span> <span data-ttu-id="73d6c-147">也就是说，调用**IBTTransportBatch**::**完成**不得失败。</span><span class="sxs-lookup"><span data-stu-id="73d6c-147">That is, the call to **IBTTransportBatch**::**Done** must not fail.</span></span> <span data-ttu-id="73d6c-148">如果在调用**IBTTransportBatch**::**完成**失败，没有批处理回调。</span><span class="sxs-lookup"><span data-stu-id="73d6c-148">If the call to **IBTTransportBatch**::**Done** fails, there is no batch callback.</span></span>  
  
 <span data-ttu-id="73d6c-149">您意识到，您需要将同步代码添加到您的适配器后，该实现其实非常简单。</span><span class="sxs-lookup"><span data-stu-id="73d6c-149">After you realize that you have to add synchronization code to your adapter, the implementation is fairly straightforward.</span></span>  
  
 <span data-ttu-id="73d6c-150">一个简单的方法是实现与一个复合同步对象**输入**并**保留**方法的工作线程和一个**终止**方法时阻止线程是仍包含在受保护的执行。</span><span class="sxs-lookup"><span data-stu-id="73d6c-150">One simple approach is to implement a compound synchronization object with **enter** and **leave** methods for the worker threads and a **terminate** method that blocks while a thread is still within the protected execution.</span></span> <span data-ttu-id="73d6c-151">(顺便说一下，解决方法是非常类似于熟悉的多个读取器 / 单编写器结构的工作线程可以认为的读取器和**终止**方法作为编写器。)</span><span class="sxs-lookup"><span data-stu-id="73d6c-151">(Incidentally, the solution is very similar to the familiar multiple-reader, single-writer structure where the worker threads can be thought of as readers and the **terminate** method as the writer.)</span></span>  
  
 <span data-ttu-id="73d6c-152">**终止**方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="73d6c-152">The **terminate** method is as follows:</span></span>  
  
```  
void terminate ()  
{  
this.control.Terminate();  
}  
```  
  
 <span data-ttu-id="73d6c-153">对于每个工作线程：</span><span class="sxs-lookup"><span data-stu-id="73d6c-153">For each worker thread:</span></span>  
  
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
  
 <span data-ttu-id="73d6c-154">在从 BizTalk Server 回调：</span><span class="sxs-lookup"><span data-stu-id="73d6c-154">In the callback from BizTalk Server:</span></span>  
  
```  
batchComplete (…)  
{  
//  the callback from BizTalk Server  
//  process results  
this.control.Leave();  
}  
```  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="73d6c-155">附带了 ControlledTermination.cs 在基本适配器示例中，显示此处描述的同步机制的示例代码。</span><span class="sxs-lookup"><span data-stu-id="73d6c-155">ships with sample code ControlledTermination.cs in the Base Adapter sample, showing the synchronization mechanism described here.</span></span>