---
title: 监视 |Microsoft 文档
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
ms.openlocfilehash: e9c45bb70e3f92f4c85def07add4390a0451cb87
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298901"
---
# <a name="monitoring"></a>监视
默认情况下，所有的 BizTalk 服务器监视和任务使用的默认操作帐户没有特定运行方式帐户定义为运行方式配置文件中的 BizTalk Server 监视帐户目标时。 若要配置的最小所需的监视目的的 BizTalk Server 的权限集与运行方式帐户，都需要以下权限：  
  
-   帐户必须是受监视的计算机的内置管理员组和性能监视器用户组的成员。  
  
-   帐户必须是中的 SQL 实例或托管的数据库和 BizTalk 组被监视的作业的实例的 SysAdmin 角色的成员。  
  
-   有关 BizTalk Server 中监视的目的，帐户必须是 BizTalk 运算符组的一部分。  
  
-   用于通过 SCOM 控制台中运行任务，该帐户必须是 BizTalk 应用程序用户组的一部分。  
  
-   执行管理任务，该帐户必须是 BizTalk 管理员组的一部分。