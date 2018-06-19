---
title: 如何汇总运行状况 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c37644cd-7d3c-4e93-ad56-101043cfa685
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25dd7a2aea4d01a2fd84fe294f793cda833d1322
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297661"
---
# <a name="how-health-rolls-up"></a>运行状况如何汇总
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包将 BizTalk Server 部署、 应用程序和其构成项目分类到其中的一个层的运行状况可以依赖于较低层的运行状况的层结构。  
  
-   BizTalk 部署  
  
-   BizTalk 应用程序  
  
## <a name="health-roll-up-for-biztalk-deployment"></a>注册 BizTalk 部署的运行状况汇总  
 下图显示如何 BizTalk Server 部署的运行状况状态汇总此管理包中。  
  
 ![部署模型](../technical-guides/media/biztalk2010mp-deploymentmodel.gif "BizTalk2010MP DeploymentModel")  
  
 下表描述在 BizTalk Server 部署工作流关系图中显示的组件。  
  
|Name|Description|运行状况|  
|----------|-----------------|------------|  
|BizTalk 部署组|包含与组件，如运行时规则引擎的多个运行时服务器的组。|此组的运行状况取决于的可用性<br /><br /> -BAM 角色<br />-BizTalk 主机部署<br />-BizTalk 运行时角色<br />规则引擎规则|  
|BAM 角色|在哪些 BAM 安装组件服务器。|此运行状况取决于 BAM 运行时角色和 BAM 门户。|  
|BizTalk 主机部署|一个定义的运行时参数或运行的各种应用程序项目的边界的逻辑实体。 此 （主机实例） 的多个实例作为 NT 服务在不同的运行时服务器上运行。|此组的运行状况取决于此主机的不同实例的可用性。|  
|BizTalk 运行时角色|BizTalk 运行时安装的服务器。|此组的运行状况取决于的可用性<br /><br /> -SSO 服务<br />管理数据库<br />-MessageBox 数据库<br />-SSO 数据库<br />跟踪数据库|  
|规则引擎角色|具有安装的规则引擎的服务器。|此组的运行状况取决于规则引擎服务和规则引擎数据库的可用性<br /><br /> 规则引擎服务<br />规则引擎数据库|  
|BAM 运行时角色|服务器的 BAM 安装运行时组件。|此运行状况取决于的可用性<br /><br /> -BAM 主导入数据库<br />-BAM 存档数据库<br />-BAM 分析<br />-BAM 警报|  
|BAM 门户|具有 BAM 门户应用程序安装和配置的 Web 服务器。|此运行状况取决于 BAM 门户应用程序的可用性。|  
|主机实例|配置在 BizTalk 运行时服务器上运行的 Windows NT 服务。|此运行状况是依赖于 Windows NT 服务的状态。|  
|SSO 服务|SSO Windows NT 服务。|此运行状况是依赖于 SSO 服务的状态。|  
|管理数据库|包含一个或多个 BizTalk 数据库的 SQL 服务器。|此运行状况是依赖于 SQL Server 数据库可用性的可用性。|  
|MessageBox 数据库|包含一个或多个 BizTalk MessageBox 数据库的 SQL 服务器。|此运行状况是依赖于 SQL Server 数据库可用性的可用性。|  
|规则引擎服务|规则引擎服务用于处理 BizTalk 规则。|此运行状况取决于规则引擎服务的可用性。|  
|规则引擎数据库|包含一个或多个 BizTalk 规则引擎数据库的 SQL 服务器。|此运行状况是依赖于 SQL Server 数据库可用性的可用性。|  
|BAM 主导入数据库|包含 BAM 数据库的 SQL 服务器。|此运行状况是依赖于 SQL Server 数据库可用性的可用性。|  
|BAM 存档数据库|包含已存档的数据的 SQL Server 数据库。|此运行状况是依赖于 SQL Server 数据库可用性的可用性。|  
|BAM 分析|包含脱机和联机 BAM 分析数据。|此运行状况是取决于 BAM 分析数据的可用性。|  
|BAM 警报|SQL 通知服务。|此运行状况是取决于通知服务的状态。|  
|BAM 警报服务|SQL 通知服务。|此运行状况是取决于通知服务的状态。|  
|BAM 分析数据库|包含脱机和联机 BAM 分析数据的 SQL Server 数据库。|此运行状况是依赖于 SQL Server 数据库可用性的可用性。|  
|BAM 星型架构数据库|包含中间临时表、度量值表和维度表。|此运行状况是依赖于 SQL Server 数据库可用性的可用性。|  
|跟踪数据库|存储运行状况监视由 BizTalk Server 跟踪引擎跟踪数据的 SQL Server 数据库。|此运行状况是依赖于 SQL Server 数据库可用性的可用性。|  
|SSO 数据库|托管 SSO 数据库的 SQL 服务器。|此运行状况是依赖于 SQL Server 数据库可用性的可用性。|  
  
## <a name="health-roll-up-for-biztalk-application"></a>注册 BizTalk 应用程序的运行状况汇总  
 下图显示如何 BizTalk 应用程序和其构成的项目的运行状况状态汇总此管理包中。  
  
 ![应用程序模型](../technical-guides/media/biztalkserver2010mp-applicationmodel.gif "BizTalkServer2010MP ApplicationModel")  
  
 下表描述在 BizTalk 应用程序工作流关系图中显示的组件。  
  
|Name|Description|运行状况|  
|----------|-----------------|------------|  
|BizTalk 组|包含应用程序项目的组。 所有这些项目存储在集中数据库名为作为配置数据库中。 可以从任何运行时计算机发现这些项目。|此组的运行状况取决于 BizTalk 主机和 BizTalk 应用程序的可用性。|  
|主机|一个定义的运行时参数或运行的各种应用程序项目的边界的逻辑实体。 此 （主机实例） 的多个实例作为 NT 服务在不同的运行时服务器上运行。|此组的运行状况取决于此主机的不同实例的可用性。|  
|应用程序|一组的业务流程、 架构、 映射和管道等的 BizTalk 应用程序项目。 如消息组件发送端口、 接收位置和接收端口。 BizTalk Server 接收到合适的消息时，将在主机实例中运行的这些项目的实例。|此运行状况取决于<br /><br /> -配置状态接收端口<br />-运行时状态接收端口<br />的发送端口配置状态<br />-业务流程的运行状况<br />的业务流程运行时状态|  
|接收端口|在主机实例中运行一个 BizTalk 项目。 这将运行 BizTalk Server 接收一条消息时。 接收端口包含一个或多个接收位置。|此运行状况取决于配置状态和运行时状态的接收端口。|  
|接收位置|BizTalk 项目，从外部系统接收消息。 这使用适配器具有其关联的终结点收到一条消息。|此运行状况取决于配置状态和运行时状态的接收位置。|  
|发送端口|将处理过的消息发送到外部系统。|此运行状况取决于配置状态和运行时状态发送端口。|  
|业务流程|收到一条消息从接收端口和处理消息。 Orchestration 是与工作流类似。|此运行状况取决于业务流程的配置状态和运行时状态。|  
|发送端口组|发送端口的逻辑组，从 BizTalk 消息框中接收消息并将其发送到外部系统。|此组的运行状况取决于此组中的发送端口的运行状况。|