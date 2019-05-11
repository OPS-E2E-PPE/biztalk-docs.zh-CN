---
title: 如何更新对 BAM 存档数据库名称的引用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Archive database [BAM], restoring
- restoring, BAM
- restoring [BAM], Archive database
- restoring [BAM], updating references
- Archive database [BAM], updating references
- BAM, restoring
ms.assetid: a0b8543e-6fc1-412e-b74e-683352d9c49e
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3fcba19a3852a70c402276fed1ca56ea1b8f0c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333716"
---
# <a name="how-to-update-references-to-the-bam-archive-database-name"></a>如何更新对 BAM 存档数据库名称的引用
如果备份了 BAMArchive 数据库，在系统或数据发生故障时可以还原该备份并将其重命名。  
  
 若要还原 BAMArchive 数据库，请执行中的步骤[如何还原您数据库](../core/how-to-restore-your-databases.md)。 此外，还必须执行下列常规步骤后, 跟介绍详细信息中的步骤的过程：  
  
-   使用新的服务器名称和数据库名称更新 BAM DTS 包。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组才能执行此过程。  
  
### <a name="to-update-references-to-the-bam-archive-database-name-sql-server-2008-r2sp1"></a>若要更新对 BAM 存档数据库名称 (SQL Server 2008 R2/SP1) 的引用  
  
1.  停止任何 BAM 多维数据集更新和数据维护 DTS 包，或者阻止它们运行，直到 BAMArchive 数据库的还原。  
  
2.  停止 BizTalk 应用程序服务 （其中包括 BAM 事件总线服务） 以便不会尝试导入数据库的更多的数据。  
  
    1.  单击**启动**，单击**运行**，然后键入**services.msc**。  
  
    2.  右键单击**BizTalk 服务 BizTalk 组：BizTalkServerApplication**服务，然后单击**停止**。  
  
3.  单击**启动**，单击**程序**，单击**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Business Intelligence Development Studio**.  
  
4.  在 SQL Server Business Intelligence Development Studio，创建新项目。 单击**文件**，单击**新建**，然后单击**项目**。  
  
5.  在中**新的项目**对话框中**模板**，单击**Integration Services 项目**，然后单击**确定**。  
  
6.  在中**Integration Services 项目**对话框中**解决方案资源管理器**，右键单击**SSIS 包**，然后单击**添加现有包**.  
  
7.  在中**添加现有包副本**对话框中**Server**下拉列表框中，选择包含 BAM_DM 包的服务器。  
  
8.  在中**包路径**，请单击省略号按钮。  
  
9. 在中**SSIS 包**对话框框中，选择 BAM_DM 包，单击**确定**，然后单击**确定**。  
  
     包现在列在解决方案资源管理器。  
  
10. 在中**解决方案资源管理器**，双击该 BAM_DM 包。 在中**连接管理器**，双击数据库编号 3(MSDB 数据库）。  
  
11. 在中**连接管理器**对话框中**服务器名称**框中，输入 MSDB 服务器的名称，然后单击**确定**。  
  
12. 单击**包资源管理器**选项卡上，双击**变量**文件夹，然后更新主导入服务器名称和主键的值导入数据库名称。  
  
13. 单击**文件**，然后单击**全部保存**。  
  
14. 在中**Microsoft SQL Server Management Studio**，单击**Connect**。  
  
15. 单击**Integration Services**，双击**存储的包**，单击**MSDB**，右键单击该 BAM_DM 包，并单击**导入包**.  
  
16. 在中**导入包**对话框中**包位置**，选择**文件系统**。  
  
17. 在中**包路径**，导航到保存的项目，选择 BAM_DM\*.dtsx 文件，然后单击**打开**。  
  
18. 在单击**包名称**框以自动填充此框。  
  
19. 单击**确定**，然后单击**是**覆盖。  
  
20. 重新启动 BizTalk 应用程序服务。  
  
    1.  单击**启动**，单击**运行**，然后键入**services.msc**。  
  
    2.  右键单击**BizTalk 服务 BizTalk 组：BizTalkServerApplication**服务，然后单击**启动**。  
  
21. 启用任何 BAM 多维数据集更新和数据维护 SSIS 包。  
  
## <a name="see-also"></a>请参阅  
 [备份和还原 BAM](../core/backing-up-and-restoring-bam.md)