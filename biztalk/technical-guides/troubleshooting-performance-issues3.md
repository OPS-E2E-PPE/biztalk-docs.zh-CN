---
title: 故障排除性能 Issues3 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a348c4b-7df2-43e9-810c-1f538a97d7e1
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40f7ae950a7078152d2952fb72ebe39303d41813
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998806"
---
# <a name="troubleshooting-performance-issues"></a>故障排除性能问题
本部分包含诊断的一般准则，解决性能问题与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]及其依赖项。 这些准则可能还用于抢先，关键问题之前找出潜在问题。  
  
## <a name="diagnosing-performance-problems-in-the-biztalk-server-environment"></a>BizTalk Server 环境中诊断性能问题  
 通常的性能问题可以缩小到的以下组件之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境：  
  
- 接收适配器或适配器正在从其接收文档的系统。 例如，如果文档在接收 HTTP 适配器以非最优的速率，则问题可能是使用 HTTP 接收适配器或发布到 HTTP 适配器的客户端。  
  
- 业务流程服务实例。  
  
- 性能[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]承载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。  
  
- 发送适配器或正接收此适配器发送的文档的系统。 例如，如果以非最优速率 SQL 适配器发送文档然后问题可能是与 SQL 发送适配器或运行的计算机[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]更新 SQL 适配器。  
  
  使用以下准则来帮助识别的各组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]较差的环境：  
  
- 捕获的任何警告或错误中生成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]事件查看器。  
  
- 在按照"识别性能瓶颈"中的步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkId=154238 ](http://go.microsoft.com/fwlink/?LinkId=154238)来帮助确定性能瓶颈。  
  
  确定了性能较差的组件后，请遵循以下相应的准则来帮助解决问题：  
  
  **解决相关来发送和接收适配器的性能问题的准则**  
  
- 有关问题进行故障排除信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器，请参阅中的"BizTalk Server 适配器故障排除"[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkId=154240 ](http://go.microsoft.com/fwlink/?LinkId=154240)。 本部分包含常规故障排除信息，包括有关如何设置日志记录对于某些适配器，信息和可用的信息诊断网络问题，问题与 MSDTC、 注册表、 文件出现问题的问题系统，并使用 IIS 的问题。  
  
- 有关与 MSDTC、 证书、 企业单一登录，故障排除信息和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，参阅中的相应部分的"故障排除 BizTalk Server 依赖项"[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkId=154242](http://go.microsoft.com/fwlink/?LinkId=154242).  
  
  **解决与业务流程相关的性能问题的准则**  
  
- 有关修改 BTSNTSvc.exe.config 文件的相应部分的信息，请参阅"业务流程引擎配置"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkId=154244 ](http://go.microsoft.com/fwlink/?LinkId=154244)。  
  
  **解决与 SQL Server 相关的性能问题的准则**  
  
- SQL Server Profiler 可用于捕获发送到的 TRANSACT-SQL 语句[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]这些语句的结果集。 由于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与紧密集成[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，分析[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]配置文件跟踪可以是用于分析中可能发生的问题的有用工具[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]读取和写入时[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库。 有关如何使用信息[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Profiler，请参阅中的"使用 SQL Server Profiler"[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]联机丛书，网址[ http://go.microsoft.com/fwlink/?linkid=104423 ](http://go.microsoft.com/fwlink/?linkid=104423)。  
  
- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio 可用于直接对执行 SQL 语句[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库。 此功能可能可用于查询[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库或用于更新[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在某些情况下的数据库。 有关使用 SQL Server Management Studio 执行 SQL 语句的详细信息，请参阅"编写、 分析，并使用 SQL Server Management Studio 的编辑脚本"中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]联机丛书，网址[ http://go.microsoft.com/fwlink/?linkid=104425 ](http://go.microsoft.com/fwlink/?linkid=104425)。  
  
- 有关解决与相关的性能问题的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请参阅"故障排除 SQL Server"，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkId=154250 ](http://go.microsoft.com/fwlink/?LinkId=154250)。  
  
## <a name="see-also"></a>请参阅  
 [http://go.microsoft.com/fwlink/?linkid=104430](http://go.microsoft.com/fwlink/?linkid=104430)