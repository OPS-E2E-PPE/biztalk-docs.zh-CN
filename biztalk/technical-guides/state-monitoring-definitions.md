---
title: 状态监视定义 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa2c8247-5e25-4624-9f0d-c7fe621ffba2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 169eddb0ab412f09a8463b6ef82cd3fcef7f2315
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305499"
---
# <a name="state-monitoring-definitions"></a>状态监视定义
状态监视功能可帮助回答是否被监视的计算机处于正常状态在给定时间从特定的应用程序的角度来看一个问题。 System Center Operations Manager (SCOM) 更新向用户公开的不同托管实体的状态，并将状态作为状态监控视图的一部分呈现。  
  
 若要了解[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]状态监视视图，您必须了解的概念理解 SCOM 状态监视。 以下术语用于描述状态监视的关键组件：  
  
- **角色**-由服务发现的环境中执行服务器的角色。 例如，BizTalk 运行时角色封装运行时项目和 BizTalk Server 中的实例。  
  
- **组件**-用于运行状况汇总的一部分来测量的服务器角色的总体运行状况的子角色。 例如，BAM 警报组件用于生成警报以指示整体运行状况状态。  
  
- **实例**-特定计算机可以承载的服务器角色的实例。  
  
  简单地说，以下是 SCOM 状态监控的重要原则：  
  
- 计算机组的运行状况派生自包含在计算机组中计算机的运行状况。  
  
- 计算机显示的状态是否 （简称为服务器角色） 的应用程序运行在计算机上运行正常，并且运行状况派生自承载的应用程序的运行状况。  
  
- 在应用程序级别 （服务器角色） 中，服务器角色的状态为该服务器角色的所有应用程序实例的总体状态。 例如，接收位置等业务流程、 一个或多个项目的运行状况、 接收端口和其他操作影响的状态和 BizTalk 应用程序的总体运行状况。  
  
- 在应用程序实例级别 （服务器角色实例），应用程序实例的运行状况派生的不同区域 （称为组件） 的应用程序实例的运行状况。  
  
- SCOM 警报与相关联的组件的运行状况。 组件的状态设置为红色、 黄色或绿色时触发警报以指示整体运行状况。  
  
- 组件运行状况有助于服务器角色的运行状况。  
  
  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
- 每个 BizTalk Server 是被视作 BizTalk Server 角色的实例。  
  
- 因此，将被 BizTalk Server 角色的计算机中计算该计算机中的所有 BizTalk Server 进程的所有事件/活动结果。  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包可用于 BizTalk Server 项目，其中包括状态监视  
  
- 例如，业务流程的应用程序项目。 如消息传送组件接收端口、 接收位置和发送端口。  
  
- 部署项目，如服务器、 主机实例，SSO，依此类推。  
  
  下表列出了三个状态的直观地表示运行状况状态的所有 BizTalk Server 平台和应用程序级别项目。 这提供 SCOM 操作员的多服务器部署的高级视图以便快速关注重要问题。  
  
|项目|绿色|Yellow|Red|  
|---------------|-----------|------------|---------|  
|应用程序级别项目|将处于运行状态。|不超过 70%的实例出现故障。|超过 70%的实例出现故障或导致了严重错误。|  
|级别的部署项目|将处于运行状态。|不适用|不处于运行状态或已停止。|