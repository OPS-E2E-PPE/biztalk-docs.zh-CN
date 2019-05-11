---
title: 避免出现 DBNETLIB 异常 |Microsoft Docs
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
ms.openlocfilehash: 6cc51bd9e997e4cca8526f855495b1ceec9f7e81
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358711"
---
# <a name="avoiding-dbnetlib-exceptions"></a>避免出现 DBNETLIB 异常
当 BizTalk Server 运行时无法与 MessageBox 或管理数据库进行通信时，将出现 DBNetLib （数据库网络库） 错误。 此操作时，会捕获此异常的 BizTalk Server 运行时实例关闭，然后循环每隔一分钟进行检查，请参阅数据库是否可用。  
  
 DBNetLib 错误的最常见原因是当其中一台 （可能是多个） MessageBox 数据库服务器变得极其繁忙，进一步与之进行通信的尝试导致超时，这会导致出现 DBNetLib 异常。  
  
 如果 MessageBox 数据库是十分繁忙，除了 DBNetLib 错误可以发生在生产环境中时其中一个的多个 MessageBox 数据库的宿主 BizTalk 数据库服务器受到 I/O （输入/输出） 限制。  
  
 本主题描述了可能会导致 DBNetLib 错误和建议避免这些错误的情况。  
  
## <a name="cause-and-resolution-for-the-dbnetlib-error"></a>原因和 DBNetLib 错误的解决方法  
  
### <a name="symptoms-of-a-dbnetlib-error"></a>DBNetLib 错误的症状  
 Microsoft BizTalk Server 主机实例将终止，然后重新启动自身，并类似于以下的错误写入到 BizTalk Server 应用程序日志：  
  
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
  
### <a name="biztalk-database-servers-hosting-messagebox-databases-becoming-io-bound"></a>受 I/O 的 MessageBox 数据库的宿主 BizTalk 数据库服务器绑定  
 BizTalk server 进行通信和直接与 MessageBox 数据库的宿主数据库服务器交互。 如果任何作为 MessageBox 数据库宿主的数据库服务器被过度占用，受到 I/O （输入/输出） 限制的情况下，则可能会停止响应。 BizTalk 服务器之一可能又会失去连接与这些数据库服务器之一，并将出现 DBNetLib 错误。  
  
 我们的测试显示被高度占用的数据库服务器将受到 I/O 限制时的物理磁盘的"%idle 时间"继续降低并达到 10%以下。 如果"%idle 时间"继续降到该级别，这是你的数据库服务器是可能变得无响应的指示。  
  
#### <a name="cause"></a>原因  
 有多种原因可导致 MessageBox 数据库受到 I/O 限制的宿主的数据库服务器，其中一些如下所示：  
  
-   如果 MessageBox 数据库的宿主数据库计算机绑定低的硬件规范，如： 低内存、 数量和速度的处理器等。  
  
-   如果 MessageBox 数据库的宿主数据库计算机上的物理磁盘是共享由其他高度占用的数据库。 在情况下时 （包括 MessageBox） 的多个数据库同时被高度占用一次物理磁盘会处于 I/O 绑定情况。  
  
     以下是此情况的一个示例：  
  
     我们有时会承载 BizTalkDTADb 和/或 BAM 数据库的数据库服务器占用高百分比的物理磁盘 %disk 读和写数的测试显示。 当承载 MessageBox 数据库的数据库服务器磁盘是正在由另一个高度占用的共享数据库，例如 BizTalkDTADb 或 BAM，并且如果这两个数据库同时被高度占用，则可能会导致数据库服务器的物理磁盘受到 I/O绑定，然后停止响应。  
  
-   如果 BizTalkDTADb 与一个或多个 MessageBox 数据库共享相同的物理磁盘的数据库服务器上，如果存档和清除不经常运行，该磁盘可能受到 I/O 限制。  
  
#### <a name="resolution"></a>解决方法  
 请确保承载 BizTalk MessageBox(s) 的数据库服务器不要进入这样的情况下，被高度占用并可能停止响应。  
  
 服务器磁盘被高度占用的主要原因下面列出了一些以及如何缓解此问题的建议。  
  
##### <a name="low-hardware-specs"></a>硬件规格较低  
 我们的测试表明，该服务器会更多使用时的硬件规格无法跟上它正在尝试处理的负载量。 硬件规格较低，系统通过在数据库上发生的活动量迅速瘫痪。 这可能会导致服务器的 %disk 读和写数继续增加，不能稳定，还磁盘的空闲时间百分比继续降低并达到 10%，这可能会导致你的数据库服务器停止响应。  
  
 根据活动和对 BizTalk 部署的负载量，如果您发现您听到负载较高的期间无响应的数据库服务器，则应考虑升级数据库服务器中的以下部分： Cpu、 内存的数目并连接到 SAN。 当然，您应该为适当的诊断，找出哪些部分 （内存、 Cpu 数量等） 是需要升级硬件中的瓶颈。  
  
##### <a name="sharing-one-server-or-disk-for-more-than-one-group-of-biztalk-databases"></a>共享一个服务器或多个组 BizTalk 数据库的磁盘  
 正如前面提到，以外 Messagebox 中，例如 BizTalk 跟踪 (BizTalkDTADb) 数据库和 BAM 数据库的数据库可能会占用服务器的物理磁盘上的高周期。 因此，如果这些数据库碰巧与 MessageBox 数据库中，共享相同的物理磁盘，则它们可能会阻塞该磁盘并使其停止响应，从而导致 BizTalk server 与 MessageBox 数据库的连接并因此发生 dbnetlib 错误。  
  
 强烈建议您分隔应具有大量占用服务器的物理磁盘从 BizTalk MessageBox(s)，因此它们共享不同的物理磁盘 （或将它们分不同的服务器上） 的任何数据库。 建议在其自己单独的驱动器/服务器上的 BizTalkDTADb 和 BAM 数据库分开 MessageBox(s)，并还建议将每个 MessageBox 数据库 （在这种情况，有多个） 在其自己的磁盘上。  
  
##### <a name="archiving-and-purging"></a>存档和清除  
 在这种情况有 BizTalkDTADb 和 MessageBox 数据库共享同一服务器上的同一磁盘时您必须存档和清除 BizTalkDTADb 数据库定期，否则为它们会无限增大。  
  
 测试表明它是很好的做法，定期存档和清除，但如果在比平时更高的负载下运行然后您可能需要考虑存档和更频繁地清除。 如果 BizTalkDTADb 数据库的增长速度不会保留定期，则最后执行这些操作时它们可能需要很长时间，并在运行时占用了大部分可用的数据库服务器资源。