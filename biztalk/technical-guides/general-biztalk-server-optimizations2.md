---
title: 一般 BizTalk Server Optimizations2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41b452e9-d94c-4bcb-8ef6-e9cea28fc0ab
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af09f938d93377a6463926fad3725c9f9dace294
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022179"
---
# <a name="general-biztalk-server-optimizations"></a>一般 BizTalk Server 优化
以下建议可用于增加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能。 本主题中列出的优化应用后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]已安装并配置。  
  
## <a name="create-multiple-biztalk-server-hosts-and-separate-host-instances-by-functionality"></a>创建多个 BizTalk Server 主机和单独的主机实例的功能  
 为发送、 接收、 处理和跟踪功能，应创建单独的主机。 创建多个 BizTalk 主机在 BizTalk 组中配置工作负荷时提供灵活性和是 BizTalk 组中的 BizTalk 服务器之间分发处理的主要方式。 多个主机还允许您停止一个主机，而不会影响其他主机。 例如，可能想要停止发送消息，以让他们队列在 Messagebox 数据库中，同时仍允许入站的接收的消息出现。 主机实例分隔功能还提供以下优势：  
  
-   每个主机实例中的.NET 线程池具有其自己的内存、 句柄和线程等资源集。  
  
-   多个 BizTalk 主机还会减少 Messagebox 数据库主机队列表上的争用，因为每个主机分配 Messagebox 数据库中其自己的工作队列表。  
  
-   限制是 BizTalk Server 中实现在主机级别。 这允许您设置的每个主机的不同限制的特征。  
  
-   安全性是通过实现在主机级别;每个主机在离散的 Windows 标识下运行。 这样，您，例如，为 Host_A 访问赋予 FileShare_B，同时不允许任何其他主机访问文件共享。  
  
