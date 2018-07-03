---
title: Windows Server 群集进行疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 283cf4cd-ce40-48b7-8549-9ab17d7d2c34
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f9143fe9abc8ff5ce103a7ae90978e60e4d6813
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002150"
---
# <a name="troubleshooting-a-windows-server-cluster"></a>Windows Server 群集进行疑难解答
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持 Windows Server 群集的主机群集支持，为企业单一登录 (SSO) 主密钥提供高可用性并提供高可用性使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 本主题提供有关使用一些通用准则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 Windows Server 群集环境，并讨论了一些使用时可能发生的已知的问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 Windows Server 群集环境中。  
  
## <a name="general-guidelines"></a>通用指导原则  
 按照下述通用准则执行可以最大限度地提高 Windows Server 群集的使用效率，以及排除可能影响 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的 Windows Server 群集问题。  
  
1. 全部 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 概念验证都适用于虚拟化服务器环境中的 Windows Server 群集。  
  
    **包含在 Windows Server 2008 的 HYPER-V 角色可用于创建虚拟化的服务器环境。**  
  
   - 有关 Windows Server 2008 HYPER-V 的详细信息，请参阅"虚拟化和合并"网址[ http://go.microsoft.com/fwlink/?LinkID=121187 ](http://go.microsoft.com/fwlink/?LinkID=121187)。  
  
   - 为深入利用提供的 HYPER-V 虚拟化技术的优势的信息的详细信息，请参阅白皮书"高级虚拟化权益的 Windows Server 2008 Enterprise Edition 的"下载[http://go.microsoft.com/fwlink/?LinkId=123530](http://go.microsoft.com/fwlink/?LinkId=123530).  
  
   - 在提供了有关使用 HYPER-V 创建 Windows Server 2008 群集的步骤[ http://go.microsoft.com/fwlink/?LinkId=129680 ](http://go.microsoft.com/fwlink/?LinkId=129680)。  
  
     通过使 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 概念验证适用于虚拟服务器环境中的 Windows Server 群集，可提供很高的灵活性，并且使用的硬件资源要比 Windows Server 少很多。 如果采用此方法，则要为在主机上并行运行的每台虚拟机分配至少 512 MB 的内存，并且还要为主机操作系统再分配 512 MB 的内存。 例如，对于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案与使用五个虚拟机 （两个 BizTalk Server 群集节点，两个 Microsoft SQL Server 群集节点和一个域控制器），你要计划 3 GB 的内存在主机上安装的 Windows Server 群集计算机。 如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 概念验证环境要求超过 2 GB 的内存，请考虑在主机上安装 64 位版本的 Windows（需要 Hyper-V 角色），以确保主机的操作系统可访问所有已安装的内存。  
  
## <a name="troubleshooting-resources"></a>故障排除资源  
 **用于排除 Windows Server 2008 故障转移群集的资源**  
  
-   审阅[故障转移群集验证和 Windows Server 2008 的故障排除](http://go.microsoft.com/fwlink/?LinkId=129729)Microsoft TechNet 网站上的 TechNet 网络广播。 此网络广播介绍了如何对故障转移群集验证进行疑难解答，以及 Windows Server 2008 问题的疑难解答。  
  
-   有关分析 Windows Server 2008 故障转移群集的问题的详细信息，请参阅主题[查看事件和故障转移群集的日志](http://go.microsoft.com/fwlink/?LinkId=129730)Microsoft TechNet 网站上。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="any-attempt-to-bring-a-clustered-msdtc-resource-online-fails-which-causes-dependent-biztalk-server-services-to-fail"></a>使群集的 MSDTC 资源联机的任何尝试失败，这导致相关的 BizTalk Server 服务失败  
  
##### <a name="problem"></a>问题  
 群集的分布式事务处理协调器 (MSDTC) 资源无法联机**使联机**选项在群集管理器，这会导致[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]依赖于 MSDTC 的运行时操作失败的事务支持。  
  
##### <a name="cause"></a>原因  
 很多原因都可能导致群集的 MSDTC 资源失败，这些原因包括：  
  
-   没有使用正确的磁盘和网络名称资源依赖项配置群集的 MSDTC 资源，或者资源依赖项有问题。  
  
-   权限问题将使群集的 MSDTC 资源不能被激活。  
  
##### <a name="resolution"></a>解决方法  
 **完成 Windows Server 2008 群集上的以下步骤：**  
  
-   按照中的步骤[清单： 在 Windows Server 2008 故障转移群集中创建 MS DTC 资源](http://go.microsoft.com/fwlink/?LinkId=129677)Windows Server 2008 故障转移群集上创建一个或多个群集的 MSDTC 资源。  
  
## <a name="see-also"></a>请参阅  
 [使用 Windows Server 群集为 BizTalk Server 主机 2 提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [聚类分析 BizTalk Server 数据库](../core/clustering-the-biztalk-server-databases1.md)   
 [BizTalk Server 高可用性示例方案](../core/sample-biztalk-server-high-availability-scenarios.md)   
 [高可用性 SSO 安装选项](../core/high-availability-sso-installation-options.md)