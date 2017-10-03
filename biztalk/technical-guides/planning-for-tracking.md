---
title: "规划对其进行跟踪 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ffc8573-1b4a-47c7-96ab-0471f43facf5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9853fccde9c5fa6e8c223106c8386f19298d0b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-tracking"></a>规划对其进行跟踪
邮件跟踪是依据的部分消息实例，如消息正文、 消息属性和元数据将存储在数据库中，通常用于存档目的的过程。 随后可以通过从中的组中心数据库页运行查询来查看跟踪的消息实例部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 除了访问已存档的数据，还可以查看实时数据，这可能非常有用的工具进行标识和修复开发中的问题或过渡环境。  
  
 由于消息跟踪的过程可能会消耗大量的资源，因此创建你的计划前应查看本主题。  
  
 有关跟踪的详细信息，请参阅[运行状况和活动跟踪](http://go.microsoft.com/fwlink/?LinkId=154187)(http://go.microsoft.com/fwlink/?LinkId=154187)。  
  
## <a name="configuring-and-enabling-the-dta-purge-and-archive-sql-agent-job"></a>配置和启用 DTA 清除和存档 SQL 代理作业  
 此作业存档和清除旧数据从 BizTalk 跟踪数据库，从而阻止将其变得太大。 这是必需的正常[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。 大型跟踪数据库将开始对跟踪主机和任何其他进程的性能影响该查询跟踪数据库。  
  
-   **确保 DTA 清除和存档 SQL 代理作业正确配置和启用，并且已成功完成。** 默认情况下不启用此作业，因为你必须首先将其配置为包括可以在其中写入存档文件的目录。  
  
-   **确保作业能够快速生成传入的跟踪数据清除的跟踪数据。** 是可以接受作业的计划全力支持在高峰负载，但它应始终能保持同步。 如果清除作业获取，并且永远不会是能够赶上，BizTalk 跟踪数据库将不断变大，，性能将最终会受到不利影响。  
  
-   **查看软清除并硬清除参数，以确保你一直在进行数据足够长的时间，但不是太长。** 有关这些参数的详细信息请参阅[存档和清除 BizTalk 跟踪数据库](http://go.microsoft.com/fwlink/?LinkID=153816)(http://go.microsoft.com/fwlink/?LinkID=153816)。  
  
-   **如果你只需以清除旧数据并不需要将其存档在第一次，然后更改 SQL 代理作业调用存储的过程"dtasp_PurgeTrackingDatabase"。** 这跳过存档步骤中，并只是执行清除。 有关详细信息，有关此存储的过程和更改 SQL 代理作业以使用它，请参阅[如何清除数据从 BizTalk 跟踪数据库](http://go.microsoft.com/fwlink/?LinkID=153817)(http://go.microsoft.com/fwlink/?LinkID=153817)。  
  
-   **如果你需要保留存档文件的 BizTalk 跟踪数据库，请确保你有一个进程的位置，以成功还原并使用它们。**  
  
-   **如果您遇到性能问题的暂时解决通过清除 BizTalk 跟踪数据库，并且你想要配置 BizTalk 不再收集跟踪信息，你可能想要考虑关闭全局跟踪。** 有关如何关闭全局跟踪的信息，请参阅主题[如何打开关闭全局跟踪](http://go.microsoft.com/fwlink/?LinkID=154193)(http://go.microsoft.com/fwlink/?LinkID=154193)。  
  
## <a name="creating-a-dedicated-tracking-host"></a>创建专用的跟踪主机  
 当选项**允许主机跟踪**在 BizTalk Server 管理控制台中，该主机的实例的主机将运行跟踪数据解码服务 (TDDS) 将跟踪的数据，从启用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox数据库部署到 BizTalk 跟踪数据库。 因为 TDDS 可能占用大量资源，请考虑创建的"专用"跟踪主机**允许主机跟踪**选项启用状态并且其不会运行任何其他[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进程 （如适配器或业务流程）。 如果你的 BizTalk 组包含多个 BizTalk server，它也被视为最佳做法 TDDS 为提供高可用性组中每个服务器上创建一个此主机的实例。  
  
## <a name="testing-to-measure-maximum-sustainable-tracking-throughput"></a>测试度量值最大可持续跟踪吞吐量  
 较详细跟踪的消息是一个非常资源密集型活动和如果未正确管理可以产生极负面的性能影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。 因此，应测量的最大可持续跟踪吞吐量你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境，以确保系统可持续，并将在给定的消息流入率无限期地运行。 有关测量最大可持续跟踪吞吐量的详细信息，请参阅[测量最大的可持续跟踪吞吐量](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815)。  
  
##  <a name="BKMK_TrackingBP"></a>跟踪的最佳实践  
  
-   **确定需要跟踪在规划过程的信息**： 你应决定在规划过程暂存需要跟踪，以便部署项目后你可以设置跟踪选项和限制的跟踪数据量的信息为你提供所需的信息。  
  
-   **不跟踪所有消息**： 我们建议你不都跟踪所有消息，因为每次一条消息接触，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使另一个副本。 通过跟踪特定端口，而是可以缩小范围。 这有助于你的系统的性能最大化，并以使数据库整洁。  
  
-   **在发送端口上设置跟踪和接收管道上的而不是端口**： 如果你设置跟踪选项卡上的管道，你还将设置使用管道的每个端口全局跟踪选项。 反过来，这可能会在导致被跟踪比你预期，这将降低系统性能的更多数据。 相反，你可以将端口设置跟踪选项卡上的发送和接收端口。  
  
-   **各种各样的因素时考虑大小 BizTalk 跟踪数据库**:  
  
    -   当 BizTalk 跟踪数据库的大小调整，帐户有关 SQL Server 的因素，如索引大小，通过将应变乘数添加到您的计算。  
  
    -   在确定 BizTalk 跟踪数据库中的消息的大小，将添加消息上下文的平均大小到的消息大小如果一点很重要，相比的消息大小。  
  
    -   将 BizTalk 跟踪数据库中的消息大小限制，限制在提升的属性的数目。 如果你需要这些路由目的应仅使用提升的属性，否则使用可分辨的字段。  
  
    -   如果业务流程**形状开始和结束**选项启用时，考虑到每个业务流程实例中的每个形状的启动和停止事件保存在 BizTalk 跟踪数据库的帐户。