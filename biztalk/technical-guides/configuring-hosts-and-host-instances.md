---
title: 配置主机和主机实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a36a73a4-cc5f-47d6-b56f-7871684c4489
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 286bdaaff66cf0b85caa3bb169bb506501ff386f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968998"
---
# <a name="configuring-hosts-and-host-instances"></a>配置主机和主机实例
BizTalk 主机表示的零个或多个运行时进程在其中可以部署一组逻辑[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务和项目 （例如适配器处理程序接收位置和业务流程）。 主机实例是运行的计算机上的主机的物理实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 有关 BizTalk 主机和主机实例的详细信息，请参阅[主机](http://go.microsoft.com/fwlink/?LinkId=154189)(<http://go.microsoft.com/fwlink/?LinkId=154189>) 和[主机实例](http://go.microsoft.com/fwlink/?LinkId=154190)(<http://go.microsoft.com/fwlink/?LinkId=154190>)。  
  
 有关管理 BizTalk 主机和主机实例的详细信息，请参阅[管理 BizTalk 主机和主机实例](http://go.microsoft.com/fwlink/?LinkId=154191)(http://go.microsoft.com/fwlink/?LinkId=154191)。  
  
 有关如何配置专用的跟踪主机的信息，请参阅[配置专用跟踪主机](../technical-guides/configuring-a-dedicated-tracking-host.md)。  
  
## <a name="separating-host-instances-by-functionality"></a>分隔主机实例的功能  
 除了主机实例配置的高可用性方面，您应单独的发送、 接收、 处理和跟踪到多个主机的功能。 这提供了灵活性，在你的 BizTalk 组中配置工作负荷时，将处理分散 BizTalk 组的主要方式。 这还允许您停止一个主机，而不会影响其他主机。 例如，可能想要停止发送消息，以让他们队列在 MessageBox 数据库中，同时仍允许入站的接收的消息出现。  
  
 主机实例分隔功能还提供以下优势：  
  
- 每个主机实例中的.NET 线程池具有其自己的内存、 句柄和线程等资源集。  
  
- 由于每个主机分配的 MessageBox 数据库中其自己的工作队列表，多个 BizTalk 主机还会减少 MessageBox 数据库主机队列表上的争用。  
  
- 限制中实现[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机级别。 这允许您设置的每个主机的不同限制的特征。  
  
- 在主机级别，则实现安全每个主机在离散的 Windows 标识下运行。 这将允许您，例如，若要为提供**Host_A**访问权限**FileShare_B**，同时不允许任何其他主机访问文件共享。  
  
  > [!NOTE]  
  >  虽然有与创建其他主机实例的优点，也有潜在的缺点如果创建了太多主机实例。 每个主机实例是一个 Windows 服务 （BTSNTSvc.exe 或 BTSNTSvc64.exe），它可生成针对 MessageBox 数据库的更多负载，会占用计算机资源 （如 CPU、 内存、 线程)。  
  
  有关修改的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机属性，请参阅[如何修改主机属性](http://go.microsoft.com/fwlink/?LinkId=154192)(<http://go.microsoft.com/fwlink/?LinkId=154192>)。  
  
##  <a name="BKMK_MemLimit"></a> 32 位 BizTalk 主机实例的内存使用率的最大实际限制  
 使用 3 GB，集的 32 位 Windows 操作系统上的 32 位进程具有 3 个千兆字节 (GB) 的可寻址内存，如果过程"大地址注意"（即，可执行文件有映像标头中设置的 IMAGE_FILE_LARGE_ADDRESS_AWARE 标志）。  BizTalk 主机进程中，在"识别大地址"，可以寻址 3 GB 的内存使用 3 GB，组的 Windows 操作系统上。  同样，在 64 位 Windows 操作系统 (AMD64) 上的 32 位进程具有 4GB 可寻址内存，如果进程"注意大地址"。  同样，BizTalk 主机进程中，"注意大地址"，可以解决 4 GB 的内存在 64 位 Windows 操作系统上作为 32 位进程运行时。 在 64 位 Windows 操作系统 (AMD64) 上的 64 位进程具有 8tb 的可寻址内存。  
  
 即使可寻址的 32 位 Windows 操作系统 （不带 /3GB 开关） 上的进程的最大内存是 2 GB，也是如此 （如 BizTalk 主机实例） 的.NET 应用程序将收到内存不足错误之前的"虚拟字节"达到 2 GB。 下表概述了这些不同，并包括虚拟字节和专用字节为单位的实际限制。  
  
|处理|Windows OS|（使用一个大型地址识别的过程） 的可寻址内存|虚拟字节、 可行限制|PrivateBytes、 可行限制|  
|-------------|----------------|---------------------------------------------------------------|---------------------------------------|--------------------------------------|  
|32 位|32 位|2 GB|1400 MB|800 MB|  
|32 位|使用 3 GB 的 32 位|3 GB|2400 MB|1800 MB|  
|32 位|64 位|4 GB|3400 MB|2800 MB|  
|64 位|64 位|8 千吉字节|-|-|  
  
 有关详细信息，请参阅：  
  
-   [ASP.NET 性能监视及何时更换管理员](http://go.microsoft.com/fwlink/?LinkId=151856)(http://go.microsoft.com/fwlink/?LinkId=151856)  
  
-   [Windows 版本的内存限制](http://go.microsoft.com/fwlink/?LinkId=151857)(http://go.microsoft.com/fwlink/?LinkId=151857)  
  
## <a name="see-also"></a>请参阅  
 [清单： 配置 BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)   
 [配置专用跟踪主机](../technical-guides/configuring-a-dedicated-tracking-host.md)