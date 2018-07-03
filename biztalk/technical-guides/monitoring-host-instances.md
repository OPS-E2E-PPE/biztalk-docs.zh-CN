---
title: 监视主机实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4e7c6b80-7371-46ea-bf9c-82acb22012a3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91ad5ec158466db6716b515fe3d34ae76c4cde0f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003334"
---
# <a name="monitoring-host-instances"></a>监视主机实例
本主题介绍使用 Microsoft System Center Operations Manager 监视 BizTalk 主机实例。  
  
## <a name="using-threshold-rules-to-monitor-health"></a>使用阈值规则监视运行状况  
 BizTalk Server 管理包集成了提供的 BizTalk 主机的运行状况的综合视图的性能阈值规则。 提供以下两种不同类型的阈值规则：  
  
- 一般情况下 （例如，对所有 BizTalk 主机和所有 MessageBox 数据库） 应用的规则。  
  
- 特定于特定的 BizTalk 主机的规则。  
  
  一般的规则监视基于通用阈值的所有 BizTalk 主机。 例如，规则 Monitor HostQ Size 监视基于通用阈值的所有 BizTalk 主机的工作队列。 如果有三个不同的主机，其所有工作队列都监视由相同规则和任何主机工作队列超过通用阈值时将发出警报。  
  
  BizTalk 主机特定的规则，可为不同的主机配置不同的阈值。 例如，规则 Monitor HostQ Size – BizTalkServerApplication 是特定于宿主的规则，用于监视 BizTalkServerApplication 主机工作队列。 在此示例中可以定义特定的 Operations Manager 提供程序为特定的性能计数器实例和阈值规则中使用该提供程序。 这些规则是特定于宿主的因为必须为每个新创建的主机定义特定规则。  
  
  因为用于创建规则的模板规则是适用于你的环境提供了 BizTalk 特定于宿主的规则。 默认情况下，所有阈值监视规则都被禁用：  
  
- 到你的环境，应使用特定的阈值配置一般的规则。  
  
- 您应该创建 BizTalk 主机特定规则基于模板规则和相应的阈值。  
  
## <a name="monitoring-biztalk-host-instances"></a>监视 BizTalk 主机实例  
 针对特定的 BizTalk 主机的规则是从监视角度来看更灵活。 BizTalkServerApplication 主机在 BizTalk Server 管理包中提供的所有阈值监视规则都均为模板规则。 若要使用这些规则，应使用 Operations Manager 管理员控制台：  
  
- 创建一份中的模板规则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]规则组，并将其重命名。  
  
- 创建新的 Operations Manager 提供程序的 BizTalk 主机特定的性能计数器实例。  
  
- 修改规则所使用的 Operations Manager 提供程序并使其指向新。  
  
  假设你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装有 BizTalk 主机 ReceiveHost，并且你想要监视此主机的主机队列大小。 在这种情况下，应创建为 BizTalk 主机基于队列大小的性能计数器的 ReceiveHost 实例上的 Operations Manager 提供程序。 您还应设置适合您环境的规则阈值。  
  
  如果使用的特定于宿主的阈值监视规则，则应禁用通用监视规则。 这可阻止多余警报。  
  
## <a name="see-also"></a>请参阅  
 [使用 System Center Operations Manager 2007 监视 BizTalk Server](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)