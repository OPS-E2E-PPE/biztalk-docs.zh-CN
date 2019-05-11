---
title: 潜在优势将 BizTalk Server 解决方案部署到 HYPER-V 虚拟化环境 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 588c70f0-68f0-4e58-8f3d-aa6834397bd4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38ae71a171cfe992551c8167361e0536140488bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401279"
---
# <a name="potential-benefits-of-deploying-a-biztalk-server-solution-to-a-hyper-v-virtualized-environment"></a>潜在优势将 BizTalk Server 解决方案部署到 HYPER-V 虚拟化环境
本主题介绍了一些部署的优势在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 HYPER-V 虚拟化环境的解决方案。  
  
## <a name="benefits-of-running-a-biztalk-server-solution-on-a-hyper-v-virtualized-environment"></a>虚拟环境中运行 Hyper V 上的 BizTalk Server 解决方案的好处  
 部署 BizTalk Server 解决方案以在 HYPER-V 虚拟化环境中运行可提供以下大的灵活性和功能：  
  
- **能够在一台物理计算机-定义多个非重复逻辑安全边界**的 HYPER-V 可容纳的非重复逻辑安全边界或在单个物理硬件资源内的分区创建。 分区是隔离的单个逻辑单元的虚拟机监控程序，在其中执行操作系统支持。 例如，可以创建多个 BizTalk Server 组，而您将不能执行此操作时安装一台 HYPER-V 主机计算机上运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]单个主机计算机的主机操作系统上。  
  
- **易于部署和管理-** 合并[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以简化部署过程划分为较少的物理服务器的计算机。 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 通过使用.vhd 文件的物理和虚拟计算机部署来使用简化的方法。 此外，全面的 HYPER-V 管理解决方案是使用 System Center Virtual Machine Manager 中可用。 有关 System Center Virtual Machine Manager 的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkID=111303 ](http://go.microsoft.com/fwlink/?LinkID=111303)。  
  
- **错误通过 HYPER-V 群集-支持**因为 HYPER-V 是群集感知应用程序、 Windows Server 2008 提供了本机主机群集的 HYPER-V 虚拟化环境中创建的虚拟机的支持。  
  
- **横向扩展的易用**额外的处理能力、 网络带宽和存储容量可以容纳的你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案快速、 轻松地通过分派到来宾从主计算机的其他可用资源虚拟机。 这可能需要升级主计算机或来宾虚拟机在移动到功能更强大的主机计算机。 实时迁移功能[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]允许你将转移到最佳的物理计算机的性能、 缩放或最佳合并运行 Vm，而不会影响用户。  
  
- **合并的硬件资源-** 多个物理服务器可以轻松地整合到相对较少的服务器通过实现使用的 HYPER-V 虚拟化。 合并适合于已部署的硬件资源利用。  
  
  若要找出更多详细信息的功能和优势的 HYPER-V 提供了，请参阅[使用的 HYPER-V 虚拟化](http://go.microsoft.com/fwlink/?LinkID=202438)。