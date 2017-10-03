---
title: "监视主机实例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e7c6b80-7371-46ea-bf9c-82acb22012a3
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 561c40e791d82b28060a45ada51bebed4cd784c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-host-instances"></a>监视主机实例
本主题介绍使用 Microsoft System Center Operations Manager 的监视 BizTalk 主机实例。  
  
## <a name="using-threshold-rules-to-monitor-health"></a>使用阈值规则来监视运行状况  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]管理包包含提供 BizTalk 主机的运行状况的综合视图的性能阈值规则。 提供以下两种不同类型的阈值规则：  
  
-   一般情况下 （例如，对所有 BizTalk 主机和所有 MessageBox 数据库） 应用的规则。  
  
-   特定于特定的 BizTalk 主机的规则。  
  
 泛型规则监视基于常见阈值的所有 BizTalk 主机。 例如，规则监视器 HostQ 大小监视基于常见阈值的所有 BizTalk 主机的工作队列。 如果有三个不同的主机，其所有工作队列都监视由相同规则，并在任何主机工作队列跨常见阈值时发生警报。  
  
 BizTalk 特定于宿主的规则，可以为不同的主机配置不同的阈值。 例如，规则监视器 HostQ 大小 – BizTalkServerApplication 是特定于宿主的监视的规则，BizTalkServerApplication 主机的工作队列。 在此示例中可以定义的特定的 Operations Manager 提供程序特定的性能计数器实例，并在阈值规则中使用该提供程序。 由于这些规则是特定于宿主的你必须对每个新创建的主机定义特定的规则。  
  
 BizTalk 特定于宿主的规则被提供用于创建规则的模板规则是适用于你的环境。 默认情况下，所有阈值监视规则都被禁用：  
  
-   到你的环境，应使用特定的阈值配置一般规则。  
  
-   你应创建基于模板规则和适当的阈值的 BizTalk 特定于宿主的规则。  
  
## <a name="monitoring-biztalk-host-instances"></a>监视 BizTalk 主机实例  
 面向特定的 BizTalk 主机的规则是从监视角度来看更灵活。 BizTalkServerApplication 主机中提供的监视规则的所有阈值[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]管理包是模板规则。 若要使用这些规则，应使用 Operations Manager 管理员控制台：  
  
-   创建一份中的模板规则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]规则组并将其重命名。  
  
-   创建新 BizTalk 特定于宿主的性能计数器实例的 Operations Manager 提供程序。  
  
-   修改使用该规则的 Operations Manager 提供程序，并使其指向新。  
  
 假设你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装有 BizTalk 主机 ReceiveHost 并且你想要监视此主机的主机队列大小。 在这种情况下，应创建 Operations Manager 提供程序基于队列大小的性能计数器的 ReceiveHost 实例上的 BizTalk 主机。 您还应设置适合您环境的规则阈值。  
  
 如果你使用的特定于宿主的阈值监视规则，则应禁用泛型的监视规则。 这可阻止多余警报。  
  
## <a name="see-also"></a>另请参阅  
 [监视与 System Center Operations Manager 2007 的 BizTalk Server](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)