---
title: "用于测试工具 |Microsoft 文档"
ms.custom: 
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a9b71f02-86df-4b03-bd2c-4d4d2014db02
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e88bfee5d45cc1cc7bdc93d8dd50aeb1841e3a28
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="tools-for-testing"></a>用于测试工具
下表列出了可用于执行测试的操作的准备情况与关联的工具[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
|测试|工具|改用|  
|-------------|----------|---------|  
|**单元和功能测试**|Microsoft Visual Studio|用于.NET 代码进行单元测试。 有关适用于 Visual Studio 的测试功能的详细信息，请参阅[测试应用程序](http://go.microsoft.com/fwlink/?LinkId=159595)(http://go.microsoft.com/fwlink/?LinkId=159595)。|  
||BizUnit|为自动测试的 BizTalk 解决方案而设计的一种框架。 **注意：** Microsoft，不支持使用此工具和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。 <br /><br /> 有关 BizUnit 的详细信息，请参阅[BizUnit-框架，用于自动分布式系统的测试](http://go.microsoft.com/fwlink/?LinkID=85168)(http://go.microsoft.com/fwlink/?LinkID=85168)。|  
||NUnit|用于.NET 代码进行单元测试。 **注意：** Microsoft，不支持使用此工具和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。 <br /><br /> 有关使用 NUnit 的详细信息，请参阅[Nunit](http://go.microsoft.com/fwlink/?LinkID=47931) (http://go.microsoft.com/fwlink/?LinkID=47931)。|  
|**代码覆盖率测试**|Visual Studio 2010 代码覆盖率|用于以确保，通过应用程序的所有执行路径充分执行都测试，并确定死函数或在代码中的类。 一般情况下，应删除无法访问或永远不会执行的代码。 有关代码覆盖率功能的 Microsoft Visual Studio 2010 的详细信息请参阅[使用代码覆盖率确定如何正在测试的代码量](http://go.microsoft.com/fwlink/?LinkId=210624)(http://go.microsoft.com/fwlink/?LinkId=210624)。|  
|**性能测试**|性能分析的日志 (PAL) 工具|用于分析性能计数器日志文件的工具。<br /><br /> 有关性能分析的日志 (PAL) 工具的详细信息，请参阅[性能分析的日志 (PAL) 工具](https://github.com/clinthuffman/PAL)。|  
||Microsoft BizTalk LoadGen 2007 工具|负载生成工具用于运行性能和压力测试针对[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。<br /><br /> 下载[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)|  
||Visual Studio 2010 负载测试|Visual Studio 2010 旗舰版中可用，可以模拟从默认情况下，最多 250 个用户和使用 Visual Studio 负载测试虚拟用户包超过 250 名用户的负载。 有关执行负载测试使用 Visual Studio 的详细信息请参阅[测试应用程序性能和压力](http://go.microsoft.com/fwlink/?LinkId=203129)(http://go.microsoft.com/fwlink/?LinkId=203129)。|  
||[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]业务流程探查器|用于查看指定时间内; 跟踪数据的业务流程用于确定在业务流程中存在性能瓶颈，很有帮助。 **注意：** Microsoft，不支持使用此工具和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。 <br /><br /> 有关详细信息[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]Orchestration 探查器，请参阅[BizTalk Server 2006 Orchestration 事件探查器](http://go.microsoft.com/fwlink/?LinkId=102209)(http://go.microsoft.com/fwlink/?LinkId=102209)。|  
|**Web 服务测试**|soapUI|一种开放源代码实用程序，可以用于测试 Web 服务。 **注意：** Microsoft，不支持使用此工具和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。 <br /><br /> 有关 soapUI 的详细信息，请参阅[soapUI.org](http://go.microsoft.com/fwlink/?LinkId=102196) (http://go.microsoft.com/fwlink/?LinkId=102196)。|  
||Fiddler|有助于查看 HTTP 流量"的应用程序。" 有关使用 Fiddler 工具进行调试 HTTP 的详细信息，请参阅[Fiddler PowerToy-第 1 部分： HTTP 调试](http://go.microsoft.com/fwlink/?LinkID=84796)(http://go.microsoft.com/fwlink/?LinkID=84796)。 **注意：** Microsoft，不支持使用此工具和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。 <br /><br /> 可以从下载 Fiddler 工具[简介 Fiddler](http://go.microsoft.com/fwlink/?LinkID=99357) (http://go.microsoft.com/fwlink/?LinkID=99357)。|  
|**调试**|DebugView|用于监视内核模式和 Win32 调试输出本地或远程工具。<br /><br /> DebugView 有关的详细信息，请参阅[DebugView for Windows](http://go.microsoft.com/fwlink/?LinkId=102210) (http://go.microsoft.com/fwlink/?LinkId=102210)。|  
||BizTalk MsgBoxViewer|分析 BizTalk MessageBox 和其他数据库并生成 HTML 报告包含警告，如果与数据库相关的任何，和其他信息。 **注意：** Microsoft，不支持使用此工具和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。 <br /><br /> 可以从下载 BizTalk MsgBoxViewer 工具[BizTalk MsgBoxViewer-从此处下载该工具的最新版本](http://go.microsoft.com/fwlink/?LinkId=151930)(http://go.microsoft.com/fwlink/?LinkId=151930)。|  
||终止符|解析由 BizTalk MsgBoxViewer 工具发现的任何问题。 有关如何与 BizTalk MsgBoxViewer 工具集成终止符工具的详细信息，请参阅[使用 BizTalk 终止符，若要解决问题由 BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932) (http://go.microsoft.com/fwlink/?LinkId=151932)。 **注意：** Microsoft，不支持使用此工具和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。 <br /><br /> 可以从下载终止符工具[终止符](http://go.microsoft.com/fwlink/?LinkId=151931)(http://go.microsoft.com/fwlink/?LinkId=151931)。|  
||BizTalk Server 最佳做法分析器|BizTalk Server 最佳做法分析器检查 BizTalk Server 部署，并生成与最佳做法标准相关的问题的列表。 该工具执行配置级别验证从不同的信息源，例如 Windows Management Instrumentation (WMI) 类、 SQL Server 数据库和注册表项收集数据。 数据然后用于评估部署配置。 该工具读取和仅限报告并不会修改任何系统设置，并不是自我调整工具。<br /><br /> BizTalk Server 最佳做法分析器工具可以从下载[BizTalk Server 最佳做法分析器](http://go.microsoft.com/fwlink/?LinkId=83317)(http://go.microsoft.com/fwlink/?LinkId=83317)。|  
  
## <a name="see-also"></a>另请参阅  
 [清单：测试操作准备情况](~/technical-guides/checklist-testing-operational-readiness.md)