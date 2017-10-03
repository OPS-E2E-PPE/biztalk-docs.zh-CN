---
title: "如何更新对 BAM 存档数据库名称的引用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Archive database [BAM], restoring
- restoring, BAM
- restoring [BAM], Archive database
- restoring [BAM], updating references
- Archive database [BAM], updating references
- BAM, restoring
ms.assetid: a0b8543e-6fc1-412e-b74e-683352d9c49e
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0df87a548c2a6a5a207673d96a984e16287f04a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-references-to-the-bam-archive-database-name"></a>如何更新对 BAM 存档数据库名称的引用
如果备份了 BAMArchive 数据库，则在系统或数据发生故障时，可以还原该备份，然后重新命名它。  
  
 若要还原 BAMArchive 数据库，执行中的步骤[如何还原您的数据库](../core/how-to-restore-your-databases.md)。 此外，你必须执行下列常规步骤后, 跟一个描述各步骤的详细信息的过程：  
  
-   使用新的服务器名称和数据库名称更新 BAM DTS 包。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的身份登录，才能执行此过程。  
  
### <a name="to-update-references-to-the-bam-archive-database-name-sql-server-2008-r2sp1"></a>更新对 BAM 存档数据库名称的引用 (SQL Server 2008 R2/SP1)  
  
1.  停止任何 BAM 多维数据集更新和数据维护 DTS 包，或者阻止它们运行，直到 BAMArchive 数据库的还原完成为止。  
  
2.  停止 BizTalk 应用程序服务 （其中包括 BAM 事件总线服务） 以便不会尝试将更多的数据导入到数据库。  
  
    1.  单击**启动**，单击**运行**，然后键入**services.msc**。  
  
    2.  右键单击**BizTalk 服务 BizTalk 组： BizTalkServerApplication**服务，然后单击**停止**。  
  
3.  单击**启动**，单击**程序**，单击**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Business Intelligence Development Studio**.  
  
4.  在 SQL Server Business Intelligence Development Studio 中，创建一个新项目。 单击**文件**，单击**新建**，然后单击**项目**。  
  
5.  在**新项目**对话框中，在**模板**，单击**Integration Services 项目**，然后单击**确定**。  
  
6.  在**Integration Services 项目**对话框中，在**解决方案资源管理器**，右键单击**SSIS 包**，然后单击**添加现有包**.  
  
7.  在**添加现有包副本**对话框中，在**服务器**下拉列表框中，选择包含 BAM_DM 包的服务器。  
  
8.  在**包路径**，单击省略号按钮。  
  
9. 在**SSIS 包**对话框框中，选择 BAM_DM 包，单击**确定**，然后单击**确定**。  
  
     现在，该包列在解决方案资源管理器中。  
  
10. 在**解决方案资源管理器**，双击 BAM_DM 包。 在**连接管理器**，双击数据库的编号 3 （MSDB 数据库）。  
  
11. 在**连接管理器**对话框中，在**服务器名称**框中，输入 MSDB 服务器的名称，然后单击**确定**。  
  
12. 单击**包资源管理器**选项卡上，双击**变量**文件夹，然后更新主导入服务器名称和主的值导入数据库名称。  
  
13. 单击**文件**，然后单击**保存所有**。  
  
14. 在**Microsoft SQL Server Management Studio**，单击**连接**。  
  
15. 单击**Integration Services**，双击**存储的包**，单击**MSDB**，右击 BAM_DM 包，然后单击**导入包**.  
  
16. 在**导入包**对话框中，在**包位置**，选择**文件系统**。  
  
17. 在**包路径**，导航到已保存项目，选择 BAM_DM\*.dtsx 文件，然后单击**打开**。  
  
18. 在内部单击**包名称**框以在框中自动填充。  
  
19. 单击**确定**，然后单击**是**覆盖。  
  
20. 重新启动 BizTalk 应用程序服务。  
  
    1.  单击**启动**，单击**运行**，然后键入**services.msc**。  
  
    2.  右键单击**BizTalk 服务 BizTalk 组： BizTalkServerApplication**服务，然后单击**启动**。  
  
21. 启用任何 BAM 多维数据集更新和数据维护 SSIS 包。  
  
## <a name="see-also"></a>另请参阅  
 [备份和还原 BAM](../core/backing-up-and-restoring-bam.md)