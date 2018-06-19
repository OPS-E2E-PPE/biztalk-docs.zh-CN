---
title: 工具和实用程序可用于故障排除 |Microsoft 文档
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
ms.openlocfilehash: 086c7144d39b459a342e3c4f6c5c87f669fffedc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302381"
---
# <a name="tools-and-utilities-for-troubleshooting"></a>工具和实用程序可用于故障排除
本主题介绍几个工具和实用程序可用于诊断 Microsoft 中的问题的根本原因[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组件或依赖项。  
  
|故障排除|工具|改用|  
|---------------------|----------|---------|  
|**SQL Server 故障排除**|SQL 活动监视器|SQL Server 2008 活动监视器提供有关 SQL Server 过程和了解这些进程如何影响当前的 SQL Server 实例的信息。 有关 SQL Server 2008 活动监视器的详细信息，请参阅[活动监视器](http://go.microsoft.com/fwlink/?LinkId=146355)(http://go.microsoft.com/fwlink/?LinkId=146355) SQL Server 文档中。 有关如何从 SQL Server Management Studio 中打开活动监视器的信息，请参阅[如何： 打开活动监视器 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=135094) (http://go.microsoft.com/fwlink/?LinkId=135094) SQL Server 文档中。|  
||SQL Server 2008 数据收集|SQL Server 2008 提供了可用于获取和保存数据，则通过多个来源收集的数据收集器。 数据收集器，可使用使你可以确定的范围和频率的运行 SQL Server 2008 的计算机上的数据收集的数据集合容器。 有关实现 SQL Server 2008 数据收集的详细信息，请参阅[数据收集](http://go.microsoft.com/fwlink/?LinkId=146356)(http://go.microsoft.com/fwlink/?LinkId=146356) SQL Server 文档中。|  
||**与性能相关故障排除**|重新记录实用程序可用于从由性能监视器创建的日志提取性能计数器，并将数据转换为其他格式，如制表符分隔的文本文件 (文本 TSV)、 以逗号分隔的文本文件 (CSV 文本)、 二进制文件和 SQL 数据库。 此数据可以再进行分析，并且查询使用诸如 Log Parser 之类的其他工具来为关键绩效指标 (Kpi) 生成统计信息。 重新记录实用程序随 Windows Server 2003 和后续版本提供。|  
|Windows 性能分析工具||Windows 性能工具旨在为大量的性能问题，包括应用程序开始时间，启动问题的分析延迟过程调用和中断活动 （Dpc 和 Isr） 系统的响应能力问题，应用程序资源使用情况和中断风暴。 有关详细信息，请参阅[Windows 性能分析开发人员中心](http://go.microsoft.com/fwlink/?LinkId=139763)(http://go.microsoft.com/fwlink/?LinkId=139763)。|  
|Pathping||Pathping 上某个目标主机的方式提供有关在一个或多个路由器跃点处的数据可能丢失的信息。 为此，请 pathping 将 Internet 控制消息协议 (ICMP) 数据包发送到路径中的每个路由器中。 Windows 2000 Server 以来 Pathping.exe 是适用于 Windows 的所有版本。|  
|IOMeter||IOMeter 是用于测量磁盘输入/输出性能的开放源工具。 有关详细信息，请参阅[IOMeter](http://go.microsoft.com/fwlink/?LinkId=122412) (http://go.microsoft.com/fwlink/?LinkId=122412)。 **重要说明：** Microsoft，不支持使用此工具和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。|  
|**常规故障排除**|事件查看器<br />网络监视器<br />SQL Server 事件探查器<br />SQL Server 查询编辑器<br />-DTCTester<br />-DTCPing<br />性能控制台<br />-RegMon<br />-FileMon<br />-调试诊断工具的 IIS 诊断工具包|请参阅[工具和实用程序用于故障排除](http://go.microsoft.com/fwlink/?LinkId=154416)(http://go.microsoft.com/fwlink/?LinkId=154416)。|  
  
## <a name="see-also"></a>另请参阅  
 [用于测试工具](../technical-guides/tools-for-testing.md)   
 [清单： 配置 BizTalk Server](~/technical-guides/checklist-configuring-biztalk-server.md)