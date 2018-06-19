---
title: 监视和减少数据库 I/O 争用 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd6d3343-3fa3-469a-9772-e94f22fdf558
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 446a4b512b4f38869637cb3968305fad1e869dae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298773"
---
# <a name="monitoring-and-reducing-database-io-contention"></a>监视和减少数据库 I/O 争用
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能通常预测时[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]性能方面，这反过来通常预测时磁盘 I/O 性能。 因此，你应监视和性能调整运行的计算机上的磁盘 I/O[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]该 house[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。  
  
## <a name="monitoring-disk-io"></a>监视磁盘 I/O  
 需要进行大量数据库的性质，因此[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 磁盘 I/O 可以轻松地成为上 MessageBox 瓶颈和 BizTalk 跟踪数据库; 这是 true 即使磁盘 I/O 以前尚未中的数据库文件瓶颈你[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]环境。 因此，我们建议你主动测量存放的数据和事务日志文件的磁盘的磁盘 I/O 性能。 有关监视使用系统监视器的磁盘 I/O 性能的详细信息，请参阅[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]文章["预部署 I/O 最佳实践"](http://go.microsoft.com/fwlink/?LinkId=104829) (http://go.microsoft.com/fwlink/?LinkId=104829)。 如果使用 SAN，你可能还需要从 SAN 硬件制造商联系，以测量磁盘输入/输出性能的特定工具。  
  
## <a name="separating-the-messagebox-and-biztalk-tracking-dta-databases-and-log-files"></a>分隔的 MessageBox 和 BizTalk 跟踪 (DTA) 数据库和日志文件  
 由于 MessageBox 和 BizTalk 跟踪数据库中最活跃的我们建议你将数据文件和事务日志文件放置于其中每种上专用的驱动器，以减少磁盘 I/O 争用问题的可能性。 例如，将需要四个驱动器的 MessageBox 和 BizTalk 跟踪数据库文件;为每个以下的一个驱动器：  
  
-   MessageBox 数据文件  
  
-   MessageBox 事务日志文件  
  
-   BizTalk 跟踪数据文件  
  
-   BizTalk 跟踪事务日志文件  
  
 分隔 MessageBox 和 BizTalk 跟踪数据库和分离数据库文件和事务日志文件在不同的物理磁盘上被视为减少磁盘 I/O 争用的最佳做法。 请尝试以尽可能跨多个物理磁盘轴磁盘 I/O。 有关如何避免磁盘争用情况的详细信息，请参阅[如何避免磁盘争用](http://go.microsoft.com/fwlink/?LinkId=158809)(http://go.microsoft.com/fwlink/?LinkId=158809) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能优化指南。  
  
 你应该在配置后手动将文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[BizTalk Server 数据库优化白皮书](http://go.microsoft.com/fwlink/?LinkId=101578)(http://go.microsoft.com/fwlink/?LinkId=101578)。  
  
## <a name="see-also"></a>另请参阅  
 [使用日志 (PAL) 工具的性能分析](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)