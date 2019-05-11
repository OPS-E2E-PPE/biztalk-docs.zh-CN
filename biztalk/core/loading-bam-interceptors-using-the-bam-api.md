---
title: 使用 BAM API 加载 BAM 侦听器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d77ea5fb-a796-48f1-8c77-173e995c5252
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1236d674a643224d2aaf5ca2cb5be2be15c2f2bb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331150"
---
# <a name="loading-bam-interceptors-using-the-bam-api"></a><span data-ttu-id="93504-102">使用 BAM API 加载 BAM 侦听器</span><span class="sxs-lookup"><span data-stu-id="93504-102">Loading BAM Interceptors Using the BAM API</span></span>
<span data-ttu-id="93504-103">本主题提供有关如何从代码（而不是通过配置文件）加载 WF 和 WCF 侦听器的信息。</span><span class="sxs-lookup"><span data-stu-id="93504-103">This topic provides information about loading the WF and WCF interceptors from your code rather than through a configuration file.</span></span>  
  
## <a name="loading-the-wf-interceptor-from-code"></a><span data-ttu-id="93504-104">从代码加载 WF 侦听器</span><span class="sxs-lookup"><span data-stu-id="93504-104">Loading the WF Interceptor from Code</span></span>  
 <span data-ttu-id="93504-105">若要从代码加载 WF 侦听器运行时，必须创建 WorkflowRuntime 的新实例，并使用 BamTrackingService 的新实例调用 AddService 方法。</span><span class="sxs-lookup"><span data-stu-id="93504-105">To load the WF interceptor runtime from your code, you must create a new instance of WorkflowRuntime and call the AddService method with a new instance of BamTrackingService.</span></span> <span data-ttu-id="93504-106">此过程演示如下。</span><span class="sxs-lookup"><span data-stu-id="93504-106">This is demonstrated below.</span></span>  
  
```csharp  
string connectionString = "Integrated Security=SSPI;Data Source=.;Initial Catalog=BAMPrimaryImport";  
int PollingIntervalSec = 300;  
  
WorkflowRuntime workflowRuntime = new WorkflowRuntime();  
workflowRuntime.AddService(new BamTrackingService(connectionString, interceptorConfigurationPollingInterval));  
```  
  
## <a name="loading-the-wcf-interceptor-from-code"></a><span data-ttu-id="93504-107">从代码加载 WCF 侦听器</span><span class="sxs-lookup"><span data-stu-id="93504-107">Loading the WCF Interceptor from Code</span></span>  
 <span data-ttu-id="93504-108">若要加载 WCF 侦听器，必须创建一个打开服务并可访问实现的派生类。</span><span class="sxs-lookup"><span data-stu-id="93504-108">To load the WCF interceptor, you must create a derived class that opens the service and is accessible to your implementation.</span></span> <span data-ttu-id="93504-109">此过程演示如下。</span><span class="sxs-lookup"><span data-stu-id="93504-109">This is demonstrated below.</span></span>  
  
```csharp  
// Your project must have a reference to Microsoft.BizTalk.BAM.Interceptors.dll.  
// Create a derived class accessible to the implementation that opens the service.  
internal class MyBamBehaviorExtension : BamBehaviorExtension  
{  
    internal MyBamBehaviorExtension(string connectionString, int pollingInterval)  
        : base()  
    {  
        this.ConnectionString = connectionString;  
        this.PollingIntervalSec = pollingInterval.ToString();  
    }  
  
    internal IEndpointBehavior Create()  
    {  
        return (IEndpointBehavior) this.CreateBehavior();  
    }  
}  
  
// Add the endpoint behavior just before the service is opened.   
// In this example the connection string and polling intervals are being read from appSettings in App.config.  
MyBamBehaviorExtension bamBehaviorExtension = new MyBamBehaviorExtension(ConfigurationManager.AppSettings["ConnectionString"], int.Parse(ConfigurationManager.AppSettings["PollingIntervalSec"]));  
IEndpointBehavior bamBehavior = bamBehaviorExtension.Create();  
foreach (System.ServiceModel.Description.ServiceEndpoint endpoint in myServiceHost.Description.Endpoints)  
{  
    if (endpoint.Behaviors.Find<MyBamBehaviorExtension>() == null)  
        endpoint.Behaviors.Add(bamBehavior);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="93504-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="93504-110">See Also</span></span>  
 [<span data-ttu-id="93504-111">使用 BAM WCF 和 WF 侦听器</span><span class="sxs-lookup"><span data-stu-id="93504-111">Using the BAM WCF and WF Interceptors</span></span>](../core/using-the-bam-wcf-and-wf-interceptors.md)