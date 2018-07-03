---
title: 一般 BizTalk Server Optimizations1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8032553-bae3-440d-9197-b926160b0bdf
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2605a7acd9610b0b5417e8c5d7c875f67f22f30c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006710"
---
# <a name="general-biztalk-server-optimizations"></a>一般 BizTalk Server 优化
以下建议可用于提高 BizTalk Server 性能。 本主题中列出的优化后安装并配置 BizTalk Server 应用。  
  
## <a name="configure-msdtc"></a>配置 MSDTC  
 若要简化 SQL Server 和 BizTalk Server 之间的事务，必须启用 Microsoft 分布式事务处理协调器 (MS DTC)。 若要在 BizTalk Server 上配置 MSDTC，请参阅主题[提高操作系统性能的通用指南](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)。  
  
## <a name="recommendations-for-configuring-biztalk-server-hosts"></a>配置 BizTalk Server 主机的建议  
 本部分提供有关配置 BizTalk Server 主机的建议。  
  
### <a name="create-multiple-biztalk-server-hosts-and-separate-host-instances-by-functionality"></a>创建多个 BizTalk Server 主机和单独的主机实例的功能  
 请遵循以下准则来创建多个 BizTalk Server 主机并在这些主机之间分配工作负荷：  
  
-   为发送、 接收、 处理和跟踪功能创建单独的主机。 创建多个 BizTalk 主机在 BizTalk 组中配置工作负荷时提供灵活性，但跨 BizTalk 组中运行 BizTalk Server 的计算机分发处理的主要方式。 使用多个主机，可停止一台主机，而不会影响其他主机。 例如，可能想要停止发送消息，以让他们队列 MessageBox 数据库中同时仍然允许在不同的主机实例中运行的接收适配器接收的入站的消息。 主机实例分隔功能还提供以下优势：  
  
    -   运行多个 BizTalk 主机可减少 MessageBox 数据库主机队列表上的争用，因为每个主机分配是 MessageBox 数据库中其自己的工作队列表。  
  
    -   限制是 BizTalk Server 中实现在主机级别。 这允许您设置的每个主机的不同限制的特征。  
  
    -   安全性是通过实现在主机级别;每个主机在离散的 Windows 标识下运行。 这允许您，例如，为 Host_A 访问到 FileShare_B，同时不允许任何其他主机访问文件共享。  
  
-   每个主机实例中的.NET 线程池具有其自己的内存、 句柄和线程等资源集。 在主机之间分配工作负荷时，请考虑进行整体缩放的资源放置在同一主机中。  
  
-   单独的适配器和业务流程，在不同主机上具有不同的资源的优先级。 此方法适合于运行高优先级应用程序专用的 BizTalk Server 计算机上的主机的放置。  
  
