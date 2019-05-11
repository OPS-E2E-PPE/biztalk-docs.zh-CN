---
title: 工具和实用程序进行故障排除 |Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56b0946a-56de-47cd-95d9-365722cdbaed
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 069df3178612c86f56552e7863aa7b9d6fa2ccf5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401191"
---
# <a name="tools-and-utilities-for-troubleshooting"></a>工具和实用程序进行故障排除
本主题介绍几个工具和实用程序，也可用于诊断 Microsoft 中的问题的根本原因[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组件或依存关系。  
  
|疑难解答|Tool|改用|  
|---------------------|----------|---------|  
|**SQL Server 故障排除**|SQL 活动监视器|SQL Server 2008 活动监视器提供了有关 SQL Server 进程以及这些进程如何影响 SQL Server 的当前实例的信息。 有关 SQL Server 2008 活动监视器的详细信息，请参阅[活动监视器](http://go.microsoft.com/fwlink/?LinkId=146355)(http://go.microsoft.com/fwlink/?LinkId=146355) SQL Server 文档中。 有关如何从 SQL Server Management Studio 中打开活动监视器的信息，请参阅[如何：打开活动监视器 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=135094) (http://go.microsoft.com/fwlink/?LinkId=135094) SQL Server 文档中。|  
||SQL Server 2008 数据收集|SQL Server 2008 提供了一个数据收集器，可用于获取和保存从多个源收集的数据。 数据收集器，可使用数据收集容器，使您能够确定作用域和运行 SQL Server 2008 的计算机上的数据收集的频率。 有关实现 SQL Server 2008 数据集合详细信息，请参阅[数据收集](http://go.microsoft.com/fwlink/?LinkId=146356)(http://go.microsoft.com/fwlink/?LinkId=146356) SQL Server 文档中。|  
||**与性能相关的疑难解答**|重新记录实用工具用于从性能监视器创建的日志提取性能计数器，并将数据转换成其他格式，如制表符分隔的文本文件 (文本 TSV)、 逗号分隔的文本文件 (文本 CSV)、 二进制文件和 SQL 数据库。 此数据可以再进行分析，使用诸如 Log Parser 之类的其他工具来生成关键绩效指标 (Kpi) 的统计信息查询。 重新记录实用程序附带了 Windows Server 2003 和后续版本。|  
|Windows 性能分析工具||Windows 性能工具专为分析范围广泛的性能问题，包括应用程序启动时间，启动问题的延迟过程调用并中断活动 （Dpc 和 Isr） 系统响应能力问题，应用程序资源使用情况和中断风暴。 有关详细信息，请参阅[Windows 性能分析开发人员中心](http://go.microsoft.com/fwlink/?LinkId=139763)(http://go.microsoft.com/fwlink/?LinkId=139763)。|  
|pathping||Pathping 上某个目标主机的方式提供有关在一个或多个路由器跃点处的数据可能丢失的信息。 为此，请 pathping 将 Internet 控制消息协议 (ICMP) 数据包发送到路径中每个路由器中。 Windows 2000 Server 以来 Pathping.exe 是所有版本的 Windows 中提供的。|  
|IOMeter||IOMeter 是用于测量磁盘 I/O 性能的开放源代码工具。 有关详细信息，请参阅[IOMeter](http://go.microsoft.com/fwlink/?LinkId=122412) (http://go.microsoft.com/fwlink/?LinkId=122412)。 **重要提示：** 使用此工具不受 Microsoft，因此 Microsoft 不保证此程序的适用性。 使用此程序是完全由您自己承担。|  
|**常规故障排除**|-事件查看器<br />-网络监视器<br />SQL Server Profiler<br />SQL Server 查询编辑器<br />-   DTCTester<br />-DTCPing<br />性能控制台<br />-   RegMon<br />-   FileMon<br />-Debug IIS 诊断工具包的诊断工具|请参阅[工具和实用程序用于故障排除](http://go.microsoft.com/fwlink/?LinkId=154416)(http://go.microsoft.com/fwlink/?LinkId=154416)。|  
  
## <a name="see-also"></a>请参阅  
 [测试工具](../technical-guides/tools-for-testing.md)   
 [清单：配置 BizTalk Server](~/technical-guides/checklist-configuring-biztalk-server.md)