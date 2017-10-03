---
title: "网络优化 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9ff0392f-37ae-4ca6-8cc6-d53065de64c5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbf4b0e8df9d8baa81a91576dc37fd89413714f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="network-optimizations"></a>网络优化
在 BizTalk Server 环境中的 BizTalk Server 计算机都独立于 SQL Server 计算机，BizTalk 服务器处理的每个消息无需通过网络通信。 这种通信包括相当大的 BizTalk Server 计算机和 BizTalk 消息框数据库、 BizTalk 管理数据库、 BAM 数据库和其他数据库之间的流量。 在高负载情况下，此通信可能会导致大量网络流量，尤其是在网络设置未经过优化，没有足够的网络接口卡已安装，或足够的网络带宽可能成为瓶颈，可用。  
  
 本主题提供用于提高在同一个 HYPER-V 主机计算机上运行的 HYPER-V 虚拟机之间的网络性能的步骤，并提供了提高网络性能的一些常规建议。  
  
> [!NOTE]  
>  最常见的指示器网络 IO 是瓶颈是计数器"SQL Server： 等待 Statistics\Network IO 等待。" 时的值**平均等待时间**此计数器中为大于零上的一个或多个 SQL Server 计算机，则网络 IO 是瓶颈。  
  
## <a name="improving-network-performance-of-biztalk-server-on-hyper-v"></a>HYPER-V 上提高网络性能的 BizTalk Server  
  
### <a name="configure-hyper-v-virtual-machines-that-are-running-on-the-same-hyper-v-host-computer-to-use-a-private-virtual-network"></a>配置在同一个 HYPER-V 主机计算机用于专用虚拟网络运行的 HYPER-V 虚拟机  
 若要提高运行的 HYPER-V 虚拟机之间的网络性能同一个 HYPER-V 主机计算机，创建私有虚拟网络和路由网络流量通过私有虚拟网络的虚拟机之间。  
  
##### <a name="create-a-private-virtual-network"></a>创建专用的虚拟网络  
  
1.  单击**启动**，单击**所有程序**。 单击**管理工具**，然后单击**Hyper-v 管理器**。  
  
2.  在 HYPER-V 管理器的左侧窗格中，右键单击**Hyper-v 管理器**，然后单击**连接到服务器**。  
  
3.  在**选择计算机**对话框中，输入 HYPER-V 主机计算机的名称，然后单击**确定**。  
  
4.  在 HYPER-V 管理器的左侧窗格中，右键单击 HYPER-V 主机，并依次**虚拟网络管理器**。  
  
5.  虚拟网络管理器中，在**你想要创建哪种类型的虚拟网络？**，单击**私有**，然后单击**添加**。  
  
6.  输入新的虚拟网络的名称，然后单击**确定**。 虚拟网络现可供此 HYPER-V 主机运行每个 HYPER-V 虚拟机。  
  
##### <a name="add-the-private-virtual-network-to-hyper-v-virtual-machines-running-on-the-hyper-v-host"></a>添加到 HYPER-V 虚拟机在 HYPER-V 主机上运行的专用虚拟网络  
  
1.  单击**启动**，单击**所有程序**。 单击**管理工具**，然后单击**Hyper-v 管理器**。  
  
2.  在 HYPER-V 管理器的左侧窗格中，右键单击**Hyper-v 管理器**，然后单击**连接到服务器**。  
  
3.  在**选择计算机**对话框中，输入 HYPER-V 主机计算机的名称，然后单击**确定**。  
  
4.  关闭任何正在运行的虚拟机，要通过虚拟机中，右键单击，然后单击添加专用虚拟网络**关闭**。  
  
5.  之后关闭虚拟机，右键单击虚拟机，然后依次**设置**若要更改虚拟机的设置。  
  
6.  在**< machine_name > 设置**对话框中，在**添加硬件**，单击以选择**网络适配器**，然后单击**添加**.  
  
