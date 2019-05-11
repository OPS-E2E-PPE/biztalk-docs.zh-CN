---
title: 监视 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7effa38f-f9f2-40b7-8d8b-fa13cf94aa4f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8c7d6e8870d435163c83c053f981d42bad1858d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249627"
---
# <a name="monitoring"></a>监视
默认情况下，所有 BizTalk 服务器监视和任务都使用的默认操作帐户没有特定的运行方式帐户定义的运行方式配置文件的 BizTalk Server 监视帐户中的目标时。 若要配置运行方式帐户与最小所需的监视目的的 BizTalk Server 的权限集，都需要以下权限：  
  
-   该帐户必须是受监视的计算机的内置管理员组和性能监视器用户组的成员。  
  
-   该帐户必须是 SQL 实例或托管的数据库和 BizTalk 组所监视的作业实例中 SysAdmin 角色的成员。  
  
-   有关 BizTalk Server 中监视的目的，帐户必须是 BizTalk Operators 组的一部分。  
  
-   用于通过 SCOM 控制台运行任务，该帐户必须是 BizTalk Application Users 组的一部分。  
  
-   用于执行管理任务，该帐户必须是 BizTalk 管理员组的一部分。