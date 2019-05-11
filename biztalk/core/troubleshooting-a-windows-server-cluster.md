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
ms.openlocfilehash: 8c6c55660b886b1739326abef13e1dc5f2c829ff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243223"
---
# <a name="troubleshooting-a-windows-server-cluster"></a>Windows Server 群集进行疑难解答
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持 Windows Server 群集的主机群集支持，为企业单一登录 (SSO) 主密钥提供高可用性并提供高可用性使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 本主题提供有关使用一些通用准则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 Windows Server 群集环境，并讨论了一些使用时可能发生的已知的问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 Windows Server 群集环境中。  
  
## <a name="general-guidelines"></a>通用指导原则  
 请遵循以下常规准则，以最大限度地与 Windows Server 群集的工作效率和解决可能会影响的 Windows Server 群集问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
1. 完整[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]概念验证都适用于虚拟化的服务器环境中的 Windows Server 群集。  
  
    **包含在 Windows Server 2008 的 HYPER-V 角色可用于创建虚拟化的服务器环境。**  
  
   - 有关 Windows Server 2008 HYPER-V 的详细信息，请参阅"虚拟化和合并"网址[ http://go.microsoft.com/fwlink/?LinkID=121187 ](http://go.microsoft.com/fwlink/?LinkID=121187)。  
  
   - 为深入利用提供的 HYPER-V 虚拟化技术的优势的信息的详细信息，请参阅白皮书"高级虚拟化权益的 Windows Server 2008 Enterprise Edition 的"下载[http://go.microsoft.com/fwlink/?LinkId=123530](http://go.microsoft.com/fwlink/?LinkId=123530).  
  
   - 在提供了有关使用 HYPER-V 创建 Windows Server 2008 群集的步骤[ http://go.microsoft.com/fwlink/?LinkId=129680 ](http://go.microsoft.com/fwlink/?LinkId=129680)。  
  
     执行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]概念验证适用于虚拟化的服务器环境中的 Windows Server 群集可提供极大的灵活性，并且使用硬件的资源比所需的 Windows Server 群集的资源要少得多。 如果使用这种方法，则分配至少 512 MB 的内存的主机计算机并行运行每个虚拟机和额外的 512 MB 的内存的主机操作系统。 例如，对于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案与使用五个虚拟机 （两个 BizTalk Server 群集节点，两个 Microsoft SQL Server 群集节点和一个域控制器），你要计划 3 GB 的内存在主机上安装的 Windows Server 群集计算机。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]概念验证环境要求超过 2 GB 的内存，请考虑 （需要 HYPER-V 角色） 在主机计算机上安装 Windows 的 64 位版本，以确保所有已安装的内存可访问由主机操作系统。  
  
## <a name="troubleshooting-resources"></a>疑难解答资源  
 **用于排除 Windows Server 2008 故障转移群集的资源**  
  
-   审阅[故障转移群集验证和 Windows Server 2008 的故障排除](http://go.microsoft.com/fwlink/?LinkId=129729)Microsoft TechNet 网站上的 TechNet 网络广播。 此网络广播介绍了如何排查故障转移群集验证和 Windows Server 2008 故障排除。  
  
-   有关分析 Windows Server 2008 故障转移群集的问题的详细信息，请参阅主题[查看事件和故障转移群集的日志](http://go.microsoft.com/fwlink/?LinkId=129730)Microsoft TechNet 网站上。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="any-attempt-to-bring-a-clustered-msdtc-resource-online-fails-which-causes-dependent-biztalk-server-services-to-fail"></a>任何尝试将群集的 MSDTC 资源联机失败这会导致依赖 BizTalk Server 服务失败  
  
##### <a name="problem"></a>问题  
 群集的分布式事务处理协调器 (MSDTC) 资源无法联机**使联机**选项在群集管理器，这会导致[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]依赖于 MSDTC 的运行时操作失败的事务支持。  
  
##### <a name="cause"></a>原因  
 群集的 MSDTC 资源失败可能发生多个原因包括以下：  
  
-   群集的 MSDTC 资源未使用正确的磁盘配置和网络名称资源依赖关系或资源依赖关系失败。  
  
-   权限问题导致群集的 MSDTC 资源被激活。  
  
##### <a name="resolution"></a>解决方法  
 **完成 Windows Server 2008 群集上的以下步骤：**  
  
-   按照中的步骤[核对清单：在 Windows Server 2008 故障转移群集中创建 MS DTC 资源](http://go.microsoft.com/fwlink/?LinkId=129677)Windows Server 2008 故障转移群集上创建一个或多个群集的 MSDTC 资源。  
  
## <a name="see-also"></a>请参阅  
 [使用 Windows Server 群集为 BizTalk Server 主机 2 提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [聚类分析 BizTalk Server 数据库](../core/clustering-the-biztalk-server-databases1.md)   
 [BizTalk Server 高可用性示例方案](../core/sample-biztalk-server-high-availability-scenarios.md)   
 [高可用性 SSO 安装选项](../core/high-availability-sso-installation-options.md)