7.  上**网络适配器**配置页上，在**网络：**，选择你以前创建的专用虚拟网络，然后单击**确定**。 你现在已专用虚拟网络提供到 HYPER-V 虚拟机将可访问下次启动虚拟机。  
  
8.  为你想要通过专用虚拟网络的网络流量路由每个虚拟机重复上述步骤。  
  
9. 启动已添加到专用虚拟网络的虚拟机。 右键单击每个虚拟机，然后单击**启动**。  
  
##### <a name="configure-each-virtual-machine-to-use-the-private-virtual-network"></a>配置每个虚拟机使用专用虚拟网络  
  
1.  启动每个虚拟机后，是可以为网络连接到虚拟机可以访问的专用虚拟网络。 在使用 TCP/IPv4，每个虚拟机上配置的网络连接，并指定 TCP/IPv4 协议的设置。  
  
    1.  访问网络连接属性页中，选择**Internet 协议版本 4(TCP/IPv4)**，然后单击**属性**。  
  
    2.  单击此单选按钮旁边**使用下面的 IP 地址**。  
  
2.  输入一个值**IP 地址**的专用 IP 范围中的字段在地址中标识"RFC 1918 地址分配的专用 IP 地址" [http://go.microsoft.com/fwlink/?LinkID=31904](http://go.microsoft.com/fwlink/?LinkID=31904)。  
  
3.  记下指定; 的 IP 地址你将需要将此值与更高版本的主机文件条目中的此计算机的 NetBIOS 名称相关联。  
  
4.  输入适当的值**子网掩码**字段。  
  
    > [!NOTE]  
    >  Windows 应填充**子网掩码**具有适当的值字段根据输入到的值**IP 地址**字段。  
  
5.  保留**默认网关**字段保留为空，单击**确定**，然后单击**关闭**。  
  
6.  在配置每个虚拟机后使用唯一的专用 IP 地址，使用的 IP 地址和其他运行的虚拟机在 HYPER-V 主机计算机上的 NetBIOS 名称中更新每个虚拟机上的 HOSTS 文件。 更新的主机文件应保存到的 %systemroot%\drivers\etc\ 文件夹中，每个虚拟机上。  
  
    > [!NOTE]  
    >  默认情况下 Windows 检查本地的主机文件，首先来通过与其他虚拟机，唯一的专用 IP 地址更新每个虚拟机上的 HOSTS 文件解析 NetBIOS 名称，因为在这些计算机之间的网络流量，现在将通过路由专用的虚拟网络。  
  
### <a name="disable-tcp-offloading-for-the-virtual-machine-network-cards"></a>禁用 TCP 卸载虚拟机网卡  
 在 MSDN 主题"使用用于启用和禁用任务 Offloading (NDIS 5.1) 的注册表值"中所述编辑注册表[http://go.microsoft.com/fwlink/?LinkId=147619](http://go.microsoft.com/fwlink/?LinkId=147619)禁用 TCP 卸载用于每个虚拟机上的网络卡。  
  
> [!IMPORTANT]  
>  对注册表编辑器的不当使用可能会引起问题，而必须重新安装操作系统。 请慎用注册表编辑器，风险自负。 有关如何备份、 还原和修改注册表的详细信息，请参阅 Microsoft 知识库文章"Microsoft Windows 注册表说明"在[http://go.microsoft.com/fwlink/?LinkId=62729](http://go.microsoft.com/fwlink/?LinkId=62729)。  
  
## <a name="general-guidelines-for-improving-network-performance"></a>提高网络性能的一般准则  
 以下建议可用于提高网络性能：  
  
### <a name="add-additional-network-cards-to-computers-in-the-biztalk-server-environment"></a>将附加网络接口卡添加到 BizTalk Server 环境中的计算机  
 只需添加其他的硬盘驱动器可以提高磁盘性能、 添加附加网络接口卡可以提高网络性能。 如果在 BizTalk Server 环境中的计算机上的网络卡饱和并且卡是瓶颈，请考虑添加一个或多个附加网络接口卡以提高性能。  
  
### <a name="implement-network-segmentation"></a>实现网络分段  
 请按照中的建议**子网**部分的"BizTalk Server 数据库优化"白皮书，网址[http://go.microsoft.com/fwlink/?LinkID=101578](http://go.microsoft.com/fwlink/?LinkID=101578)。  
  
### <a name="where-possible-replace-hubs-with-switches"></a>如果可能，替换交换机的中心  
 交换机包含用于在源和目标之间的流量而中心使用广播的模型路由流量直接路由逻辑。 因此交换机更高效，并提高了性能。  
  
### <a name="remove-unnecessary-network-protocols"></a>删除不必要的网络协议  
 Windows Server 计算机有时具有多个网络服务和安装比实际需要的协议。 每个额外的网络客户端、 服务或协议将放置其他开销在系统资源。  
  
 此外，每个已安装的协议生成网络流量。 通过删除不必要的网络客户端、 服务和协议，系统资源均可供其他进程、 避免过多的网络流量和必须进行协商的网络绑定数减少到最少。  
  
 若要查看当前安装的网络客户端，协议和服务，请按照下列步骤：  
  
1.  单击**启动**，指向**设置**，然后单击**控制面板**。  
  
2.  双击**网络连接**以在计算机上显示的网络连接。  
  
3.  右键单击**本地区域连接**（或你的网络连接的条目），然后单击**属性**要显示的网络连接的属性对话框。  
  
4.  若要删除不必要的项，请选择它，然后单击**卸载**。 若要禁用某个项，只需清除与项关联的复选框。  
  
 如果你不确定的卸载某个项的连接的效果，然后禁用项，而不是卸载它。 禁用项，可确定哪些服务、 协议和客户端实际需要的系统上。 在确定，禁用一项在服务器上有没有负面影响，然后可以卸载项。  
  
 在许多情况下，只有以下三个组件是标准的基于 TCP/IP 网络上的操作所必需的：  
  
-   Microsoft 网络客户端  
  
-   文件和打印机共享 Microsoft 网络的  
  
-   Internet 协议 (TCP/IP)  
  
### <a name="network-adapter-drivers-on-all-computers-in-the-biztalk-server-environment-should-be-tuned-for-performance"></a>BizTalk Server 环境中的所有计算机上的网络适配器驱动程序应针对性能优化  
  
> [!IMPORTANT]  
>  在之前应用到网络适配器驱动程序优化，始终安装的最新的网络适配器设备驱动程序的网络卡在环境中。  
  
 调整网络适配器设备驱动程序，以最大化传入和传出数据包缓冲，可用的内存量。 也最大化缓冲区计数，尤其是传输缓冲区和合并缓冲区。 默认值为这些参数，并是否即使提供，制造商和驱动程序版本之间的不同。 目标是以最大化网络适配器硬件，通过完成的工作并允许网络操作，以减少网络流量高峰和关联的拥塞的最大可能会发生缓冲区空间。  
  
> [!NOTE]  
>  若要优化网络适配器驱动程序的步骤因制造商而异。  
  
 请按照下列步骤，若要访问中的网络适配器设置[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]:  
  
1.  单击**启动**、 然后单击**控制面板**。  
  
2.  单击**网络和 Internet**，然后单击**网络和共享中心**。  
  
3.  单击**更改适配器设置**，右键单击**本地区域连接**（或你的网络连接的名称），然后单击**属性**。  
  
4.  上**常规**选项卡上，单击**配置**。  
  
5.  单击**高级**到可以为网络适配器配置的访问属性的选项卡。  
  
 应为每个网络适配器在 BizTalk Server 环境中配置以下属性：  
  
> [!NOTE]  
>  您应用这些设置对于每个物理网络适配器，包括单个网络适配器集中的聚合、 负载平衡，或容错配置的网络适配器成组。 某些组合软件，你可能需要也适用于团队的这些设置。 请注意，某些网络适配器是自我调整可能不会提供该选项来手动配置参数。  
  
-   **电源选项**– 配置网络适配器驱动程序，以防止电源管理功能关闭以节约电源的网络适配器。 此功能可用于客户端计算机但很少，如果曾应，BizTalk Server 或 SQL Server 的计算机上使用。  
  
-   **固定速度/双工 （请不要使用 AUTO）** -它是非常重要的网络速度、 双工、 和流控制参数设置为在交换机上的设置与对应它们连接到。 这将减轻定期"自动同步"这可能暂时需要连接离线的匹配项。  
  
-   **最大值将合并缓冲区**-映射寄存器是用于将物理地址转换为支持总线控制的网络适配器的虚拟地址的系统资源。 将合并缓冲区来供网络驱动程序，如果驱动程序用完了映射寄存器。 设置此值最高可达可能以获得最佳性能。 在服务器上具有有限的物理内存，这可能产生一个负数影响如合并缓冲区使用的系统内存。 大多数系统上但是，最大值设置可以应用而不会显著降低可用内存。  
  
-   **最大传输/发送描述符和发送缓冲区**-此设置指定多少传输控制缓冲区驱动程序分配内存以供网络接口。 这直接反映出该驱动程序可以有其"发送"队列中的未完成数据包数。 设置此值最高可达可能以获得最佳性能。 在服务器上具有有限的物理内存，这可能产生负面影响，作为发送缓冲区使用的系统内存。 大多数系统上但是，最大值设置可以应用而不会显著降低可用内存。  
  
-   **最大接收缓冲区**-此设置指定的网络接口驱动程序时将数据复制到的协议内存所使用的内存缓冲区量。 它通常由为相对较低的值的默认设置。 设置此值最高可达可能以获得最佳性能。 在服务器上具有有限的物理内存，这可能产生一个负数影响作为接收缓冲区使用的系统内存。 大多数系统上但是，最大值设置可以应用而不会显著降低可用内存。  
  
-   **所有上卸载选项**-在几乎所有情况下，当启用网络接口卸载功能时，会提高性能。 某些网络适配器提供单独的参数来启用或禁用卸载用于发送和接收流量。 卸载任务从 CPU 卸载到网络适配器可以帮助较低的 CPU 使用率，从而提高总体系统性能的服务器上。 Microsoft TCP/IP 传输可以卸载一个或多个具有相应的功能的网络适配器的以下任务：  
  
    -   **校验和任务**-TCP/IP 传输可以卸载计算并验证 IP 和 TCP 校验和以发送和接收到的网络适配器，如果网络适配器驱动程序提供了此功能，请启用此选项。  
  
    -   **IP 安全任务**-计算和验证的加密的校验和，有关身份验证标头 (AH) 和封装安全负载 (ESP) 到网络适配器，可以卸载 TCP/IP 传输。 加密和解密的 ESP 到网络适配器的负载，也可以卸载 TCP/IP 传输。 如果网络适配器驱动程序提供了此功能，请启用这些选项。  
  
    -   **分段的大型的 TCP 数据包**-TCP/IP 传输支持大量发送卸载 (LSO)。 LSO，使用 TCP/IP 传输可以卸载大型的 TCP 数据包的分段。  
  
    -   **堆栈卸载**– 整个网络堆栈可以卸载到具有相应的功能的网络适配器。 如果网络适配器驱动程序提供了此功能，请启用此选项。  
  
-   **LAN 唤醒禁用 （除非使用时）** – 配置网络适配器驱动程序，以禁用唤醒 on lan 功能。 此功能可能很有用的客户端计算机，但很少是否应在 BizTalk Server 或 SQL Server 的计算机上。  
  
 有关优化性能的网络适配器的详细信息，请参阅**网络设备设置**部分的"BizTalk Server 数据库优化"白皮书，网址[http://go.microsoft.com/fwlink/?LinkID=101578](http://go.microsoft.com/fwlink/?LinkID=101578)。