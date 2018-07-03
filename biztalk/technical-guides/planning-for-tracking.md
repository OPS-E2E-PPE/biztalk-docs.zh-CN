---
title: 规划跟踪 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ffc8573-1b4a-47c7-96ab-0471f43facf5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0c45c61efee90b68efc927d88dbcf6429fe13e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973822"
---
# <a name="planning-for-tracking"></a>规划跟踪
跟踪的消息是所依据的部分消息实例，如消息正文、 消息属性和元数据存储在数据库中，通常出于存档目的的过程。 随后可以通过从中的组中心页运行查询来查看所跟踪的消息实例部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 除了访问存档的数据，还可以查看实时数据，可以是用于识别和解决问题在开发或过渡环境的有用工具。  
  
 由于消息跟踪的过程可能会消耗大量的资源，因此创建你的计划之前应该查看本主题。  
  
 有关跟踪的详细信息，请参阅[运行状况与活动跟踪](http://go.microsoft.com/fwlink/?LinkId=154187)(http://go.microsoft.com/fwlink/?LinkId=154187)。  
  
## <a name="configuring-and-enabling-the-dta-purge-and-archive-sql-agent-job"></a>配置和启用 DTA 清除和存档 SQL 代理作业  
 此作业中存档和清除旧数据从 BizTalk 跟踪数据库，从而阻止变得太大。 这是必需的正常[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。 大型跟踪数据库将开始跟踪主机和任何其他进程的性能影响该查询跟踪数据库。  
  
-   **请确保该 DTA 清除和存档 SQL 代理作业已正确配置和启用，并且已成功完成。** 默认情况下不启用此作业，因为必须先配置为包含在其中写入的存档文件的目录。  
  
-   **确保作业可以快速生成传入跟踪数据清除跟踪数据。** 可接受的作业以在负载高峰，全力支持，但它应始终能够保持同步。 如果清除作业落后，并且永远不会为能够保持同步，BizTalk 跟踪数据库会继续增加，并最终将产生负面影响性能。  
  
-   **查看软清除和硬清除参数，以确保你一直在进行数据足够长的时间，但不是太长。** 有关这些参数的详细信息请参阅[存档和清除 BizTalk 跟踪数据库](http://go.microsoft.com/fwlink/?LinkID=153816)(http://go.microsoft.com/fwlink/?LinkID=153816)。  
  
-   **如果您只需清除旧数据，则不需要将其存档在第一次，然后更改 SQL 代理作业来调用存储的过程"dtasp_PurgeTrackingDatabase"。** 这跳过存档步骤中，并只是执行清除。 有关更多相关信息的存储的过程和更改 SQL 代理作业以使用它，请参阅[如何从 BizTalk 跟踪数据库中清除数据](http://go.microsoft.com/fwlink/?LinkID=153817)(http://go.microsoft.com/fwlink/?LinkID=153817)。  
  
-   **如果你需要将 BizTalk 跟踪数据库保留在存档文件，请确保你有一个进程已成功还原和使用它们。**  
  
-   **如果您遇到暂时解决通过清除 BizTalk 跟踪数据库的性能问题，并且你想要配置 BizTalk，不再收集跟踪信息，你可能想要考虑禁用全局跟踪。** 有关如何禁用全局跟踪的信息，请参阅主题[如何禁用全局跟踪](http://go.microsoft.com/fwlink/?LinkID=154193)(http://go.microsoft.com/fwlink/?LinkID=154193)。  
  
## <a name="creating-a-dedicated-tracking-host"></a>创建专用的跟踪主机  
 当选项**允许主机跟踪**的主机在 BizTalk Server 管理控制台中，该主机的实例将运行跟踪数据解码服务 (TDDS) 移动跟踪的数据，从启用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox数据库部署到 BizTalk 跟踪数据库。 因为 TDDS 可能占用大量资源，请考虑创建的"专用"跟踪主机**允许主机跟踪**选项处于启用状态，这不会运行任何其他[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进程 （例如适配器或业务流程）。 如果你的 BizTalk 组包含多个 BizTalk 服务器，它也被视为最佳做法为 TDDS 提供高可用性组中每个服务器上创建此主机的实例。  
  
## <a name="testing-to-measure-maximum-sustainable-tracking-throughput"></a>测试与度量值的最大可承受跟踪吞吐量  
 较详细跟踪的消息是大量的资源密集型活动，如果未得到正确管理可以产生的性能非常不利影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。 因此，应度量值的最大可承受跟踪吞吐量你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境，以确保系统具有可持续性并以给定的消息流速率将无限期地运行。 测量最大可承受跟踪吞吐量的详细信息，请参阅[测量的最大可承受跟踪吞吐量](http://go.microsoft.com/fwlink/?LinkID=153815)(<http://go.microsoft.com/fwlink/?LinkID=153815>)。  
  
##  <a name="BKMK_TrackingBP"></a> 跟踪的最佳做法  
  
- **确定您需要在规划期间跟踪的信息**： 您应决定期间的规划阶段所需跟踪，以便部署项目后你可以设置跟踪选项并限制跟踪到的数据量的信息为您提供所需的信息。  
  
- **不要跟踪所有消息**： 我们建议不都跟踪所有消息，因为每次访问消息时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将生成另一个副本。 而是可以通过跟踪特定端口来缩小范围。 这可以帮助您的系统性能最大化和保持数据库整洁。  
  
- **将发送端口上设置跟踪和接收端口而不是在管道上的**： 如果设置管道的跟踪选项，则还将设置为使用的管道的每个端口全局跟踪选项。 反过来，这可能会在导致被跟踪比你预期，这将降低系统性能的更多数据。 相反，您可以设置跟踪选项上的发送端口和接收端口。  
  
- **请考虑各种因素时调整 BizTalk 跟踪数据库的大小**:  
  
  -   调整 BizTalk 跟踪数据库的大小时，可以通过将应变乘数添加到你的计算考虑 SQL Server 因素，例如，索引大小。  
  
  -   在确定 BizTalk 跟踪数据库中的消息的大小，消息上下文的平均大小为消息大小如果添加这一点非常重要的消息大小。  
  
  -   将 BizTalk 跟踪数据库中的消息大小限制，限制提升的属性的数目。 如果需要用于路由目的应仅使用升级属性，否则使用可分辨的字段。  
  
  -   如果业务流程**形状开始和结束**选项处于启用状态，请考虑每个业务流程实例中的每个形状的开始和停止事件保存在 BizTalk 跟踪数据库中。