> [!NOTE]  
>  虽然有与创建其他主机实例的优点，也有潜在的缺点如果创建了太多主机实例。 每个主机实例是一个 Windows 服务 (BTSNTSvc.exe)，它可以生成针对 MessageBox 数据库的更多负载，并会占用计算机资源 （如 CPU、 内存、 线程）。  
  
 有关修改 BizTalk Server 主机属性的详细信息，请参阅"如何为修改主机属性"中的 BizTalk Server 帮助在[ http://go.microsoft.com/fwlink/?LinkId=101588 ](http://go.microsoft.com/fwlink/?LinkId=101588)。  
  
## <a name="configure-a-dedicated-tracking-host"></a>配置专用的跟踪主机  
 BizTalk Server 适用于吞吐量，因此主业务流程和消息传递引擎执行不实际消息直接移至 BizTalk 跟踪数据库或 BAM 数据库，因为这会将转移这些引擎从其主作业的执行业务流程。 相反，BizTalk Server 使消息留在 MessageBox 数据库，并将其标记为需要迁移到 BizTalk 跟踪数据库。 后台进程 （跟踪主机），然后将消息移动到 BizTalk 跟踪和 BAM 数据库。 跟踪是资源密集型操作，因为单独的主机应创建专用于跟踪，因此可尽量减少跟踪具有与消息处理专用的主机上的影响。  
  
 使用专用的跟踪主机还允许您停止其他 BizTalk 主机而不会影响与 BizTalk Server 跟踪。 跟踪数据从 Messagebox 数据库的移动的 BizTalk Server 系统正常运行至关重要。 如果停止 BizTalk 主机负责将跟踪数据移 BizTalk 组中，将不运行的跟踪数据解码服务。 这种影响是，如下所示：  
  
- HAT 跟踪数据不会从 Messagebox 数据库移至 BizTalk 跟踪数据库。  
  
- BAM 跟踪数据不会从 Messagebox 数据库移至 BAM 主导入数据库。  
  
- 不移动数据，因为它不能从 Messagebox 数据库中删除。  
  
- 跟踪数据解码服务停止时，跟踪侦听器仍将触发并将跟踪数据写入到 Messagebox 数据库。 如果不移动数据时，这将导致 Messagebox 数据库变得臃肿，这会影响性能随时间变化。 即使不会跟踪自定义属性或 BAM 配置文件未设置，默认情况下的某些数据被跟踪 （如管道接收 / 发送事件和业务流程事件）。 如果您不想要运行的跟踪数据解码服务，请关闭所有跟踪，以便没有侦听器将数据保存到数据库。 若要禁用全局跟踪，请参阅"如何为禁用全局跟踪"在 BizTalk Server 帮助[ http://go.microsoft.com/fwlink/?LinkId=101589 ](http://go.microsoft.com/fwlink/?LinkId=101589)。 使用 BizTalk Server 管理控制台来有选择性地禁用跟踪事件。  
  
  跟踪主机应运行 BizTalk Server （适用于在其中一个出现故障的情况下的冗余） 的至少两台计算机上运行。 为了获得最佳性能，应具有至少一个跟踪主机实例，每个 Messagebox 数据库。 跟踪主机实例的实际数目应 （N + 1），其中 N = Messagebox 数据库的数量。 "+ 1"是为实现冗余，一台计算机承载跟踪失败的情况下。  
  
  一个跟踪主机实例将跟踪数据的特定 Messagebox 数据库，但永远不会有多个跟踪主机实例特定的 Messagebox 数据库移动数据。 例如，如果您有三个 Messagebox 数据库，并且只有两个跟踪主机实例，然后其中一个主机实例需要将数据移动 Messagebox 数据库中的两个。 添加第三个跟踪主机实例分配跟踪主机到另一台计算机运行 BizTalk Server 的工作。 在此方案中，添加第四个跟踪主机实例将不分发任何详细的跟踪主机，但会提供一个额外跟踪主机实例的容错能力。  
  
  有关 BAM 事件总线服务的详细信息，请参阅 BizTalk Server 帮助中的以下主题：  
  
- "管理 BAM 事件总线服务"，在[ http://go.microsoft.com/fwlink/?LinkId=101590 ](http://go.microsoft.com/fwlink/?LinkId=101590)。  
  
- "创建的 BAM 事件总线服务实例"，在[ http://go.microsoft.com/fwlink/?LinkId=101591 ](http://go.microsoft.com/fwlink/?LinkId=101591)。  
  
## <a name="manage-aspnet-thread-usage-or-concurrently-executing-requests-for-web-applications-that-host-orchestrations-published-as-a-web-or-wcf-service"></a>管理 ASP.NET 线程使用情况或并发执行的请求的 Web 应用程序主机的业务流程发布为 Web 或 WCF 服务  
 工作线程和 I/O 线程 （IIS 6.0 和 IIS 7.0 在经典模式下） 或同时执行托管业务流程的 ASP.NET Web 应用程序的请求 （IIS 7.0 集成模式） 的数的大量发布为 Web 服务应在已修改以下条件：  
  
-   CPU 使用率不是托管的 Web 服务器上的瓶颈。  
  
-   值**ASP.NET 应用 v2.0.50727\Request Wait Time**或**ASP.NET 应用 v2.0.50727\Request 执行时间**性能计数器是非常大。  
  
-   类似于承载 Web 应用程序的计算机的应用程序日志中生成以下错误：  
  
    ```  
    Event Type: Warning  
    Event Source: W3SVC Event Category: None  
    Event ID: 1013  
    Date: 6/4/2009  
    Time: 1:03:47 PM  
    User: N/A  
    Computer: <ComputerName>  
    Description: A process serving application pool 'DefaultAppPool' exceeded time limits during shut down. The process id was '<xxxx>'  
    ```  
  
### <a name="manage-aspnet-thread-usage-for-web-applications-that-host-orchestrations-on-iis-60-and-on-iis-70-running-in-classic-mode"></a>管理 ASP.NET 线程使用情况的 Web 应用程序承载在 IIS 6.0 上和在经典模式下运行的 IIS 7.0 上的业务流程  
 当**autoConfig** IIS 6.0 服务器或在经典模式下运行的 IIS 7.0 服务器的 machine.config 文件中的值设置为**true**、 ASP.NET 2.0 管理的工作线程数和 I/O 线程是分配给任何关联的 IIS 工作进程：  
  
```  
<processModel autoConfig="true" />  
```  
  
 若要手动修改的工作线程和 ASP.NET 2.0 Web 应用程序的 I/O 线程数，打开关联的 machine.config 文件中，并输入新值**maxWorkerThreads**和**maxIoThreads**参数：  
  
```  
<!-- <processModel autoConfig="true" /> -->  
    <processModel maxWorkerThreads="200" maxIoThreads="200" />  
```  
  
> [!NOTE]  
>  这些值是仅; 作为指导请确保测试对这些参数的更改。  
  
 有关优化的 ASP.NET 2.0 Web 应用程序的 machine.config 文件中的参数的详细信息，请参阅 Microsoft 知识库文章[821268"争用、 性能不佳和死锁时从 ASP.NET 发出 Web 服务请求应用程序"](http://go.microsoft.com/fwlink/?LinkID=66483) (http://go.microsoft.com/fwlink/?LinkID=66483)。  
  
### <a name="manage-the-number-of-concurrently-executing-requests-for-web-applications-that-host-orchestrations-on-iis-70-running-in-integrated-mode"></a>管理并发执行的 Web 应用程序托管在集成模式下运行的 IIS 7.0 上的业务流程的请求数  
 ASP.NET 2.0 承载于 IIS 7.0 中集成模式下，当使用线程处理方式不同于 IIS 6.0 或 IIS 7.0 上在经典模式下。 当 ASP.NET 2.0 承载于 IIS 7.0 中集成模式下时，ASP.NET 2.0 限制的并发执行数**请求**而不是数**线程**并发执行的请求。 同步方案这将间接限制线程数，但异步方案的请求和线程数可能会大不相同。 当在集成模式下，IIS 7.0 上运行 ASP.NET 2.0 **maxWorkerThreads**并**maxIoThreads** machine.config 文件中的参数不用于管理的正在运行的线程数。 相反，并发执行的请求的更改号从默认值为每个 CPU 的 12 通过修改为指定的值**maxConcurrentThreadsPerCPU**。 **MaxConcurrentThreadsPerCPU** reqistry 中或在 aspnet.config 文件的配置部分中，可以指定值。 请执行以下步骤，若要更改的默认值为**maxConcurrentThreadsPerCPU**来控制的同时执行的请求数：  
  
 **若要在注册表中设置 maxConcurrentThreadsPerCPU 值**  
  
> [!WARNING]  
>  对注册表编辑器的不当使用可能会引起问题，而必须重新安装操作系统。 请慎用注册表编辑器，风险自负。 有关如何备份、 还原和修改注册表的详细信息，请参阅 Microsoft 知识库文章"Microsoft Windows 注册表说明"处[ http://go.microsoft.com/fwlink/?LinkId=62729 ](http://go.microsoft.com/fwlink/?LinkId=62729)。  
  
> [!NOTE]  
>  此设置是全局的并且不能更改为单个应用程序池或应用程序。  
  
1. 依次单击 **启动”** 和 **运行”**，键入 **regedit.exe**，然后单击 **确定”** 以启动注册表编辑器。  
  
2. 导航到**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0**  
  
3. 通过执行以下步骤创建项：  
  
   1.  上**编辑**菜单上，单击**新建**，然后单击**密钥**。  
  
   2.  类型**maxConcurrentThreadsPerCPU**，然后按**ENTER**。  
  
   3.  下**maxConcurrentThreadsPerCPU**密钥，请创建 DWORD 项具有 maxConcurrentThreadsPerCPU 的新值。  
  
   4.  关闭“注册表编辑器”。  
  
   **若要在 aspnet.config 文件的配置节中设置应用程序池的 maxConcurrentThreadsPerCPU 值**  
  
> [!NOTE]  
>  必须安装 Microsoft.NET Framework 3.5 Service Pack 1，以容纳通过配置文件设置以下值。 您可以下载 Microsoft.NET Framework 3.5 Service Pack 1 从[ http://go.microsoft.com/fwlink/?LinkID=136345 ](http://go.microsoft.com/fwlink/?LinkID=136345)。  
  
-   打开应用程序池的 aspnet.config 文件并输入新值**maxconcurrentrequestspercpu 配置**并**requestQueueLimit**参数：  
  
```  
<system.web>  
    <applicationPool maxConcurrentRequestsPerCPU="12" requestQueueLimit="5000"/>  
</system.web>  
```  
  
> [!NOTE]  
>  此值将覆盖为指定的值**maxConcurrentThreadsPerCPU**注册表中。 RequestQueueLimit 设置等同于 processModel/requestQueueLimit，不同之处在于 aspnet.config 文件中的设置将覆盖在 machine.config 文件中的设置。  
  
## <a name="define-clr-hosting-thread-values-for-biztalk-host-instances"></a>定义的 CLR 承载 BizTalk 主机实例的线程值  
 因为 Windows 线程是 Windows 进程可用的最基本的可执行单元，因此，有必要为与 BizTalk 主机实例相关联的 .NET 线程池分配足够的线程以防止线程不足。 线程不足时，是不足够的线程用于执行请求的作业的性能有负面影响。 在同一时间，应格外小心以防止分配更多不必要的主机与相关联的.net 线程池线程。 为与主机相关联的 .NET 线程池分配过多的线程会增加上下文切换。 Windows 内核从运行一个线程为不同的线程，这会导致性能开销切换时，会发生上下文切换。 过多的线程分配可能会导致过多的上下文切换，这将产生负面影响整体性能。  
  
 通过在 BizTalk Server 的注册表中创建相应的 CLR Hosting 值，可以修改与 BizTalk 主机的实例相关联的 .NET 线程池中可用的 Windows 线程数。  
  
> [!WARNING]  
>  对注册表编辑器的不当使用可能会引起问题，而必须重新安装操作系统。 请慎用注册表编辑器，风险自负。 有关如何备份、 还原和修改注册表的详细信息，请参阅 Microsoft 知识库文章"Microsoft Windows 注册表说明"处[ http://go.microsoft.com/fwlink/?LinkId=62729 ](http://go.microsoft.com/fwlink/?LinkId=62729)。  
  
> [!NOTE]  
>  **工作线程**用于处理排队的工作项并**I/O 线程**是与 I/O 完成端口来处理已完成的异步 I/O 请求相关联的回调线程。  
  
 **若要修改与每个 BizTalk 主机实例相关联的.NET 线程池可用线程数，请按照下列步骤：**  
  
1. 停止 BizTalk 主机实例。  
  
2. 依次单击 **启动”** 和 **运行”**，键入 **regedit.exe**，然后单击 **确定”** 以启动注册表编辑器。  
   导航到**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc$**<em>主机名</em>] 其中*主机名*是与主机相关联的主机名称实例。  
  
   > [!NOTE]  
   >  如果有从 BizTalk Server 2004 升级到 BizTalk Server 2006 安装，此注册表项可能表示为 **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc * * * guid*] 其中*guid*是唯一的 BizTalk Server 主机的每个实例的 GUID。  
  
3. 找到**CLR Hosting**密钥。 如果该键不存在，然后通过执行以下步骤创建项：  
  
   1.  上**编辑**菜单上，单击**新建**，然后单击**密钥**。  
  
   2.  类型**CLR Hosting**，然后按**ENTER**。  
  
4. 下**CLR Hosting**密钥，请创建具有所示值的以下 DWORD 项。  
  
   |DWORD 项|默认值|推荐值|  
   |-----------------|-------------------|-----------------------|  
   |MaxIOThreads|20|100|  
   |MaxWorkerThreads|25|100**重要说明：** 该值增加到 100 可以拥有对承载 BizTalk Server MessageBox 数据库的 SQL Server 计算机的性能产生负面影响。 当发生此问题时，SQL Server 可能会遇到死锁情况。 建议此参数不超过 100 的值。|  
   |MinIOThreads|@shouldalert|25|  
   |MinWorkerThreads|@shouldalert|25|  
  
   > [!NOTE]  
   >  这些建议值足够在大多数情况下，但可能需要根据每个主机实例中运行适配器处理程序或业务流程的数量增加。  
  
   > [!NOTE]  
   >  这些值隐式乘以服务器上的处理器数。 例如，MaxWorkerThreads 项设置为值 100 将在具有 4 个 CPU 的服务器上有效设置值 400。  
  
5. 关闭“注册表编辑器”。  
  
6. 重新启动 BizTalk 主机实例。  
  
## <a name="disable-tracking-for-orchestrations-send-ports-receive-ports-and-pipelines-when-tracking-is-not-required"></a>禁用跟踪的业务流程、 发送端口、 接收端口和管道，不需要跟踪时  
 跟踪可能会产生系统开销在 BizTalk Server 的性能，因为数据已写入到 MessageBox 数据库并以异步方式移至 BizTalk 跟踪数据库。 如果跟踪不是一项业务要求，请禁用跟踪，以减少开销并提高性能。 有关配置跟踪的详细信息，请参阅"配置跟踪使用 BizTalk Server 管理控制台"中 BizTalk Server 帮助[ http://go.microsoft.com/fwlink/?LinkID=106742 ](http://go.microsoft.com/fwlink/?LinkID=106742)。  
  
## <a name="decrease-the-purging-period-for-the-dta-purge-and-archive-job-from-7-days-to-2-days-in-high-throughput-scenarios"></a>清除周期越短 DTA 清除和存档作业从 7 天在高吞吐量方案中的 2 天  
 默认情况下，用于跟踪 BizTalk Server 中的数据的清除间隔设置为 7 天。 在高吞吐量方案中，这可以导致在跟踪数据库中，最终影响 MessageBox 和又产生负面影响的消息处理吞吐量的性能数据过多逐渐累积。  
  
 在高吞吐量方案中，降低硬件和软件为 2 天，可从默认值为 7 天内清除时间间隔。 有关配置清除间隔的详细信息，请参阅"如何为配置 DTA 清除和存档作业"在 BizTalk Server 帮助[ http://go.microsoft.com/fwlink/?LinkID=104908 ](http://go.microsoft.com/fwlink/?LinkID=104908)。  
  
## <a name="install-the-latest-service-packs"></a>安装最新 service pack  
 应安装 BizTalk Server 和.NET Framework 的最新 service pack，因为它们包含可以更正可能会遇到性能问题的修补程序。  
  
## <a name="do-not-cluster-biztalk-hosts-unless-absolutely-necessary"></a>未群集 BizTalk 主机除非绝对必要  
 虽然[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]和后续版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以将 BizTalk 主机配置为群集资源，您应只考虑执行此操作，如果您需要向不能跨多个 BizTalk 托管的资源提供高可用性计算机。 如示例中，使用 FTP 适配器的端口应只位于一个主机实例，如 FTP 协议不提供文件锁定，但是，它引入了单点故障，它会从聚类分析中受益。 包含适配器，如文件、 SQL、 HTTP 或处理仅限主机，主机可以在内部负载平衡跨计算机的并且不会得益于聚类分析。  
  
## <a name="performance-optimizations-in-the-biztalk-server-documentation"></a>BizTalk Server 文档中的性能优化  
 将应用从 BizTalk Server 文档中的以下建议：  
  
-   "解决 MessageBox 延迟问题"网址 [http://go.microsoft.com/fwlink/?LinkId=114747](http://go.microsoft.com/fwlink/?LinkId=114747)  
  
-   在的"确定性能瓶颈" [http://go.microsoft.com/fwlink/?LinkID=104418](http://go.microsoft.com/fwlink/?LinkID=104418)  
  
-   在的"避免出现 DBNETLIB 异常" [http://go.microsoft.com/fwlink/?LinkID=108787](http://go.microsoft.com/fwlink/?LinkID=108787)  
  
-   在的"避免 TCP/IP 端口耗尽的情况" [http://go.microsoft.com/fwlink/?LinkID=101610](http://go.microsoft.com/fwlink/?LinkID=101610)  
  
-   在的"设置 EPM 线程池大小" [http://go.microsoft.com/fwlink/?LinkId=114748](http://go.microsoft.com/fwlink/?LinkId=114748)