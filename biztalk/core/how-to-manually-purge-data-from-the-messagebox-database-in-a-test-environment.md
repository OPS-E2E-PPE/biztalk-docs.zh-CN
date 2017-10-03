---
title: "如何手动清除数据，从测试环境中的 MessageBox 数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 398991a9-344a-487a-a817-dfc97d48ebe6
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4a6d5f8b232e31a140ee4786b87d2bb270505f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-manually-purge-data-from-the-messagebox-database-in-a-test-environment"></a>如何在测试环境中从 MessageBox 数据库中手动清除数据
在开发或测试环境中运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时，MessageBox 数据库中存储的数据通常不是业务关键的“实时”数据，因此可能会被删除。 在这些情况下，可能需要一个“快速和更新”的方法将数据从 MessageBox 数据库清除。 按照本主题中的过程，使用 bts_CleanupMsgbox 存储过程将数据从 MessageBox 数据库手动清除。  
  
> [!NOTE]
>  应该只在测试环境中执行这些步骤。 不支持在生产环境中手动清除 BizTalk MessageBox 数据库。  
  
### <a name="to-stop-biztalk-services"></a>停止 BizTalk 服务  
  
1.  从 Services 控制台停止 BizTalk 服务的任何实例。  
  
2.  如果正在运行独立主机（例如 HTTP、SOAP 或 WCF）中的任何适配器，请通过从命令提示符下运行 IISRESET 来重新启动 IIS。  
  
3.  关闭任何正在运行的自定义独立适配器。  
  
### <a name="to-create-and-execute-the-btscleanupmsgbox-stored-procedure-using-sql-server-2008"></a>使用 SQL Server 2008 创建和执行 bts_CleanupMsgbox 存储过程  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。  
  
2.  在**连接到 SQL Server**对话框中，选择 SQL server 和适当的身份验证方法，，然后单击**连接**。  
  
3.  在**可用数据库**下拉列表中，选择 BizTalk Messagebox 数据库 (**BizTalkMsgBoxDB**默认情况下)。  
  
4.  单击**新查询**工具栏上的图标。  
  
5.  打开**msgbox_cleanup_logic.sql**文件从 SQL Server Management Studio。 msgbox_cleanup_logic.sql 文件位于 BizTalk Server 计算机的 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\ 目录。  
  
6.  单击**执行查询**来运行脚本，创建 bts_CleanupMsgbox 工具栏上的图标的存储过程。 Bts_CleanupMsgbox 存储过程然后可以在存储过程的列表中为 dbo.bts_CleanupMsgbox 查看。  
  
7.  单击**新查询**工具栏上的图标。  
  
8.  将以下命令粘贴到新的查询窗口中：  
  
    ```  
    exec bts_CleanupMsgbox  
    ```  
  
9. 单击**执行查询**运行 bts_CleanupMsgbox 工具栏上的图标的存储过程。  
  
    > [!IMPORTANT]
    >  不要在运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的生产服务器上运行 bts_CleanupMsgbox 存储过程。 您仅应在测试环境中运行 bts_CleanupMsgbox 存储过程。 不支持运行 bts_CleanupMsgbox 在生产环境中的存储的过程。  
  
10. 根据需要重新启动 BizTalk 服务。  
  
## <a name="considerations-when-running-the-btscleanupmsgbox-stored-procedure"></a>运行 bts_CleanupMsgbox 存储过程时的注意事项  
 运行 bts_CleanupMsgbox 存储过程时，应考虑以下注意事项：  
  
1.  如果热修复补丁程序安装到你的测试系统更新 BizTalk 数据库架构时，热修复补丁程序可能用此存储过程的空版本覆盖 bts_CleanupMsgbox 存储过程。 在这种情况下，你将需要按照本主题以重新创建 bts_CleanupMsgbox 存储过程中概述的过程。  
  
2.  如果你创建新的 MessageBox 数据库，bts_CleanupMsgbox 存储过程将为空，并且将需要按照本主题以重新创建 bts_CleanupMsgbox 存储过程中概述的过程。  
  
3.  Bts_CleanupMsgbox 存储过程的使用是**不支持**生产系统上。 此存储过程会删除 MessageBox 数据库中的所有数据。  
  
## <a name="see-also"></a>另请参阅  
 [如何从 BizTalk 跟踪数据库清除数据](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)