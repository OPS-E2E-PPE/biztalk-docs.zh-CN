---
title: 应用 IIS 配置设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d638f83-e1c8-4e35-b345-361d5a3093fa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36b79e7bbd5d070fe9be9f11d5c3b609fe1ccf6e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009422"
---
# <a name="apply-iis-configuration-settings"></a>应用 IIS 配置设置
默认情况下，SOAP、 HTTP 和基于 HTTP 的 WCF 适配器 （和在常规的.NET） 只有两个并发 HTTP 连接从打开每个 BizTalk 主机实例到任何特定的目标服务器。 例如，如果有 SOAP 发送端口发送消息到**<http://www.contoso.com/SomeWebService.asmx>**，然后默认情况下，每个上运行每个主机实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将打开到只有两个并发 HTTP 连接<strong>www.contoso.com</strong>，无论需要发送的消息数。  
  
 此设置符合 HTTP 1.1 规范的 IETF rfc，尽管它是适用于用户方案，但未优化的高吞吐量服务器到服务器通信。 默认设置将有效地限制从每个将发送到两个并发为每个目标服务器的出站 SOAP 和 HTTP 调用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机实例。  
  
## <a name="configure-aspnet-maxconcurrentrequests-for-iis-70-integrated-mode"></a>为 IIS 7.0 集成模式下配置 ASP.NET MaxConcurrentRequests  
 当 ASP.NET 2.0 托管在 IIS 7.0 集成模式下时，使用线程处理方式不同 IIS 6.0 或 IIS 7.0 在经典模式下。 当 ASP.NET 2.0 承载于 IIS 7.0 中集成模式下时，ASP.NET 2.0 限制并发执行的请求而不是并发执行的请求的线程数的数。 同步的情况下，这会因为请求的数量将是相同的线程数间接限制线程数。 但异步情况下，请求和线程的数量可能非常不同因为您可以比以往更多请求的线程数多于。 在集成模式下，可以在 IIS 7.0 上运行 ASP.NET 2.0，将忽略 minFreeThreads 和 minLocalRequestFreeThreads"httpRuntime"元素在 machine.config 中。 IIS 7.0 集成模式下，对于名为内 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0 maxconcurrentrequestspercpu 配置一个 dword 值确定每个 CPU 的并发请求数。 默认情况下，注册表项不存在并且每 CPU 的请求数限制为 12。 .NET framework 3.5 SP1 包括支持通过 aspnet.config 文件中的配置 IIS 应用程序池对 v2.0 二进制文件的更新。 此配置仅适用于集成模式 （经典/ISAPI 模式会忽略这些设置）。下面列出了新的 aspnet.config 配置节具有默认值：  
  
