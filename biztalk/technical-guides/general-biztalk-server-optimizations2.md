---
title: "常规 BizTalk Server Optimizations2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41b452e9-d94c-4bcb-8ef6-e9cea28fc0ab
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 622844e282b9b0206f92979827406a324cd2f86f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="general-biztalk-server-optimizations"></a>一般 BizTalk Server 优化
以下建议可用于增加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能。 本主题中列出的优化应用后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]已安装并配置。  
  
## <a name="create-multiple-biztalk-server-hosts-and-separate-host-instances-by-functionality"></a>按功能创建多个 BizTalk Server 主机和单独的主机实例  
 为发送、 接收、 处理和跟踪功能，应创建单独的主机。 创建多个 BizTalk 主机提供灵活性，在你的 BizTalk 组中配置工作负荷时，并且不在 BizTalk 组中的 BizTalk 服务器之间分布处理的主要方式。 多个主机还允许你停止一台主机，而不影响其他主机。 例如，你可能想要停止发送消息，告知对方队列在 Messagebox 数据库中，同时仍允许入站的接收的消息发生。 将主机实例分离的功能还提供以下好处：  
  
-   每个主机实例中.NET 线程池具有其自己的内存、 句柄和线程等资源集。  
  
-   多个 BizTalk 主机也将减少 Messagebox 数据库主机队列表上的争用，因为每个主机分配其自己的 Messagebox 数据库中的工作队列表。  
  
-   在主机级别情况下，限制实现在 BizTalk Server 中。 这可以为每个主机设置不同的限制特征。  
  
-   在主机级别; 实现安全每个主机将离散的 Windows 标识下运行。 这将允许您，例如，使 Host_A 能够访问 FileShare_B，同时不允许任何其他主机，以访问文件共享。  
  
