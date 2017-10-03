---
title: "配置主机和主机实例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a36a73a4-cc5f-47d6-b56f-7871684c4489
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55dda06d447d9e27c7c8b491986b499003c0bb73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-hosts-and-host-instances"></a>配置主机和主机实例
BizTalk 主机表示的零个或多个运行时进程，在其中你可以将部署的逻辑组[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务和项目 （如适配器处理程序接收位置和业务流程）。 主机实例是运行的计算机上的主机的物理实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 有关 BizTalk 主机和主机实例的详细信息，请参阅[主机](http://go.microsoft.com/fwlink/?LinkId=154189)(http://go.microsoft.com/fwlink/?LinkId=154189) 和[主机实例](http://go.microsoft.com/fwlink/?LinkId=154190)(http://go.microsoft.com/fwlink/?LinkId=154190)。  
  
 有关管理 BizTalk 主机和主机实例的详细信息，请参阅[管理 BizTalk 主机和主机实例](http://go.microsoft.com/fwlink/?LinkId=154191)(http://go.microsoft.com/fwlink/?LinkId=154191)。  
  
 有关如何配置专用的跟踪主机的信息，请参阅[配置专用的跟踪主机](../technical-guides/configuring-a-dedicated-tracking-host.md)。  
  
## <a name="separating-host-instances-by-functionality"></a>分隔按功能的主机实例  
 除了主机实例配置的高可用性方面，你应该将发送、 接收、 处理和跟踪到多个主机的功能。 这提供了灵活性，在你的 BizTalk 组中配置工作负荷时，将处理分散 BizTalk 组的主要方式。 这还允许您停止一台主机，而不影响其他主机。 例如，你可能想要停止发送消息，告知对方队列在 MessageBox 数据库中，同时仍允许入站的接收的消息发生。  
  
 将主机实例分离的功能还提供以下好处：  
  
-   每个主机实例中.NET 线程池具有其自己的内存、 句柄和线程等资源集。  
  
-   多个 BizTalk 主机也将减少 MessageBox 数据库主机队列表上的争用，因为每个主机分配其自己的 MessageBox 数据库中的工作队列表。  
  
-   限制中实现[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机级别。 这可以为每个主机设置不同的限制特征。  
  
-   在主机级别; 实现安全性每个主机将离散的 Windows 标识下运行。 这将允许您，例如，以便**Host_A**访问**FileShare_B**，同时不允许任何其他主机，以访问文件共享。  
  
    > [!NOTE]  
    >  尽管为创建额外的主机实例带来的好处，还有潜在缺点如果创建过多的主机实例。 每个主机实例是一个 Windows 服务 （BTSNTSvc.exe 或 BTSNTSvc64.exe），它生成额外的负载，针对 MessageBox 数据库，并会占用计算机资源 （如 CPU、 内存、 线程)。  
  
 有关修改[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机属性，请参阅[如何修改主机属性](http://go.microsoft.com/fwlink/?LinkId=154192)(http://go.microsoft.com/fwlink/?LinkId=154192)。  
  
##  <a name="BKMK_MemLimit"></a>最大的实际的 32 位 BizTalk 主机实例的内存使用量限制  
 在使用 3 GB 集的 32 位 Windows 操作系统上的 32 位进程具有 3 千兆字节 (GB) 的可寻址的内存，如果进程"大的地址感知"（即，可执行文件具有映像标头中设置的 IMAGE_FILE_LARGE_ADDRESS_AWARE 标志）。  BizTalk 主机过程中，"感知大地址"，可以处理 3 GB 的内存使用 3 GB 组的 Windows 操作系统上。  同样，在 64 位 Windows 操作系统 (AMD64) 上的 32 位进程具有 4 GB 的内存，如果进程"大的地址感知"。  同样，BizTalk 主机过程中，"感知大地址"，可以解决 4 GB 的内存在 64 位 Windows 操作系统上作为 32 位进程运行时。 在 64 位 Windows 操作系统 (AMD64) 上的 64 位进程具有 8 千吉字节的可寻址的内存。  
  
 即使可寻址 （不带 /3GB 开关） 32 位 Windows 操作系统上某个进程的最大内存是 2 GB，在"虚拟字节"到达 2 GB 之前将收到的.NET 应用程序 （例如 BizTalk 主机实例），内存不足错误。 下表概述了这些不同，并包括虚拟字节和专用字节的实际限制。  
  
|处理|Windows 操作系统|（使用大型地址感知进程） 的可寻址内存|虚拟字节、 可行限制|PrivateBytes、 可行限制|  
|-------------|----------------|---------------------------------------------------------------|---------------------------------------|--------------------------------------|  
|32 位|32 位|2 GB|1400 MB|800 MB|  
|32 位|32 位有 3 GB|3 GB|2400 MB|1800 MB|  
|32 位|64 位|4 GB|3400 MB|2800 MB|  
|64 位|64 位|8 千吉字节|-|-|  
  
 有关详细信息，请参阅：  
  
-   [ASP.NET 性能监视，以及何时向管理员发出警报](http://go.microsoft.com/fwlink/?LinkId=151856)(http://go.microsoft.com/fwlink/?LinkId=151856)  
  
-   [Windows 版本的内存限制](http://go.microsoft.com/fwlink/?LinkId=151857)(http://go.microsoft.com/fwlink/?LinkId=151857)  
  
## <a name="see-also"></a>另请参阅  
 [清单： 配置 BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)   
 [配置专用的跟踪主机](../technical-guides/configuring-a-dedicated-tracking-host.md)