> [!NOTE]  
>  虽然有与创建其他主机实例的优点，也有潜在的缺点如果创建了太多主机实例。 每个主机实例是一个 Windows 服务 (BTSNTSvc.exe)，它可以生成针对 MessageBox 数据库的更多负载，并会占用计算机资源 （如 CPU、 内存、 线程）。  
  
 有关修改 BizTalk Server 主机属性，请参阅[如何修改主机属性](http://go.microsoft.com/fwlink/?LinkID=154359)(http://go.microsoft.com/fwlink/?LinkID=154359) BizTalk Server 2010 帮助中。  
  
### <a name="configure-a-dedicated-tracking-host"></a>配置专用的跟踪主机  
 BizTalk Server 适用于吞吐量，因此主业务流程和消息传递引擎执行不实际消息直接移至 BizTalk 跟踪数据库或 BAM 数据库，因为这会将转移这些引擎从其主作业的执行业务流程。 相反，BizTalk Server 使消息留在 MessageBox 数据库，并将其标记为需要迁移到 BizTalk 跟踪数据库。 后台进程 （跟踪主机），然后将消息移动到 BizTalk 跟踪和 BAM 数据库。 跟踪是资源密集型操作，因为单独的主机应创建专用于跟踪，因此可尽量减少跟踪具有与消息处理专用的主机上的影响。 为了获得最佳性能，应至少一个跟踪主机实例，每个 MessageBox 数据库。 跟踪主机实例的实际数应为 N + 1，其中 N = MessageBox 数据库的数量。 "+ 1"是为实现冗余，一台计算机承载跟踪失败的情况下。  
  
 使用专用的跟踪主机还允许您停止其他 BizTalk 主机而不会影响与 BizTalk Server 跟踪。 跟踪数据从 MessageBox 数据库的移动的 BizTalk Server 系统正常运行至关重要。 如果停止 BizTalk 主机负责将跟踪数据移 BizTalk 组中，将不运行的跟踪数据解码服务。 这种影响是，如下所示：  
  
- HAT 跟踪数据不会从 MessageBox 数据库移至 BizTalk 跟踪数据库。  
  
- BAM 跟踪数据不会从 MessageBox 数据库移至 BAM 主导入数据库。  
  
- 不移动数据，因为它不能从 MessageBox 数据库中删除。  
  
- 跟踪数据解码服务停止时，跟踪侦听器仍将触发并将跟踪数据写入到 MessageBox 数据库。 如果不移动数据时，这将导致 MessageBox 数据库变得臃肿，这会影响性能随时间变化。 即使不会跟踪自定义属性或 BAM 配置文件未设置，默认情况下的某些数据被跟踪 （如管道接收 / 发送事件和业务流程事件）。 如果您不想要运行的跟踪数据解码服务，请关闭所有跟踪，以便没有侦听器将数据保存到数据库。 若要禁用全局跟踪，请参阅[如何禁用全局跟踪](http://go.microsoft.com/fwlink/?LinkID=154193)(http://go.microsoft.com/fwlink/?LinkID=154193) BizTalk Server 2010 帮助中。 使用 BizTalk Server 管理控制台来有选择性地禁用跟踪事件。  
  
  跟踪主机应运行 BizTalk Server （适用于在其中一个出现故障的情况下的冗余） 的至少两台计算机上运行。 为了获得最佳性能，应具有至少一个跟踪主机实例，每个 MessageBox 数据库。 跟踪主机实例的实际数目应 （N + 1），其中 N = MessageBox 数据库的数量。 "+ 1"是为实现冗余，一台计算机承载跟踪失败的情况下。  
  
  一个跟踪主机实例将跟踪数据的特定 MessageBox 数据库，但永远不会有多个跟踪主机实例特定的 MessageBox 数据库移动数据。 例如，如果您有三个 MessageBox 数据库，并且只有两个跟踪主机实例，然后其中一个主机实例需要将数据移动 MessageBox 数据库中的两个。 添加第三个跟踪主机实例分配跟踪主机到另一台计算机运行 BizTalk Server 的工作。 在此方案中，添加第四个跟踪主机实例将不分发任何详细的跟踪主机，但会提供一个额外跟踪主机实例的容错能力。  
  
  有关 BAM 事件总线服务的详细信息，请参阅 BizTalk Server 2010 帮助中的以下主题：  
  
- [管理 BAM 事件总线服务](http://go.microsoft.com/fwlink/?LinkID=154194)(http://go.microsoft.com/fwlink/?LinkID=154194)。  
  
- [创建 BAM 事件总线服务的实例](http://go.microsoft.com/fwlink/?LinkID=154195)(http://go.microsoft.com/fwlink/?LinkID=154195)。  
  
### <a name="do-not-cluster-biztalk-hosts-unless-absolutely-necessary"></a>未群集 BizTalk 主机除非绝对必要  
 虽然 BizTalk Server 2010 使你可以将 BizTalk 主机配置为群集资源，应只考虑执行此操作，如果您需要向不能跨多个 BizTalk 计算机托管的资源提供高可用性。 例如，使用 FTP 适配器的端口应仅在一台主机实例中，与位于 FTP 协议不提供文件锁定。 但是，它引入了单点故障，它会从聚类分析中受益。 包含适配器，如文件、 SQL、 HTTP 或处理仅限主机，主机可以在内部负载平衡的计算机，并不会得益于聚类分析。  
  
## <a name="increase-the-number-of--http-concurrent-connections-allowed-by-changing-the-value-for-the-maxconnection-parameter"></a>增加允许的更改将 maxconnection 参数的值的 HTTP 并发连接数  
 默认情况下，HTTP 适配器 （包括基于 WCF 的 HTTP 适配器） 从运行 BizTalk Server 以任何特定的目标服务器的每台计算机打开只有两个并发 HTTP 连接。  
  
 此设置符合 HTTP 1.1 规范的 IETF rfc，尽管它是适用于用户方案，但未优化的高吞吐量。 从运行 BizTalk Server 的每台计算机设置为两个并发发送有效地限制对每个服务器的出站 HTTP 调用。  
  
 若要增加并发连接数，可以修改在 BizTalk Server 配置文件中，BTSNTSvc.exe.config （或 BTSNTSvc64.exe.config 的 64 位主机），每个 BizTalk 服务器上将 maxconnection 参数的值。 可以将其被调用的特定服务器增加。 根据经验，maxconnection 参数的值应设置为 12 * 的 Cpu 或承载 web 应用程序的计算机上的内核数。  
  
> [!NOTE]  
>  请勿增加到被调用的 Web 服务器过重的 HTTP 连接的这种较大的值将 maxconnection 参数的值。 更改后将 maxconnection 参数的值，请执行压力测试将请求发送到每个目标 Web 服务器，以确定将提供良好的性能和 HTTP 的 maxconnection 的值将发送但不使目标 Web服务器。  
  
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
  
 **\<添加地址 ="<https://www.contoso.com>"maxconnection ="24"/\>**   
**\<添加地址 ="<http://www.contoso.com:8080>"maxconnection ="24"/\>**   
**\<添加地址 ="http://*IPAddress*"maxconnection ="24"/\>** 有关优化 IIS 和 ASP.NET Web 服务设置的详细信息，请参阅可能会影响 HTTP 适配器的"ASP.NET 设置性能"部分[配置参数的影响适配器性能](http://go.microsoft.com/fwlink/?LinkID=154200)(<http://go.microsoft.com/fwlink/?LinkID=154200>) 在 BizTalk Server 2010 帮助中。  
  
## <a name="manage-aspnet-thread-usage-or-concurrently-executing-requests-for-web-applications-that-can-host--isolated-received-locations-back-end-web-services-and-wcf-services"></a>管理 ASP.NET 线程使用情况或并发执行的可承载的 Web 应用程序请求隔离的接收的位置、 后端 Web 服务和 WCF 服务  
 工作线程和 I/O 线程数 （IIS 7.5 和 IIS 7.0 在经典模式下） 或并发执行的请求 （IIS 7.5 和 7.0 集成模式下） 为 ASP.NET Web 应用程序主机隔离接收的位置、 后端 Web 服务和 WCF 服务的数量的数量应在以下情况下修改：  
  
-   CPU 使用率不是托管的 Web 服务器上的瓶颈。  
  
-   值：  
  
    -   **ASP.NET 应用 v4.0.30319 \Request Wait Time**或**ASP.NET 应用 v4.0.30319 \Request 执行时间**性能计数器是非常大。  
  
    -   **ASP.NET 应用 v2.0.50727\Request Wait Time**或**ASP.NET 应用 v2.0.50727\Request 执行时间**性能计数器是非常大。  
  
-   在承载 Web 应用程序的计算机的应用程序日志中生成类似于以下错误。  
  
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
  
### <a name="manage-aspnet-thread-usage-for-web-applications-that-can-host-isolated-received-locations-back-end-web-services-and-wcf-services-on-iis-75-and-iis-70-running-in-classic-mode"></a>管理独立的接收的位置、 后端 Web 服务和 IIS 7.5 和 IIS 7.0 以经典模式运行的 WCF 服务可以托管的 Web 应用程序的 ASP.NET 线程使用的情况  
 当**autoConfig**在经典模式下运行的 IIS 7.5 和 IIS 7.0 服务器的 machine.config 文件中的值设置为**true**，ASP.NET 2.0 和 ASP.NET 4 管理的工作线程和 I/O 线程数分配给任何关联的 IIS 工作进程。  
  
```  
<processModel autoConfig="true" />  
```  
  
 若要手动修改的工作线程和 ASP.NET 2.0 和 ASP.Net 4 Web 应用程序的 I/O 线程数，打开关联的 machine.config 文件中，并输入新值**maxWorkerThreads**和**maxIoThreads**参数。  
  
```  
<!-- <processModel autoConfig="true" /> -->  
    <processModel maxWorkerThreads="200" maxIoThreads="200" />  
```  
  
> [!NOTE]  
>  这些值是仅; 作为指导请确保测试对这些参数的更改。  
  
 有关优化的 ASP.NET 2.0 Web 应用程序的 machine.config 文件中的参数的详细信息，请参阅 Microsoft 知识库文章 821268[争用、 性能不佳和死锁时通过 ASP 发出 Web 服务请求。NET 应用程序](http://go.microsoft.com/fwlink/?LinkID=144169)(http://go.microsoft.com/fwlink/?LinkID=144169)。  
  
### <a name="manage-the-number-of-concurrently-executing-requests-for-aspnet-20-web-applications-that-can-host-isolated-received-locations-back-end-web-services-and-wcf-services-on-iis-75-and-iis-70-running-in-integrated-mode"></a>管理并发执行隔离的接收的位置、 后端 Web 服务和 IIS 7.5 和 IIS 7.0 集成模式下运行的 WCF 服务可以托管的 ASP.NET 2.0 Web 应用程序的请求数  
 当 ASP.NET 2.0 承载于 IIS 7.5 和 IIS 7.0 中集成模式下时，使用线程处理方式不同 IIS 7.5 和 IIS 7.0 在经典模式下。 当 ASP.NET 2.0 承载于 IIS 7.5 和 IIS 7.0 中集成模式下时，ASP.NET 2.0 限制的并发执行数**请求**而不是数**线程**并发执行请求数。 同步方案这将间接限制线程数，但异步方案的请求和线程数可能会大不相同。 当在集成模式下，IIS 7.5 和 IIS 7.0 上运行 ASP.NET 2.0 **maxWorkerThreads**并**maxIoThreads** machine.config 文件中的参数不用于管理的正在运行的线程数。 相反，并发执行的请求的更改号从默认值为每个 CPU 的 12 通过修改为指定的值**maxconcurrentrequestspercpu 配置**。 **Maxconcurrentrequestspercpu 配置**reqistry 中或在 aspnet.config 文件的配置部分中，可以指定值。 请执行以下步骤，若要更改的默认值为**maxconcurrentrequestspercpu 配置**来控制的同时执行的请求数：  
  
 **若要在注册表中设置 maxconcurrentrequestspercpu 配置值**  
  
> [!WARNING]  
>  对注册表编辑器的不当使用可能会引起问题，而必须重新安装操作系统。 请慎用注册表编辑器，风险自负。 有关如何备份、 还原和修改注册表的详细信息，请参阅 Microsoft 知识库文章 256986[适用于高级用户的 Windows 注册表信息](http://go.microsoft.com/fwlink/?LinkId=62729)(http://go.microsoft.com/fwlink/?LinkId=62729)。  
  
> [!NOTE]  
>  此设置是全局的并且不能更改为单个应用程序池或应用程序。  
  
1. 依次单击 **启动”** 和 **运行”**，键入 **regedit.exe**，然后单击 **确定”** 以启动注册表编辑器。  
  
2. 导航到**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0**  
  
3. 通过执行以下步骤创建项：  
  
   1.  上**编辑**菜单上，单击**新建**，然后单击**密钥**。  
  
   2.  类型**maxconcurrentrequestspercpu 配置**，然后按**ENTER**。  
  
   3.  下**maxconcurrentrequestspercpu 配置**密钥，请创建 DWORD 项 maxconcurrentrequestspercpu 配置为新值。  
  
   4.  关闭“注册表编辑器”。  
  
   **若要在配置节的 aspnet.config 文件中设置 maxconcurrentrequestspercpu 配置为应用程序池**  
  
> [!NOTE]  
>  必须安装 Microsoft.NET Framework 3.5 Service Pack 1，以容纳通过配置文件设置以下值。 您可以下载 Microsoft.NET Framework 3.5 Service Pack 1 从[Microsoft.NET Framework 3.5 Service Pack 1](http://go.microsoft.com/fwlink/?LinkID=136345) (http://go.microsoft.com/fwlink/?LinkID=136345)。  
  
 打开应用程序池的 aspnet.config 文件并输入新值**maxconcurrentrequestspercpu 配置**并**requestQueueLimit**参数。  
  
```  
<system.web>  
    <applicationPool maxConcurrentRequestsPerCPU="12" requestQueueLimit="5000"/>  
</system.web>  
```  
  
> [!NOTE]  
>  此值将覆盖为指定的值**maxconcurrentrequestspercpu 配置**注册表中。 RequestQueueLimit 设置等同于 processModel/requestQueueLimit，不同之处在于 aspnet.config 文件中的设置将覆盖在 machine.config 文件中的设置。  
  
 有关在 IIS 7.0 上配置 ASP.NET 线程使用情况的详细信息，请参阅[Thomas Marquardt 的博客上的 IIS 7.0 ASP.NET 线程使用情况](http://go.microsoft.com/fwlink/?LinkId=157518)(http://go.microsoft.com/fwlink/?LinkId=157518)。  
  
### <a name="manage-the-number-of-concurrently-executing-requests-for-aspnet-4web-applications-that-can-host-isolated-received-locations-back-end-web-services-and-wcf-services-on-iis-75-and-70-running-in-integrated-mode"></a>管理并发执行隔离的接收的位置、 后端 Web 服务和 IIS 7.5 和 7.0 集成模式下运行的 WCF 服务可以托管的 ASP.NET 4Web 应用程序的请求数  
 使用.NET Framework 4，maxconcurrentrequestspercpu 配置的默认设置为 5000，它是一个非常大的数字，并因此将留出足够的并发执行的异步请求。 有关详细信息，请参阅[ \<applicationPool\>元素 （Web 设置）](http://go.microsoft.com/fwlink/?LinkID=205339) (http://go.microsoft.com/fwlink/?LinkID=205339)。  
  
 IIS 7.5 和 IIS 7.0 集成模式下，对于名为内 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\4.0.30319.0 maxconcurrentrequestspercpu 配置一个 dword 值确定每个 CPU 的并发请求数。 默认情况下，注册表项不存在并且每 CPU 的请求数被限制为 5000。  
  
 **若要在注册表中设置 maxconcurrentrequestspercpu 配置值**  
  
> [!WARNING]  
>  对注册表编辑器的不当使用可能会引起问题，而必须重新安装操作系统。 请慎用注册表编辑器，风险自负。 有关如何备份、 还原和修改注册表的详细信息，请参阅 Microsoft 知识库文章 256986[适用于高级用户的 Windows 注册表信息](http://go.microsoft.com/fwlink/?LinkId=62729)(http://go.microsoft.com/fwlink/?LinkId=62729)。  
  
> [!NOTE]  
>  此设置是全局的并且不能更改为单个应用程序池或应用程序。  
  
1. 依次单击 **启动”** 和 **运行”**，键入 **regedit.exe**，然后单击 **确定”** 以启动注册表编辑器。  
  
2. 导航到**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\4.0.30319.0**。  
  
3. 通过执行以下步骤创建项：  
  
   1.  上**编辑**菜单上，单击**新建**，然后单击**密钥**。  
  
   2.  类型**maxconcurrentrequestspercpu 配置**，然后按**ENTER**。  
  
   3.  下**maxconcurrentrequestspercpu 配置**密钥，请创建 DWORD 项 maxconcurrentrequestspercpu 配置为新值。  
  
   4.  关闭“注册表编辑器”。  
  
   **若要在配置节的 aspnet.config 文件中设置 maxconcurrentrequestspercpu 配置为应用程序池**  
  
> [!NOTE]  
>  必须安装 Microsoft.NET Framework 4 以容纳通过配置文件设置以下值。 您可以下载 Microsoft.NET Framework 4 [Microsoft.NET Framework 4 （Web 安装程序）](http://go.microsoft.com/fwlink/?LinkID=189318) (http://go.microsoft.com/fwlink/?LinkID=189318)。  
  
-   打开应用程序池的 aspnet.config 文件并输入新值**maxconcurrentrequestspercpu 配置**并**requestQueueLimit**参数。  
  
     以下示例中的值是默认值。  
  
    ```  
    <system.web>  
        <applicationPool maxConcurrentRequestsPerCPU="5000" requestQueueLimit="5000"/>  
    </system.web>  
    ```  
  
> [!NOTE]  
>  此值将覆盖为指定的值**maxconcurrentrequestspercpu 配置**注册表中。 **RequestQueueLimit**设置为 processModel/requestQueueLimit 相同，只不过 aspnet.config 文件中的设置将覆盖在 machine.config 文件中的设置。  
  
## <a name="define-clr-hosting-thread-values-for-biztalk-host-instances"></a>定义的 CLR 承载 BizTalk 主机实例的线程值  
 因为 Windows 线程是 Windows 进程可用的最基本的可执行单元，因此，有必要为与 BizTalk 主机实例相关联的 .NET 线程池分配足够的线程以防止线程不足。 线程不足时，是不足够的线程用于执行请求的作业的性能有负面影响。 在同一时间，应格外小心以防止分配更多不必要的主机与相关联的.net 线程池线程。 为与主机相关联的 .NET 线程池分配过多的线程会增加上下文切换。 Windows 内核从运行一个线程为不同的线程，这会导致性能开销切换时，会发生上下文切换。 过多的线程分配可能会导致过多的上下文切换，这将产生负面影响整体性能。 默认分配给 BizTalk 主机实例的.NET 线程池的线程数取决于安装的.NET Framework 版本。 .NET Framework 4 和.NET Framework 3.5 SP1 大大增加默认值，这可能导致过多的线程分配上的 BizTalk Server 计算机和 MessageBox 数据库上的过多的锁争用。  
  
 使用**BizTalk 设置仪表板**，可以修改默认值为 Windows 可用的线程数的.net 线程池与 BizTalk 主机实例相关联。 有关如何修改.NET CLR 设置的详细信息，请参阅[如何修改.NET CLR 设置](http://go.microsoft.com/fwlink/?LinkID=205344)(http://go.microsoft.com/fwlink/?LinkID=205344)。 .NET CLR 设置因 CPU 核心而异。  
  
> [!NOTE]  
>  **工作线程**用于处理排队的工作项并**I/O 线程**是与 I/O 完成端口来处理已完成的异步 I/O 请求相关联的回调线程。  
  
|线程设置|默认值|推荐值|  
|------------------------|-------------------|-----------------------|  
|最大 IO 线程数|250|250|  
|最大工作线程数|25|100**重要说明：** 该值增加到 100 可以拥有对承载 BizTalk Server MessageBox 数据库的 SQL Server 计算机的性能产生负面影响。 当发生此问题时，SQL Server 可能会遇到死锁情况。 我们建议不增加 100 的值超出此参数。|  
|最小 IO 线程数|25|25|  
|最小工作线程数|5|25|  
  
> [!NOTE]  
>  建议的值不是绝对，可能需要进行调整，具体取决于 BizTalk 应用程序。 一次更改一个参数值，然后进行其他更改之前测量的性能和稳定性的 BizTalk 平台的影响。  
  
> [!NOTE]  
>  这些值隐式乘以服务器上的处理器数。 例如，设置**MaxWorkerThreads**进入到 100 的值将有效地在 4 个 CPU 的服务器上设置值 400。  
  
## <a name="disable-biztalk-server-group-level-tracking"></a>禁用 BizTalk Server 组级别跟踪  
 跟踪可能会产生系统开销在 BizTalk Server 的性能，因为数据已写入到 MessageBox 数据库并以异步方式移至 BizTalk 跟踪数据库。 在生产 BizTalk Server 环境中配置跟踪时，应考虑以下事项：  
  
- 根据经验，如果跟踪不是一项业务要求，请禁用组级别跟踪，以减少开销并提高性能。  
  
   若要禁用 BizTalk Server 组级别跟踪，请执行以下步骤：  
  
  1.  在中**BizTalk Server 管理控制台**，展开**BizTalk Server 管理**，右键单击**BizTalk 组**，然后单击**设置**.  
  
  2.  在 BizTalk 设置仪表板对话框中，在组页上清除**启用组级别跟踪**复选框。  
  
  3.  单击**确定**应用所做的修改并退出设置仪表板。  
  
- 仅使用消息正文跟踪如有必要。 具体取决于消息吞吐量和消息大小，消息正文跟踪可能会导致很大的开销。 虽然 BizTalk 活动跟踪具有明显的优势，以进行调试和审核，它还具有很大的性能和可伸缩性的影响。 因此，您应该跟踪是出于调试和安全原因，是绝对必要，可避免跟踪冗余信息的数据。  
  
- 默认情况下，业务流程的情况下会启用以下跟踪选项：  
  
  - 业务流程开始和结束  
  
  - 消息发送和接收  
  
  - 形状开始和结束  
  
    业务流程跟踪选项"形状开始和结束"会产生很大的开销并不应在高吞吐量是必要的生产环境中启用。 业务流程跟踪选项也可在上的 BizTalk 管理控制台中访问**跟踪**业务流程属性对话框的页。  
  
  有关配置跟踪的详细信息，请参阅[配置使用 BizTalk Server 管理控制台跟踪](http://go.microsoft.com/fwlink/?LinkId=158021)(http://go.microsoft.com/fwlink/?LinkId=158021)。  
  
## <a name="decrease-the-purging-period-for-the-dta-purge-and-archive-job-from-7-days-to-2-days-in-high-throughput-scenarios"></a>清除周期越短 DTA 清除和存档作业从 7 天在高吞吐量方案中的 2 天  
 默认情况下，用于跟踪 BizTalk Server 中的数据的清除间隔设置为 7 天。 在高吞吐量方案中，这可以导致在跟踪数据库中，最终影响 MessageBox 和又产生负面影响的消息处理吞吐量的性能数据过多逐渐累积。  
  
 在高吞吐量方案中，降低硬件和软件为 2 天，可从默认值为 7 天内清除时间间隔。 有关配置清除间隔的详细信息，请参阅[如何配置 DTA 清除和存档作业](http://go.microsoft.com/fwlink/?LinkID=153814)(http://go.microsoft.com/fwlink/?LinkID=153814) BizTalk Server 2010 帮助中。  
  
## <a name="configure-the-temp-path-for-the-biztalk-service-account-to-point-to-a-separate-disk-or-lun"></a>配置 BizTalk 服务帐户以指向不同的磁盘或 LUN 的 %temp%路径  
 这应进行因为 BizTalk 使用到流文件的临时位置来执行复杂的映射操作时的磁盘。  
  
## <a name="install-the-latest-service-packs"></a>安装最新 service pack  
 应安装 BizTalk Server 和.NET Framework 的最新 service pack，因为它们包含可以更正可能会遇到性能问题的修补程序。  
  
## <a name="performance-optimizations-in-the-biztalk-server-documentation"></a>BizTalk Server 文档中的性能优化  
 将应用从 BizTalk Server 文档中的以下建议：  
  
-   [MessageBox 延迟问题故障排除](http://go.microsoft.com/fwlink/?LinkId=158019)(http://go.microsoft.com/fwlink/?LinkId=158019)  
  
-   [确定性能瓶颈](http://go.microsoft.com/fwlink/?LinkID=154238)(http://go.microsoft.com/fwlink/?LinkID=154238)  
  
-   [避免出现 DBNETLIB 异常](http://go.microsoft.com/fwlink/?LinkID=155308)(http://go.microsoft.com/fwlink/?LinkID=155308)  
  
-   [避免 TCP/IP 端口耗尽](http://go.microsoft.com/fwlink/?LinkID=153240)(http://go.microsoft.com/fwlink/?LinkID=153240)  
  
-   [设置 EPM 线程池大小](http://go.microsoft.com/fwlink/?LinkId=158020)(http://go.microsoft.com/fwlink/?LinkId=158020)  
  
## <a name="see-also"></a>请参阅  
 [优化 BizTalk Server 性能](../technical-guides/optimizing-biztalk-server-performance.md)