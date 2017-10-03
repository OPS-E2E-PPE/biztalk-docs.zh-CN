---
title: "状态监视定义 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa2c8247-5e25-4624-9f0d-c7fe621ffba2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97007535e67a4c3540278cee7ff82fec18d492c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="state-monitoring-definitions"></a>状态监视定义
状态监视有助于回答问题在给定时间从特定的应用程序的角度监视的计算机是否正常运行。 System Center Operations Manager (SCOM) 更新不同向用户公开的托管实体的状态，并显示状态的监视视图的状态的一部分。  
  
 若要了解[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]状态监视视图，你必须了解的概念 SCOM 状态监视。 下面的术语用于描述状态监视的关键元素：  
  
-   **角色**-由服务发现的环境中执行服务器的角色。 例如，BizTalk 运行时角色封装的运行时项目和 BizTalk Server 中的实例。  
  
-   **组件**-的运行状况汇总一部分用于测量服务器角色的总体运行状况的子角色。 例如，BAM 警报组件用于生成警报，以指示的总体运行状况状态。  
  
-   **实例**-特定计算机可以托管服务器角色的实例。  
  
 简言之，以下是 SCOM 状态监控的重要原则：  
  
-   计算机组的运行状况源自计算机组中包含计算机的运行状况。  
  
-   计算机的状态显示在计算机上运行的应用程序（称作服务器角色）是否运行正常，并且运行状况从作为宿主的应用程序的运行状况派生。  
  
-   在应用程序级别（服务器角色），服务器角色的状态是该服务器角色的所有应用程序实例的整体状态。 例如，运行状况的一个或多个项目，如业务流程，接收位置、 接收端口和依此类推会影响的状态和 BizTalk 应用程序的总体运行状况。  
  
-   在应用程序实例级别 （服务器角色实例），应用程序实例的运行状况源自的 （称为组件） 的应用程序实例的不同方面的运行状况。  
  
-   SCOM 警报与组件的运行状况相关联。 在触发警报以指示整体运行状况时，组件的状态设置为红色、黄色或绿色。  
  
-   组件的运行状况将影响服务器角色的运行状况。  
  
 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中：  
  
-   每个 BizTalk 服务器将被视为的 BizTalk Server role 的实例。  
  
-   因此，某一计算机中的 BizTalk Server 角色将被计算为该计算机中所有 BizTalk Server 进程的所有事件/活动的结果。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包可用于 BizTalk Server 项目，其中包括监视状态  
  
-   例如，业务流程的应用程序项目。 如消息组件接收端口、 接收位置和发送端口。  
  
-   部署项目，如服务器，承载情况下，SSO，依此类推。  
  
 下表列出以可视方式表示所有的 BizTalk Server 平台和应用程序级项目的运行状况状态的三种状态。 因此，SCOM 操作员能够清楚地了解多服务器部署的情况，以便更快地关注重要问题。  
  
|项目|绿色|Yellow|Red|  
|---------------|-----------|------------|---------|  
|应用程序级项目|处于运行状态。|不超过 70%的实例出现故障。|超过 70%的实例出现故障，或导致严重错误。|  
|部署级别项目|处于运行状态。|不适用|未处于运行状态或已停止。|