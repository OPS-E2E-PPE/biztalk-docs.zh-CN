---
title: "优化 IIS 性能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6722a2ee-3704-4aaa-9b0d-cef97bcb9a04
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93f1bca77aea5aa6c75521e46edc8fc4d01b2d73
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="optimizing-iis-performance"></a>优化 IIS 性能
## <a name="apply-iis-configuration-options-to-improve-iis-performance"></a>应用 IIS 配置选项来提高 IIS 性能  
 Internet 信息服务 (IIS) 公开大量影响 IIS 性能的配置参数。 本主题介绍了几种这些参数，并提供用于设置参数值以提高 IIS 性能的常规指导。  
  
### <a name="log-only-essential-information-or-completely-disable-iis-logging"></a>仅记录基本信息或完全禁用 IIS 日志记录  
 应最小化或甚至在生产环境中禁用 IIS 日志记录。 若要禁用日志记录，请按照下列步骤：  
  
1.  单击**启动**，指向**所有程序**，单击**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
2.  在**连接**窗格中，单击以展开**站点**，单击此项可选择为其您是否要禁用日志记录，请单击选中的网站**功能视图**，，然后双击**日志记录**功能。  
  
3.  单击**禁用**中**操作**窗格中，若要禁用此网站的日志记录。  
  
### <a name="disable-iis-asp-debugging-in-production-environments"></a>禁用 IIS ASP 在生产环境中进行调试  
 应在生产环境中禁用 IIS ASP 调试。 若要禁用 IIS ASP 调试请按照下列步骤： 在**连接**窗格中，单击以展开**站点**，单击以选择为其您是否要禁用 ASP 调试，请单击以选择网站**功能视图**，然后双击**ASP**功能。 单击以展开**编译**，单击以展开**调试属性**，并确认同时**启用客户端调试**和**启用服务器端调试**设置为**False**。  
  
1.  单击**启动**，指向**所有程序**，单击**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
2.  在**连接**窗格中，单击以展开**站点**，单击此项可选择为其您是否要禁用 ASP 调试，请单击选中的网站**功能视图**，，然后双击**ASP**功能。  
  
3.  单击以展开**编译**，单击以展开**调试属性**，并确认同时**启用客户端调试**和**启用服务器端调试**设置为**False**。  
  
4.  如有必要，单击**应用**中**操作**窗格。  
  
 禁用调试 ASP.NET 应用程序和 Web 服务通过指定\<编译调试 ="false"\> web 应用程序的 web.config 文件中的部分。  
  
### <a name="tune-the-value-of-the-asp-threads-per-processor-limit-property"></a>优化每个处理器限制对线程 ASP 属性的值  
 ASP**处理器限制每个线程**属性指定的最大工作线程为每个 IIS 创建的处理器数。 之前的处理器使用率满足至少 50%或更高版本，应增加处理器限制每个线程的值。 此设置可能大大会影响 Web 应用程序的可伸缩性和服务器的性能通常。 因为此属性定义的最大可以同时执行的 ASP 请求数，此设置应保持为默认值，除非你 ASP 应用程序进行扩展的外部组件调用。 在这种情况下，可能会增加处理器限制每个线程的值。 这样做将使要创建更多的线程，以处理更多的并发请求的服务器。 处理器限制每个线程的默认值为 25。 此属性的最大建议的值为 100。  
  
 若要增加处理器限制每个线程的值，请执行以下步骤： 在**连接**窗格中，选择 web 服务器，请单击以选中**功能视图**，然后双击**ASP**功能。  
  
1.  单击**启动**，指向**所有程序**，单击**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
2.  在**连接**窗格中，选择 web 服务器，请单击以选中**功能视图**，然后双击**ASP**功能。  
  
