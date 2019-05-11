---
title: 在 Operations Manager 控制台中查看信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6acdf425-4c36-4d89-9493-81b33481fe6d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a03daf6612a3f31313d3826f95357d99d0841f73
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249319"
---
# <a name="viewing-information-in-the-operations-manager-console"></a>在 Operations Manager 控制台中查看信息
使用与提供的视图[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包，以了解当前可用性、 配置、 运行状况，以及 BizTalk Server 环境的性能。 视图可能会包含很长的对象列表。 若要查找特定对象组，您可以使用 Operations Manager 工具栏上的作用域、 搜索和查找按钮。 有关详细信息，请参阅如何管理监视数据使用作用域、 搜索，并在 Operations Manager 2007 R2\2012 帮助中查找主题。  
  
 以下视图正下方列出**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]** 在操作控制台的监视窗格中的节点。  
  
-   **应用程序视图**:BizTalk 管理员是希望监视的状态和运行状况的各种 BizTalk Server 项目和应用程序，如业务流程发送端口、 接收位置，依次类推。  
  
-   **部署视图**:企业 IT 管理员希望监视状态和各种企业部署托管 SQL Server 数据库，托管 SSO 服务、 主机实例计算机、 IIS 的计算机的计算机运行状况的网络服务等。  
  
## <a name="application-views"></a>应用程序视图  
 应用程序视图包含下表中描述的元素。  
  
### <a name="elements"></a>元素  
  
|视图名称|Description|  
|---------------|-----------------|  
|应用程序状态视图|这是一个仪表板视图，显示 BizTalk 应用程序的运行状况。 BizTalk 应用程序的运行状况取决于其构成项目，如业务流程、 发送端口组、 发送端口、 接收端口和接收位置的运行状况。 详细信息视图窗格提供托管的 BizTalk 应用程序的属性。|  
|组状态视图|这是一个仪表板视图，显示 BizTalk 组的运行状况。 BizTalk 组的运行状况取决于 BizTalk 主机和 BizTalk 应用程序的运行状况。 详细信息视图窗格提供了 BizTalk 组的属性。|  
|主机状态视图|这是一个仪表板视图，显示 BizTalk 主机的运行状况。 BizTalk 主机的运行状况取决于宿主的 BizTalk 应用程序实例的运行状况。 详细信息视图窗格中提供的 BizTalk 主机的属性。|  
  
#### <a name="application-artifacts-views"></a>应用程序项目视图  
 应用程序项目视图中所包含下表中描述的元素。  
  
### <a name="elements"></a>元素  
  
|视图名称|Description|  
|---------------|-----------------|  
|业务流程状态视图|显示的配置和运行时状态的业务流程的托管应用程序。|  
|接收位置状态视图|显示的配置和运行时状态的接收位置承载的应用程序。|  
|接收端口的状态视图|显示的配置和运行时状态的接收端口的托管应用程序。|  
|发送端口组状态视图|显示的配置和运行时状态的发送端口组的托管应用程序。|  
|发送端口状态视图|显示的配置和运行时状态的发送端口的托管应用程序。|  
  
## <a name="deployment-views"></a>部署视图  
 部署视图包含下表中描述的元素。  
  
### <a name="elements"></a>元素  
  
|视图名称|Description|  
|---------------|-----------------|  
|部署状态视图|这是显示 BizTalk 部署组的运行状况仪表板视图。 BizTalk 部署组的运行状况取决于其构成的运行时服务器组件，如 BAM 角色、 规则引擎角色、 BizTalk 运行时角色和 BizTalk 主机的运行状况。 详细信息视图窗格提供了 BizTalk 部署组的属性。|  
|主机状态视图|这是一个仪表板视图，显示 BizTalk 主机的运行状况。 BizTalk 主机的运行状况取决于宿主的 BizTalk 应用程序实例的运行状况。 详细信息视图窗格中提供的 BizTalk 主机的属性。|  
|规则引擎角色状态视图|这是显示在运行时服务器运行的规则引擎服务的运行状况仪表板视图。 详细信息视图窗格提供了安装的规则引擎服务的运行时服务器的属性。|  
|运行时角色状态视图|这是此仪表板视图显示已安装的运行时规则引擎服务的运行时服务器的运行状况。 BizTalk 运行时角色的运行状况取决于其组件，如 SSO 服务、 管理数据库、 messagebox 数据库中，SSO 数据库和跟踪数据库的运行状况。 详细信息视图窗格提供了在运行时服务器的属性。|  
  
### <a name="bam-component-views"></a>BAM 组件视图  
  
### <a name="elements"></a>元素  
  
|视图名称|Description|  
|---------------|-----------------|  
|BAM 警报状态视图|显示 BizTalk BAM 警报组件的状态视图。|  
|BAM 分析状态视图|显示 BizTalk BAM 分析组件的状态视图。|  
|BAM 性能视图|图例窗格显示有关 BAM 的性能计数器。|  
|BAM 门户状态视图|显示 BAM 门户的状态视图。|  
|BAM 运行时状态视图|显示 BAM 运行时的状态视图。|  
  
#### <a name="bam-alerts"></a>BAM 警报  
  
### <a name="elements"></a>元素  
  
|视图名称|Description|  
|---------------|-----------------|  
|BAM 警报状态视图|显示这是通知服务，当任何关键服务都不可用时，生成 BizTalk BAM 警报的列表。|  
  
##### <a name="runtime-component-views"></a>运行时组件视图  
  
### <a name="elements"></a>元素  
  
|视图名称|Description|  
|---------------|-----------------|  
|应用程序服务状态视图|在 BizTalk 组中显示的所有主机实例的运行状况。|  
|消息框性能状态视图|图例窗格中显示的消息框跟踪数据大小的性能计数器。|  
|消息传送适配器性能视图|图例窗格中显示的性能计数器的 MSMQ 接收适配器接收的字节。|  
|消息传送性能视图|图例窗格中显示为活动的接收位置的性能计数器。|  
|业务流程性能视图|图例窗格中显示为可运行的业务流程的性能计数器。|  
|服务器资源使用情况视图|图例窗格显示物理磁盘空闲时间百分比的性能计数器。|  
  
###### <a name="runtime-alerts"></a>运行时的警报  
  
### <a name="elements"></a>元素  
  
|视图名称|Description|  
|---------------|-----------------|  
|核心警报视图|显示 BizTalk 核心警报。|  
|消息传送的警报视图|显示 BizTalk 消息传送警报。|