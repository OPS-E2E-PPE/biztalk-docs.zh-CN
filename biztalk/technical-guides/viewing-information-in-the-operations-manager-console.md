---
title: "在 Operations Manager 控制台中查看信息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6acdf425-4c36-4d89-9493-81b33481fe6d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 687932839c379ed9589a51baae0ae8562f4af705
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="viewing-information-in-the-operations-manager-console"></a>在 Operations Manager 控制台中查看信息
使用提供的视图[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包，以了解当前的可用性、 配置、 运行状况，以及 BizTalk Server 环境的性能。 视图可能会包含很长的对象列表。 若要查找特定对象或对象组，您可以使用 Operations Manager 工具栏上的“作用域”、“搜索”和“查找”按钮。 有关详细信息，请参阅如何管理监视数据使用作用域、 搜索，并在 Operations Manager 2007 R2\2012 帮助中查找主题。  
  
 以下视图正下方列出 **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]** 在操作控制台的监视窗格中的节点。  
  
-   **应用程序视图**: BizTalk 管理员有兴趣监视状态和运行状况的各种 BizTalk 服务器项目，如业务流程的应用程序发送端口、 接收位置，依此类推。  
  
-   **部署视图**： 企业 IT 管理员感兴趣的状态和承载 SQL Server 的机数据库，SSO 服务，主机实例机，IIS 承载的计算机的各种企业部署的运行状况监视网络服务，依次类推。  
  
## <a name="application-views"></a>应用程序视图  
 应用程序视图包含下表中描述的元素。  
  
### <a name="elements"></a>元素  
  
|视图名称|Description|  
|---------------|-----------------|  
|应用程序状态视图|这是一个仪表板视图，显示 BizTalk 应用程序的运行状况。 BizTalk 应用程序的运行状况取决于其构成的项目，比如业务流程，发送端口组、 发送端口、 接收端口和接收位置的运行状况。 详细信息视图窗格中提供的托管的 BizTalk 应用程序的属性。|  
|组状态视图|这是一个仪表板视图，显示 BizTalk 组的运行状况。 BizTalk 组的运行状况取决于 BizTalk 主机和 BizTalk 应用程序的运行状况。 详细信息视图窗格中提供的 BizTalk 组的属性。|  
|主机状态视图|这是一个仪表板视图，显示 BizTalk 主机的运行状况。 BizTalk 主机的运行状况取决于的托管的 BizTalk 应用程序实例的运行状况。 详细信息视图窗格提供 BizTalk 主机的属性。|  
  
#### <a name="application-artifacts-views"></a>应用程序项目视图  
 应用程序项目视图中所包含下表中描述的元素。  
  
### <a name="elements"></a>元素  
  
|视图名称|Description|  
|---------------|-----------------|  
|业务流程状态视图|显示的配置和运行时状态的业务流程的托管应用程序。|  
|接收位置状态视图|显示的配置和运行时状态的接收位置的托管应用程序。|  
|接收端口状态视图|显示的配置和运行时状态接收端口的托管应用程序。|  
|发送端口组状态视图|显示的配置和运行时状态发送端口组的托管应用程序。|  
|发送端口状态视图|显示的配置和运行时状态发送端口的托管应用程序。|  
  
## <a name="deployment-views"></a>部署视图  
 部署视图包含下表中描述的元素。  
  
### <a name="elements"></a>元素  
  
|视图名称|Description|  
|---------------|-----------------|  
|部署状态视图|这是一个仪表板视图，显示 BizTalk 部署组的运行状况。 BizTalk 部署组的运行状况取决于其构成的运行时服务器组件，如 BAM 角色、 规则引擎角色、 BizTalk 运行时角色和 BizTalk 主机的运行状况。 详细信息视图窗格提供 BizTalk 部署组的属性。|  
|主机状态视图|这是一个仪表板视图，显示 BizTalk 主机的运行状况。 BizTalk 主机的运行状况取决于的托管的 BizTalk 应用程序实例的运行状况。 详细信息视图窗格提供 BizTalk 主机的属性。|  
|规则引擎角色状态视图|这是显示在运行时服务器运行的规则引擎服务的运行状况仪表板视图。 详细信息视图窗格中提供的已安装的规则引擎服务的运行时服务器的属性。|  
|运行时角色状态视图|这是此仪表板视图显示已安装的运行时规则引擎服务运行时服务器的运行状况。 BizTalk 运行时角色的运行状况取决于其组件，如 SSO 服务、 管理数据库、 消息框数据库、 SSO 数据库和跟踪数据库的运行状况。 详细信息视图窗格中提供的运行时服务器的属性。|  
  
### <a name="bam-component-views"></a>BAM 组件视图  
  
### <a name="elements"></a>元素  
  
|视图名称|Description|  
|---------------|-----------------|  
|BAM 警报状态视图|显示 BizTalk BAM 警报组件的状态视图。|  
|BAM 分析状态视图|显示 BizTalk BAM 分析组件的状态视图。|  
|BAM 性能视图|图例窗格显示 BAM 性能计数器。|  
|BAM 门户状态视图|显示 BAM 门户的状态视图。|  
|BAM 运行时状态视图|显示 BAM 运行时的状态视图。|  
  
#### <a name="bam-alerts"></a>BAM 警报  
  
### <a name="elements"></a>元素  
  
|视图名称|Description|  
|---------------|-----------------|  
|BAM 警报状态视图|显示 BizTalk BAM 警报的列表，也不能是一项通知服务生成的任何关键的服务都不可用时。|  
  
##### <a name="runtime-component-views"></a>运行时组件视图  
  
### <a name="elements"></a>元素  
  
|视图名称|Description|  
|---------------|-----------------|  
|应用程序服务状态视图|显示 BizTalk 组中的所有主机实例的运行状况。|  
|消息框性能状态视图|图例窗格中显示的消息框跟踪数据大小的性能计数器。|  
|消息传送适配器性能视图|图例窗格显示有关 MSMQ 接收适配器接收的字节数的性能计数器。|  
|消息传递性能视图|图例窗格中显示的活动接收位置的性能计数器。|  
|业务流程性能视图|图例窗格中显示的性能计数器可运行的业务流程。|  
|服务器资源使用量视图|图例窗格显示物理磁盘空闲时间百分比性能计数器。|  
  
###### <a name="runtime-alerts"></a>运行时的警报  
  
### <a name="elements"></a>元素  
  
|视图名称|Description|  
|---------------|-----------------|  
|核心警报视图|显示 BizTalk 核心警报。|  
|消息传送警报视图|显示 BizTalk 消息的警报。|