---
title: "常规 BizTalk Server Optimizations1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8032553-bae3-440d-9197-b926160b0bdf
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee8447bb77fee160c34cc86d30a0b7ac981c53aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="general-biztalk-server-optimizations"></a>一般 BizTalk Server 优化
可以使用以下建议以提高 BizTalk Server 性能。 安装并配置 BizTalk Server 之后，将应用本主题中列出的优化。  
  
## <a name="configure-msdtc"></a>配置 MSDTC  
 若要简化 SQL Server 和 BizTalk Server 之间的事务，必须启用 Microsoft 分布式事务处理协调器 (MS DTC)。 若要配置 BizTalk Server 上的 MSDTC，请参阅主题[提高操作系统性能的一般准则](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)。  
  
## <a name="recommendations-for-configuring-biztalk-server-hosts"></a>配置 BizTalk Server 主机的建议  
 本部分提供配置 BizTalk Server 主机的建议。  
  
### <a name="create-multiple-biztalk-server-hosts-and-separate-host-instances-by-functionality"></a>按功能创建多个 BizTalk Server 主机和单独的主机实例  
 请遵循以下准则来创建多个 BizTalk Server 主机和跨这些主机分配工作负荷：  
  
-   为发送、 接收、 处理和跟踪功能创建单独的主机。 创建多个 BizTalk 主机提供灵活性，在你的 BizTalk 组中配置工作负荷时，并且不在 BizTalk 组中运行 BizTalk Server 的计算机之间分布处理的主要方式。 使用多个主机允许一台主机停止而不会影响其他主机。 例如，你可能想要停止发送消息，告知对方队列 MessageBox 数据库中同时仍然允许不同的主机实例中运行的接收适配器能够接收传入的消息。 将主机实例分离的功能还提供以下好处：  
  
    -   运行多个 BizTalk 主机减少 MessageBox 数据库主机队列表上的争用，因为每个主机分配其自己的 MessageBox 数据库中的工作队列表。  
  
    -   在主机级别情况下，限制实现在 BizTalk Server 中。 这可以为每个主机设置不同的限制特征。  
  
    -   在主机级别; 实现安全每个主机将离散的 Windows 标识下运行。 这允许您，例如，为 Host_A 访问到 FileShare_B，同时不允许任何其他主机，以访问文件共享。  
  
-   每个主机实例中.NET 线程池具有其自己的内存、 句柄和线程等资源集。 跨主机分配工作负荷时考虑将进行整体缩放的资源放在同一主机中。  
  
-   单独的适配器和不同的主机具有不同的优先级别的资源的业务流程。 此方法还包含专用的 BizTalk Server 计算机上运行高优先级的应用程序的主机的放置。  
  
