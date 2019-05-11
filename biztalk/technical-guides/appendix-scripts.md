---
title: 附录：Scripts | Microsoft Docs
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
ms.openlocfilehash: 0c99c48018d7c4b5e7f9d6905611128a2cc2a8dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401343"
---
# <a name="appendix-scripts"></a>附录：脚本
此管理包中包含以下脚本。  
  
|脚本|用途|  
|------------|-------------|  
|Microsoft.BizTalk.Server.2013.ArtifactsDiscovery.vbs|此脚本发现应用程序项目根据 $Config 选项 $ 参数。 选项包括<br /><br /> -所有发送端口、 发送端口组中应用程序，其托管关系到应用程序和发送端口组包含发送端口的关系。<br />-所有业务流程的应用程序，其与应用程序的托管关系。<br />-All 接收端口、 接收位置的应用程序，其托管关系中对应用程序和接收端口包含接收位置的关系。|  
|Microsoft.BizTalk.Server.2013.ApplicationDiscovery.vbs|此脚本发现以下各项：<br /><br /> 的组和组的主机应用程序关系中所有应用程序。<br />的组和组主机主机关系中所有主机。|  
|Microsoft.BizTalk.Server.2013.BAMAnalysisDiscovery.vbs|此脚本发现 BAM 分析和警报发现 BAM 运行时组件的位置的计算机上的组件。|  
|Microsoft.BizTalk.Server.2013.BAMPortalDiscovery.vbs|此脚本可发现的计算机的 IIS 上配置 BAM 门户。 这还发现 BAM 角色和 BAM 门户中的包含关系。|  
|Microsoft.BizTalk.Server.2013.BAMRuntimeDiscovery.vbs|此脚本发现作为 $Config 参数传递的计算机上的 BAM 运行时组件/ComputerName$。 如果计算机名称未传递然后它使用在管理数据库中的最低服务器 ID 的运行时计算机上发现 BAM。 这还发现 BAM 角色和 BAM 运行时在它的包含关系。|  
|Microsoft.BizTalk.Server.2013.BizTalkApplicationServiceDiscovery.vbs|此脚本发现以及与运行时角色及其托管关系的计算机上的所有 BizTalk 应用程序服务。|  
|Microsoft.BizTalk.Server.2013.BizTalkGroupDiscovery.vbs|此脚本可发现作为 $Config 参数传递的计算机上的 BizTalk 组/ComputerName$。 如果计算机名称未传递它发现具有管理数据库中的最低服务器 ID 的运行时计算机上的组。|  
|Microsoft.BizTalk.Server.2013.BizTalkRoleDiscovery.vbs|此脚本发现基于参数的指定计算机中的 BizTalk server 角色。 $Config 选项 $。 选项包括：<br /><br /> BizTalk 运行时角色、 BizTalk 组部署和组部署中运行时的包含关系。<br />BizTalk 规则引擎角色、 BizTalk 组部署和包含在组部署中的规则引擎。 BAM 角色始终发现的任何选项，以及其组部署中的包含关系。|  
|BizTalkAnalysisDatabaseMonitor.vbs|此脚本将生成 SQL 分析数据库的连接的可用性监视的数据。 监视器状态可以为成功或错误。|  
|BizTalkArtifactConfigurationMonitor.vbs|此脚本将生成 BizTalk 应用程序项目配置的监视数据。 每个项目将为三个监视状态成功、 警告和错误之一。|  
|BizTalkArtifactSuspendedInstancesMonitor.vbs|此脚本将生成的每个项目的挂起实例的数量基于 BizTalk 应用程序项目运行时状态的监视数据。 每个项目将为三个监视状态成功、 警告和错误之一。|  
|BizTalkBAMPortalMonitor.vbs|此脚本将生成 BAM 门户的可用性监视的数据。 监视器状态可以为成功或错误。|  
|BizTalkHostConfigurationMonitor.vbs|此脚本将生成 BizTalk 主机基于其所有主机实例 (BTSNTSvc.exe) 的可用性监视的数据。 监视器状态可以是成功 (运行 > = 成功限制)、 警告 (运行 > = 警告限制和正在运行 < 成功限制) 或错误。|  
|BizTalkDatabaseMonitor.vbs|此脚本将生成 SQL 数据库的连接的可用性监视的数据。 监视器状态可以为成功或错误。|  
|BizTalkMultipleDatabaseMonitor.vbs|此脚本将生成的一组 SQL 数据库作为单个实体的连接的可用性的监视数据。 监视器状态可以是任一错误 （主数据库不可用），警告 （某些非主数据库不可用） 或成功 （所有数据库都可用）。|  
|BizTalkHostProbeAction.vbs|此脚本将生成基于其所有主机实例 (BTSNTSvc.exe) 的可用性的 BizTalk 主机的诊断数据。 错误和警告状态，它显示未运行的主机实例。|  
|Microsoft.BizTalk.Server.2013.HostAction.vbs|使用此脚本到启动/停止 BizTalk 主机。|  
|Microsoft.BizTalk.Server.2013.OrchestrationAction.vbs|使用此脚本到启动/停止业务流程 （BizTalk 应用程序项目）。|  
|Microsoft.BizTalk.Server.2013.EnableReceiveLocation.vbs|此脚本是用于启用/禁用接收位置 （BizTalk 应用程序项目）。|  
|Microsoft.BizTalk.Server.2013.SendPortAction.vbs|使用此脚本到启动/停止发送端口 （BizTalk 应用程序项目）。|  
|Microsoft.BizTalk.Server.2013.SendPortGroupAction.vbs|使用此脚本到启动/停止发送端口组 （BizTalk 应用程序项目）。|