```  
<system.web>  
   <applicationPool maxConcurrentRequestsPerCPU="12" maxConcurrentThreadsPerCPU="0" requestQueueLimit="5000"/>  
</system.web>  
```  
  
 根据经验，maxconcurrentrequestspercpu 配置应设置为太大的值，如 5000。  
  
 在 IIS 7.0 集成模式下，maxWorkerThreads 和 machine.config 文件的"processModel"部分中的 maxIoThreads 参数不用于控制数本身运行的请求，但仍然使用它们来控制 CLR 线程池的大小由 ASP.NET。 当在 machine.config 的"processModel"部分具有"autoConfig = true"（这是默认设置），这将为应用程序池提供每个逻辑 CPU 的最多 100 个工作线程 (MaxWorkerThreads)。 因此具有 2 个双核 Cpu 的常见商用服务器必须 400 MaxWorkerThreads。 这应足以满足所有要求最苛刻的应用程序除外。  
  
 有关在 IIS 7.0 和 6.0 上配置 ASP.NET 线程使用情况的详细信息，请参阅[Thomas Marquardt 的博客上的 IIS 7.0 和 6.0 上 ASP.NET 线程使用情况](http://go.microsoft.com/fwlink/?LinkId=157518)(http://go.microsoft.com/fwlink/?LinkId=157518)。  
  
## <a name="log-only-essential-information-or-completely-disable-iis-logging"></a>仅记录基本信息或完全禁用 IIS 日志记录  
 应最小化或甚至在生产环境中禁用 IIS 日志记录。 若要禁用日志记录，请执行以下步骤：  
  
1.  单击**启动**，依次指向**所有程序**，单击**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
2.  在中**连接**窗格中，单击以展开**站点**，单击此项可选择为其想要禁用日志记录，请单击以选择的 Web 站点**功能视图**，，然后双击**日志记录**功能。  
  
3.  单击**禁用**中**操作**窗格，可以禁用此网站的日志记录。  
  
## <a name="disable-iis-asp-debugging-in-production-environments"></a>禁用 IIS ASP 在生产环境中进行调试  
 应在生产环境中禁用 IIS ASP 调试。 若要禁用 IIS ASP 调试，请执行以下步骤：  
  
1. 单击**启动**，依次指向**所有程序**，单击**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
2. 在中**连接**窗格中，单击以展开**站点**，单击此项可选择为其想要禁用 ASP 调试，请单击以选择的 web 站点**功能视图**，，然后双击**ASP**功能。  
  
3. 单击此项可展开**编译**，单击此项可展开**调试属性**，并验证这两**启用客户端调试**和**启用服务器端调试**设置为**False**。  
  
4. 如有必要，单击**Apply**中**操作**窗格。  
  
   禁用调试 ASP.NET 应用程序和 Web 服务通过指定\<编译调试 ="false"\> web 应用程序的 web.config 文件中的部分。  
  
## <a name="tune-the-value-of-the-asp-threads-per-processor-limit-property"></a>优化 ASP 线程针对每个处理器限制属性的值  
 ASP**线程针对每个处理器限制**属性指定的最大工作线程为每个 IIS 创建的处理器数。 之前的处理器使用率满足至少达到 50%或更高版本，应增加处理器限制每个线程的值。 此设置可以极大地影响 Web 应用程序的可伸缩性和性能的服务器一般情况下。 由于此属性定义的 ASP 请求可同时执行的最大数量，此设置应保持为默认值，除非 ASP 应用程序正在扩展的调用外部组件。 在这种情况下，可能会增加线程针对每个处理器限制的值。 这样做使要创建更多的线程以处理更多的并发请求的服务器。 处理器限制每个线程的默认值为 25。 此属性的最大建议的值为 100。  
  
 若要增加处理器限制每个线程的值，请执行以下步骤：  
  
1. 单击**启动**，依次指向**所有程序**，单击**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
2. 在中**连接**窗格中，选择 web 服务器，请单击以选中**功能视图**，然后双击**ASP**功能。  
  
3. 单击此项可展开**限制属性**下**行为**，单击**线程针对每个处理器限制**，输入所需的值**线程针对每个处理器限制**然后单击**Apply**中**操作**窗格。  
  
   有关如何修改中的属性详细信息\<限制\>元素的 IIS 7.0 \<asp\>元素中，请参阅[ASP 限制\<限制\>](http://go.microsoft.com/fwlink/?LinkId=157483) (http://go.microsoft.com/fwlink/?LinkId=157483).  
  
> [!NOTE]  
>  由于只能在服务器级别上应用此属性，此属性的修改会影响在服务器运行的所有网站。  
  
> [!NOTE]  
>  ASP**线程针对每个处理器限制**适用于 IIS 7.0 属性取代了 IIS 6.0 **ASPProcessorThreadMax** ASP 元数据库设置。 有关 IIS 6.0 ASPProcessorThreadMax ASP 元数据库设置的信息，请参阅[微调 ASP 元数据库设置](http://go.microsoft.com/fwlink/?LinkId=158834)(http://go.microsoft.com/fwlink/?LinkId=158834) MSDN 上。  
  
## <a name="tune-the-value-of-the-asp-queue-length-property"></a>优化 ASP Queue Length 属性的值  
 优化此属性的目标是确保良好的响应时间，同时最大程度减少 ASP 请求队列已满时，服务器何种频率发送到客户端的 HTTP 503 （服务器太忙） 错误。 如果 ASP Queue Length 属性的值太低，则服务器会更高的频率发送 HTTP 503 错误。 如果 ASP Queue Length 属性的值过高，用户会认为，服务器不响应时实际上在队列中等待其请求。 通过在高流量时段观看队列，应该识别模式的 web 请求高峰和低谷。 请记下的最大资源值，并将峰值值的正上方的 ASP 队列长度属性的值。 使用队列来处理短期的高峰，请确保响应时间并限制系统，以避免重载时持续出现意外的峰值。 如果还没有用于调整 ASP Queue Length 属性的数据，将是很好的起点设置队列的一对一比率为总线程数。 例如，如果针对每个处理器限制对线程 ASP 属性设置为 25，并且具有四个处理器 (4 * 25 = 100 线程)、 将 ASP 队列长度属性设置为 100 和调整从该处。  
  
 若要增加队列长度属性的值，请执行以下步骤：  
  
1. 单击**启动**，依次指向**所有程序**，单击**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
2. 在中**连接**窗格中，选择 Web 服务器，请单击以选中**功能视图**，然后双击**ASP**功能。  
  
3. 单击此项可展开**限制属性**下**行为**，单击**队列长度**，输入所需的值**队列长度**，然后单击**Apply**中**操作**窗格。  
  
   有关如何修改中的属性详细信息\<限制\>元素的 IIS 7.0 \<asp\>元素中，请参阅[ASP 限制\<限制\>](http://go.microsoft.com/fwlink/?LinkId=157483) (http://go.microsoft.com/fwlink/?LinkId=157483).  
  
> [!NOTE]  
>  由于只能在服务器级别上应用此属性，此属性的修改会影响在服务器运行的所有网站。  
  
> [!NOTE]  
>  ASP**队列长度**适用于 IIS 7.0 属性取代了 IIS 6.0 **AspRequestQueueMax** ASP 元数据库设置。 有关 IIS 6.0 AspRequestQueueMax ASP 元数据库设置的信息，请参阅[微调 ASP 元数据库设置](http://go.microsoft.com/fwlink/?LinkId=158834)(http://go.microsoft.com/fwlink/?LinkId=158834) MSDN 上。  
  
## <a name="tune-the-maxpoolthreads-registry-entry"></a>优化 MaxPoolThreads 注册表项  
 此设置指定每个处理器创建的池线程的数。 池线程监视网络中的请求和处理传入的请求。 MaxPoolThreads 计数不包括 ISAPI 应用程序使用的线程。 通常情况下，不应创建每个处理器超过 20 个线程。 MaxPoolThreads 是位于 HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\InetInfo\Parameters\ 默认值为 4 的 REG_DWORD 注册表条目。  
  
## <a name="disable-wcf-services-tracing"></a>禁用跟踪的 WCF 服务  
 使用配置编辑器工具 (SvcConfigEditor.exe) 来禁用 WCF 服务在生产环境中进行跟踪。 有关配置编辑器工具的详细信息，请参阅[配置编辑器工具 (SvcConfigEditor.exe)](http://go.microsoft.com/fwlink/?LinkID=127070) (http://go.microsoft.com/fwlink/?LinkID=127070)。  
  
## <a name="see-also"></a>请参阅  
 [清单：配置 BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)