---
title: "清单： 执行每月的维护检查 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 588b74fa-6bf5-43ad-aa15-3595adde76d1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35b7b3aa9a9d6dfcea7dfc40f740defdeff2d45f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-performing-monthly-maintenance-checks"></a>清单： 执行每月的维护检查
本主题介绍在执行每月的可靠性、 管理、 安全性和性能的维护检查所涉及的步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。  
  
|步骤|参考|  
|-----------|---------------|  
|请确保主密钥进行备份运行并随时可供脱机存储 （可靠性检查）。|[如何备份主密钥](http://go.microsoft.com/fwlink/?LinkId=151395)(http://go.microsoft.com/fwlink/?LinkId=151395)。|  
|确保所有群集的服务已故障转移测试 （可靠性检查）。|[查看和测试 SQL Server 群集配置故障转移方案](../technical-guides/reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios.md)测试组故障转移|  
|确保企业 SSO 服务已群集化 （可靠性检查）。|[群集主密钥服务器](../technical-guides/clustering-the-master-secret-server.md)|  
|确保在 SQL Server 服务 （可靠性检查） 下，BizTalk Server 数据库组成了群集。|[群集 BizTalk Server Databases2](../technical-guides/clustering-the-biztalk-server-databases2.md)|  
|确保至少两个物理 BizTalk 服务器属于 BizTalk 组 （可靠性检查）。|[确保多个服务器是 BizTalk 组的一部分](../technical-guides/maintaining-reliability.md#BKMK_BTSGrp)|  
|确定是否正在使用任何不稳定的代码，如果是，使用单独的主机 （可靠性检查）。|[BizTalk 主机的高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)|  
|执行所有新 BizTalk 应用程序 （可靠性检查） 的功能测试。|-   [测试应用程序](../technical-guides/testing-an-application.md)<br />-   [BizTalk 应用程序部署的暂存任务](http://go.microsoft.com/fwlink/?LinkId=154686)(http://go.microsoft.com/fwlink/?LinkId=154686)。|  
|配置和计划备份的 BizTalk Server 作业 （可靠性检查）。|-   [如何配置备份 BizTalk Server 作业](http://go.microsoft.com/fwlink/?LinkID=153813)(http://go.microsoft.com/fwlink/?LinkID=153813)<br />-   [如何安排备份 BizTalk Server 作业](http://go.microsoft.com/fwlink/?LinkId=154674)(http://go.microsoft.com/fwlink/?LinkId=154674)|  
|确保每个 BizTalk 机 （完整性检查） 上安装了一组程序集的正确版本。|使用**BizTalk 程序集检查和远程 GAC**工具 (BTSAssemblyChecker.exe) 来检查程序集部署到 BizTalk 管理数据库的版本，并以验证它们是否正确注册所有上的GAC中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。 此工具可用于验证包含某些 BizTalk 应用程序的项目的所有程序集安装在所有 BizTalk 节点。 该工具是结合稳定版本控制策略以验证一组程序集的正确版本上安装了每个 BizTalk 机，尤其是使用通过并行部署方法时特别有用。 该工具，同时提供[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]安装介质上 Support\Tools\x86\BTSAssemblyChecker.exe。|  
|确定是否有任何不必要的 BizTalk 应用程序、 项目和配置 （管理检查）。|-删除所有不必要 BizTalk 应用程序、 项目和配置。<br />-删除 BizTalk 应用程序或项目详细信息使用 BTSTask 命令行工具请参见[RemoveApp 命令](http://go.microsoft.com/fwlink/?LinkId=154687)(http://go.microsoft.com/fwlink/?LinkId=154687)。<br />-从使用 BizTalk Server 管理控制台或 BTSTask 命令行工具的应用程序中删除项目的详细信息，请参见[如何从应用程序中删除项目](http://go.microsoft.com/fwlink/?LinkId=154688)(http://go.microsoft.com/fwlink/？LinkId = 154688)。|  
|检查 BizTalk Server 管理控制台的任何未经批准的更改 （管理检查）。|[使用 BizTalk Server 管理控制台](http://go.microsoft.com/fwlink/?LinkId=154689)(http://go.microsoft.com/fwlink/?LinkId=154689)。|  
|检查 BTSNTSvc.exe.config 的任何未经批准的修改 （管理检查）。|[BTSNTSvc.exe.config 文件](http://go.microsoft.com/fwlink/?LinkId=154690)(http://go.microsoft.com/fwlink/?LinkId=154690)。|  
|检查任何未经批准的修改 （管理检查） 的 BizTalk Server 相关的注册表项。|Microsoft 知识库文章 256986，["Windows 高级用户的注册表信息"](http://go.microsoft.com/fwlink/?LinkId=158859) (http://go.microsoft.com/fwlink/?LinkId=158859)。|  
|运行最佳做法分析器 BizTalk 服务器 （管理检查）。|[BizTalk Server 最佳做法分析器](http://go.microsoft.com/fwlink/?LinkId=83317)(http://go.microsoft.com/fwlink/?LinkId=83317)。|  
|确保安装最新 service pack 和更新程序 （管理和安全检查）。|[Microsoft Update](http://go.microsoft.com/fwlink/?LinkId=154691) (http://go.microsoft.com/fwlink/?LinkId=154691)。|  
|确保不同贸易合作伙伴的项目不会安装在相同的主机 （安全检查）。|[配置主机和主机实例](../technical-guides/configuring-hosts-and-host-instances.md)|  
|确保仅域级别的用户和组 （安全检查），使用 BizTalk Server。|[域组](http://go.microsoft.com/fwlink/?LinkId=154692)(http://go.microsoft.com/fwlink/?LinkId=154692)。|  
|请确保启用了 MSDTC 安全配置 （安全检查）。|请遵循的"设置 Windows Server 2003 SP1、 Windows XP SP2、 Windows Server 2008 和 Windows Vista 上适当的 MSDTC 安全配置选项"部分中的准则[问题疑难解答与 MSDTC](http://go.microsoft.com/fwlink/?LinkId=154693) (http://go.microsoft.com/fwlink/？LinkId = 154693)。|  
|确定是否需要将 BizTalk Server 缓存刷新间隔增加 （性能检查）。|[如何调整配置缓存刷新间隔](../technical-guides/how-to-adjust-the-configuration-cache-refresh-interval.md)|  
|确定是否需要是每个主机的限制选项调整 （性能检查）。|-有关限制的入站和出站主机的信息，请参见[主机限制是什么？](http://go.microsoft.com/fwlink/?LinkId=154694) (http://go.microsoft.com/fwlink/?LinkId=154694)。<br />-触发器、 操作和入站和出站带宽限制的缓解策略有关的信息，请参见"限制条件触发器、 操作和缓解策略"部分[如何 BizTalk 服务器实现主机的限制](http://go.microsoft.com/fwlink/?LinkId=154695) (http://go.microsoft.com/fwlink/?LinkId=154695)。|  
|确定是否启用不必要的跟踪，如业务流程、 形状和业务规则引擎 (BRE) 事件跟踪 （性能检查）。|-   [如何禁用跟踪](../technical-guides/how-to-disable-tracking.md)<br />-   [规划对其进行跟踪](../technical-guides/planning-for-tracking.md)<br />-   [跟踪的最佳实践](../technical-guides/planning-for-tracking.md#BKMK_TrackingBP)|  
|确定您是否正在跟踪维护 （性能检查） 使用的专用的主机。|[配置专用的跟踪主机](../technical-guides/configuring-a-dedicated-tracking-host.md)|  
|检查上升趋势 （性能检查） 的 BizTalk Server 数据库大小。|-有关大小调整跟踪数据库详细信息，请参见[跟踪数据库大小调整准则](http://go.microsoft.com/fwlink/?LinkId=154677)(http://go.microsoft.com/fwlink/?LinkId=154677)。<br />-有关调整大小的 MessageBox，BizTalkDTADb、 BAMPrimaryImport 数据库的详细信息，请参阅[标识数据库层中的瓶颈](http://go.microsoft.com/fwlink/?LinkId=154678)(http://go.microsoft.com/fwlink/?LinkId=154678)。|  
  
## <a name="see-also"></a>另请参阅  
 [日常维护清单](../technical-guides/routine-maintenance-checklists.md)