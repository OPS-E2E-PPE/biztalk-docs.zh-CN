---
title: 影响适配器性能的配置参数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 90bbb9fb-0b31-45f0-a54c-7b2025e653b9
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ba58e8f08b453c76ffcf0bc38bf2e75ebf07b20
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356463"
---
# <a name="configuration-parameters-that-affect-adapter-performance"></a>影响适配器性能的配置参数
本部分介绍可能会影响 BizTalk Server 适配器性能的配置设置。  
  
## <a name="clr-hosting-thread-values-for-the-host"></a>主机的 CLR 宿主线程值  
 因为 Windows 线程是最基本的可执行单元可用于 Windows 进程，务必分配足够的线程以防止线程不足的 BizTalk 主机实例相关联的.NET 线程池。 线程不足时，是不足够的线程用于执行请求的工作，可以对性能产生负面影响。 在同一时间，应格外小心以防止分配更多不必要的主机与相关联的.NET 线程池线程。 与主机相关联的.NET 线程池线程过多分配可能会增加上下文切换，这可能会也产生负面影响整体性能。 当从运行某个 Windows 内核切换到不同的线程的线程和可以是代价高昂的 CPU 操作时，会发生上下文切换。  
  
 修改通过在 BizTalk Server 设置仪表板中配置适当的值与 BizTalk 主机实例相关联的.NET 线程池中可用的 Windows 线程数。 有关修改.NET CLR 值的详细信息，请参阅[如何修改.NET CLR 设置](http://msdn.microsoft.com/library/ff629681\(v=BTS.70\).aspx)。  
  
## <a name="aspnet-settings-that-can-impact-http-or-soap-adapter-performance"></a>可能会影响 HTTP 或 SOAP 适配器性能的 ASP.NET 设置  
 以下设置可应用于托管 HTTP 或 SOAP 适配器与进行通信的 Web 应用程序的 ASP.NET 应用程序。 在托管 Web 应用程序的服务器的 web.config 或 machine.config 文件中设置这些参数。 修改这些设置以适应负载生成的 HTTP 或 SOAP 适配器发送端口。 有关这些设置的详细信息，请参阅[争用、 性能不佳和死锁时进行从 ASP.NET 应用程序的 Web 服务请求](http://go.microsoft.com/fwlink/p/?LinkId=196842)。  
  
|**参数**|**配置文件的部分**|**默认值**|**建议的值**|  
|-------------------|---------------------------------------|-----------------------|---------------------------|  
|**minFreeThreads**<br /><br /> 最小自由线程，以允许执行新请求数。 ASP.NET 保留了多个免费对于需要其他线程完成其处理的请求。|\<httpRuntime\>|8|88 * 托管 Web 应用程序的服务器上的处理器数。|  
|**minFreeLocalRequestFreeThreads**<br /><br /> 最小 ASP.NET 保持用于执行新的本地请求的自由线程数。 此数量的线程保留保留的请求来自本地主机，以防某些请求在其处理期间向本地主机发出子请求。 这将避免可能的死锁，由于递归重入 Web 服务器。|\<httpRuntime\>|4|76 * 托管 Web 应用程序的服务器上的处理器数。|  
|**executionTimeout**<br /><br /> 指示最大允许请求执行 ASP.NET 自动关闭前的秒数。|\<httpRuntime\>|90|90|  
|**maxconnection**<br /><br /> 确定多少个连接可以建立到特定的 IP 地址。|\<connectionManagement\>|2<br /><br /> 值为 2，此设置符合 HTTP 1.1 规范的 IETF rfc 和适用于用户方案，但未针对高吞吐量进行优化。|12 * 托管 Web 应用程序的服务器上的处理器数。|  
|**maxWorkerThreads**<br /><br /> 配置要用于在每个 CPU 的基础上的进程的工作线程的最长。|\<processModel\>|20|100**注意：** 此值隐式乘以服务器上的处理器数。|  
|**minWorkerThreads**|\<processModel\>|1|**maxWorkerThreads** / 2**注意：** 在配置文件中默认情况下，minWorkerThreads 参数不是。 必须将其添加。 **注意：** 此值隐式乘以服务器上的处理器数。|  
|**maxIoThreads**<br /><br /> 由 ASP.NET 用来限制使用的完成线程数。|\<processModel\>|20|100<br /><br /> 此值隐式乘以服务器上的处理器数。|  
  
 如果承载 Web 服务的计算机运行的 ASP.NET 2.0 或更高版本，则可以设置**autoConfig = true**要自动配置以下设置以获得最佳的 Machine.config 文件的 processModel 部分根据计算机配置的性能：  
  
-   **MaxWorkerThreads**属性。  
  
-   **MaxIoThreads**属性。  
  
-   **MinFreeThreads** httpRuntime 元素的属性。  
  
-   **MinLocalRequestFreeThreads** httpRuntime 元素的属性。  
  
-   **MaxConnection**的属性\<connectionManagement\>元素 （网络设置） 元素。  
  
> [!NOTE]
>  **ProcessModel**部分可以仅在 Machine.config 文件中设置，并会影响服务器运行的所有 ASP.NET 应用程序。  
  
 有关详细信息**processModel** machine.config 文件的元素，请参阅 Microsoft MSDN 网站上的[ http://go.microsoft.com/fwlink/p/?LinkId=62307 ](http://go.microsoft.com/fwlink/p/?LinkId=62307)。  
  
## <a name="registry-setting-that-governs-the-tcp-window-size"></a>控制 TCP 窗口大小的注册表设置  
 以下注册表设置控制 TCP 窗口大小，即量接收连接过程中可以缓冲的数据 （以字节为单位）。 如果此参数未设置为最佳值然后适配器性能会受到负面影响。 实现此注册表设置可增大 TCP 窗口大小。  
  
> [!WARNING]
>  如果注册表编辑器使用不当可能会导致严重的问题，可能需要重新安装操作系统。 Microsoft 无法保证可以解决的错误地使用注册表编辑器而导致的问题。 请慎用注册表编辑器，风险自负。 在修改注册表之前，应始终备份注册表，并确保您知道如何还原备份，如果出现问题。  
  
 若要增加默认的 TCP 窗口大小，请执行以下步骤：  
  
1.  依次单击 **启动”** 和 **运行”**，键入 **regedit.exe**，然后单击 **确定”** 以启动注册表编辑器。  
  
     导航到**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\\**  
  
2.  下**参数**密钥，请用指示值创建以下 DWORD 项。  
  
    |DWORD 项|默认值|推荐值|  
    |-----------------|-------------------|-----------------------|  
    |**TcpWindowSize**<br /><br /> 此设置确定的最大 TCP 接收窗口大小的计算机。 接收窗口指定发件人未接收到确认的情况下可以传输的字节数。 通常情况下，较大接收窗口会改善高带宽网络性能。|17520|将设置为以太网最大段大小 (MSS) 的最大为 64240 1460年的倍数。 如果使用 Windows 缩放，则设置为最大值 65535。|  
  
    > [!NOTE]
    >  必须重新启动计算机中的这些更改才会生效。  
  
3.  关闭“注册表编辑器”。  
  
## <a name="see-also"></a>请参阅  
 [性能和容量规划](../core/performance-and-capacity-planning.md)