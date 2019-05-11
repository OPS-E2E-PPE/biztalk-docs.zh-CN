---
title: 测试结果：BizTalk Server 关键性能指标 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 902cdfc1-21ab-4f56-b97b-2f8979514b11
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2499a67156dff5c83be1103c89b94befe6424492
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400635"
---
# <a name="test-results-biztalk-server-key-performance-indicators"></a>测试结果：BizTalk Server 关键性能指标
本主题总结了 BizTalk Server 关键性能指标 (KPI) 的测试方案期间观察到。 具体而言，这些测试计算吞吐量由度量"**BizTalk： 消息传送/文档处理数/秒**"性能监视器计数器和滞后时间，由 Visual studio 客户端响应时间进行度量。  
  
## <a name="summary-of-biztalk-server-key-performance-indicators"></a>BizTalk Server 关键性能指标的摘要  
 对于每个方案的物理机是受限制，以便逻辑处理器和虚拟处理器的数目是等效。 执行此操作使用 /maxmem 和 /numproc boot.ini 开关。 有关使用这些开关的详细信息，请参阅"启动 INI 选项参考"网址[ http://go.microsoft.com/fwlink/?LinkId=122139 ](http://go.microsoft.com/fwlink/?LinkId=122139)。  
  
 **比较 BizTalk Server 关键性能指标-** 的 HYPER-V 虚拟机上运行 BizTalk Server 为此测试方案在物理硬件上提供约 95%的 BizTalk 服务器的吞吐量和延迟的性能。 由于无状态性质[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，其他 BizTalk Server 虚拟机可以轻松地添加到环境根据需要提供横向扩展并提高系统的整体性能。 可通过使用 sysprep 实用工具从基本映像生成新的映像创建并向环境添加其他 BizTalk Server。  
  
> [!NOTE]  
>  Sysprep 应答文件和脚本都是计算机的提供与 BizTalk Server 以便能够使用 sysprep 来创建更多映像具有的现有映像中安装 BizTalk Server。 这些示例脚本旨在用于向 BizTalk Server 安装在 32 位和 64 位版本的 Windows Server 2008 仅。 有关详细信息，请参阅 BizTalk Server 联机文档。  
  
 预配、 整合和管理的虚拟机服务，可以显著加快通过使用 System Center Virtual Machine Manager (VMM)。 有关 System Center Virtual Machine Manager 的详细信息，请参阅 [http://go.microsoft.com/fwlink/?LinkID=111303](http://go.microsoft.com/fwlink/?LinkID=111303)  
  
 在此性能实验室中获得的结果显示从实现运行时的性能显著的改进[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]上[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]的 HYPER-V 虚拟机中。 运行[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]上的 HYPER-V 虚拟机提供约 75%的吞吐量和延迟的性能[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]与物理硬件上运行 BizTalk Server 时，观察到约 95%的性能和[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]上的 HYPER-V 虚拟机。 这种性能提高是提高性能的很大程度上由引起[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]作为来宾操作系统的 HYPER-V 上运行时。 从相关的性能比较[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]HYPER-V 指南位于[ http://go.microsoft.com/fwlink/?LinkId=147144 ](http://go.microsoft.com/fwlink/?LinkId=147144)。  
  
 下图说明了各种测试平台上的 BizTalk Server 性能：  
  
 ![BizTalk 关键绩效指标](../technical-guides/media/biztalkkpi.gif "BizTAlkKPI")  
  
 下表说明了每个配置的收集 KPI 的相对性能。 每个结果集的计算的基线配置 KPI 的一个百分比。  
  
|KPI|虚拟 BizTalk/物理 SQL|在单独的主机的虚拟 BizTalk/虚拟 SQL|合并环境上的虚拟 BizTalk/虚拟 SQL|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|每秒处理 \BizTalk:Messaging\Documents|94.3%|79.8%|67%|  
|滞后时间，单位由 Visual Studio 客户端|94.3%|79.7%|66.9%|  
  
 有关如何优化 BizTalk Server 解决方案的性能的详细信息，请参阅 BizTalk Server 性能优化指南网址[ http://go.microsoft.com/fwlink/?LinkId=122477 ](http://go.microsoft.com/fwlink/?LinkId=122477)。  
  
## <a name="performance-comparison-results-summary"></a>性能比较结果摘要  
 94.3%吞吐量和 94.3%延迟来实现仅运行时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上的 HYPER-V 提供建议，虚拟化这一解决方案是使用 HYPER-V 的级别提供了预配、 合并、 灵活性和易用性以及卓越的性能管理后，可以将解决方案部署到 HYPER-V 环境。  
  
### <a name="throughput-comparison-sample-results"></a>吞吐量比较示例结果  
 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk Server 环境中使用的计算机上的 HYPER-V 虚拟机，BizTalk Server 解决方案由度量吞吐量运行"**BizTalk： 消息传送/文档处理数/秒**"范围是从 67%的吞吐量，可以利用它来 94.3%时在 BizTalk Server 环境中使用的计算机的所有已安装在物理硬件上性能监视器计数器。  
  
### <a name="latency-comparison-sample-results"></a>延迟比较示例结果  
 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 BizTalk Server 环境中使用的计算机运行的 HYPER-V 虚拟机上，BizTalk Server 解决方案由 Visual Studio 客户端响应度量的延迟时间范围是从 66.9%94.3%的可以利用它来延迟时所有在 BizTalk Server 环境中使用的计算机的已安装在物理硬件上。