> [!NOTE]  
>  尽管为创建额外的主机实例带来的好处，还有潜在缺点如果创建过多的主机实例。 每个主机实例是一个 Windows 服务 (BTSNTSvc.exe)，它生成额外的负载，针对 MessageBox 数据库，并会占用计算机资源 （如 CPU、 内存、 线程）。  
  
 有关修改 BizTalk Server 主机属性的详细信息，请参阅"如何为修改主机属性"中的 BizTalk Server 帮助在[http://go.microsoft.com/fwlink/?LinkId=101588](http://go.microsoft.com/fwlink/?LinkId=101588)。  
  
## <a name="configure-a-dedicated-tracking-host"></a>配置专用的跟踪主机  
 BizTalk Server 进行了优化吞吐量，因此主要业务流程和消息传送引擎不实际移动消息直接到 BizTalk 跟踪或 BAM 数据库，因为这将会从其主作业的执行业务流程这些引擎将转换。 相反，BizTalk Server 使 MessageBox 数据库中的消息，并将其标记为需要迁移到 BizTalk 跟踪数据库。 后台进程 （跟踪主机），然后移动消息到 BizTalk 跟踪和 BAM 数据库。 跟踪是资源密集型操作，因为单独的主机应创建专用于跟踪，从而将跟踪已与消息处理专用的主机上的影响降至最低。  
  
 使用专用的跟踪主机还使你可以在不干扰 BizTalk Server 跟踪的情况下停止其他 BizTalk 主机。 跟踪从 Messagebox 的数据库的数据的移动是正常的 BizTalk Server 系统的关键。 如果停止 BizTalk 主机负责将跟踪数据移动 BizTalk 组中，跟踪数据解码服务将不会运行。 此方法的影响是，如下所示：  
  
-   HAT 跟踪数据不会从 Messagebox 数据库移至 BizTalk 跟踪数据库。  
  
-   BAM 跟踪数据不会从 Messagebox 数据库移至 BAM 主导入数据库。  
  
-   因为不移动数据时，它不能从 Messagebox 数据库中删除。  
  
-   当停止跟踪数据解码服务时，跟踪拦截器仍将激发并将跟踪数据写入到 Messagebox 数据库。 如果不移动数据时，这将导致 Messagebox 数据库变得臃肿，这将影响随时间推移的性能。 即使自定义属性不会跟踪或 BAM 配置文件未设置，默认情况下的某些数据跟踪 （如管道接收 / 发送事件和业务流程事件）。 如果您不想要运行的跟踪数据解码的服务，请关闭所有跟踪，以便不拦截器将数据保存到数据库。 若要禁用全局跟踪，请参阅"如何启用关闭全局跟踪"BizTalk Server 中在帮助[http://go.microsoft.com/fwlink/?LinkId=101589](http://go.microsoft.com/fwlink/?LinkId=101589)。 使用 BizTalk Server 管理控制台有选择性地禁用跟踪事件。  
  
 跟踪主机应运行 BizTalk Server （适用于在其中一个发生故障的情况下的冗余） 的在至少两台计算机上运行。 为了获得最佳性能，应具有至少一个跟踪每个 Messagebox 数据库的主机实例。 跟踪主机实例的实际数应 （N + 1），其中 N = Messagebox 数据库的数目。 "+ 1"是以实现冗余，一台计算机承载跟踪失败的情况下。  
  
 跟踪主机实例移动特定的 Messagebox 数据库的跟踪数据，但将永远不会有多个跟踪主机实例特定的 Messagebox 数据库的数据移动。 例如，如果你有三个 Messagebox 数据库，并只有两个跟踪主机实例，然后其中一个主机实例需要 Messagebox 数据库中的两个移动数据。 添加第三个跟踪主机实例将分发跟踪主机到另一台计算机运行 BizTalk Server 的工作。 在此方案中，程序将添加第四个跟踪主机实例将不会将任何详细的跟踪主机的分发工作，但将提供一个额外跟踪容错能力的主机实例。  
  
 有关 BAM 事件总线服务的详细信息，请参阅 BizTalk Server 帮助中的下列主题：  
  
-   在的"管理 BAM 事件总线服务" [http://go.microsoft.com/fwlink/?LinkId=101590](http://go.microsoft.com/fwlink/?LinkId=101590)。  
  
-   在的"创建 BAM 事件总线服务的实例" [http://go.microsoft.com/fwlink/?LinkId=101591](http://go.microsoft.com/fwlink/?LinkId=101591)。  
  
## <a name="manage-aspnet-thread-usage-or-concurrently-executing-requests-for-web-applications-that-host-orchestrations-published-as-a-web-or-wcf-service"></a>管理 ASP.NET 线程使用情况或并发执行的请求的 Web 应用程序主机业务流程发布为 Web 或 WCF 服务  
 作为 Web 服务应在修改发布的工作人员和 I/O 线程 （IIS 6.0 和 IIS 7.0 在经典模式下） 或同时执行的 ASP.NET Web 应用程序承载业务流程的请求 （IIS 7.0 集成模式） 的数目数以下条件：  
  
-   CPU 使用率不成为瓶颈的宿主的 Web 服务器上。  
  
-   值**的 ASP.NET 应用程序 v2.0.50727\Request Wait Time**或**的 ASP.NET 应用程序 v2.0.50727\Request 执行时间**性能计数器是异常高。  
  
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
  
### <a name="manage-aspnet-thread-usage-for-web-applications-that-host-orchestrations-on-iis-60-and-on-iis-70-running-in-classic-mode"></a>管理 ASP.NET 的 Web 应用程序承载在 IIS 6.0 上并以经典模式运行的 IIS 7.0 上的业务流程的线程使用情况  
 当**autoConfig**的 IIS 6.0 服务器或 IIS 7.0 服务器以经典模式运行的 machine.config 文件中的值设置为**true**、 ASP.NET 2.0 管理的工作线程数和 I/O 线程是分配给任何关联的 IIS 工作进程：  
  
```  
<processModel autoConfig="true" />  
```  
  
 若要手动修改的辅助角色和 ASP.NET 2.0 Web 应用程序的 I/O 线程数，请打开关联的 machine.config 文件中，，然后输入的新值**maxWorkerThreads**和**maxIoThreads**参数：  
  
```  
<!-- <processModel autoConfig="true" /> -->  
    <processModel maxWorkerThreads="200" maxIoThreads="200" />  
```  
  
> [!NOTE]  
>  这些值是仅; 作为指导确保测试对这些参数的更改。  
  
 有关调整 ASP.NET 2.0 Web 应用程序的 machine.config 文件中的参数的详细信息，请参阅 Microsoft 知识库文章[821268"争用、 不佳的性能和死锁时从 ASP.NET 发出 Web 服务请求应用程序的"](http://go.microsoft.com/fwlink/?LinkID=66483) (http://go.microsoft.com/fwlink/?LinkID=66483)。  
  
### <a name="manage-the-number-of-concurrently-executing-requests-for-web-applications-that-host-orchestrations-on-iis-70-running-in-integrated-mode"></a>管理并发执行的 Web 应用程序承载在集成模式下运行的 IIS 7.0 上的业务流程的请求的数量  
 当在集成模式下情况下，ASP.NET 2.0 承载于 IIS 7.0 上时，使用线程处理方式与处理比在 IIS 6.0 或 IIS 7.0 上在经典模式下。 当 ASP.NET 2.0 IIS 7.0 上承载在集成模式下时，ASP.NET 2.0 限制并发执行的次数**请求**而不是数**线程**并发执行的请求。 对于同步方案这间接将限制线程数，但对于异步方案将可能非常不同的请求和线程数。 当在集成模式下，在 IIS 7.0 上运行 ASP.NET 2.0 **maxWorkerThreads**和**maxIoThreads** machine.config 文件中的参数不用于管理正在运行的线程数。 相反的同时执行的请求数可以更改从每个 CPU 的 12 的默认值修改为指定的值**maxConcurrentThreadsPerCPU**。 **MaxConcurrentThreadsPerCPU** reqistry 中或在配置节的 aspnet.config 文件中，可以指定值。 执行这些步骤可更改的默认值为**maxConcurrentThreadsPerCPU**可管理的同时执行的请求数：  
  
 **在注册表中设置 maxConcurrentThreadsPerCPU 值**  
  
> [!WARNING]  
>  对注册表编辑器的不当使用可能会引起问题，而必须重新安装操作系统。 请慎用注册表编辑器，风险自负。 有关如何备份、 还原和修改注册表的详细信息，请参阅 Microsoft 知识库文章"Microsoft Windows 注册表说明"在[http://go.microsoft.com/fwlink/?LinkId=62729](http://go.microsoft.com/fwlink/?LinkId=62729)。  
  
> [!NOTE]  
>  此设置是全局设置，无法为单个应用程序池或应用程序的更改。  
  
1.  依次单击 **启动”**和 **运行”**，键入 **regedit.exe**，然后单击 **确定”** 以启动注册表编辑器。  
  
2.  导航到**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0**  
  
3.  通过执行以下步骤创建项：  
  
    1.  上**编辑**菜单上，单击**新建**，然后单击**密钥**。  
  
    2.  类型**maxConcurrentThreadsPerCPU**，然后按**ENTER**。  
  
    3.  下**maxConcurrentThreadsPerCPU**密钥，创建 DWORD 条目 maxConcurrentThreadsPerCPU 的新值。  
  
    4.  关闭“注册表编辑器”。  
  
 **在 aspnet.config 文件的配置部分中设置应用程序池的 maxConcurrentThreadsPerCPU 值**  
  
> [!NOTE]  
>  必须安装 Microsoft.NET Framework 3.5 Service Pack 1，以适应通过配置文件中设置下面的值。 你可以下载 Microsoft.NET Framework 3.5 Service Pack 1 从[http://go.microsoft.com/fwlink/?LinkID=136345](http://go.microsoft.com/fwlink/?LinkID=136345)。  
  
-   打开应用程序池下的 aspnet.config 文件，然后输入新值**maxconcurrentrequestspercpu 配置**和**requestQueueLimit**参数：  
  
```  
<system.web>  
    <applicationPool maxConcurrentRequestsPerCPU="12" requestQueueLimit="5000"/>  
</system.web>  
```  
  
> [!NOTE]  
>  此值将覆盖指定的值**maxConcurrentThreadsPerCPU**注册表中。 RequestQueueLimit 设置操作 processModel/requestQueueLimit 相同，只不过 aspnet.config 文件中的设置将重写 machine.config 文件中的设置。  
  
## <a name="define-clr-hosting-thread-values-for-biztalk-host-instances"></a>定义 CLR 承载 BizTalk 主机实例的线程值  
 因为 Windows 线程是 Windows 进程可用的最基本的可执行单元，因此，有必要为与 BizTalk 主机实例相关联的 .NET 线程池分配足够的线程以防止线程不足。 当线程资源不足出现时，并不足够可用来执行请求对性能造成负面影响的工作的线程。 在同一时间，应格外小心以防止分配到与主机比所需的.net 线程池的多个线程。 为与主机相关联的 .NET 线程池分配过多的线程会增加上下文切换。 Windows 内核切换为不同的线程，产生的性能开销运行一个线程时发生上下文切换。 过多线程分配可能会导致过多的上下文切换，这将带来负面影响整体性能。  
  
 通过在 BizTalk Server 的注册表中创建相应的 CLR Hosting 值，可以修改与 BizTalk 主机的实例相关联的 .NET 线程池中可用的 Windows 线程数。  
  
> [!WARNING]  
>  对注册表编辑器的不当使用可能会引起问题，而必须重新安装操作系统。 请慎用注册表编辑器，风险自负。 有关如何备份、 还原和修改注册表的详细信息，请参阅 Microsoft 知识库文章"Microsoft Windows 注册表说明"在[http://go.microsoft.com/fwlink/?LinkId=62729](http://go.microsoft.com/fwlink/?LinkId=62729)。  
  
> [!NOTE]  
>  **工作线程**用于处理排队的工作项和**I/O 线程**I/O 完成端口来处理已完成的异步 I/O 请求与关联的专用的回调线程。  
  
 **若要修改在与每个 BizTalk 主机实例关联的.NET 线程池的可用线程数，请按照下列步骤：**  
  
1.  停止 BizTalk 主机实例。  
  
2.  依次单击 **启动”**和 **运行”**，键入 **regedit.exe**，然后单击 **确定”** 以启动注册表编辑器。  
    导航到**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc$***主机名*] 其中*主机名*是与主机关联的主机的名称实例。  
  
    > [!NOTE]  
    >  如果你已从 BizTalk Server 2004 升级您的 BizTalk Server 2006 安装，此注册表项可能表示为**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc***guid*]其中*guid*是唯一的 BizTalk Server 主机的每个实例的 GUID。  
  
3.  找到**的 CLR 承载**密钥。 如果该键不存在，然后通过执行以下步骤创建项：  
  
    1.  上**编辑**菜单上，单击**新建**，然后单击**密钥**。  
  
    2.  类型**的 CLR 承载**，然后按**ENTER**。  
  
4.  下**的 CLR 承载**密钥，使用指定的值创建以下 DWORD 值。  
  
    |DWORD 项|默认值|推荐值|  
    |-----------------|-------------------|-----------------------|  
    |MaxIOThreads|20|100|  
    |MaxWorkerThreads|25|100**重要说明：**增加 100 超出此值可以对承载 BizTalk Server MessageBox 数据库的 SQL Server 计算机的性能产生负面影响。 当发生此问题时，SQL Server 可能会遇到死锁情况。 建议此参数不超过 100 的值。|  
    |MinIOThreads|1|25|  
    |MinWorkerThreads|1|25|  
  
    > [!NOTE]  
    >  这些建议值将足以满足大多数情况下，但可能需要根据每个主机实例中运行多少适配器处理程序或业务流程增加。  
  
    > [!NOTE]  
    >  这些值隐式乘以在服务器上的处理器数。 例如，MaxWorkerThreads 项设置为值 100 将在具有 4 个 CPU 的服务器上有效设置值 400。  
  
5.  关闭“注册表编辑器”。  
  
6.  重新启动 BizTalk 主机实例。  
  
## <a name="disable-tracking-for-orchestrations-send-ports-receive-ports-and-pipelines-when-tracking-is-not-required"></a>禁用业务流程的跟踪、 发送端口时，将收到端口和管道跟踪不是必需的  
 跟踪可能会产生开销在 BizTalk Server 中的性能，因为数据具有要写入到 MessageBox 数据库，然后以异步方式移动到 BizTalk 跟踪数据库。 如果跟踪不是一项业务要求，然后禁用跟踪，以降低开销和提高性能。 有关配置跟踪的详细信息，请参阅"配置跟踪使用的 BizTalk Server 管理控制台"BizTalk Server 中在帮助[http://go.microsoft.com/fwlink/?LinkID=106742](http://go.microsoft.com/fwlink/?LinkID=106742)。  
  
## <a name="decrease-the-purging-period-for-the-dta-purge-and-archive-job-from-7-days-to-2-days-in-high-throughput-scenarios"></a>清除周期越短 DTA 清除和从 7 天到高吞吐量方案中的 2 天的存档作业  
 默认情况下，跟踪 BizTalk Server 中的数据的清除间隔设置为 7 天。 在高吞吐量方案中，这可能导致在跟踪数据库中，最终影响 MessageBox 和反过来产生负面影响消息处理吞吐量的性能数据上的过多生成。  
  
 在高吞吐量的情况下，减少硬件和软件为 2 天清除从默认值 7 天的间隔。 有关配置清除间隔的详细信息，请参阅"如何为配置 DTA 清除和存档作业"BizTalk Server 中在帮助[http://go.microsoft.com/fwlink/?LinkID=104908](http://go.microsoft.com/fwlink/?LinkID=104908)。  
  
## <a name="install-the-latest-service-packs"></a>安装最新的 service pack  
 应安装 BizTalk Server 和.NET Framework 的最新服务包，因为这些文件组包含的修补程序可以更正你可能会遇到性能问题。  
  
## <a name="do-not-cluster-biztalk-hosts-unless-absolutely-necessary"></a>未群集 BizTalk 主机除非绝对必要  
 虽然[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]和后续版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]允许你将 BizTalk 主机配置为群集资源，还应考虑将执行此操作，如果你需要提供到的资源，不能跨多个 BizTalk 托管的高可用性计算机。 如示例，使用 FTP 适配器的端口应仅位于一台主机实例，如 FTP 协议不提供文件锁定，但是，这将带来单点故障，这会带来好处群集。 包含适配器，如文件、 SQL、 HTTP 或处理仅限的主机，主机可以内部负载平衡跨计算机的并且不会得益于群集。  
  
## <a name="performance-optimizations-in-the-biztalk-server-documentation"></a>BizTalk Server 文档中的性能优化  
 请遵循以下建议根据 BizTalk Server 文档中：  
  
-   在的"疑难解答 MessageBox 延迟问题" [http://go.microsoft.com/fwlink/?LinkId=114747](http://go.microsoft.com/fwlink/?LinkId=114747)  
  
-   在的"识别性能瓶颈" [http://go.microsoft.com/fwlink/?LinkID=104418](http://go.microsoft.com/fwlink/?LinkID=104418)  
  
-   在的"避免 DBNETLIB 异常" [http://go.microsoft.com/fwlink/?LinkID=108787](http://go.microsoft.com/fwlink/?LinkID=108787)  
  
-   在的"避免 TCP/IP 端口耗尽" [http://go.microsoft.com/fwlink/?LinkID=101610](http://go.microsoft.com/fwlink/?LinkID=101610)  
  
-   在的"设置 EPM 线程池大小" [http://go.microsoft.com/fwlink/?LinkId=114748](http://go.microsoft.com/fwlink/?LinkId=114748)