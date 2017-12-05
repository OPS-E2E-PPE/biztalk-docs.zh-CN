---
title: "测试结果： BizTalk Server 关键绩效指标 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 902cdfc1-21ab-4f56-b97b-2f8979514b11
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab682b0d773a613e6dfcdf143ef0afbeb5af48fa
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="test-results-biztalk-server-key-performance-indicators"></a>测试结果： BizTalk Server 关键绩效指标
本主题总结了 BizTalk Server 关键绩效指标 (KPI) 测试方案期间观察到。 具体而言，这些测试评估吞吐量测量"**BizTalk： 消息传送/文档处理数/秒**"性能监视器计数器和滞后时间，由 Visual studio 客户端响应时间度量。  
  
## <a name="summary-of-biztalk-server-key-performance-indicators"></a>BizTalk Server 关键绩效指标的摘要  
 每个方案的物理机被限制，以便已等效的逻辑处理器和虚拟处理器数。 执行此操作使用 /maxmem 和 /numproc boot.ini 开关。 有关使用这些开关的详细信息，请参阅"启动 INI 选项参考"在[http://go.microsoft.com/fwlink/?LinkId=122139](http://go.microsoft.com/fwlink/?LinkId=122139)。  
  
 **比较 BizTalk Server 关键绩效指标 –** HYPER-V 虚拟机上运行 BizTalk Server 提供在物理硬件上为此测试方案的大约 95%的 BizTalk Server 的吞吐量和延迟性能。 无状态性质，因此[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，其他 BizTalk Server 虚拟机可轻松添加到环境需要提供向外的扩展，并提高系统的整体性能。 可以通过使用 sysprep 实用工具从基本映像生成新的映像完成创建并将其他 BizTalk Server 添加到环境。  
  
> [!NOTE]  
>  Sysprep 应答文件和脚本不提供与 BizTalk Server 以容纳使用 sysprep 从现有的计算机的映像创建其他映像安装 BizTalk Server。 这些示例脚本被旨在与安装在 32 位和 64 位版本的 Windows Server 2008 上的 BizTalk Server 一起使用。 有关详细信息请参阅 BizTalk Server 联机文档。  
  
 设置、 整合和管理的虚拟机可以显著加快通过使用 System Center Virtual Machine Manager (VMM)。 有关 System Center Virtual Machine Manager 的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkID=111303](http://go.microsoft.com/fwlink/?LinkID=111303)  
  
 在此性能实验室中获得的结果显示从实现运行时的性能显著的改进[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]上[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]HYPER-V 虚拟机中。 运行[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]HYPER-V 上虚拟机提供大约为 75%的吞吐量和延迟性能[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]与物理硬件上运行 BizTalk Server 时，观察到大约 95%的性能和[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]在 HYPER-V 虚拟机。 这种性能提高是很大程度上是由引起的性能提高[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]时作为来宾操作系统在 HYPER-V 上运行。 从相关的性能比较[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]HYPER-V 指南位于[http://go.microsoft.com/fwlink/?LinkId=147144](http://go.microsoft.com/fwlink/?LinkId=147144)。  
  
 下图阐释了在不同的测试平台上的 BizTalk Server 性能：  
  
 ![BizTalk 关键绩效指标](../technical-guides/media/biztalkkpi.gif "BizTAlkKPI")  
  
 下表说明了每个配置的收集 KPI 的相对性能。 每个结果集是按百分比计算的基线配置 KPI。  
  
|KPI|虚拟 BizTalk/物理 SQL|在单独的主机的虚拟 BizTalk/虚拟 SQL|合并环境上的虚拟 BizTalk/虚拟 SQL|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|处理的 \BizTalk:Messaging\Documents 数/秒|94.3%|79.8%|67%|  
|滞后时间为单位，由 Visual Studio 客户端|94.3%|79.7%|66.9%|  
  
 有关如何优化 BizTalk Server 解决方案的性能的详细信息，请参阅 BizTalk Server 性能优化指南在[http://go.microsoft.com/fwlink/?LinkId=122477](http://go.microsoft.com/fwlink/?LinkId=122477)。  
  
## <a name="performance-comparison-results-summary"></a>性能比较结果摘要  
 94.3%吞吐量和实现仅运行时的 94.3%延迟[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 上提供的建议，虚拟化解决方案使用 HYPER-V 此层提供了出色的性能，以及设置、 合并、 灵活性和易用性管理，还可能将解决方案部署到 HYPER-V 环境。  
  
### <a name="throughput-comparison-sample-results"></a>吞吐量比较示例结果  
 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 BizTalk Server 环境中使用的计算机在 HYPER-V 虚拟机，BizTalk Server 解决方案测量吞吐量上运行"**BizTalk： 消息传送/文档处理数/秒**"范围是 67%到 94.3%可达成的吞吐量的 BizTalk Server 环境中使用的计算机的所有安装在物理硬件上时的性能监视器计数器。  
  
### <a name="latency-comparison-sample-results"></a>延迟比较示例结果  
 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 BizTalk Server 环境中使用的计算机已 HYPER-V 虚拟机上运行，BizTalk Server 解决方案由 Visual Studio 客户端响应度量的延迟时间范围是从 66.9%到的延迟可达成 94.3%时所有在 BizTalk Server 环境中使用的计算机的已安装在物理硬件上。