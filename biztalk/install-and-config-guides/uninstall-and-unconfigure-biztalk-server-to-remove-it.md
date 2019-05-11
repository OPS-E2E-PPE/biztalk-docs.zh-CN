---
title: 卸载并取消配置 BizTalk Server 将其删除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9ea8757-ca49-421b-bf7b-89344201398a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df844f6fce54b7be266a068561638b512a687924
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401465"
---
# <a name="uninstall-and-unconfigure-biztalk-server-to-remove-it"></a>卸载并取消配置 BizTalk Server 将其删除
卸载并取消配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 
  
##  <a name="BKMK_BeforeYouBegin"></a> 开始之前  
  
- 在卸载之前，必须取消-配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
- 本主题列出了不同的作业、 包和要删除的数据库。 列出的名称是默认名称。 你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境可以使用非默认名称。  
  
- 完成中列出的顺序的步骤。 否则，卸载会不完整。  
  
##  <a name="BKMK_Unconfigure"></a> 取消配置 BizTalk Server  
  
1. 右键单击**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置**，然后选择**以管理员身份运行**。  
  
2. 在配置中，选择**取消对功能**。  
  
3. 选择你想要取消配置，并选择的功能**确定**。 如果系统提示继续操作，请选择**是**。 若要从计算机中删除所有内容，可以选择所有功能。  
  
4. 选择**下一步**，然后继续完成向导。  
  
   在临时文件夹中，类似于生成的日志文件：C:\Users\username\AppData\Local\Temp\ConfigLog(8-29-2016 0h37m59s).log。  
  
##  <a name="BKMK_Uninstall"></a> 卸载 BizTalk Server 运行时组件  
  
1. 打开**程序和功能**。  
  
2. 选择你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从列表中，版本并**卸载**。  
  
3. **删除**它，然后继续完成向导。  
  
   在临时文件夹中，类似于生成的日志文件：C:\Users\\*username*\AppData\Local\Setup(083016 xxxxxx).htm  
  
##  <a name="BKMK_UninstallSSO"></a> 卸载企业单一登录  
  
1. 打开**程序和功能**。  
  
2. 选择**Microsoft 企业单一登录**从列表中，并**卸载**。  
  
3. **删除**它，然后继续完成向导。  
  
   在临时文件夹中，类似于生成的日志文件：C:\Users\\*username*\AppData\Local\Setup(083016 xxxxxx).htm  
  
##  <a name="BKMK_RemoveRemaining"></a> 删除 SQL 作业、 数据库和包  
  
#### <a name="delete-sql-server-agent-jobs"></a>删除 SQL Server 代理作业  
  
1.  打开**SQL Server Management Studio**以管理员身份。  
  
2.  在中**SQL Server Management Studio**，连接到**数据库引擎**，展开**SQL Server 代理**，然后展开**作业**。  
  
3.  删除以下作业 (右键单击该作业，然后选择**删除**):  
  
    -   备份 BizTalk Server (BizTalkMgmtDb)  
  
    -   CleanupBTFExpiredEntriesJob_BizTalkMgmtDb  
  
    -   DTA 清除和存档 (BizTalkDTADb)  
  
    -   MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb  
  
    -   MessageBox_Message_Cleanup_BizTalkMsgBoxDb  
  
    -   MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb  
  
    -   MessageBox_Parts_Cleanup_BizTalkMsgBoxDb  
  
    -   MessageBox_UpdateStats_BizTalkMsgBoxDb  
  
    -   Monitor BizTalk Server (BizTalkMgmtDb)  
  
    -   Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb  
  
    -   PurgeSubscriptionsJob_BizTalkMsgBoxDb  
  
    -   Rules_Database_Cleanup_BizTalkRuleEngineDb  
  
    -   TrackedMessages_Copy_BizTalkMsgBoxDb  
  
        > [!NOTE]
        >  如果你部署了 BAM，可能需要删除 bam_\<*多维数据集名称*\>_\<*视图名称*\>作业。  
  
#### <a name="delete-biztalk-server-databases"></a>删除 BizTalk Server 数据库  
  
1.  在中**对象资源管理器**，展开**数据库**。  
  
2.  删除以下数据库 (右键单击数据库，然后选择**删除**):  
  
    -   BAMArchive  
  
    -   BAMPrimaryImport  
  
    -   BAMStarSchema  
  
    -   BizTalkDTADb  
  
    -   BizTalkMgmtDb  
  
    -   BizTalkMsgBoxDb  
  
    -   BizTalkRuleEngineDb  
  
    -   SSODB  
  
#### <a name="remove-sql-server-integration-services-packages"></a>删除 SQL Server Integration Services 包  
  
1.  在中**对象资源管理器**，**连接**到**Integration Services**。  
  
2.  展开**存储的包**，然后展开**MSDB**。  
  
3.  删除具有以下前缀的包 (右键单击该包，然后选择**删除**):  
  
    -   BAM_AN_\<*多维数据集名称*\>  
  
    -   BAM_DM_\<*视图名称*\>  
  
