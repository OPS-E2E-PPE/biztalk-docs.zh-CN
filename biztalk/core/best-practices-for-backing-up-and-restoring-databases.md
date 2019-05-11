---
title: 备份和还原数据库的最佳做法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- best practices, maintaining
- restoring, best practices
- best practices, backing up
- backing up, restoring
- backing up, best practices
- maintaining, best practices
- best practices, restoring
ms.assetid: 649ca56b-3cc1-49ad-9f74-ba1521e65ee1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9ac2784a19a55d477f71c9b6542b7d46948d63f
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529133"
---
# <a name="best-practices-for-backing-up-and-restoring-databases"></a>备份和还原数据库的最佳实践
请查看以下最佳实践以帮助确保你可以备份和还原 BizTalk Server 数据库。  
  
-   **开发备份和还原策略并对其进行测试。**  
  
     使用合适的计划，您可以因硬件故障而丢失时迅速恢复数据。  
  
-   **管理磁盘空间并归档以前的备份文件。**  
  
     备份 BizTalk Server 作业不会删除过期的备份文件，因此需要管理这些备份文件，以节省磁盘空间。 为数据库创建了新的完全备份后，应该将过期的备份文件移到存档存储设备，以回收主磁盘空间。  
  
-   **不要在同一计算机或您要备份的磁盘上存储备份。**  
  
     应为不同于原始数据的计算机备份指定的计算机或磁盘。 否则，如果将丢失所有数据的硬件出现故障。  
  
-   **保留副本。**  
  
     将保留该媒体的至少三个副本。 在正确受控环境中保留非现场至少一个副本。  
  
-   **执行试验性还原。**  
  
     执行试验性还原每月至少一次以验证你的文件已正确备份。 试验性还原可以发现不会显示验证您的软件运行正常时的硬件问题。 不要等到硬盘之前，请参阅是否可以还原系统和数据库。  
  
-   **保护设备和媒体。**  
  
     保护存储设备和备份介质。 它是有人可以通过将数据还原到另一台服务器，它们是管理员的窃取的媒体来访问数据。  
  
-   **监视备份和还原过程。**  
  
     若要确保备份和还原过程已成功，则应该监视用于备份和还原 BizTalk Server 的 SQL Server 代理作业。  
  
## <a name="see-also"></a>请参阅  
 [备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)