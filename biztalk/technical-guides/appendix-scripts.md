---
title: 附录： 脚本 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6394321-13c9-4b1d-b529-eba3d53b33c4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12df00876f6b2da9ebb98631016bd42947b4a40a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299909"
---
# <a name="appendix-scripts"></a>附录： 脚本
此管理包中包括以下脚本。  
  
|脚本|用途|  
|------------|-------------|  
|Microsoft.BizTalk.Server.2013.ArtifactsDiscovery.vbs|此脚本发现应用程序项目基于 $Config 选项 $ 参数。 选项包括<br /><br /> -All 发送端口，将端口组应用程序，其托管关系中发送到应用程序和发送端口组包含发送端口的关系。<br />-所有业务流程的应用程序，应用程序到其托管关系。<br />-All 接收端口，则接收应用程序，其托管关系中的位置的应用程序和接收端口包含接收位置关系。|  
|Microsoft.BizTalk.Server.2013.ApplicationDiscovery.vbs|此脚本发现以下各项：<br /><br /> 的在组和组主机应用程序关系所有应用程序。<br />的在组和组主机主机关系中所有主机。|  
|Microsoft.BizTalk.Server.2013.BAMAnalysisDiscovery.vbs|此脚本发现 BAM 分析，并提醒其中发现 BAM 运行时组件的计算机上的组件。|  
|Microsoft.BizTalk.Server.2013.BAMPortalDiscovery.vbs|此脚本发现 BAM 门户上的计算机的 IIS 配置。 这还发现 BAM 角色和 BAM 门户中它的包含关系。|  
|Microsoft.BizTalk.Server.2013.BAMRuntimeDiscovery.vbs|此脚本发现 BAM 作为参数 $Config 传递的计算机上的运行时组件/ComputerName$。 如果计算机名称未传递然后它将发现 BAM 具有在管理数据库中的最低服务器 ID 的运行时计算机上。 这还发现 BAM 角色和 BAM 运行时在它的包含关系。|  
|Microsoft.BizTalk.Server.2013.BizTalkApplicationServiceDiscovery.vbs|此脚本发现以及其宿主关系与运行时角色的计算机上的所有 BizTalk 应用程序服务。|  
|Microsoft.BizTalk.Server.2013.BizTalkGroupDiscovery.vbs|此脚本发现作为参数 $Config 传递的计算机上的 BizTalk 组/ComputerName$。 如果计算机名称未传递然后它将发现具有管理数据库中的最低服务器 ID 的运行时计算机上的组。|  
|Microsoft.BizTalk.Server.2013.BizTalkRoleDiscovery.vbs|此脚本发现基于参数的指定计算机中的 BizTalk 服务器角色。 $Config 选项 $。 包括以下选项：<br /><br /> -BizTalk 运行时角色、 BizTalk 组部署和包含组部署中的运行时。<br />-BizTalk 规则引擎角色、 BizTalk 组部署和包含组部署中的规则引擎。 BAM 角色始终发现的任何选项，以及其组部署中的包含关系。|  
|BizTalkAnalysisDatabaseMonitor.vbs|此脚本生成基于连接的 SQL 分析数据库的可用性监视的数据。 监视器状态可以是成功或错误。|  
|BizTalkArtifactConfigurationMonitor.vbs|此脚本生成 BizTalk 应用程序项目配置的监视数据。 每个项目将为三个的监视状态成功、 警告和错误之一。|  
|BizTalkArtifactSuspendedInstancesMonitor.vbs|此脚本生成基于每个项目的挂起实例数的 BizTalk 应用程序项目运行时状态的监视数据。 每个项目将为三个的监视状态成功、 警告和错误之一。|  
|BizTalkBAMPortalMonitor.vbs|此脚本生成 BAM 门户的可用性监视的数据。 监视器状态可以是成功或错误。|  
|BizTalkHostConfigurationMonitor.vbs|此脚本生成基于其所有主机实例 (BTSNTSvc.exe) 的可用性的 BizTalk 主机监视的数据。 可以任一成功监视器状态 (运行 > = 成功限制)，警告 (运行 > = 警告限制并运行 < 成功限制) 或错误。|  
|BizTalkDatabaseMonitor.vbs|此脚本生成基于连接的 SQL 数据库的可用性监视的数据。 监视器状态可以是成功或错误。|  
|BizTalkMultipleDatabaseMonitor.vbs|此脚本生成作为单个实体基于连接的 SQL 数据库的某个组的可用性监视的数据。 监视器状态可以是任一错误 （不可用主数据库），警告 （某些非主数据库不可用） 或成功 （可用的所有数据库）。|  
|BizTalkHostProbeAction.vbs|此脚本生成基于其所有主机实例 (BTSNTSvc.exe) 的可用性的 BizTalk 主机的诊断数据。 对于错误和警告状态中，它将显示未运行的主机实例。|  
|Microsoft.BizTalk.Server.2013.HostAction.vbs|使用此脚本到启动/停止 BizTalk 主机。|  
|Microsoft.BizTalk.Server.2013.OrchestrationAction.vbs|使用此脚本到启动/停止业务流程 （BizTalk 应用程序项目）。|  
|Microsoft.BizTalk.Server.2013.EnableReceiveLocation.vbs|此脚本是用于启用/禁用接收位置 （BizTalk 应用程序项目）。|  
|Microsoft.BizTalk.Server.2013.SendPortAction.vbs|使用此脚本到启动/停止发送端口 （BizTalk 应用程序项目）。|  
|Microsoft.BizTalk.Server.2013.SendPortGroupAction.vbs|使用此脚本到启动/停止发送端口组 （BizTalk 应用程序项目）。|