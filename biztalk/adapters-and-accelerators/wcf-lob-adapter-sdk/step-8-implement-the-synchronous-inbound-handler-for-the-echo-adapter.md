---
title: 步骤 8：实现 Echo 适配器的同步入站处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 723eac73-40c4-41b4-aca1-dd7451d25bfe
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3a692493b39b51499a2a42adfcbd485dd4cfc0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363150"
---
# <a name="step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter"></a>步骤 8：实现 Echo 适配器的同步入站处理程序
![步骤 8 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-8of9.gif "Step_8of9")  
  
 **若要完成的时间：** 45 分钟  
  
 在此步骤中，将实现 echo 适配器的入站的功能。 此功能允许适配器以侦听数据或从目标系统的事件。 根据[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，只需实现`Microsoft.ServiceModel.Channels.Common.IInboundHandler`接口，如果您的适配器支持入站的功能。 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]自动生成派生的类为您调用 EchoAdpterInboundHandler。  
  
 在以下部分中，更新 EchoAdpterInboundHandler 类，以获取更好地了解如何实现此接口。 完成此步骤，必须 echo 适配器的工作入站处理程序。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，你必须已成功完成[步骤 7:实现 Echo 适配器的同步出站处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)。 基本熟悉`Microsoft.ServiceModel.Channels.Common.IInboundHandler`也会有所帮助。  
  
## <a name="the-iinboundhandler-interface"></a>IInboundHandler 接口  
 `Microsoft.ServiceModel.Channels.Common.IInboundHandler`定义为：  
  
```  
public interface IInboundHandler : IConnectionHandler, IDisposable  
{  
          void StartListener(string[] actions, TimeSpan timeout);  
          void StopListener(TimeSpan timeout);  
          bool TryReceive(TimeSpan timeout, out Message message, out IInboundReply reply);  
          bool WaitForMessage(TimeSpan timeout);  
}  
```  
  
 方法说明是：  
  
|方法|Description|  
|------------|-----------------|  
|StartListener|开始侦听消息与提供的 Ws-addressing 操作。 如果未指定，它侦听所有或默认操作。|  
|StopListener|停止侦听。|  
|TryReceive|尝试接收来自目标系统的入站的消息。|  
|WaitForMessage|等待来自目标系统的入站 WCF 消息。|  
  
 有关每个方法参数的说明的更多详细信息，请参阅文档上`Microsoft.ServiceModel.Channels.Common.IInboundHandler`接口。  
  
## <a name="implementing-the-echoadpterinboundhandler"></a>实现 EchoAdpterInboundHandler  
 Echo 适配器使用`System.IO.FileSystemWatcher`来模拟在目标系统。 在下面的示例，实现每个方法内的`Microsoft.ServiceModel.Channels.Common.IInboundHandler`接口，StartListener、 StopListener、 TryReceive 和 WaitForMessage。  
  
#### <a name="to-implement-iinboundhandler-interface-in-the-echoadpterinboundhandler-class"></a>若要在 EchoAdpterInboundHandler 类中实现 IInboundHandler 接口  
  
1.  在解决方案资源管理器中双击**EchoAdapterInboundHandler.cs**文件。  
  
2.  在 Visual Studio 编辑器中，将以下行添加到现有的 using 指令集。  
  
    ```csharp  
    using System.IO;  
    using System.ServiceModel.Channels;  
    using System.Xml;  
    using System.Diagnostics;  
    ```  
  
3.  现在将类级变量添加到 EchoAdapterInboundHandler 类。 这些变量用于监视文件活动的文件系统。 将下面的声明复制到在构造函数前的类。  
  
    ```csharp  
    private Queue<Message> inboundQueue;  
    private FileSystemWatcher inboundWatcher;  
    private Object inboundQueueSynchronizationLock;  
    private string path;  
    private string filter;  
    ```  
  
4.  在 EchoAdapterInboundHandler 构造函数方法中，添加以下代码来初始化监视基础结构的文件，并要捕获的监视路径和筛选器。  
  
    ```csharp  
    inboundWatcher = null;  
    inboundQueueSynchronizationLock = new Object();  
    path = connection.ConnectionFactory.Adapter.InboundFileSystemWatcherFolder;  
    filter = connection.ConnectionFactory.Adapter.InboundFileFilter;  
    ```  
  
5.  现在，添加以下代码**StartListener**方法。 该代码实现逻辑以验证参数并开始监视文件活动。  
  
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
  
6.  继续通过添加一个实现**StopListener**方法。  
  
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
  
7.  现在提供一个实现**TryReveive**方法。 此方法检索最新文件从内部队列接收消息，如果有可用。  
  
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
  
8.  继续通过添加一个实现**WaitForMessage**方法。  
  
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
  
9. 现在提供的文件观察程序的回调。 若要执行此操作，添加新方法**FileMonitor_Created**到**EchoAdapterInboundAdapter**类。  
  
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
  
10. 现在，你必须删除**NotImplementedException**由内部引发的异常**EchoAdapterInboundReply**类。 若要执行此操作，删除以下语句从**中止**并**答复**方法。  
  
    ```csharp  
    throw new NotImplementedException("The method or operation is not implemented.");  
    ```  
  
     你**中止**并**答复**方法应如下所示。  
  
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
  
11. 若要完成入站处理程序的实现，添加以下类**EchoAdapterOutboundHandler.cs**。 此类支持超时的入站处理程序实现。  
  
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
  
12. 在 Visual Studio 中，在**文件**菜单上，单击**全部保存**。  
  
13. 在“生成”  菜单上，单击“生成解决方案” 。 它应编译错误。 如果没有，请确保您已按照上述每个步骤。  
  
> [!NOTE]
>  保存所做的工作。 可以安全地关闭 Visual Studio 或转到下一步，[步骤 9:生成并部署 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md)。  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 在 Echo 适配器教程的此步骤中，为入站处理程序提供实现。 这种实现提供文件观察 Echo 适配器使用的功能**FileSystemWatcher**的.NET Framework 类。  
  
## <a name="next-steps"></a>后续步骤  
 在下一步中，你将部署适配器。  
  
## <a name="see-also"></a>请参阅  
 [步骤 9：生成并部署 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md)   
 [步骤 7：实现 Echo 适配器的同步出站处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)