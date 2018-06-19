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
# <a name="how-to-terminate-an-adapter"></a>如何终止适配器
下列主题用于指导您正确关闭适配器。  
  
## <a name="terminating-an-adapter"></a>终止适配器  
 当消息引擎正在关闭它将调用**IBTTransportControl**。**终止**每个进程内适配器上。 此方法返回后，BizTalk Server 会销毁适配器。 本地适配器会立即销毁，而对托管适配器而言，由于存在 .NET 垃圾收集过程，此操作发生的时间没有那么确定。 适配器应阻止**终止**并执行任何必要的清理工作，直至其准备将其销毁。  
  
## <a name="terminating-isolated-receive-adapters"></a>终止独立的接收适配器  
 独立接收适配器没有**终止**对其调用，因为它们没有承载 BizTalk 服务中。 相反，它们应调用**IBTTransportProxy**。**TerminateIsolatedReceiver**通知他们即将关闭的消息传送引擎。  
  
## <a name="clean-up-com-objects-by-using-marshalreleasecomobject"></a>使用 Marshal.ReleaseComObject 清理 COM 对象  
 在编写使用 COM 对象的托管代码时，公共语言运行时 (CLR) 会生成用于保存对 COM 对象的引用的代理对象。 代理对象为托管对象，同时遵循垃圾回收的常用规则。 由于垃圾收集器仅可查看 .NET 运行时分配的内存，而并不会注意到 COM 对象，因而会产生问题。 因为代理对象较小，较大的 COM 对象可能会由于 CLR 垃圾收集器没有注意到它而遗留在内存中。  
  
 若要避免此问题，显式释放基础 COM 对象时，你已完成，特别是任何**IBTTransportBatch**对象。 执行此操作通过调用**封送**。**ReleaseComObject**。  
  
> [!NOTE]
>  **ReleaseComObject**返回剩余引用的数目和此返回值为 0 时才释放的 COM 对象。 通常**ReleaseComObject**在一次循环来确保释放的对象中调用。 该应用程序完成后，应调用**SuppressFinalize**此对象上因为无需进行任何以完成。 最后一个步骤是检查此对象是否确实为 COM 对象。  
  
 下面的代码演示以上描述的过程：  
  
```  
if (Marshal.IsComObject (batch))  
(  
While (0 <Marshal.ReleaseComObject(batch)  
;  
GC.SuppressFinalize (batch);  
  
```  
  
 显式释放**IBTTransportBatch**从返回的对象**GetBatch**可以对性能的重大进步。  
  
## <a name="always-use-terminate-when-closing-an-adapter"></a>始终使用 Terminate 关闭适配器  
 BizTalk 服务器作为适配器识别你的代码，则必须实现一个接口，称为**IBTTransportControl**。 此接口定义 BizTalk Server 如何与您的适配器进行通信，接口的定义方式如下：  
  
```  
public interface IBTTransportControl   
{  
void Initialize(IBTTransportProxy transportProxy);  
void Terminate();  
}  
```  
  
 该接口包含两种方法，**初始化**和**终止**。  
  
### <a name="initialize"></a>“初始化”  
 BizTalk Server 调用**初始化**后它会加载适配器程序集的方法。 执行此操作的目的在于将传输代理（BizTalk Server 的主要句柄）传入适配器。 实现**初始化**只需将传输代理存储在成员变量。  
  
### <a name="terminate"></a>Terminate  
 BizTalk Server 调用**终止**在服务关闭让适配器时间才能完成的所有批执行的方法。 这可使的实现**终止**复杂得多的方法。  
  
 适配器不应返回从**终止**调用，直到它具有任何挂起的工作已完成。 在 BizTalk Server 调用**终止**，适配器应尝试停止所有当前的任务并不会启动任何新的。  
  
 因为**终止**称为的关闭服务，一部分的服务控制管理器终止这一过程，如果适配器永远块以**终止**。 在这种情况下，在服务控制管理器停止 BizTalk Server 服务时，您会看到其发出的警告。 如果可能，请避免以此方式提前终止适配器。 如果适配器没有正确处理此终止过程，且在该过程开始关闭时还有线程在运行，则在关闭时可能有时会发现来自 BizTalk Server 的访问冲突。  
  
 因为 BizTalk Server 接口的异步性，在承受负载的情况下可能还有很多批以及线程需要执行。 **终止**调用应为实现适配器计算机然后再继续 BizTalk 服务器已成功执行每个批处理结束等待。 批处理结束处于有信号状态的**BatchComplete** BizTalk Server 中的回调。 **终止**调用应等待每个挂起**BatchComplete**发生。 不过，批的执行必须成功。 也就是说，调用**IBTTransportBatch**::**完成**一定不能失败。 如果调用**IBTTransportBatch**::**完成**失败，没有批处理回调。  
  
 在您发现必须向适配器添加同步代码时，实现就变得相当简单了。  
  
 一个简单方法是实现具有的复合的同步对象**输入**和**保留**对于工作线程的方法和一个**终止**方法时阻止线程是仍处于受保护的执行。 (顺便说一下，解决方案是非常相似的熟悉的多个读取器、 单编写器结构中的工作线程可以被想象成读取器和**终止**为编写器的方法。)  
  
 **终止**方法是，如下所示：  
  
```  
void terminate ()  
{  
this.control.Terminate();  
}  
```  
  
 对于每一工作线程：  
  
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
  
 在来自 BizTalk Server 的回调中：  
  
```  
batchComplete (…)  
{  
//  the callback from BizTalk Server  
//  process results  
this.control.Leave();  
}  
```  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]附带了在基适配器示例中，显示这个同步机制在此处所述的示例代码 ControlledTermination.cs。