3.  单击以展开**限制属性**下**行为**，单击**处理器限制每个线程**，输入所需的值**线程每个处理器限制**单击**应用**中**操作**窗格。  
  
 有关如何修改中的属性的详细信息\<限制\>元素 IIS 7.5/7.0 \<asp\>元素，请参阅[ASP 限制\<限制\>](http://go.microsoft.com/fwlink/?LinkId=157483)(http://go.microsoft.com/fwlink/?LinkId=157483)。  
  
> [!NOTE]  
>  由于此属性仅可在服务器级别应用，此属性的修改会影响在服务器运行的所有网站。  
  
### <a name="tune-the-value-of-the-asp-queue-length-property"></a>优化 ASP 队列长度属性的值  
 优化此属性的目标是确保良好的响应时间，同时最小化 ASP 请求队列已满时，服务器频率发送到客户端的 HTTP 503 （服务器太忙） 错误。 如果 ASP 队列长度属性的值太低，则服务器将使用更高的频率发送 HTTP 503 错误。 如果 ASP 队列长度属性的值过高，所以用户可能会认为，服务器没有响应时实际上他们的请求正在等待队列中。 通过在高流量期间观看队列，你应识别 web 请求高峰和低谷的模式。 记下的峰值值，并设置正上方的峰值值 ASP 队列长度属性的值。 使用队列以处理短期峰值，请确保响应时间，并限制系统，从而避免重载时持续，出现意外的峰值。 如果你没有用于调整 ASP 队列长度属性的数据，将是很好的起点将队列一对一比率设置为线程的总数。 例如，如果每个处理器限制对线程 ASP 属性设为 25，具有四个处理器 (4 * 25 = 100 线程)，将 ASP 队列长度属性设置为 100 并从该处优化。  
  
 若要增加队列长度的值属性，请按照下列步骤：  
  
1.  单击**启动**，指向**所有程序**，单击**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
2.  在**连接**窗格中，选择 Web 服务器，请单击以选中**功能视图**，然后双击**ASP**功能。  
  
3.  单击以展开**限制属性**下**行为**，单击**队列长度**，输入所需的值**队列长度**，然后单击**应用**中**操作**窗格。  
  
 有关如何修改中的属性的详细信息\<限制\>元素 IIS 7.5/7.0 \<asp\>元素，请参阅[ASP 限制\<限制\>](http://go.microsoft.com/fwlink/?LinkId=157483)(http://go.microsoft.com/fwlink/?LinkId=157483)。  
  
> [!NOTE]  
>  由于此属性仅可在服务器级别应用，此属性的修改会影响在服务器运行的所有网站。  
  
### <a name="tune-the-maxpoolthreads-registry-entry"></a>优化 MaxPoolThreads 注册表项  
 此设置指定每个处理器创建的池线程的数。 池线程监视网络中的请求和处理传入请求。 MaxPoolThreads 计数不包括由 ISAPI 应用程序使用的线程。 通常情况下，不应创建 20 个以上每个处理器的线程。 MaxPoolThreads 是位于 HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\InetInfo\Parameters\ 默认值为 4 的 REG_DWORD 注册表项。  
  
### <a name="disable-wcf-services-tracing"></a>禁用跟踪的 WCF 服务  
 使用配置编辑器工具 (SvcConfigEditor.exe) 禁用在生产环境中进行跟踪的 WCF 服务。 有关配置编辑器工具的详细信息，请参阅[配置编辑器工具 (SvcConfigEditor.exe)](http://go.microsoft.com/fwlink/?LinkID=127070) (http://go.microsoft.com/fwlink/?LinkID=127070)。  
  
### <a name="configure-aspnet-20-maxconcurrentrequests-for-iis-7570-integrated-mode"></a>为 IIS 7.5/7.0 集成模式下配置 ASP.NET 2.0 MaxConcurrentRequests  
 当 ASP.NET 2.0 承载在 IIS 7.5/7.0 在集成模式下时，使用线程处理方式与处理比在 IIS 7.5/7.0 在经典模式下。 当在集成模式下情况下，ASP.NET 2.0 承载于 IIS 7.5 上时，ASP.NET 2.0 限制并发执行的请求而不是并发执行的请求的线程数的次数。 对于同步方案，这将间接限制因为的请求数将相同的线程数的线程数。 但对于异步方案，请求和线程的数量将可能会非常有所不同，因为你可能有更多的请求数多于线程数。 当在集成模式下，可以在 IIS 7.5 上运行 ASP.NET 2.0 时，忽略 minFreeThreads 和 minLocalRequestFreeThreads machine.config 中的"httpRuntime"元素。 对于 IIS 7.5 集成模式，名为内 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0 maxconcurrentrequestspercpu 配置一个 dword 值确定每个 CPU 的并发请求数。 默认情况下，注册表项不存在并且每 CPU 的请求数限制为 12。 .NET framework 3.5 SP1 包括支持配置的 IIS 应用程序池下的 aspnet.config 文件通过对 v2.0 二进制文件的更新。 此配置仅适用于集成模式 （经典/ISAPI 模式会忽略这些设置）。下面列出了新的 aspnet.config 配置节，以使用默认值：  
  
```  
<system.web>  
   <applicationPool maxConcurrentRequestsPerCPU="12" maxConcurrentThreadsPerCPU="0" requestQueueLimit="5000"/>  
</system.web>  
```  
  
 在 IIS 7.5 集成模式下，maxWorkerThreads 和 machine.config 文件的"processModel"部分中的 maxIoThreads 参数不用于管理数本身，运行请求，但它们仍用于控制 CLR 线程池的大小由 ASP.NET。 当 machine.config"processModel"部分有"autoConfig = true"（这是默认设置），这会为应用程序池提供每个逻辑 CPU 的最多 100 个工作线程 (MaxWorkerThreads)。 因此有 2 双核 Cpu 的常见商品服务器都 400 MaxWorkerThreads。 这应该是足够除了要求最高的应用程序。  
  
 有关在 IIS 7.5 上配置 ASP.NET 线程使用情况的详细信息，请参阅[ASP.NET 在 IIS 7.0 上的线程使用情况的 Thomas Marquardt 博客](http://go.microsoft.com/fwlink/?LinkId=157518)(http://go.microsoft.com/fwlink/?LinkId=157518)。  
  
### <a name="configure-aspnet-4-maxconcurrentrequests-for-iis-7570-integrated-mode"></a>为 IIS 7.5/7.0 集成模式下配置 ASP.NET 4 MaxConcurrentRequests  
 .NET Framework 4，maxconcurrentrequestspercpu 配置的默认设置是 5000 的非常大的数字，因此将留出足够的并发执行的异步请求。 有关详细信息，请参阅[ \<applicationPool\>元素 （Web 设置）](http://go.microsoft.com/fwlink/?LinkID=205339) (http://go.microsoft.com/fwlink/?LinkID=205339)。  
  
 对于 IIS 7.5/7.0 集成模式，名为内 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\4.0.30319.0 maxconcurrentrequestspercpu 配置一个 dword 值确定每个 CPU 的并发请求数。 默认情况下，注册表项不存在并且每 CPU 的请求数限制为 5000。  
  
### <a name="enable-iis-http-compression"></a>启用 IIS HTTP 压缩  
 若要更有效地使用可用带宽，启用 IIS HTTP 压缩。 HTTP 压缩提供更快之间启用压缩的浏览器和 IIS，而不考虑你的内容是否从本地存储或 UNC 资源提供服务的传输时间。  
  
-   **若要在 Web 服务器级别配置压缩：**  
  
    1.  单击**启动**，指向**所有程序**，单击**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
    2.  在**连接**窗格中，选择 Web 服务器，请单击以选中**功能视图**，然后双击**压缩**功能。  
  
    3.  设置所需的压缩选项，然后单击**应用**中**操作**窗格。  
  
-   **若要在网站级别上配置压缩：**  
  
    1.  单击**启动**，指向**所有程序**，单击**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
    2.  在**连接**窗格中，单击以展开**站点**，单击此项可选择为其想要配置压缩，请单击选中的网站**功能视图**，和然后双击**压缩**功能。  
  
    3.  设置所需的压缩选项，然后单击**应用**中**操作**窗格。  
  
## <a name="see-also"></a>另请参阅  
 [优化性能](../technical-guides/optimizing-performance.md)