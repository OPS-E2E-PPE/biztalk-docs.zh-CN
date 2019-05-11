---
title: 清除和存档跟踪数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14094fda-3fd9-4d45-9bbb-cd9377c2cbad
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f18b65d8e33a7a651d743f0ff6cd3292396189a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399555"
---
# <a name="purging-and-archiving-tracking-data"></a>清除和存档跟踪数据
若要配置和启用 DTA 清除和存档 SQL 代理作业至关重要。 此作业存档和清除 BizTalk 跟踪 (DTA) 数据库中的旧数据。 这是必需的正常[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。 大型的跟踪数据库将开始跟踪主机和任何其他进程的性能影响该查询跟踪数据库。 如果从跟踪数据库不清除跟踪数据，则数据库将继续增长。  
  
## <a name="guidelines-for-using-the-dta-purge-and-archive-job"></a>使用 DTA 的准则清除和存档作业  
  
-   **请确保该 DTA 清除和存档 SQL 代理作业已正确配置和启用，并且已成功完成。**  
  
     默认情况下不启用此作业，因为必须先配置为包含在其中写入的存档文件的目录。  
  
-   **如果您只需清除旧数据，则不需要将其存档在第一次，然后更改 SQL 代理作业来调用存储的过程"dtasp_PurgeTrackingDatabase"。**  
  
     这跳过存档步骤中，并只是执行清除。 有关更多相关信息的存储的过程和更改 SQL 代理作业以使用它，请参阅["如何清除数据从 BizTalk 跟踪数据库的"](http://go.microsoft.com/fwlink/?LinkId=153817) (http://go.microsoft.com/fwlink/?LinkId=153817)。  
  
-   **确保作业可以快速生成传入跟踪数据清除跟踪数据。**  
  
     可接受的作业以在负载高峰，全力支持，但它应始终能够保持同步。 如果清除作业落后，并且永远不会为能够保持同步，跟踪数据库会继续增加，并最终将产生负面影响性能。  
  
-   **查看软清除和硬清除参数，以确保保持最佳的时间长度的数据。**  
  
     有关这些参数的详细信息请参阅["存档和清除 BizTalk 跟踪数据库"](http://go.microsoft.com/fwlink/?LinkId=153816) (http://go.microsoft.com/fwlink/?LinkId=153816)。  
  
-   **如果需要保留跟踪存档文件，请确保你有一个进程已成功还原和使用它们。**  
  
## <a name="see-also"></a>请参阅  
 [清单：配置 SQL Server](~/technical-guides/checklist-configuring-sql-server.md)