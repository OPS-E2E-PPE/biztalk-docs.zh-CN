---
title: "清除和存档跟踪数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14094fda-3fd9-4d45-9bbb-cd9377c2cbad
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94a2560bc8a57a8f60bf2d1ebcddf68b62fd178a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="purging-and-archiving-tracking-data"></a>清除和存档跟踪数据
务必要配置并启用 DTA 清除和存档 SQL 代理作业。 此作业存档，并从 BizTalk 跟踪 (DTA) 数据库中清除旧数据。 这是必需的正常[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。 大型的跟踪数据库将开始对跟踪主机和任何其他进程的性能影响该查询跟踪数据库。 如果跟踪数据不会清除从跟踪数据库，数据库将继续增长。  
  
## <a name="guidelines-for-using-the-dta-purge-and-archive-job"></a>使用 DTA 的指导原则清除和存档作业  
  
-   **确保 DTA 清除和存档 SQL 代理作业正确配置和启用，并且已成功完成。**  
  
     默认情况下不启用此作业，因为你必须首先将其配置为包括可以在其中写入存档文件的目录。  
  
-   **如果你只需以清除旧数据并不需要将其存档在第一次，然后更改 SQL 代理作业调用存储的过程"dtasp_PurgeTrackingDatabase"。**  
  
     这跳过存档步骤中，并只是执行清除。 有关详细信息，有关此存储的过程和更改 SQL 代理作业以使用它，请参阅["如何清除数据从 BizTalk 跟踪数据库的"](http://go.microsoft.com/fwlink/?LinkId=153817) (http://go.microsoft.com/fwlink/?LinkId=153817)。  
  
-   **确保作业能够快速生成传入的跟踪数据清除的跟踪数据。**  
  
     是可以接受作业的计划全力支持在高峰负载，但它应始终能保持同步。 如果清除作业获取，并且永远不会是能够赶上，跟踪数据库将不断变大，，性能将最终会受到不利影响。  
  
-   **查看软清除并硬清除参数，以确保你保存的数据的最佳总时间。**  
  
     有关这些参数的详细信息请参阅["存档和清除 BizTalk 跟踪数据库"](http://go.microsoft.com/fwlink/?LinkId=153816) (http://go.microsoft.com/fwlink/?LinkId=153816)。  
  
-   **如果你需要保留跟踪存档文件，请确保你有一个进程的位置，以成功还原并使用它们。**  
  
## <a name="see-also"></a>另请参阅  
 [清单： 配置 SQL Server](~/technical-guides/checklist-configuring-sql-server.md)