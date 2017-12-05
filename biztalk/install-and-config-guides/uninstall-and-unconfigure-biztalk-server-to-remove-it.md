---
title: "卸载和取消配置 BizTalk Server 才能删除它 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9ea8757-ca49-421b-bf7b-89344201398a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 704c1f54a01ceb4c4b7b4cd80ad2df6fc34faa68
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="uninstall-and-unconfigure-biztalk-server-to-remove-it"></a>卸载 BizTalk Server 并取消配置以将其删除
卸载并取消对 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的配置。 
  
##  <a name="BKMK_BeforeYouBegin"></a> 开始之前  
  
-   卸载之前，你必须取消对 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的配置。  
  
-   本主题列出了要删除的不同作业、包和数据库。 列出的名称是默认名称。 你的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境可以使用非默认名称。  
  
-   按列出的顺序完成各步骤。 否则，卸载会不完整。  
  
##  <a name="BKMK_Unconfigure"></a> 取消对 BizTalk Server 的配置  
  
1.  右键单击“[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置”，然后单击“以管理员身份运行”。  
  
2.  在“配置”中，选择“取消对功能的配置”。  
  
3.  选择要取消配置的功能，然后选择“确定”。 如果系统提示继续操作，请选择“是”。 若要从计算机中完全删除，可以选择所有功能。  
  
4.  选择“下一步”，然后继续完成向导。  
  
 日志文件生成于临时文件夹，如下所示：C:\Users\username\AppData\Local\Temp\ConfigLog(8-29-2016 0h37m59s).log。  
  
##  <a name="BKMK_Uninstall"></a> 卸载 BizTalk Server 运行时组件  
  
1.  打开“程序和功能”。  
  
2.  从列表中选择 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 版本，然后选择“卸载”。  
  
3.  “删除”它，然后继续完成向导。  
  
 日志文件生成于临时文件夹，如下所示：C:\Users\\*username*\AppData\Local\Setup(083016 xxxxxx).htm  
  
##  <a name="BKMK_UninstallSSO"></a> 卸载企业单一登录  
  
1.  打开“程序和功能”。  
  
2.  从列表中选择“Microsoft 企业单一登录”，然后选择“卸载”。  
  
3.  “删除”它，然后继续完成向导。  
  
 日志文件生成于临时文件夹，如下所示：C:\Users\\*username*\AppData\Local\Setup(083016 xxxxxx).htm  
  
##  <a name="BKMK_RemoveRemaining"></a> 删除 SQL 作业、数据库和包  
  
#### <a name="delete-sql-server-agent-jobs"></a>删除 SQL Server 代理作业  
  
1.  以管理员身份打开 **SQL Server Management Studio**。  
  
2.  在“SQL Server Management Studio”中，连接到“数据库引擎”，依次展开“SQL Server 代理”，然后展开“作业”。  
  
3.  删除以下作业（右键单击作业，然后选择“删除”：  
  
    -   备份 BizTalk Server (BizTalkMgmtDb)  
  
    -   CleanupBTFExpiredEntriesJob_BizTalkMgmtDb  
  
    -   DTA 清除和存档 (BizTalkDTADb)  
  
    -   MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb  
  
    -   MessageBox_Message_Cleanup_BizTalkMsgBoxDb  
  
    -   MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb  
  
    -   MessageBox_Parts_Cleanup_BizTalkMsgBoxDb  
  
    -   MessageBox_UpdateStats_BizTalkMsgBoxDb  
  
    -   监视 BizTalk Server (BizTalkMgmtDb)  
  
    -   Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb  
  
    -   PurgeSubscriptionsJob_BizTalkMsgBoxDb  
  
    -   Rules_Database_Cleanup_BizTalkRuleEngineDb  
  
    -   TrackedMessages_Copy_BizTalkMsgBoxDb  
  
        > [!NOTE]
        >  如果你部署 BAM，可能需要删除 bam_\<*多维数据集名称*\>_\<*视图名称*\>作业。  
  
#### <a name="delete-biztalk-server-databases"></a>删除 BizTalk Server 数据库  
  
1.  在“对象资源管理器”中，展开“数据库”。  
  
2.  删除以下数据库（右键单击数据库，然后选择“删除”）：  
  
    -   BAMArchive  
  
    -   BAMPrimaryImport  
  
    -   BAMStarSchema  
  
    -   BizTalkDTADb  
  
    -   BizTalkMgmtDb  
  
    -   BizTalkMsgBoxDb  
  
    -   BizTalkRuleEngineDb  
  
    -   SSODB  
  
#### <a name="remove-sql-server-integration-services-packages"></a>删除 SQL Server Integration Services 包  
  
1.  在“对象资源管理器”中，**连接**到 **Integration Services**。  
  
2.  展开“已存储的包”，然后展开“MSDB”。  
  
3.  删除具有以下前缀的包（右键单击该包，然后选择“删除”：  
  
    -   BAM_AN_\<*多维数据集名称*\>  
  
    -   BAM_DM_\<*查看名称*\>  
  
