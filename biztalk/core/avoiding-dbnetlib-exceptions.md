---
title: 避免 DBNETLIB 异常 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fbee0cf-d249-4d98-8d16-168ded32f9f1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: decd258c5f4c965c79d9821c82671c6997ac9e3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231909"
---
# <a name="avoiding-dbnetlib-exceptions"></a>避免出现 DBNETLIB 异常
当 BizTalk Server 运行时无法与 MessageBox 数据库或管理数据库进行通信时，将出现 DBNetLib（数据库网络库）错误。 出现此错误时，捕获该异常的 BizTalk Server 运行时实例将关闭，然后每分钟检查一次该数据库是否可用。  
  
 导致 DBNetLib 错误的最常见原因是 MessageBox 数据库服务器之一（可能是多个）变得极其繁忙，进一步尝试与之进行通信会造成超时，而超时会导致出现 DBNetLib 异常。  
  
 除了 MessageBox 数据库十分繁忙的情况之外，在生产环境中，如果承载一个或多个 MessageBox 数据库的 BizTalk 数据库服务器受到 I/O（输入/输入出）限制，也会出现 DBNetLib 错误。  
  
 本主题说明可导致 DBNetLib 错误的情况和避免这些错误的建议。  
  
## <a name="cause-and-resolution-for-the-dbnetlib-error"></a>DBNetLib 错误的原因和解决方法  
  
### <a name="symptoms-of-a-dbnetlib-error"></a>DBNetLib 错误的症状  
 Microsoft BizTalk Server 主机实例终止，然后自行重新启动，类似以下的错误被写入 BizTalk Server 应用程序日志：  
  
```  
Event Type:Warning  
Event Source:BizTalk Server <version>  
Event Category:BizTalk Server <version>   
Event ID:5410  
Computer:BIZTALKSERVER  
Description:  
An error occurred that requires the BizTalk service to terminate. The most common causes are the following:  
 1) An unexpected out of memory error.  
 OR  
 2) An inability to connect or a loss of connectivity to one of the BizTalk databases.   
 The service will shutdown and auto-restart in 1 minute. If the problematic database remains unavailable, this cycle will repeat.  
  
 Error message: [DBNETLIB][ConnectionWrite (send()).]General network error. Check your network documentation.  
 Error source:    
  
 BizTalk host name: BizTalkHost  
 Windows service name: BTSSvc$BizTalkHost   
  
---------------------------------------------------------  
Event Type:Error  
Event Source:BizTalk Server <version>  
Event Category:BizTalk Server <version>   
Event ID:6913  
Computer:BIZTALKSERVER  
Description:  
An attempt to connect to "BizTalkMsgBoxDb" SQL Server database on server "SQLSERVER " failed.  
 Error: "[DBNETLIB][ConnectionWrite (send()).]General network error. Check your network documentation."  
```  
  
### <a name="biztalk-database-servers-hosting-messagebox-databases-becoming-io-bound"></a>MessageBox 数据库的宿主 BizTalk 数据库服务器受到 I/O 限制  
 BizTalk 服务器直接与 MessageBox 数据库的宿主数据库服务器进行通信和交互。 如果 MessageBox 数据库的任何宿主数据库服务器被过度占用，并受到 I/O（输入/输出）限制，它可能会停止响应。 BizTalk 服务器之一随后可能与这些数据库服务器中的一个断开连接，这时将出现 DBNetLib 错误。  
  
 我们的测试显示当以下情况出现时，被高度占用的数据库服务器将受到 I/O 限制：该数据库的物理磁盘的“%Idle 时间”继续降低并达到 10% 以下。 如果“%Idle 时间”继续降到该水平以下，这表示数据库服务器可能停止响应。  
  
#### <a name="cause"></a>原因  
 有多种原因可导致 MessageBox 数据库的宿主数据库服务器受到 I/O 限制，下面是其中一些原因：  
  