> [!NOTE]  
>  尽管为创建额外的主机实例带来的好处，还有潜在缺点如果创建过多的主机实例。 每个主机实例是一个 Windows 服务 (BTSNTSvc.exe)，它生成额外的负载，针对 MessageBox 数据库，并会占用计算机资源 （如 CPU、 内存、 线程）。  
  
 有关修改 BizTalk Server 主机属性，请参阅[如何修改主机属性](http://go.microsoft.com/fwlink/?LinkID=154359)(http://go.microsoft.com/fwlink/?LinkID=154359) 在 BizTalk Server 2010 帮助中。  
  
### <a name="configure-a-dedicated-tracking-host"></a>配置专用的跟踪主机  
 BizTalk Server 进行了优化吞吐量，因此主要业务流程和消息传送引擎不实际移动消息直接到 BizTalk 跟踪或 BAM 数据库，因为这将会从其主作业的执行业务流程这些引擎将转换。 相反，BizTalk Server 使 MessageBox 数据库中的消息，并将其标记为需要迁移到 BizTalk 跟踪数据库。 后台进程 （跟踪主机），然后移动消息到 BizTalk 跟踪和 BAM 数据库。 由于跟踪是资源密集型操作，单独的主机应创建专用于跟踪，从而将跟踪已与消息处理专用的主机上的影响降至最低。 为了获得最佳性能，应至少一个跟踪每个 MessageBox 数据库的主机实例。 跟踪主机实例的实际数应为 N + 1，其中 N = MessageBox 数据库的数目。 "+ 1"是以实现冗余，一台计算机承载跟踪失败的情况下。  
  
 使用专用的跟踪主机还使你可以在不干扰 BizTalk Server 跟踪的情况下停止其他 BizTalk 主机。 跟踪从 MessageBox 的数据库的数据的移动是正常的 BizTalk Server 系统的关键。 如果停止 BizTalk 主机负责将跟踪数据移动 BizTalk 组中，跟踪数据解码服务将不会运行。 此方法的影响是，如下所示：  
  
-   HAT 跟踪数据不会从 MessageBox 数据库移至 BizTalk 跟踪数据库。  
  
-   BAM 跟踪数据不会从 MessageBox 数据库移至 BAM 主导入数据库。  
  
-   因为不移动数据时，它不能从 MessageBox 数据库中删除。  
  
-   当停止跟踪数据解码服务时，跟踪拦截器仍将激发并将跟踪数据写入到 MessageBox 数据库。 如果不移动数据时，这将导致 MessageBox 数据库变得臃肿，这将影响随时间推移的性能。 即使自定义属性不会跟踪或 BAM 配置文件未设置，默认情况下的某些数据跟踪 （如管道接收 / 发送事件和业务流程事件）。 如果您不想要运行的跟踪数据解码的服务，请关闭所有跟踪，以便不拦截器将数据保存到数据库。 若要禁用全局跟踪，请参阅[如何打开关闭全局跟踪](http://go.microsoft.com/fwlink/?LinkID=154193)(http://go.microsoft.com/fwlink/?LinkID=154193) 在 BizTalk Server 2010 帮助中。 使用 BizTalk Server 管理控制台有选择性地禁用跟踪事件。  
  
 跟踪主机应运行 BizTalk Server （适用于在其中一个发生故障的情况下的冗余） 的在至少两台计算机上运行。 为了获得最佳性能，应具有至少一个跟踪每个 MessageBox 数据库的主机实例。 跟踪主机实例的实际数应 （N + 1），其中 N = MessageBox 数据库的数目。 "+ 1"是以实现冗余，一台计算机承载跟踪失败的情况下。  
  
 跟踪主机实例移动特定的 MessageBox 数据库的跟踪数据，但将永远不会有多个跟踪主机实例特定的 MessageBox 数据库的数据移动。 例如，如果你有三个 MessageBox 数据库，并只有两个跟踪主机实例，然后其中一个主机实例需要 MessageBox 数据库中的两个移动数据。 添加第三个跟踪主机实例将分发跟踪主机到另一台计算机运行 BizTalk Server 的工作。 在此方案中，程序将添加第四个跟踪主机实例将不会将任何详细的跟踪主机的分发工作，但将提供一个额外跟踪容错能力的主机实例。  
  
 有关 BAM 事件总线服务的详细信息，请参阅 BizTalk Server 2010 帮助中的下列主题：  
  
-   [管理 BAM 事件总线服务](http://go.microsoft.com/fwlink/?LinkID=154194)(http://go.microsoft.com/fwlink/?LinkID=154194)。  
  
-   [创建 BAM 事件总线服务的实例](http://go.microsoft.com/fwlink/?LinkID=154195)(http://go.microsoft.com/fwlink/?LinkID=154195)。  
  
### <a name="do-not-cluster-biztalk-hosts-unless-absolutely-necessary"></a>未群集 BizTalk 主机除非绝对必要  
 虽然 BizTalk Server 2010 使你可以将 BizTalk 主机配置为群集资源，则还应考虑执行此操作，如果你需要提供到的资源，不能跨多个 BizTalk 计算机托管的高可用性。 例如，使用 FTP 适配器的端口应仅位于一台主机实例上，为 FTP 协议不提供文件锁定。 但是，这样还引入了单点故障，群集会带来好处。 包含适配器，如文件、 SQL、 HTTP 或处理仅限的主机，主机可以内部负载平衡跨计算机，并不会得益于群集。  
  
## <a name="increase-the-number-of--http-concurrent-connections-allowed-by-changing-the-value-for-the-maxconnection-parameter"></a>增加允许的更改 maxconnection 参数的值的 HTTP 并发连接数  
 默认情况下，（包括基于 WCF 的 HTTP 适配器） 的 HTTP 适配器从每台计算机到任何特定的目标服务器运行 BizTalk Server 打开只有两个并发的 HTTP 连接。  
  
 此设置符合 HTTP 1.1 规范中，IETF RFC 并虽然很适合用户方案，但是它不针对高吞吐量优化。 设置有效地从运行 BizTalk Server 每个计算机到两个并发发送限制对每个服务器的出站 HTTP 调用。  
  
 若要增加的并发连接数，可以修改 BizTalk Server 配置文件，BTSNTSvc.exe.config （或 64 位主机 BTSNTSvc64.exe.config），每个 BizTalk Server 中的 maxconnection 参数的值。 可以将其调用的特定服务器增加。 根据经验，maxconnection 参数的值应设置为 12 * 的 Cpu 或承载 web 应用程序的计算机上的内核数。  
  
> [!NOTE]  
>  不要提高到此类较大的值，使用 HTTP 连接被调用的 Web 服务器处于过载状态而 maxconnection 参数的值。 Maxconnection 参数值更改后，请执行压力通过将请求发送到每个目标 Web 服务器，以确定将提供良好的性能和 HTTP 的 maxconnection 的值发送而不导致超出目标 Web 测试服务器。  
  
 以下为最大连接数属性的配置示例：  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address="http://www.contoso.com" maxconnection="24" />  
      <add address="*" maxconnection="48" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
 设置 maxconnection 属性时，可以指定 HTTP、 HTTPS、 web 站点 IP 地址和端口号。 其他示例包括：  
  
 **\<添加地址 ="https://www.contoso.com"maxconnection ="24"/ >**   
**\<添加地址 ="http://www.contoso.com:8080"maxconnection ="24"/ >**   
**\<添加地址 ="http://*IPAddress*"maxconnection ="24"/ > * * 有关优化 IIS 和 ASP.NET Web 服务的设置的详细信息，请参阅"ASP.NET 设置，可能会影响 HTTP 适配器性能"部分的[适配器性能影响的配置参数](http://go.microsoft.com/fwlink/?LinkID=154200)(http://go.microsoft.com/fwlink/?LinkID=154200) 在 BizTalk Server 2010 帮助中。  
  
## <a name="manage-aspnet-thread-usage-or-concurrently-executing-requests-for-web-applications-that-can-host--isolated-received-locations-back-end-web-services-and-wcf-services"></a>管理 ASP.NET 线程使用情况或并发执行的请求的 Web 应用程序可以承载独立接收到的位置后, 端 Web 服务和 WCF 服务  
 辅助和 I/O 线程 （IIS 7.5 和 IIS 7.0 在经典模式下） 或的同时执行的请求 （IIS 7.5 和 7.0 集成模式下） ASP.NET Web 应用程序主机隔离接收到的位置后, 端 Web 服务和 WCF 服务数目的数量应在以下情况下修改：  
  
-   CPU 使用率不成为瓶颈的宿主的 Web 服务器上。  
  
-   值：  
  
    -   **ASP.NET 应用 v4.0.30319 \Request Wait Time**或**的 ASP.NET 应用程序 v4.0.30319 \Request 执行时间**性能计数器是异常高。  
  
    -   **ASP.NET 应用 v2.0.50727\Request Wait Time**或**的 ASP.NET 应用程序 v2.0.50727\Request 执行时间**性能计数器是异常高。  
  
-   承载 Web 应用程序的计算机的应用程序日志中将生成类似于以下错误。  
  
    ```  
    Event Type: Warning  
    Event Source: W3SVC Event Category: None  
    Event ID: 1013  
    Date: 11/4/2010  
    Time: 1:03:47 PM  
    User: N/A  
    Computer: <ComputerName>  
    Description: A process serving application pool 'DefaultAppPool' exceeded time limits during shut down. The process id was '<xxxx>'  
    ```  
  
### <a name="manage-aspnet-thread-usage-for-web-applications-that-can-host-isolated-received-locations-back-end-web-services-and-wcf-services-on-iis-75-and-iis-70-running-in-classic-mode"></a>管理 ASP.NET 的 Web 应用程序可以承载独立接收到的位置后, 端 Web 服务和在 IIS 7.5 和 IIS 7.0 以经典模式运行的 WCF 服务的线程使用情况  
 当**autoConfig**以经典模式运行的 IIS 7.5 和 IIS 7.0 服务器的 machine.config 文件中的值设置为**true**，ASP.NET 2.0 和 ASP.NET 4 管理的工作线程和 I/O 线程数分配给任何关联的 IIS 工作进程。  
  
```  
<processModel autoConfig="true" />  
```  
  
 若要手动修改的辅助角色和 ASP.NET 2.0 和 ASP.Net 4 Web 应用程序的 I/O 线程数，请打开关联的 machine.config 文件中，，然后输入的新值**maxWorkerThreads**和**maxIoThreads**参数。  
  
```  
<!-- <processModel autoConfig="true" /> -->  
    <processModel maxWorkerThreads="200" maxIoThreads="200" />  
```  
  
> [!NOTE]  
>  这些值是仅; 作为指导确保测试对这些参数的更改。  
  
 有关调整 ASP.NET 2.0 Web 应用程序的 machine.config 文件中的参数的详细信息，请参阅 Microsoft 知识库文章 821268[争用、 性能不佳和死锁时从 ASP 发出 Web 服务请求。NET 应用程序](http://go.microsoft.com/fwlink/?LinkID=144169)(http://go.microsoft.com/fwlink/?LinkID=144169)。  
  
### <a name="manage-the-number-of-concurrently-executing-requests-for-aspnet-20-web-applications-that-can-host-isolated-received-locations-back-end-web-services-and-wcf-services-on-iis-75-and-iis-70-running-in-integrated-mode"></a>管理并发执行的 ASP.NET 2.0 Web 应用程序可以承载独立接收到的位置后, 端 Web 服务和在 IIS 7.5 和 IIS 7.0 在集成模式下运行的 WCF 服务的请求的数量  
 当在集成模式下情况下，ASP.NET 2.0 承载于 IIS 7.5 和 IIS 7.0 上时，使用线程处理以不同的方式比在 IIS 7.5 和 IIS 7.0 上在经典模式下。 当在集成模式下情况下，ASP.NET 2.0 承载于 IIS 7.5 和 IIS 7.0 上时，ASP.NET 2.0 限制并发执行的次数**请求**而不是数**线程**并发执行请求。 对于同步方案这间接将限制线程数，但对于异步方案将可能非常不同的请求和线程数。 在集成模式下，在 IIS 7.5 和 IIS 7.0 上运行 ASP.NET 2.0 时**maxWorkerThreads**和**maxIoThreads** machine.config 文件中的参数不用于管理正在运行的线程数。 相反的同时执行的请求数可以更改从每个 CPU 的 12 的默认值修改为指定的值**maxconcurrentrequestspercpu 配置**。 **Maxconcurrentrequestspercpu 配置**reqistry 中或在配置节的 aspnet.config 文件中，可以指定值。 执行这些步骤可更改的默认值为**maxconcurrentrequestspercpu 配置**可管理的同时执行的请求数：  
  
 **在注册表中设置 maxconcurrentrequestspercpu 配置值**  
  
> [!WARNING]  
>  对注册表编辑器的不当使用可能会引起问题，而必须重新安装操作系统。 请慎用注册表编辑器，风险自负。 有关如何备份、 还原和修改注册表的详细信息，请参阅 Microsoft 知识库文章 256986[高级用户的 Windows 注册表信息](http://go.microsoft.com/fwlink/?LinkId=62729)(http://go.microsoft.com/fwlink/?LinkId=62729)。  
  
> [!NOTE]  
>  此设置是全局设置，无法为单个应用程序池或应用程序的更改。  
  
1.  依次单击 **启动”**和 **运行”**，键入 **regedit.exe**，然后单击 **确定”** 以启动注册表编辑器。  
  
2.  导航到**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0**  
  
3.  通过执行以下步骤创建项：  
  
    1.  上**编辑**菜单上，单击**新建**，然后单击**密钥**。  
  
    2.  类型**maxconcurrentrequestspercpu 配置**，然后按**ENTER**。  
  
    3.  下**maxconcurrentrequestspercpu 配置**密钥，创建 DWORD 条目 maxconcurrentrequestspercpu 配置的新值。  
  
    4.  关闭“注册表编辑器”。  
  
 **在 aspnet.config 文件的配置部分中设置应用程序池的 maxconcurrentrequestspercpu 配置值**  
  
> [!NOTE]  
>  必须安装 Microsoft.NET Framework 3.5 Service Pack 1，以适应通过配置文件中设置下面的值。 你可以下载 Microsoft.NET Framework 3.5 Service Pack 1 从[Microsoft.NET Framework 3.5 Service Pack 1](http://go.microsoft.com/fwlink/?LinkID=136345) (http://go.microsoft.com/fwlink/?LinkID=136345)。  
  
 打开应用程序池下的 aspnet.config 文件，然后输入新值**maxconcurrentrequestspercpu 配置**和**requestQueueLimit**参数。  
  
```  
<system.web>  
    <applicationPool maxConcurrentRequestsPerCPU="12" requestQueueLimit="5000"/>  
</system.web>  
```  
  
> [!NOTE]  
>  此值将覆盖指定的值**maxconcurrentrequestspercpu 配置**注册表中。 RequestQueueLimit 设置操作 processModel/requestQueueLimit 相同，只不过 aspnet.config 文件中的设置将重写 machine.config 文件中的设置。  
  
 有关在 IIS 7.0 上配置 ASP.NET 线程使用情况的详细信息，请参阅[ASP.NET 在 IIS 7.0 上的线程使用情况的 Thomas Marquardt 博客](http://go.microsoft.com/fwlink/?LinkId=157518)(http://go.microsoft.com/fwlink/?LinkId=157518)。  
  
### <a name="manage-the-number-of-concurrently-executing-requests-for-aspnet-4web-applications-that-can-host-isolated-received-locations-back-end-web-services-and-wcf-services-on-iis-75-and-70-running-in-integrated-mode"></a>管理同时执行的 ASP.NET 4Web 托管应用程序可以独立接收到的位置、 后端 Web 服务和在 IIS 7.5 和 7.0 在集成模式下运行的 WCF 服务的请求的数  
 .NET Framework 4，maxconcurrentrequestspercpu 配置的默认设置是 5000，这是一个非常大的数字，因此将留出足够的并发执行的异步请求。 有关详细信息，请参阅[ \<applicationPool > 元素 （Web 设置）](http://go.microsoft.com/fwlink/?LinkID=205339) (http://go.microsoft.com/fwlink/?LinkID=205339)。  
  
 对于 IIS 7.5 和 IIS 7.0 集成模式，名为内 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\4.0.30319.0 maxconcurrentrequestspercpu 配置一个 dword 值确定每个 CPU 的并发请求数。 默认情况下，注册表项不存在并且每 CPU 的请求数限制为 5000。  
  
 **在注册表中设置 maxconcurrentrequestspercpu 配置值**  
  
> [!WARNING]  
>  对注册表编辑器的不当使用可能会引起问题，而必须重新安装操作系统。 请慎用注册表编辑器，风险自负。 有关如何备份、 还原和修改注册表的详细信息，请参阅 Microsoft 知识库文章 256986[高级用户的 Windows 注册表信息](http://go.microsoft.com/fwlink/?LinkId=62729)(http://go.microsoft.com/fwlink/?LinkId=62729)。  
  
> [!NOTE]  
>  此设置是全局设置，无法为单个应用程序池或应用程序的更改。  
  
1.  依次单击 **启动”**和 **运行”**，键入 **regedit.exe**，然后单击 **确定”** 以启动注册表编辑器。  
  
2.  导航到**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\4.0.30319.0**。  
  
3.  通过执行以下步骤创建项：  
  
    1.  上**编辑**菜单上，单击**新建**，然后单击**密钥**。  
  
    2.  类型**maxconcurrentrequestspercpu 配置**，然后按**ENTER**。  
  
    3.  下**maxconcurrentrequestspercpu 配置**密钥，创建 DWORD 条目 maxconcurrentrequestspercpu 配置的新值。  
  
    4.  关闭“注册表编辑器”。  
  
 **在 aspnet.config 文件的配置部分中设置应用程序池的 maxconcurrentrequestspercpu 配置值**  
  
> [!NOTE]  
>  必须安装 Microsoft.NET Framework 4 以适应通过配置文件中设置下面的值。 您可以下载 Microsoft.NET Framework 4 从[Microsoft.NET Framework 4 (Web Installer)](http://go.microsoft.com/fwlink/?LinkID=189318) (http://go.microsoft.com/fwlink/?LinkID=189318)。  
  
-   打开应用程序池下的 aspnet.config 文件，然后输入新值**maxconcurrentrequestspercpu 配置**和**requestQueueLimit**参数。  
  
     下面的示例中的值是默认值。  
  
    ```  
    <system.web>  
        <applicationPool maxConcurrentRequestsPerCPU="5000" requestQueueLimit="5000"/>  
    </system.web>  
    ```  
  
> [!NOTE]  
>  此值将覆盖指定的值**maxconcurrentrequestspercpu 配置**注册表中。 **RequestQueueLimit**设置等同于 processModel/requestQueueLimit，只不过 aspnet.config 文件中的设置将重写 machine.config 文件中的设置。  
  
## <a name="define-clr-hosting-thread-values-for-biztalk-host-instances"></a>定义 CLR 承载 BizTalk 主机实例的线程值  
 因为 Windows 线程是 Windows 进程可用的最基本的可执行单元，因此，有必要为与 BizTalk 主机实例相关联的 .NET 线程池分配足够的线程以防止线程不足。 当线程资源不足出现时，并不足够可用来执行请求对性能造成负面影响的工作的线程。 在同一时间，应格外小心以防止分配到与主机比所需的.net 线程池的多个线程。 为与主机相关联的 .NET 线程池分配过多的线程会增加上下文切换。 Windows 内核切换为不同的线程，产生的性能开销运行一个线程时发生上下文切换。 过多线程分配可能会导致过多的上下文切换，这将带来负面影响整体性能。 默认分配给一个 BizTalk 主机实例.NET 线程池的线程数取决于所安装的.NET Framework 的版本。 .NET Framework 4 和.NET Framework 3.5 SP1 极大地增加了默认值，这可能导致过多线程分配的 BizTalk Server 计算机和 MessageBox 数据库上的过多的锁争用上。  
  
 使用**BizTalk 设置仪表板**，你可以修改默认值为在.NET 中可用的 Windows 线程数线程池与一个 BizTalk 主机实例相关联。 有关如何修改.NET CLR 设置的详细信息，请参阅[如何修改.NET CLR 设置](http://go.microsoft.com/fwlink/?LinkID=205344)(http://go.microsoft.com/fwlink/?LinkID=205344)。 .NET CLR 设置因 CPU 核心而异。  
  
> [!NOTE]  
>  **工作线程**用于处理排队的工作项和**I/O 线程**I/O 完成端口来处理已完成的异步 I/O 请求与关联的专用的回调线程。  
  
|线程处理设置|默认值|推荐值|  
|------------------------|-------------------|-----------------------|  
|最大 IO 线程|250|250|  
|最大工作线程|25|100**重要说明：**增加 100 超出此值可以对承载 BizTalk Server MessageBox 数据库的 SQL Server 计算机的性能产生负面影响。 当发生此问题时，SQL Server 可能会遇到死锁情况。 我们建议不增加 100 的值超出此参数。|  
|最小的 IO 线程|25|25|  
|最小工作线程|5|25|  
  
> [!NOTE]  
>  建议的值并不是绝对，可能需要进行调整，具体取决于 BizTalk 应用程序。 一次更改一个参数，然后进行其他更改之前测量的性能和 BizTalk 平台的稳定性影响。  
  
> [!NOTE]  
>  这些值隐式乘以在服务器上的处理器数。 例如，设置**MaxWorkerThreads**到 100 的值将有效地设置项的值为 400 4 的 CPU 服务器上。  
  
## <a name="disable-biztalk-server-group-level-tracking"></a>禁用 BizTalk 服务器组级别跟踪  
 跟踪可能会产生开销在 BizTalk Server 中的性能，因为数据具有要写入到 MessageBox 数据库，然后以异步方式移动到 BizTalk 跟踪数据库。 在生产 BizTalk Server 环境中配置跟踪时，应考虑以下事项：  
  
-   根据经验，如果跟踪不是一项业务要求，请禁用组级别跟踪，以降低开销和提高性能。  
  
     若要禁用 BizTalk Server 组级别跟踪，请执行以下步骤：  
  
    1.  在**BizTalk Server 管理控制台**，展开**BizTalk Server 管理**，右键单击**BizTalk 组**，然后单击**设置**.  
  
    2.  在 BizTalk 设置仪表板对话框中的在组页上，清除**启用组级别跟踪**复选框。  
  
    3.  单击**确定**应用进行修改并退出设置仪表板。  
  
-   仅使用跟踪如有必要的消息正文。 根据消息吞吐量和消息大小，跟踪的消息正文可能导致很大的开销。 虽然 BizTalk 活动跟踪具有用于调试和审核的明显优势，但它也具有很大的性能和可伸缩性的影响。 因此，您应该跟踪需要严格出于调试和安全原因，并可避免跟踪冗余信息的数据。  
  
-   默认情况下，为业务流程启用以下的跟踪选项：  
  
    -   业务流程开始和结束  
  
    -   消息发送和接收  
  
    -   形状开始和结束  
  
     跟踪选项"形状开始和结束"业务流程会产生很大的开销，并且不应在其中高吞吐量是必要的生产环境中启用。 业务流程跟踪选项中均可访问上的 BizTalk 管理控制台**跟踪**业务流程属性对话框中的页。  
  
 有关配置跟踪的详细信息，请参阅[配置跟踪使用 BizTalk Server 管理控制台](http://go.microsoft.com/fwlink/?LinkId=158021)(http://go.microsoft.com/fwlink/?LinkId=158021)。  
  
## <a name="decrease-the-purging-period-for-the-dta-purge-and-archive-job-from-7-days-to-2-days-in-high-throughput-scenarios"></a>清除周期越短 DTA 清除和从 7 天到高吞吐量方案中的 2 天的存档作业  
 默认情况下，跟踪 BizTalk Server 中的数据的清除间隔设置为 7 天。 在高吞吐量方案中，这可能导致在跟踪数据库中，最终影响 MessageBox 和反过来产生负面影响消息处理吞吐量的性能数据上的过多生成。  
  
 在高吞吐量的情况下，减少硬件和软件为 2 天清除从默认值 7 天的间隔。 有关配置清除间隔的详细信息，请参阅[如何配置 DTA 清除和存档作业](http://go.microsoft.com/fwlink/?LinkID=153814)(http://go.microsoft.com/fwlink/?LinkID=153814) 在 BizTalk Server 2010 帮助中。  
  
## <a name="configure-the-temp-path-for-the-biztalk-service-account-to-point-to-a-separate-disk-or-lun"></a>配置为指向一个单独的磁盘或 LUN 的 BizTalk 服务帐户的 %temp%路径  
 应因为 BizTalk 使用到流文件的临时位置磁盘执行复杂的映射操作时完成此操作。  
  
## <a name="install-the-latest-service-packs"></a>安装最新的 service pack  
 应安装 BizTalk Server 和.NET Framework 的最新服务包，因为这些文件组包含的修补程序可以更正你可能会遇到性能问题。  
  
## <a name="performance-optimizations-in-the-biztalk-server-documentation"></a>BizTalk Server 文档中的性能优化  
 请遵循以下建议根据 BizTalk Server 文档中：  
  
-   [MessageBox 延迟问题疑难解答](http://go.microsoft.com/fwlink/?LinkId=158019)(http://go.microsoft.com/fwlink/?LinkId=158019)  
  
-   [识别性能瓶颈](http://go.microsoft.com/fwlink/?LinkID=154238)(http://go.microsoft.com/fwlink/?LinkID=154238)  
  
-   [避免 DBNETLIB 异常](http://go.microsoft.com/fwlink/?LinkID=155308)(http://go.microsoft.com/fwlink/?LinkID=155308)  
  
-   [避免 TCP/IP 端口耗尽](http://go.microsoft.com/fwlink/?LinkID=153240)(http://go.microsoft.com/fwlink/?LinkID=153240)  
  
-   [设置 EPM 线程池大小](http://go.microsoft.com/fwlink/?LinkId=158020)(http://go.microsoft.com/fwlink/?LinkId=158020)  
  
## <a name="see-also"></a>另请参阅  
 [优化 BizTalk Server 性能](../technical-guides/optimizing-biztalk-server-performance.md)