---
title: "更新对跟踪 Analysis Server 数据库的引用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a403325-1394-4668-946f-01b610cb686e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94ed784eeca992d32f431a7c6794b7051b7595e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="update-references-to-the-tracking-analysis-server-database"></a>更新对跟踪 Analysis Server 数据库的引用
跟踪 Analysis Server 数据库是可选的并包含联机分析处理 (OLAP) 多维数据集。 这些 OLAP 多维数据集是 BizTalk 跟踪数据库中包含的数据的聚合。  
  
 若要还原的跟踪 Analysis Server 数据库，使用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis 管理器来处理 MessageMetrics 和 ServiceMetrics 多维数据集。 有关说明，请参阅[管理 Backing Up and Restoring (Analysis Services)](http://go.microsoft.com/fwlink/?LinkId=130939) (http://go.microsoft.com/fwlink/?LinkId=130939) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]联机丛书。  
  
 若要还原到备用计算机的跟踪 Analysis Server 数据库，还必须通过使用以下过程中更新对 BizTalk 管理数据库中的数据库名称的引用。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的身份登录，才能执行此过程。  
  
### <a name="to-update-references-to-the-tracking-analysis-server-database-name"></a>若要更新对跟踪 Analysis Server 数据库名称的引用  
  
1.  在目标系统上，单击**启动**，单击**程序**，单击**Microsoft SQL Server 2008**，然后单击**SQL Server Management Studio**.  
  
2.  在**连接到服务器**对话框中，选择**服务器类型**作为**数据库引擎**、 提供服务器名称，但提供凭据以连接到服务器，然后单击**连接**。  
  
3.  通过单击它，双击打开相应的服务器**数据库**，双击**BizTalkMgmtDb**，然后单击**表**。  
  
4.  在细节窗格中，右键单击**adm_Group**，然后指向**打开表**。  
  
5.  修改对应于原始数据库的列，以引用新数据库的相应值。  
  
    > [!NOTE]  
    >  *\<DBType >* DBServerName 和 *\<DBType >* DBName 指示的位置的数据库，其中 *\<DBType >*对应的类型数据库，例如，TrackingAnalysis。  
  
6.  关闭该表以保存新值。  
  
## <a name="see-also"></a>另请参阅  
 [更新数据库引用](../technical-guides/updating-database-references.md)