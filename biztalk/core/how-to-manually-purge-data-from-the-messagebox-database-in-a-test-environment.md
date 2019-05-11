---
title: 如何从 MessageBox 数据库中的测试环境中手动清除数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 398991a9-344a-487a-a817-dfc97d48ebe6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1ea4d8356aa5812958e2ba9690dfbf8cc414dd5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336669"
---
# <a name="how-to-manually-purge-data-from-the-messagebox-database-in-a-test-environment"></a>如何从 MessageBox 数据库中的测试环境中手动清除数据
运行时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在开发或测试环境中，MessageBox 数据库中存储的数据通常不是业务关键"实时"数据，因此可能会被删除。 在这些情况下，可能需要的"快速和更新"方法清除的 MessageBox 数据库中的数据。 请按照本主题，以从 MessageBox 数据库使用 bts_CleanupMsgbox 存储过程中手动清除数据中的过程。  
  
> [!NOTE]
>  仅应在测试环境中执行这些步骤。 不支持手动清除 BizTalk MessageBox 数据库在生产环境中。  
  
### <a name="to-stop-biztalk-services"></a>若要停止 BizTalk 服务  
  
1.  停止 BizTalk 服务服务控制台中的任何实例。  
  
2.  如果在独立的主机 （例如，HTTP、 SOAP 或 WCF） 中正在运行的任何适配器，重新启动 IIS，通过在命令提示符下运行 IISRESET。  
  
3.  关闭正在运行的任何自定义独立适配器。  
  
### <a name="to-create-and-execute-the-btscleanupmsgbox-stored-procedure-using-sql-server-2008"></a>若要创建和执行 bts_CleanupMsgbox 存储过程使用 SQL Server 2008  
  
1. 单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。  
  
2. 在中**连接到 SQL Server**对话框中，选择 SQL server 和相应的身份验证方法，然后单击**Connect**。  
  
3. 在中**可用数据库**下拉列表中，选择 BizTalk Messagebox 数据库 (**BizTalkMsgBoxDB**默认情况下)。  
  
4. 单击**新查询**工具栏上的图标。  
  
5. 打开**msgbox_cleanup_logic.sql**文件从 SQL Server Management Studio。 Msgbox_cleanup_logic.sql 文件位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]的 BizTalk Server 计算机的 Schema\ 目录。  
  
6. 单击**执行查询**图标在工具栏上，若要运行该脚本创建 bts_CleanupMsgbox 存储过程。 Bts_CleanupMsgbox 存储过程然后可以在存储过程的列表中作为 dbo.bts_CleanupMsgbox 查看。  
  
7. 单击**新查询**工具栏上的图标。  
  
8. 将以下命令粘贴到新查询窗口：  
  
   ```  
   exec bts_CleanupMsgbox  
   ```  
  
9. 单击**执行查询**图标在工具栏上，以便运行 bts_CleanupMsgbox 存储过程。  
  
   > [!IMPORTANT]
   >  不要在正在运行的生产服务器上运行 bts_CleanupMsgbox 存储过程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 只应在测试环境中运行 bts_CleanupMsgbox 存储过程。 不支持运行 bts_CleanupMsgbox 存储的过程在生产环境中。  
  
10. 根据需要重新启动 BizTalk 服务。  
  
## <a name="considerations-when-running-the-btscleanupmsgbox-stored-procedure"></a>运行 bts_CleanupMsgbox 存储过程时的注意事项  
 运行 bts_CleanupMsgbox 存储过程时，应考虑以下事项：  
  
1.  如果您安装了修补到你的测试系统的更新 BizTalk 数据库架构，热修复补丁程序可能会覆盖 bts_CleanupMsgbox 存储过程，此存储过程的空版本。 在这种情况下，需要按照本主题，以重新创建 bts_CleanupMsgbox 存储过程中所述的过程。  
  
2.  如果创建新的 MessageBox 数据库，bts_CleanupMsgbox 存储过程将为空，并且将需要按照本主题，以重新创建 bts_CleanupMsgbox 存储过程中所述的过程。  
  
3.  使用 bts_CleanupMsgbox 存储过程是**不支持**生产系统上。 此存储的过程将删除所有 MessageBox 数据库中的数据。  
  
## <a name="see-also"></a>请参阅  
 [如何从 BizTalk 跟踪数据库中清除数据](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)