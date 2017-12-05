---
title: "适配器性能影响的配置参数 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90bbb9fb-0b31-45f0-a54c-7b2025e653b9
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e48eb329a50dda26555e76dd54dd4f4d33cb2c98
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="configuration-parameters-that-affect-adapter-performance"></a>影响适配器性能的配置参数
本部分介绍可能会影响 BizTalk Server 适配器性能的配置设置。  
  
## <a name="clr-hosting-thread-values-for-the-host"></a>主机的 CLR 宿主线程值  
 因为 Windows 线程是 Windows 进程可用的最基本的可执行单元，因此，有必要为与 BizTalk 主机实例相关联的 .NET 线程池分配足够的线程以防止线程不足。 线程不足时，没有足够的线程用于执行请求的作业，因此可能会对性能造成负面影响。 同时应注意防止为与主机相关联的 .NET 线程池分配不必要的过多线程。 为与主机相关联的 .NET 线程池分配过多的线程会增加上下文切换，也会对总体性能造成负面影响。 Windows 内核从运行一个线程切换到运行另一个线程时，会发生上下文切换，这可能是一个成本高昂的 CPU 操作。  
  
 通过在 BizTalk Server 设置仪表板中配置相应的值，可以修改与 BizTalk 主机实例相关联的 .NET 线程池中可用的 Windows 线程数。 有关修改.NET CLR 值的详细信息，请参阅[如何修改.NET CLR 设置](http://msdn.microsoft.com/library/ff629681\(v=BTS.70\).aspx)。  
  
## <a name="aspnet-settings-that-can-impact-http-or-soap-adapter-performance"></a>可能影响 HTTP 或 SOAP 适配器性能的 ASP.NET 设置  
 以下设置可应用于的 ASP.NET 应用程序承载 Web 应用程序与之通信的 HTTP 或 SOAP 适配器。 这些参数是在作为该 Web 应用程序宿主的服务器的 web.config 或 machine.config 文件中设置的。 请修改这些设置以适合 HTTP 或 SOAP 适配器发送端口生成的负载。 有关这些设置的详细信息，请参阅[争用、 性能不佳和死锁在 ASP.NET 应用程序的 Web 服务请求时](http://go.microsoft.com/fwlink/p/?LinkId=196842)。  
  
|**参数**|**配置文件节**|**默认值**|**建议的值**|  
|-------------------|---------------------------------------|-----------------------|---------------------------|  
|**minFreeThreads**<br /><br /> 允许执行新请求的自由线程的最小数目。 ASP.NET 为需要额外线程完成其处理的请求保留了多个自由线程。|\<httpRuntime\>|8|88 * 托管 Web 应用程序的服务器上的处理器数。|  
|**minFreeLocalRequestFreeThreads**<br /><br /> ASP.NET 保持用于执行新的本地请求的最小可用线程数。 此线程数目是为从本地主机传入的请求而保留的，以防某些请求在其处理期间发出对本地主机的子请求。 这可以避免由于递归重入 Web 服务器而可能带来的死锁。|\<httpRuntime\>|4|76 * 托管 Web 应用程序的服务器上的处理器数。|  
|**executionTimeout**<br /><br /> 指示在被 ASP.NET 自动关闭前，允许执行请求的最大秒数。|\<httpRuntime\>|90|90|  
|**maxconnection**<br /><br /> 确定可以向特定的 IP 地址建立多少个连接。|\<connectionManagement\>|2<br /><br /> 如果此设置的值为 2，则符合 HTTP 1.1 规范的 IETF RFC，因此此值可供用户使用，但不利于优化高吞吐量。|12 * 托管 Web 应用程序的服务器上的处理器数。|  
|**maxWorkerThreads**<br /><br /> 按 CPU 配置用于进程的辅助线程的最大数目。|\<processModel\>|20|100**注意：**此值隐式乘以在服务器上的处理器数。|  
|**minWorkerThreads**|\<processModel\>|1|**maxWorkerThreads** / 2**注意：** minWorkerThreads 参数不在默认情况下配置文件中。 你必须添加此参数。 **注意：**此值隐式乘以在服务器上的处理器数。|  
|**maxIoThreads**<br /><br /> ASP.NET 使用此参数来限制所使用的完成线程数。|\<processModel\>|20|100<br /><br /> 此值将隐式乘以服务器上的处理器数。|  
  
 如果承载的 Web 服务的计算机运行的 ASP.NET 2.0 或更高版本，则可以设置**autoConfig = true** processModel 部分要自动配置以下设置以实现最佳的 Machine.config 文件中基于机配置上的性能：  
  
-   **MaxWorkerThreads**属性。  
  
-   **MaxIoThreads**属性。  
  
-   **MinFreeThreads** httpRuntime 元素的属性。  
  
-   **MinLocalRequestFreeThreads** httpRuntime 元素的属性。  
  
-   **MaxConnection**属性\<connectionManagement\>元素 （网络设置）。  
  
> [!NOTE]
>  **ProcessModel**部分可以设置仅在 Machine.config 文件，并且会影响服务器运行的所有 ASP.NET 应用程序。  
  
 有关详细信息**processModel** machine.config 文件的元素，请参阅 Microsoft MSDN 网站在[http://go.microsoft.com/fwlink/p/?LinkId=62307](http://go.microsoft.com/fwlink/p/?LinkId=62307)。  
  
## <a name="registry-setting-that-governs-the-tcp-window-size"></a>控制 TCP 窗口大小的注册表设置  
 以下注册表设置控制 TCP 窗口大小，它是在连接过程中可以缓冲的接收数据的数量（以字节为单位）。 如果未将此参数设置为最佳值，则适配器性能会受到负面影响。 实现此注册表设置可增大 TCP 窗口大小。  
  
> [!WARNING]
>  如果注册表编辑器使用不当，则可能会产生严重问题，导致重新安装操作系统。 Microsoft 不保证可以解决因注册表编辑器使用不当而造成的问题。 请慎用注册表编辑器，风险自负。 在修改注册表之前，请务必备份注册表，并确保你知道在发生问题时如何使用备份进行还原。  
  
 若要增大默认的 TCP 窗口大小，请执行以下步骤：  
  
1.  依次单击 **启动”**和 **运行”**，键入 **regedit.exe**，然后单击 **确定”** 以启动注册表编辑器。  
  
     导航到**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\\**  
  
2.  下**参数**密钥，使用指示的值创建以下的 DWORD 条目。  
  
    |DWORD 项|默认值|推荐值|  
    |-----------------|-------------------|-----------------------|  
    |**TcpWindowSize**<br /><br /> 此设置确定计算机的最大 TCP 接收窗口大小。 接收窗口指定发送方在不会收到确认的情况下可以传输的字节数。 通常，较大的接收窗口会改善高带宽网络的性能。|17520|设置为以太网最大段大小 (MSS) 1460 的倍数，最大为 64240。 如果使用 Windows 比例，则设置为最多 65535。|  
  
    > [!NOTE]
    >  要使所做的更改生效，必须重新启动计算机。  
  
3.  关闭“注册表编辑器”。  
  
## <a name="see-also"></a>另请参阅  
 [性能和容量规划](../core/performance-and-capacity-planning.md)