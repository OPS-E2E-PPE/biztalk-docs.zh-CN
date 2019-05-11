---
title: 监视和降低数据库 I/O 争用 |Microsoft Docs
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
ms.openlocfilehash: ab8c8ca63556281644100e026a278c4141e19077
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379471"
---
# <a name="monitoring-and-reducing-database-io-contention"></a>监视和降低数据库 I/O 争用
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 性能通常取决于所设计时[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]性能，这又通常取决于所设计时的磁盘 I/O 性能。 因此，你应监视并调整到最佳性能运行的计算机上的磁盘 I/O[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]用于容装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。  
  
## <a name="monitoring-disk-io"></a>监视磁盘 I/O  
 由于需要进行大量数据库的性质[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 磁盘 I/O 很容易变得 MessageBox 中的瓶颈和 BizTalk 跟踪数据库; 这时也是如此磁盘 I/O 以前尚未为数据库文件中的瓶颈在[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]环境。 因此，我们建议您主动衡量存放的数据和事务日志文件的磁盘的磁盘 I/O 性能。 有关监视磁盘 I/O 性能使用系统监视器的详细信息，请参阅[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]一文["预部署 I/O 最佳实践"](http://go.microsoft.com/fwlink/?LinkId=104829) (<http://go.microsoft.com/fwlink/?LinkId=104829>)。 如果使用 SAN，则可能还需要从 SAN 的硬件制造商联系，以衡量磁盘 I/O 性能的特定工具。  
  
## <a name="separating-the-messagebox-and-biztalk-tracking-dta-databases-and-log-files"></a>分离 MessageBox 和 BizTalk 跟踪 (DTA) 数据库和日志文件  
 由于 MessageBox 和 BizTalk 跟踪数据库是最活跃的我们建议在专用的驱动器，以减少磁盘 I/O 争用问题的可能性上的每个放置数据文件和事务日志文件。 例如，您需要四个驱动器的 MessageBox 和 BizTalk 跟踪数据库文件;为每个以下的一个驱动器：  
  
- MessageBox 数据文件  
  
- MessageBox 事务日志文件  
  
- BizTalk 跟踪数据文件  
  
- BizTalk 跟踪事务日志文件  
  
  将 MessageBox 和 BizTalk 跟踪数据库和分离数据库文件和事务日志文件在不同的物理磁盘上被视为最佳做法的减少磁盘 I/O 争用。 请尝试以尽可能跨任意数量的物理心轴磁盘 I/O。 有关如何避免磁盘争用的详细信息，请参阅[如何避免磁盘争用](http://go.microsoft.com/fwlink/?LinkId=158809)(<http://go.microsoft.com/fwlink/?LinkId=158809>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能优化指南。  
  
  您应单独的文件手动配置后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[BizTalk Server 数据库优化白皮书](http://go.microsoft.com/fwlink/?LinkId=101578)(<http://go.microsoft.com/fwlink/?LinkId=101578>)。  
  
## <a name="see-also"></a>请参阅  
 [使用日志性能分析 (PAL) 工具](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)