-   如果承载 MessageBox 数据库的数据库计算机绑定由低硬件规范，如： 低内存、 数量和速度的处理器等。  
  
-   MessageBox 数据库的宿主数据库计算机的物理磁盘正由其他被高度占用的数据库共享。 在多个数据库（包括 MessageBox）同时被高度占用的情况下，物理磁盘可能会受 I/O 限制。  
  
     此情况的示例如下：  
  
     我们的测试显示 BizTalkDTADb 和/或 BAM 数据库的宿主数据库服务器有时会占用高百分比的物理磁盘“%Disk 读写数”。 如果 MessageBox 数据库的宿主数据库服务器磁盘由其他被高度占用的数据库（例如 BizTalkDTADb 或 BAM）共享，并且这两个数据库同时被高度占用，它们可能导致该数据库服务器物理磁盘受到 I/O 限制，然后停止响应。  
  
-   当 BizTalkDTADb 与一个或多个 MessageBox 数据库共享数据库服务器上的同一物理磁盘时，如果不经常运行存档和清除，磁盘可能受到 I/O 限制。  
  
#### <a name="resolution"></a>解决方法  
 确保宿主 BizTalk MessageBox 的数据库服务器不会处于以下状况：被高度占用并可能停止响应。  
  
 下面列出服务器磁盘被高度占用的主要原因，并给出如何减轻此问题的建议。  
  
##### <a name="low-hardware-specs"></a>硬件规格较低  
 我们的测试显示当服务器的硬件规格不能维持它尝试处理的负载量时，该服务器会更大程度地被占用。 在硬件规格较低的情况下，数据库中发生的活动量将使系统迅速瘫痪。 这可能导致服务器的“%Disk 读写数”继续增加，不能稳定，同时磁盘的“%Idle 时间”继续降低并达到 10% 以下，这可能导致该数据库服务器停止响应。  
  
 如果你发现获得期间不响应数据库服务器对高负载，具体的活动和对你的 BizTalk 部署的负载量取决于，应考虑升级你的数据库服务器中的以下部分： Cpu、 内存的数并连接到 SAN。 当然，你应该进行适当的诊断，找出硬件中需要升级的瓶颈部分（内存、CPU 数量等）。  
  
##### <a name="sharing-one-server-or-disk-for-more-than-one-group-of-biztalk-databases"></a>多组 BizTalk 数据库共享一个服务器或磁盘  
 正如前面提到的，MessageBox 以外的数据库，例如 BizTalk 跟踪 (BizTalkDTADb) 数据库和 BAM 数据库，可能会大量占用服务器物理磁盘的周期。 因此，如果这些数据库碰巧与 MessageBox 数据库共享同一物理磁盘，它们可能会阻塞该磁盘并使其停止响应，从而导致 BizTalk 服务器与 MessageBox 数据库断开连接，并因此发生 DBNetLib 错误。  
  
 强烈建议你将任何需要大量占用服务器物理磁盘的数据库与 BizTalk MessageBox 分开，以便让它们使用不同的物理磁盘（或将它们分别放在不同的服务器上）。 建议将 BizTalkDTADb 和 BAM 分别放到其各自的驱动器/服务器上，与 MessageBox 分开，同时还建议将每个 MessageBox 数据库（有多个的情况下）放在其自己的磁盘上。  
  
##### <a name="archiving-and-purging"></a>存档和清除  
 当 BizTalkDTADb 和 MessageBox 数据库共享同一服务器上的同一磁盘时，必须定期存档和清除 BizTalkDTADb 数据库，否则它们会无限增大。  
  
 测试表明定期存档和清除是一个很好的做法，但是如果在超过正常水平的高负载下运行，你可能需要考虑更频繁地存档和清除。 如果没有定期针对 BizTalkDTADb 数据库的增长进行维护，则最后执行这些操作时，它们在运行期间可能会耗费相当长时间并占用大多数可用的数据库服务器资源。