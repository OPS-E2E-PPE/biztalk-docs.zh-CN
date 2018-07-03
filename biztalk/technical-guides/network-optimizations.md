---
title: 网络优化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ff0392f-37ae-4ca6-8cc6-d53065de64c5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66419a1c864b4c22d4fb28a70c85cabf2eceb1a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994790"
---
# <a name="network-optimizations"></a>网络优化
在 BizTalk Server 环境中的 BizTalk Server 计算机都独立于 SQL Server 计算机，每个 BizTalk Server 处理的消息需要通过网络通信。 此通信包括 BizTalk Server 计算机和 BizTalk Messagebox 数据库、 BizTalk 管理数据库、 BAM 数据库和其他数据库之间的大量流量。 在高负载情况下，此通信可能会导致大量网络流量，可能成为瓶颈，尤其是在没有优化网络设置、 安装没有足够的网络接口卡，或没有足够的网络带宽可用。  
  
 本主题提供有关提高运行在同一台 HYPER-V 主机计算机上的 HYPER-V 虚拟机之间的网络性能的步骤，并提供了提高网络性能的一些常规建议。  
  
> [!NOTE]  
>  网络 IO 是瓶颈的最常见指示器是计数器"SQL Server： 等待 Statistics\Network IO 等待。" 时的值**平均等待时间**在此计数器是大于零上的一个或多个 SQL Server 计算机，则网络 IO 是瓶颈。  
  
## <a name="improving-network-performance-of-biztalk-server-on-hyper-v"></a>Hyper V 上提高网络性能的 BizTalk Server  
  
### <a name="configure-hyper-v-virtual-machines-that-are-running-on-the-same-hyper-v-host-computer-to-use-a-private-virtual-network"></a>若要使用专用虚拟网络在同一的 HYPER-V 主机计算机运行的 HYPER-V 虚拟机配置  
 若要提高网络性能之间的 HYPER-V 虚拟机上运行的同一个 HYPER-V 主机计算机，创建专用虚拟网络和路由之间的网络流量通过专用的虚拟网络的虚拟机。  
  
##### <a name="create-a-private-virtual-network"></a>创建专用的虚拟网络  
  
1.  单击**启动**，单击**所有程序**。 单击**管理工具**，然后单击**Hyper-v 管理器**。  
  
2.  在 HYPER-V 管理器的左侧窗格中，右键单击**Hyper-v 管理器**，然后单击**连接到服务器**。  
  
3.  在中**选择计算机**对话框中，输入 HYPER-V 主机计算机的名称，然后单击**确定**。  
  
4.  在 HYPER-V 管理器的左侧窗格中，右键单击 HYPER-V 主机，然后依次**虚拟网络管理器**。  
  
5.  虚拟网络管理器中下,**你想要创建什么类型的虚拟网络？**，单击**专用**，然后单击**添加**。  
  
6.  输入新的虚拟网络的名称，然后单击**确定**。 现可用于此的 HYPER-V 主机运行每个 HYPER-V 虚拟机的虚拟网络。  
  
##### <a name="add-the-private-virtual-network-to-hyper-v-virtual-machines-running-on-the-hyper-v-host"></a>添加到 HYPER-V 虚拟机的 HYPER-V 主机上运行的专用虚拟网络  
  
1.  单击**启动**，单击**所有程序**。 单击**管理工具**，然后单击**Hyper-v 管理器**。  
  
2.  在 HYPER-V 管理器的左侧窗格中，右键单击**Hyper-v 管理器**，然后单击**连接到服务器**。  
  
3.  在中**选择计算机**对话框中，输入 HYPER-V 主机计算机的名称，然后单击**确定**。  
  
4.  关闭正在运行的虚拟机要通过右键单击虚拟机，然后单击添加专用虚拟网络**关闭**。  
  
5.  之后关闭虚拟机，右键单击虚拟机，然后依次**设置**若要更改虚拟机的设置。  
  
6.  在中**设置为 < m a c h >** 对话框中的**添加硬件**，单击以选择**网络适配器**，然后单击**添加**.  
  
