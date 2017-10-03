---
title: "将 BizTalk Server 解决方案部署到 Hyper V 的潜在的好处虚拟化环境 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 588c70f0-68f0-4e58-8f3d-aa6834397bd4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9602a48b0deb4eeddc6f10b2d529d68d94cc781a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="potential-benefits-of-deploying-a-biztalk-server-solution-to-a-hyper-v-virtualized-environment"></a>将 BizTalk Server 解决方案部署到 Hyper V 的潜在的好处虚拟化环境
本主题介绍一些部署的益处你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 HYPER-V 虚拟化环境的解决方案。  
  
## <a name="benefits-of-running-a-biztalk-server-solution-on-a-hyper-v-virtualized-environment"></a>HYPER-V 上运行 BizTalk Server 解决方案的优点虚拟化环境  
 部署在 HYPER-V 虚拟化环境中运行你的 BizTalk Server 解决方案可提供以下的灵活性和功能：  
  
-   **能够在一台物理计算机-定义多个不同的逻辑安全边界**HYPER-V 还包含创建不同的逻辑安全边界或在单个物理硬件资源的分区。 分区是隔离的单个逻辑单元的虚拟机监控程序，执行操作系统的支持。 例如，可以创建多个 BizTalk Server 组，而不将可以在安装时执行此操作，在一台 HYPER-V 主机计算机上运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在主机操作系统的单个主机计算机上。  
  
-   **易于部署和管理 –**的合并[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]划分为较少的物理服务器的计算机上可以简化部署。 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]通过使用.vhd 文件，对物理和虚拟计算机部署中使用简化的方法。 此外，全面的 HYPER-V 管理解决方案为与 System Center Virtual Machine Manager 中可用。 有关 System Center Virtual Machine Manager 的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkID=111303](http://go.microsoft.com/fwlink/?LinkID=111303)。  
  
-   **错误容差支持通过 HYPER-V 群集-**因为 HYPER-V 群集感知应用程序，Windows Server 2008 提供了本机主机群集在 HYPER-V 虚拟化环境中创建的虚拟机的支持。  
  
-   **横向扩展的易用性**额外的处理能力、 网络带宽和存储容量可以容纳有关你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案快速、 轻松地通过分派到来宾从主计算机的其他可用资源虚拟机。 这可能需要升级主机或来宾虚拟机在移动到功能更强大的主机计算机。 实时迁移功能[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]让你移动正在运行到最佳的物理计算机的性能、 缩放或最佳合并而不会影响用户的 Vm。  
  
-   **硬件资源-合并**多个物理服务器可轻松地合并到相对较少服务器通过实现与 HYPER-V 虚拟化。 合并能够适应充分利用已部署的硬件资源。  
  
 若要了解更多详细信息的功能和优势 HYPER-V 提供，请参阅[与 HYPER-V 虚拟化](http://go.microsoft.com/fwlink/?LinkID=202438)。