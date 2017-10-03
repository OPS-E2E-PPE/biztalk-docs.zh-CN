---
title: "步骤 8： 为 Echo 适配器实现同步的入站处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 723eac73-40c4-41b4-aca1-dd7451d25bfe
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da34bca28f073babac4907b7d408d0642a234e2a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter"></a><span data-ttu-id="97ef9-102">步骤 8： 为 Echo 适配器实现同步的入站处理程序</span><span class="sxs-lookup"><span data-stu-id="97ef9-102">Step 8: Implement the Synchronous Inbound Handler for the Echo Adapter</span></span>
<span data-ttu-id="97ef9-103">![步骤 8 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-8of9.gif "Step_8of9")</span><span class="sxs-lookup"><span data-stu-id="97ef9-103">![Step 8 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-8of9.gif "Step_8of9")</span></span>  
  
 <span data-ttu-id="97ef9-104">**完成时间：** 45 分钟</span><span class="sxs-lookup"><span data-stu-id="97ef9-104">**Time to complete:** 45 minutes</span></span>  
  
 <span data-ttu-id="97ef9-105">在此步骤中，你可以实现入站的回显适配器的功能。</span><span class="sxs-lookup"><span data-stu-id="97ef9-105">In this step, you implement the inbound capability of the echo adapter.</span></span> <span data-ttu-id="97ef9-106">此功能允许要侦听的数据或事件从目标系统的适配器。</span><span class="sxs-lookup"><span data-stu-id="97ef9-106">This capability allows the adapter to listen for data or events from the target system.</span></span> <span data-ttu-id="97ef9-107">根据[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，只需实现`Microsoft.ServiceModel.Channels.Common.IInboundHandler`时你的适配器支持入站的功能的接口。</span><span class="sxs-lookup"><span data-stu-id="97ef9-107">According to the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], you only need to implement the `Microsoft.ServiceModel.Channels.Common.IInboundHandler` interface, when your adapter supports inbound capability.</span></span> <span data-ttu-id="97ef9-108">[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]自动生成为您调用 EchoAdpterInboundHandler 派生的类。</span><span class="sxs-lookup"><span data-stu-id="97ef9-108">The [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] automatically generates the derived class called EchoAdpterInboundHandler for you.</span></span>  
  
 <span data-ttu-id="97ef9-109">在以下部分中，你将更新 EchoAdpterInboundHandler 类，以获取更好地了解如何实现此接口。</span><span class="sxs-lookup"><span data-stu-id="97ef9-109">In the following section, you update the EchoAdpterInboundHandler class to get a better understanding on how to implement this interface.</span></span> <span data-ttu-id="97ef9-110">完成此步骤后，必须为 echo 适配器工作入站处理程序。</span><span class="sxs-lookup"><span data-stu-id="97ef9-110">When you complete this step, you have a working inbound handler for the echo adapter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="97ef9-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="97ef9-111">Prerequisites</span></span>  
 <span data-ttu-id="97ef9-112">在开始此步骤之前，你必须已成功完成[步骤 7： 为 Echo 适配器实现同步的出站处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="97ef9-112">Before you begin this step, you must have successfully completed [Step 7: Implement the Synchronous Outbound Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md).</span></span> <span data-ttu-id="97ef9-113">基本熟悉`Microsoft.ServiceModel.Channels.Common.IInboundHandler`也是有帮助。</span><span class="sxs-lookup"><span data-stu-id="97ef9-113">A basic familiarity with `Microsoft.ServiceModel.Channels.Common.IInboundHandler` is also helpful.</span></span>  
  
## <a name="the-iinboundhandler-interface"></a><span data-ttu-id="97ef9-114">IInboundHandler 接口</span><span class="sxs-lookup"><span data-stu-id="97ef9-114">The IInboundHandler Interface</span></span>  
 <span data-ttu-id="97ef9-115">`Microsoft.ServiceModel.Channels.Common.IInboundHandler`定义为：</span><span class="sxs-lookup"><span data-stu-id="97ef9-115">The `Microsoft.ServiceModel.Channels.Common.IInboundHandler` is defined as:</span></span>  
  
```  
public interface IInboundHandler : IConnectionHandler, IDisposable  
{  
          void StartListener(string[] actions, TimeSpan timeout);  
          void StopListener(TimeSpan timeout);  
          bool TryReceive(TimeSpan timeout, out Message message, out IInboundReply reply);  
          bool WaitForMessage(TimeSpan timeout);  
}  
```  
  
 <span data-ttu-id="97ef9-116">方法说明是：</span><span class="sxs-lookup"><span data-stu-id="97ef9-116">The method descriptions are:</span></span>  
  
|<span data-ttu-id="97ef9-117">方法</span><span class="sxs-lookup"><span data-stu-id="97ef9-117">Method</span></span>|<span data-ttu-id="97ef9-118">Description</span><span class="sxs-lookup"><span data-stu-id="97ef9-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="97ef9-119">StartListener</span><span class="sxs-lookup"><span data-stu-id="97ef9-119">StartListener</span></span>|<span data-ttu-id="97ef9-120">开始侦听消息与提供的 Ws-addressing 操作。</span><span class="sxs-lookup"><span data-stu-id="97ef9-120">Starts listening to messages with the provided WS-Addressing Actions.</span></span> <span data-ttu-id="97ef9-121">如果未指定，它侦听所有或默认操作。</span><span class="sxs-lookup"><span data-stu-id="97ef9-121">If none is specified, it listens to all or the default actions.</span></span>|  
|<span data-ttu-id="97ef9-122">StopListener</span><span class="sxs-lookup"><span data-stu-id="97ef9-122">StopListener</span></span>|<span data-ttu-id="97ef9-123">停止侦听。</span><span class="sxs-lookup"><span data-stu-id="97ef9-123">Stops listening.</span></span>|  
|<span data-ttu-id="97ef9-124">TryReceive</span><span class="sxs-lookup"><span data-stu-id="97ef9-124">TryReceive</span></span>|<span data-ttu-id="97ef9-125">尝试从目标系统收到一条入站的消息。</span><span class="sxs-lookup"><span data-stu-id="97ef9-125">Tries to receive an inbound message from the target system.</span></span>|  
|<span data-ttu-id="97ef9-126">WaitForMessage</span><span class="sxs-lookup"><span data-stu-id="97ef9-126">WaitForMessage</span></span>|<span data-ttu-id="97ef9-127">等待来自目标系统的入站 WCF 消息。</span><span class="sxs-lookup"><span data-stu-id="97ef9-127">Waits for an inbound WCF message from the target system.</span></span>|  
  
 <span data-ttu-id="97ef9-128">有关每个方法参数的说明的更多详细信息，请参阅文档上`Microsoft.ServiceModel.Channels.Common.IInboundHandler`接口。</span><span class="sxs-lookup"><span data-stu-id="97ef9-128">For more details on the description for each method parameters, see the documentation on the `Microsoft.ServiceModel.Channels.Common.IInboundHandler` interface.</span></span>  
  
## <a name="implementing-the-echoadpterinboundhandler"></a><span data-ttu-id="97ef9-129">实现 EchoAdpterInboundHandler</span><span class="sxs-lookup"><span data-stu-id="97ef9-129">Implementing the EchoAdpterInboundHandler</span></span>  
 <span data-ttu-id="97ef9-130">Echo 适配器使用`System.IO.FileSystemWatcher`以模拟目标系统。</span><span class="sxs-lookup"><span data-stu-id="97ef9-130">The echo adapter uses the `System.IO.FileSystemWatcher` to simulate the target system.</span></span> <span data-ttu-id="97ef9-131">在下面的示例，实现中的每个方法`Microsoft.ServiceModel.Channels.Common.IInboundHandler`接口，StartListener、 StopListener、 TryReceive 和 WaitForMessage。</span><span class="sxs-lookup"><span data-stu-id="97ef9-131">In the following, you implement each method within the `Microsoft.ServiceModel.Channels.Common.IInboundHandler` interface, StartListener, StopListener, TryReceive and WaitForMessage.</span></span>  
  
#### <a name="to-implement-iinboundhandler-interface-in-the-echoadpterinboundhandler-class"></a><span data-ttu-id="97ef9-132">若要在 EchoAdpterInboundHandler 类中实现 IInboundHandler 接口</span><span class="sxs-lookup"><span data-stu-id="97ef9-132">To implement IInboundHandler interface in the EchoAdpterInboundHandler class</span></span>  
  
1.  <span data-ttu-id="97ef9-133">在解决方案资源管理器中，双击**EchoAdapterInboundHandler.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="97ef9-133">In Solution Explorer, double-click the **EchoAdapterInboundHandler.cs** file.</span></span>  
  
2.  <span data-ttu-id="97ef9-134">在 Visual Studio 编辑器中，将以下行添加到现有的 using 指令集。</span><span class="sxs-lookup"><span data-stu-id="97ef9-134">In the Visual Studio editor, add the following lines to the existing set of using directives.</span></span>  
  
    ```csharp  
    using System.IO;  
    using System.ServiceModel.Channels;  
    using System.Xml;  
    using System.Diagnostics;  
    ```  
  
3.  <span data-ttu-id="97ef9-135">现在将类级变量添加到 EchoAdapterInboundHandler 类。</span><span class="sxs-lookup"><span data-stu-id="97ef9-135">Now add class level variables to the EchoAdapterInboundHandler class.</span></span> <span data-ttu-id="97ef9-136">这些变量用于监视文件活动的文件系统。</span><span class="sxs-lookup"><span data-stu-id="97ef9-136">These variables are used to monitor the file system for file activity.</span></span> <span data-ttu-id="97ef9-137">将下面的声明复制到构造函数前类。</span><span class="sxs-lookup"><span data-stu-id="97ef9-137">Copy the declarations below into the class before the constructor.</span></span>  
  
    ```csharp  
    private Queue<Message> inboundQueue;  
    private FileSystemWatcher inboundWatcher;  
    private Object inboundQueueSynchronizationLock;  
    private string path;  
    private string filter;  
    ```  
  
4.  <span data-ttu-id="97ef9-138">在 EchoAdapterInboundHandler 构造函数方法中，添加以下代码以初始化文件监视基础结构并捕获的监视路径和筛选器。</span><span class="sxs-lookup"><span data-stu-id="97ef9-138">Inside the EchoAdapterInboundHandler constructor method, add the following code to initialize the file watching infrastructure and to capture the monitoring path and filter.</span></span>  
  
    ```csharp  
    inboundWatcher = null;  
    inboundQueueSynchronizationLock = new Object();  
    path = connection.ConnectionFactory.Adapter.InboundFileSystemWatcherFolder;  
    filter = connection.ConnectionFactory.Adapter.InboundFileFilter;  
    ```  
  
5.  <span data-ttu-id="97ef9-139">现在添加以下代码到**StartListener**方法。</span><span class="sxs-lookup"><span data-stu-id="97ef9-139">Now add the following code to the **StartListener** method.</span></span> <span data-ttu-id="97ef9-140">该代码实现逻辑以验证参数并启动对文件活动的监视。</span><span class="sxs-lookup"><span data-stu-id="97ef9-140">The code implements logic to verify parameters and start monitoring for file activity.</span></span>  
  
    ```csharp  
    // if no actions are provided, log an error in the trace log  
    // and throw an exception  
    if (actions.Length == 0)  
    {  
        EchoAdapterUtilities.Trace.Trace(TraceEventType.Error, "http://echoadapterv2/startlistener/noactions", "No operation actions were received for listener to do specific processing.", this);  
        throw new AdapterException("Unable to receive any actions for inbound handler to start listening.");  
    }  
  
    inboundQueue = new Queue<Message>();  
    foreach (string action in actions)  
    {  
        // for the OnReceiveEcho action listen for a new file created event  
        if ("Echo/OnReceiveEcho".Equals(action))  
        {  
            if (inboundWatcher == null)  
            {  
                inboundWatcher = new FileSystemWatcher(path);  
                inboundWatcher.Filter = filter;  
                // Begin monitoring  
                inboundWatcher.EnableRaisingEvents = true;  
            }  
            inboundWatcher.Created += new FileSystemEventHandler(FileMonitor_Created);  
            EchoAdapterUtilities.Trace.Trace(TraceEventType.Information, "http://echoadapterv2/startlistener", "Listening for file created event for " + filter + " in path " + path, this);  
        }  
    }  
    ```  
  
6.  <span data-ttu-id="97ef9-141">继续通过添加的实现**StopListener**方法。</span><span class="sxs-lookup"><span data-stu-id="97ef9-141">Continue by adding an implementation for the **StopListener** method.</span></span>  
  
    ```csharp  
    if (inboundWatcher != null)  
    {  
        // End monitoring  
        inboundWatcher.EnableRaisingEvents = false;  
        inboundWatcher = null;  
    }  
    lock (inboundQueueSynchronizationLock)  
    {  
        inboundQueue.Clear();  
        inboundQueue = null;  
    }  
    ```  
  
7.  <span data-ttu-id="97ef9-142">现在提供一个实现**TryReveive**方法。</span><span class="sxs-lookup"><span data-stu-id="97ef9-142">Now provide an implementation for the **TryReveive** method.</span></span> <span data-ttu-id="97ef9-143">此方法检索最新的文件从内部队列接收消息，如果有的话。</span><span class="sxs-lookup"><span data-stu-id="97ef9-143">This method retrieves the most recent file receive message from the internal queue if one is available.</span></span>  
  
    ```csharp  
    reply = new EchoAdapterInboundReply();  
    message = null;  
    TimeoutHelper timeoutHelper = new TimeoutHelper(timeout);  
    while (true)  
    {  
        lock (inboundQueueSynchronizationLock)  
        {  
            if (inboundQueue == null)  
            {  
                //listener has been closed  
                return false;  
            }  
            if (inboundQueue.Count != 0)  
            {  
                message = inboundQueue.Dequeue();  
                if (message != null)  
                {  
                    return true;  
                }  
            }  
        }  
        if (timeoutHelper.IsExpired)  
        {  
            return false;  
        }  
        //wait for sometime, and check again  
        System.Threading.Thread.Sleep(500);  
    }  
    ```  
  
8.  <span data-ttu-id="97ef9-144">继续通过添加的实现**WaitForMessage**方法。</span><span class="sxs-lookup"><span data-stu-id="97ef9-144">Continue by adding an implementation for the **WaitForMessage** method.</span></span>  
  
    ```csharp  
    while (inboundQueue.Count == 0) { };  
    Message msg = inboundQueue.Peek();  
    if (msg != null)  
    {  
        return true;  
    }  
    else  
    {  
        return false;  
    }  
    ```  
  
9. <span data-ttu-id="97ef9-145">现在提供文件观察程序的回调。</span><span class="sxs-lookup"><span data-stu-id="97ef9-145">Now supply the callback for the file watcher.</span></span> <span data-ttu-id="97ef9-146">为此，请添加新方法**FileMonitor_Created**到**EchoAdapterInboundAdapter**类。</span><span class="sxs-lookup"><span data-stu-id="97ef9-146">To do so, add the new method **FileMonitor_Created** to the **EchoAdapterInboundAdapter** class.</span></span>  
  
    ```csharp  
    private void FileMonitor_Created(object sender, FileSystemEventArgs e)  
    {  
        lock (inboundQueueSynchronizationLock)  
        {  
            if (e.ChangeType == WatcherChangeTypes.Created)  
            {  
                // wait for file to close - should do this in a better manner  
                System.Threading.Thread.Sleep(500);  
                try  
                {  
                    EchoAdapterUtilities.Trace.Trace(TraceEventType.Information, "http://echoadapterv2/FileMonitorCreated", "File " + e.FullPath + " created.", this);  
                    FileInfo fileInfo = new FileInfo(e.FullPath);  
                    // Create WCF message to send to the inbound service  
                    // that is listening for messages from adapter  
                    String xmlData = String.Format(@"<OnReceiveEcho xmlns=""{0}""><path>{1}</path><length>{2}</length></OnReceiveEcho>", EchoAdapter.SERVICENAMESPACE, e.FullPath, fileInfo.Length);  
                    // set action string  
                    XmlReader reader = XmlReader.Create(new StringReader(xmlData));  
                    // create WCF message  
                    Message requestMessage = Message.CreateMessage(MessageVersion.Default  
                                , "Echo/OnReceiveEcho"  
                                , reader);  
                    requestMessage.Headers.To = new Uri(path);  
                    inboundQueue.Enqueue(requestMessage);  
                }  
                catch (Exception ex)  
                {  
                    String message = String.Format("An exception was thrown while trying to open file {1}.", e.FullPath);  
                    EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Error, "http://echoadapterv2/FileMonitorCreated", message, this, ex);  
                    throw new AdapterException(message, ex);  
                }  
            }  
        }  
    }  
    ```  
  
10. <span data-ttu-id="97ef9-147">现在，你必须删除**NotImplementedException**引发的内部异常**EchoAdapterInboundReply**类。</span><span class="sxs-lookup"><span data-stu-id="97ef9-147">Now you must remove the **NotImplementedException** exceptions thrown by the internal **EchoAdapterInboundReply** class.</span></span> <span data-ttu-id="97ef9-148">若要执行此操作，请删除中的以下语句**中止**和**答复**方法。</span><span class="sxs-lookup"><span data-stu-id="97ef9-148">To do this, delete the following statement from the **Abort** and **Reply** methods.</span></span>  
  
    ```csharp  
    throw new NotImplementedException("The method or operation is not implemented.");  
    ```  
  
     <span data-ttu-id="97ef9-149">你**中止**和**答复**方法应类似于以下。</span><span class="sxs-lookup"><span data-stu-id="97ef9-149">Your **Abort** and **Reply** methods should be similar to the following.</span></span>  
  
    ```csharp  
    /// <summary>  
    /// Abort the inbound reply call  
    /// </summary>  
    public override void Abort()  
    {  
    }  
  
    /// <summary>  
    /// Reply message implemented  
    /// </summary>  
    public override void Reply(System.ServiceModel.Channels.Message message  
        , TimeSpan timeout)  
    {  
    }  
    ```  
  
11. <span data-ttu-id="97ef9-150">若要完成的入站处理程序的实现，添加以下类到**EchoAdapterOutboundHandler.cs**。</span><span class="sxs-lookup"><span data-stu-id="97ef9-150">To complete the implementation for the inbound handler, add the following class to **EchoAdapterOutboundHandler.cs**.</span></span> <span data-ttu-id="97ef9-151">此类支持超时的入站处理程序实现。</span><span class="sxs-lookup"><span data-stu-id="97ef9-151">This class provides timeout support for the inbound handler implementation.</span></span>  
  
    ```csharp  
    /// <summary>  
    /// Utility class containing helper functions for measuring timeout   
    /// </summary>  
    class TimeoutHelper  
    {  
        private TimeSpan timeout;  
        private DateTime creationTime;  
        private Boolean isInfinite;  
  
        /// <summary>  
        /// Constructor  
        /// </summary>  
        /// <param name="timeout"></param>  
        public TimeoutHelper(TimeSpan timeout)  
        {  
            this.creationTime = DateTime.Now;  
            this.timeout = timeout;  
            if (timeout.Equals(Infinite)) this.isInfinite = true;  
        }  
  
        /// <summary>  
        /// Value of infinite timespan  
        /// </summary>  
        public static TimeSpan Infinite  
        {  
            get { return TimeSpan.MaxValue; }  
        }  
  
        /// <summary>  
        /// Value indicating remaining timeout  
        /// </summary>  
        public TimeSpan RemainingTimeout  
        {  
            get  
            {  
                if (this.isInfinite) return Infinite;  
                return this.timeout.Subtract(DateTime.Now.Subtract(this.creationTime));  
            }  
        }  
  
        /// <summary>  
        /// Get remaining timeout value and throw an exception if the timeout  
        /// has expired.  
        /// </summary>  
        /// <param name="exceptionMessage"></param>  
        /// <returns></returns>  
        public TimeSpan GetRemainingTimeoutAndThrowIfExpired(String exceptionMessage)  
        {  
            if (this.isInfinite) return Infinite;  
            if (RemainingTimeout < TimeSpan.Zero)  
            {  
                throw new TimeoutException(exceptionMessage);  
            }  
            return RemainingTimeout;  
        }  
  
        /// <summary>  
        /// Throw an exception if the timeout has expired.  
        /// </summary>  
        /// <param name="exceptionMessage"></param>  
        public void ThrowIfTimeoutExpired(String exceptionMessage)  
        {  
            if (RemainingTimeout < TimeSpan.Zero)  
            {  
                throw new TimeoutException(exceptionMessage);  
            }  
  
        }  
  
        /// <summary>  
        /// Value indicating whether timeout has expired.  
        /// </summary>  
        public Boolean IsExpired  
        {  
            get  
            {  
                if (this.isInfinite) return false;  
                return RemainingTimeout < TimeSpan.Zero;  
            }  
        }  
    }  
    ```  
  
12. <span data-ttu-id="97ef9-152">在 Visual Studio 中，在**文件**菜单上，单击**保存所有**。</span><span class="sxs-lookup"><span data-stu-id="97ef9-152">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
13. <span data-ttu-id="97ef9-153">在“生成”  菜单上，单击“生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="97ef9-153">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="97ef9-154">它应编译错误。</span><span class="sxs-lookup"><span data-stu-id="97ef9-154">It should compile without errors.</span></span> <span data-ttu-id="97ef9-155">如果没有，请确保您已按照上述每个步骤。</span><span class="sxs-lookup"><span data-stu-id="97ef9-155">If not, ensure that you have followed every step above.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97ef9-156">保存所做的工作。</span><span class="sxs-lookup"><span data-stu-id="97ef9-156">You saved your work.</span></span> <span data-ttu-id="97ef9-157">你可以安全地在此时关闭 Visual Studio 或转到下一步，[步骤 9： 生成和部署 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="97ef9-157">You can safely close Visual Studio at this time or go to the next step, [Step 9: Build and Deploy the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="97ef9-158">未我只需做什么？</span><span class="sxs-lookup"><span data-stu-id="97ef9-158">What Did I Just Do?</span></span>  
 <span data-ttu-id="97ef9-159">在此步骤中回显适配器教程，入站处理程序提供实现。</span><span class="sxs-lookup"><span data-stu-id="97ef9-159">In this step of the Echo Adapter tutorial, you provided an implementation for the Inbound Handler.</span></span> <span data-ttu-id="97ef9-160">这种实现提供监视功能 Echo 适配器使用的文件**FileSystemWatcher**的.NET framework 的类。</span><span class="sxs-lookup"><span data-stu-id="97ef9-160">This implementation provides file watching capabilities for the Echo Adapter using the **FileSystemWatcher** class of the .NET Framework.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="97ef9-161">后续步骤</span><span class="sxs-lookup"><span data-stu-id="97ef9-161">Next Steps</span></span>  
 <span data-ttu-id="97ef9-162">在下一步的步骤中，你将部署适配器。</span><span class="sxs-lookup"><span data-stu-id="97ef9-162">In the next step, you deploy the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97ef9-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97ef9-163">See Also</span></span>  
 <span data-ttu-id="97ef9-164">[步骤 9： 生成并部署 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="97ef9-164">[Step 9: Build and Deploy the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="97ef9-165">步骤 7： 为 Echo 适配器实现同步的出站处理程序</span><span class="sxs-lookup"><span data-stu-id="97ef9-165">Step 7: Implement the Synchronous Outbound Handler for the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)