7.  上**网络适配器**配置页上，在**网络：**，选择之前创建的专用虚拟网络，然后单击**确定**。 你现在使专用虚拟网络的 HYPER-V 虚拟机，这将启动虚拟机的下一步时间可为可用。  
  
8.  为你想要通过虚拟专用网络的网络流量路由每个虚拟机重复上述步骤。  
  
9. 启动虚拟机添加到虚拟专用网络。 右键单击每个虚拟机，然后单击**启动**。  
  
##### <a name="configure-each-virtual-machine-to-use-the-private-virtual-network"></a>每个虚拟机配置为使用专用虚拟网络  
  
1.  启动每个虚拟机后，是可以作为网络连接到虚拟机可以访问虚拟专用网络。 若要使用 TCP/IPv4，每个虚拟机上配置的网络连接并指定 TCP/IPv4 协议的设置。  
  
    1.  访问网络连接属性页中，选择**Internet 协议版本 4(TCP/IPv4)**，然后单击**属性**。  
  
    2.  单击此单选按钮旁边**使用下面的 IP 地址**。  
  
2.  输入一个值**IP 地址**的专用 IP 范围中的字段在地址中标识的"RFC 1918 专用 IP 地址的地址分配" [ http://go.microsoft.com/fwlink/?LinkID=31904 ](http://go.microsoft.com/fwlink/?LinkID=31904)。  
  
3.  请记下指定; 的 IP 地址您需要将此值与此主机文件条目更高版本中的计算机的 NetBIOS 名称相关联。  
  
4.  输入适当的值**子网掩码**字段。  
  
    > [!NOTE]  
    >  Windows 应填充**子网掩码**具有适当的值字段基于你输入的值**IP 地址**字段。  
  
5.  将保留**默认网关**字段留空，单击**确定**，然后单击**关闭**。  
  
6.  使用唯一的专用 IP 地址配置每个虚拟机之后, 使用的 IP 地址和其他运行的虚拟机的 HYPER-V 主机计算机上的 NetBIOS 名称中更新每个虚拟机上的 HOSTS 文件。 更新的主机文件应保存到 %systemroot%\drivers\etc\ 文件夹中，每个虚拟机上。  
  
    > [!NOTE]  
    >  因为默认情况下 Windows 会检查本地的 HOSTS 文件，首先以通过与其他虚拟机，唯一的专用 IP 地址更新每个虚拟机上的 HOSTS 文件中解析 NetBIOS 名称，在这些计算机之间的网络流量，现在会通过路由专用虚拟网络。  
  
### <a name="disable-tcp-offloading-for-the-virtual-machine-network-cards"></a>禁用 TCP 卸载虚拟机网卡  
 在编辑注册表，如 MSDN 主题"使用来启用和禁用任务卸载 (NDIS 5.1) 的注册表值"中所述[ http://go.microsoft.com/fwlink/?LinkId=147619 ](http://go.microsoft.com/fwlink/?LinkId=147619)禁用 TCP 卸载每个虚拟机上的网卡。  
  
> [!IMPORTANT]  
>  对注册表编辑器的不当使用可能会引起问题，而必须重新安装操作系统。 请慎用注册表编辑器，风险自负。 有关如何备份、 还原和修改注册表的详细信息，请参阅 Microsoft 知识库文章"Microsoft Windows 注册表说明"处[ http://go.microsoft.com/fwlink/?LinkId=62729 ](http://go.microsoft.com/fwlink/?LinkId=62729)。  
  
## <a name="general-guidelines-for-improving-network-performance"></a>优化网络性能的常规指南  
 以下建议可用于提高网络性能：  
  
### <a name="add-additional-network-cards-to-computers-in-the-biztalk-server-environment"></a>将附加网络接口卡添加到 BizTalk Server 环境中的计算机  
 只需添加额外的硬盘可以提高磁盘性能、 添加附加网络接口卡可以提高网络性能。 如果在 BizTalk Server 环境中的计算机上的网络卡趋于饱和，卡是一个瓶颈，请考虑添加一个或多个附加网络接口卡来提高性能。  
  
### <a name="implement-network-segmentation"></a>实现网络分段  
 请按照中的建议**子网**部分中的"BizTalk Server 数据库优化"白皮书，网址[ http://go.microsoft.com/fwlink/?LinkID=101578 ](http://go.microsoft.com/fwlink/?LinkID=101578)。  
  
### <a name="where-possible-replace-hubs-with-switches"></a>在可能的情况下，替换开关为中心  
 交换机包含用于直接路由的源和目标之间的通信，而中心使用广播的模型将流量路由逻辑。 因此开关的效率更高，并提供改进的性能。  
  
### <a name="remove-unnecessary-network-protocols"></a>删除不必要的网络协议  
 Windows Server 计算机有时了多个网络服务和安装不是实际需要的协议。 每个额外的网络客户端、 服务或协议将放置其他开销系统资源。  
  
 此外，每个已安装的协议生成网络流量。 通过删除不必要的网络客户端、 服务和协议，系统资源都可供其他进程、 避免过多的网络流量和必须协商的网络绑定数减少到最少。  
  
 若要查看当前安装的网络客户端，协议和服务，请按照下列步骤：  
  
1. 单击**启动**，依次指向**设置**，然后单击**控制面板**。  
  
2. 双击**网络连接**若要在计算机上显示的网络连接。  
  
3. 右键单击**本地连接**（或你的网络连接的条目），然后单击**属性**以显示网络连接属性对话框。  
  
4. 若要删除不必要的项目，请选择它，然后单击**卸载**。 若要禁用某项，只需清除与项关联的复选框。  
  
   如果您不确定有关卸载连接的项的效果，请禁用项，而不是无需卸载它。 禁用项，可确定哪些服务、 协议和客户端实际需要的系统上。 时确定，禁用某项的服务器上有没有负面影响，然后可以卸载该项目。  
  
   在许多情况下，只有以下三个组件是标准的基于 TCP/IP 网络上的操作所必需的：  
  
-   Microsoft 网络客户端  
  
-   文件和打印机共享 Microsoft 网络的  
  
-   Internet 协议 (TCP/IP)  
  
### <a name="network-adapter-drivers-on-all-computers-in-the-biztalk-server-environment-should-be-tuned-for-performance"></a>在 BizTalk Server 环境中的所有计算机上的网络适配器驱动程序应该优化性能  
  
> [!IMPORTANT]  
>  然后再应用到网络适配器驱动程序优化，始终安装网络卡的最新网络适配器设备驱动的程序在环境中。  
  
 调整网络适配器设备驱动程序，以最大限度地传入和传出数据包缓冲，可用的内存量。 此外最大化缓冲区计数，尤其是传输缓冲区并合并缓冲区。 默认值为这些参数，并是否甚至提供，制造商和驱动程序版本之间的不同。 目标是以最大程度提高通过网络适配器硬件，完成的工作并允许以减少网络流量喷发，并关联的拥塞的网络操作的最大可能的缓冲区空间。  
  
> [!NOTE]  
>  要优化网络适配器驱动程序的步骤因制造商而异。  
  
 请按照以下步骤访问中的网络适配器设置[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]:  
  
1. 单击**启动**、，然后单击**控制面板**。  
  
2. 单击**网络和 Internet**，然后单击**网络和共享中心**。  
  
3. 单击**更改适配器设置**，右键单击**本地区域连接**（或你的网络连接的名称），然后单击**属性**。  
  
4. 上**常规**选项卡上，单击**配置**。  
  
5. 单击**高级**选项卡可以为该网络适配器配置的访问属性。  
  
   应为 BizTalk Server 环境中每个网络适配器配置以下属性：  
  
> [!NOTE]  
>  您应用这些设置包括单个网络适配器成组网络适配器配置的聚合、 负载平衡或容错能力的集内每个物理网络适配器。 某些组合软件，可能需要将这些设置也应用于团队。 请注意，某些网络适配器自我调整，可能无法提供该选项来手动配置参数。  
  
- **电源选项**– 配置网络适配器驱动程序，以防止电源管理功能关闭网络适配器以节约电源。 此功能对于客户端计算机可能很有用，但应很少，如果曾经，在 BizTalk Server 或 SQL Server 计算机上使用。  
  
- **固定速度/双工 （不要使用 AUTO）** -它是非常重要的网络速度、 双工、 和流控制参数设置为对应于交换机上的设置它们所连接到。 这将缓解定期"自动同步"这可能暂时需要连接离线的匹配项。  
  
- **最大 Coalesce 缓冲区**-映射寄存器是用于将物理地址转换为适用于支持总线掌握的网络适配器的虚拟地址的系统资源。 Coalesce 缓冲区可供网络驱动程序如果驱动程序用尽了映射寄存器。 设置此尽可能最大性能的大值。 在服务器上物理内存有限，这可能会产生负面影响，因为合并缓冲区使用的系统内存。 在大多数系统上但是，最大值设置可以应用而不会显著降低可用内存。  
  
- **最大传输/发送描述符和发送缓冲区**-此设置指定多少传输控制缓冲区以供网络接口分配驱动程序。 这直接反映驱动程序可以在其"发送"队列中的未完成数据包数。 设置此尽可能最大性能的大值。 在服务器上物理内存有限，这可能会产生负面影响，作为发送缓冲区使用的系统内存。 在大多数系统上但是，最大值设置可以应用而不会显著降低可用内存。  
  
- **最大接收缓冲区**-此设置指定的网络接口驱动程序将数据复制到的协议内存时所使用的内存缓冲区量。 它通常默认情况下，为相对较低的值设置。 设置此尽可能最大性能的大值。 在服务器上物理内存有限，这可能会产生负面影响，如接收缓冲区使用的系统内存。 在大多数系统上但是，最大值设置可以应用而不会显著降低可用内存。  
  
- **所有上卸载选项**-在几乎所有情况下启用网络接口卸载功能时的性能得到改进。 某些网络适配器提供单独的参数来启用或禁用卸载用于发送和接收流量。 卸载任务从 CPU 卸载到网络适配器可以帮助降低 CPU 使用率将提高系统整体性能的服务器上。 Microsoft TCP/IP 传输可以卸载一个或多个到具有相应功能的网络适配器的以下任务：  
  
  -   **校验和任务**-TCP/IP 传输可以卸载在计算和验证的 IP 和 TCP 校验和的发送和接收到的网络适配器，如果网络适配器驱动程序提供了此功能，请启用此选项。  
  
  -   **IP 安全任务**-计算和的身份验证标头 (AH) 和封装安全有效负载 (ESP) 到网络适配器的加密校验和验证，可以将卸载 TCP/IP 传输。 加密和解密到网络适配器的 ESP 有效负载，还可以将卸载 TCP/IP 传输。 如果网络适配器驱动程序提供了此功能，请启用这些选项。  
  
  -   **大型 TCP 数据包分段**-TCP/IP 传输支持大量发送卸载 (LSO)。 此外，使用 TCP/IP 传输可以将卸载大型 TCP 数据包的分段。  
  
  -   **堆栈卸载**– 整个网络堆栈卸载到具有相应功能的网络适配器。 如果网络适配器驱动程序提供了此功能，请启用此选项。  
  
- **LAN 唤醒 （除非使用时） 禁用**– 配置网络适配器驱动程序，以禁用唤醒 on lan 功能。 此功能对于客户端计算机可能很有用，但应很少如果曾经使用 BizTalk Server 或 SQL Server 计算机上。  
  
  有关优化性能的网络适配器的详细信息，请参阅**网络设备设置**部分中的"BizTalk Server 数据库优化"白皮书，网址[ http://go.microsoft.com/fwlink/?LinkID=101578 ](http://go.microsoft.com/fwlink/?LinkID=101578)。