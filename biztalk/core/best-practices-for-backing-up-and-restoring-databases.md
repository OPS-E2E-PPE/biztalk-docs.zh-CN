---
title: 备份和还原数据库的最佳实践 |Microsoft 文档
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
ms.openlocfilehash: 2543f09c5118e58bd18ea2add113811fb733d884
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231173"
---
# <a name="best-practices-for-backing-up-and-restoring-databases"></a>备份和还原数据库的最佳实践
请查看以下最佳实践，以确保您能够备份和还原 BizTalk Server 数据库。  
  
-   **开发备份和还原策略，并对其进行测试。**  
  
     有了好的计划，您就可以在由于硬件故障致使数据丢失时迅速恢复数据。  
  
-   **管理磁盘空间并存档以前的备份文件。**  
  
     由于备份 BizTalk Server 作业并不删除过期的备份文件，所以需要对这些备份文件进行管理，以节省磁盘空间。 为数据库创建了新的完全备份后，应该将过期的备份文件移到存档存储设备，以回收主磁盘空间。  
  
-   **不在相同的计算机或要备份的磁盘上存储备份。**  
  
     而应该为其指定其他计算机或磁盘。 否则，当出现硬件故障时，您将丢失所有数据。  
  
-   **保留副本。**  
  
     至少应保留该媒体的三个副本。 至少保留一个非现场副本，放置在安全控制良好的环境中。  
  
-   **执行试验性还原。**  
  
     至少每月执行一次试验性还原，以验证文件备份是否正确。 试验性还原可发现在验证软件功能是否正常时未发现的硬件问题。 不要等到硬盘出现了故障，才去检查是否能还原系统和数据库。  
  
-   **保护设备和媒体。**  
  
     保护存储设备和备份媒体。 其他人可能偷窃备份媒体，并将数据还原到他们具有管理员身份的其他服务器上，以访问媒体上的数据。  
  
-   **监视备份和还原过程。**  
  
     为了确保备份和还原过程成功，您应对用来备份和还原 BizTalk Server 的 SQL Server 代理作业进行监视。  
  
## <a name="see-also"></a>另请参阅  
 [备份和还原的 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)