---
title: 清单：监视操作准备就绪 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef77ccc2-1d39-4e78-8fea-5c17d05c8174
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ece8f6b6aea58b37bf5e8f940f1f6fb197970ea4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399354"
---
# <a name="checklist-monitoring-operational-readiness"></a>清单：监视操作准备情况
本主题列出了监视生产环境时应遵循的步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  


|                                                                                                                                                                      步骤                                                                                                                                                                       |                                                                                                  参考                                                                                                   |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                                           选择和实现你的 BizTalk 应用程序和基础结构的监视策略。                                                                                                                           |                                                [监视 BizTalk Server 环境](../technical-guides/monitoring-the-biztalk-server-environment.md)                                                 |
|                                                                                                                                                            监视磁盘空间使用情况。                                                                                                                                                             |                                                              [监视磁盘空间使用情况](../technical-guides/monitoring-disk-space-usage.md)                                                               |
| 监视 SQL Server:<br /><br /> -验证计算机的运行 SQL Server 底座[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]正受到监视的数据库。<br />-验证[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]正受到监视作业。 |            -   [监视 SQL Server](../technical-guides/monitoring-sql-servers.md)<br />-   [监视 BizTalk Server 数据库](../technical-guides/monitoring-biztalk-server-databases.md)            |
|          监视 BizTalk 应用程序：<br /><br /> -修改现有规则和/或复制到一个自定义管理包，用于监视自定义的 BizTalk 应用程序的规则。<br />-创建针对每个定义的规则的操作。<br />-创建迭代的过程来自动执行手动任务。<br />-使用阈值规则来自动执行手动任务。          | -   [监视应用程序和主机实例](../technical-guides/monitoring-applications-and-host-instances.md)<br />-   [监视 BizTalk Server2](../technical-guides/monitoring-biztalk-server2.md) |

## <a name="in-this-section"></a>本节内容  

-   [监视磁盘空间使用情况](../technical-guides/monitoring-disk-space-usage.md)