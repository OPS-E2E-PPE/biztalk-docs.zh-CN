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
# <a name="how-to-terminate-an-adapter"></a>如何终止适配器
以下主题提供有关正确关闭适配器的指导。  
  
## <a name="terminating-an-adapter"></a>终止适配器  
 消息引擎即将关闭时它将调用**IBTTransportControl**。**终止**上每个进程内适配器。 此方法返回后，BizTalk Server 会销毁适配器。 发生这种情况立即，而对托管适配器完全的本机适配器在这种情况是由于.NET 垃圾回收进程不太确定的。 适配器应该一直阻止**Terminate**并执行所有必需的清理工作，直到准备好销毁。  
  
## <a name="terminating-isolated-receive-adapters"></a>终止独立接收适配器  
 独立接收适配器不具有**Terminate**因为它们没有驻留在 BizTalk 服务中对其调用。 相反，它们应调用**IBTTransportProxy**。**TerminateIsolatedReceiver**通知消息引擎它们即将关闭。  
  
## <a name="clean-up-com-objects-by-using-marshalreleasecomobject"></a>使用 Marshal.ReleaseComObject 清理 COM 对象  
 编写使用 COM 对象的托管的代码时，公共语言运行时 (CLR) 生成保存到 COM 对象的引用的代理对象。 代理对象是托管的对象，可能会有所垃圾回收的常用规则。 出现问题的因为垃圾回收器只能看到.NET 运行时分配，并不知道的 COM 对象的内存。 因为代理对象较小，大型的 COM 对象可能保留在内存中因为 CLR 垃圾回收器不是意识到这一点。  
  
 若要避免此问题，显式释放底层的 COM 对象时，你已完成，特别是任何**IBTTransportBatch**对象。 执行此操作通过调用**封送**。**ReleaseComObject**。  
  
> [!NOTE]
>  **ReleaseComObject**返回剩余引用数，并仅在返回值为零，此发布的 COM 对象。 通常**ReleaseComObject**在一个循环，以便确保在释放的对象中调用。 该应用程序完成后，应调用**SuppressFinalize**此对象上因为不需要完成。 最后一步是检查是否确实为 COM 对象。  
  
 下面的代码演示以上描述的过程：  
  
```  
if (Marshal.IsComObject (batch))  
(  
While (0 <Marshal.ReleaseComObject(batch)  
;  
GC.SuppressFinalize (batch);  
  
```  
  
 显式释放**IBTTransportBatch**从返回的对象**GetBatch**可以使性能得到显著提高。  
  
## <a name="always-use-terminate-when-closing-an-adapter"></a>始终使用 Terminate 关闭适配器  
 若要将你的代码识别为适配器的 BizTalk server，必须实现一个接口，称为**IBTTransportControl**。 此接口定义 BizTalk Server 如何与您的适配器，并按以下方式定义：  
  
```  
public interface IBTTransportControl   
{  
void Initialize(IBTTransportProxy transportProxy);  
void Terminate();  
}  
```  
  
 此接口包含两个方法，**初始化**并**终止**。  
  
### <a name="initialize"></a>“初始化”  
 BizTalk Server 调用**初始化**方法后它会加载适配器程序集。 这样做可传递到适配器的传输代理 （BizTalk Server 的主要句柄）。 实现**初始化**只需将传输代理存储在成员变量。  
  
### <a name="terminate"></a>终止  
 BizTalk Server 调用**Terminate**在服务关闭以给予适配器时间来完成的所有批处理执行的方法。 这样的实现**Terminate**变得更为复杂的方法。  
  
 适配器不应返回从**Terminate**调用，直到它具有任何挂起的工作已完成。 当 BizTalk Server 调用**Terminate**，适配器应尝试停止所有当前任务并不会启动任何新的。  
  
 因为**Terminate**称为作为服务关闭的一部分，服务控制管理器结束进程，如果适配器永久阻止**终止**。 在这种情况下，您看到从服务控制管理器警告，因为它将停止 BizTalk Server 服务。 如果可能，避免终止以此方式提前适配器。 如果适配器不会适当地处理终止进程，并且还有线程在运行时该过程开始关闭的情况下，然后可能会在关闭偶尔会看到从 BizTalk Server 的访问冲突。  
  
 由于 BizTalk Server 接口的异步性质，很可能，在负载下将有多批以及线程需要执行。 **Terminate**应实现调用要等待的适配器已成功执行 BizTalk Server 在继续之前每个批处理结束。 通过发出信号批已经结束**BatchComplete**从 BizTalk Server 的回调。 **Terminate**调用应等待每个挂起**BatchComplete**发生这种情况。 但是，必须成功执行批处理。 也就是说，调用**IBTTransportBatch**::**完成**不得失败。 如果在调用**IBTTransportBatch**::**完成**失败，没有批处理回调。  
  
 您意识到，您需要将同步代码添加到您的适配器后，该实现其实非常简单。  
  
 一个简单的方法是实现与一个复合同步对象**输入**并**保留**方法的工作线程和一个**终止**方法时阻止线程是仍包含在受保护的执行。 (顺便说一下，解决方法是非常类似于熟悉的多个读取器 / 单编写器结构的工作线程可以认为的读取器和**终止**方法作为编写器。)  
  
 **终止**方法如下所示：  
  
```  
void terminate ()  
{  
this.control.Terminate();  
}  
```  
  
 对于每个工作线程：  
  
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
  
 在从 BizTalk Server 回调：  
  
```  
batchComplete (…)  
{  
//  the callback from BizTalk Server  
//  process results  
this.control.Leave();  
}  
```  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 附带了 ControlledTermination.cs 在基本适配器示例中，显示此处描述的同步机制的示例代码。