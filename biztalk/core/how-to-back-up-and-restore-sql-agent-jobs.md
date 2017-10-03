---
title: "如何备份和还原 SQL 代理作业 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f82fc5a5-5ea5-476c-bed1-c5d41a50e673
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 253055f9a45dfdb9864d4d5202661e750d28b1b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-back-up-and-restore-sql-agent-jobs"></a>如何备份和还原 SQL 代理作业
本主题介绍如何备份和恢复 SQL Server 代理作业。 配置 SQL 作业之后应对其进行备份。  
  
## <a name="biztalk-server-jobs"></a>BizTalk Server 作业  
 以下 SQL Server 代理作业与 BizTalk Server 相关联。 每个服务器上安装的作业有所不同，具体视安装和配置的功能而定。 大多数作业是在 BizTalk Server 安装过程中创建的。 部分作业是在配置日志传送时创建的。  
  
-   备份 BizTalk Server (BizTalkMgmtDb)  
  
-   CleanupBTFExpiredEntriesJob_BizTalkMgmtDb  
  
-   DTA 清除和存档 (BizTalkDTADb)  
  
-   MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb  
  
-   MessageBox_Message_Cleanup_BizTalkMsgBoxDb  
  
-   MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb  
  
-   MessageBox_Parts_Cleanup_BizTalkMsgBoxDb  
  
-   MessageBox_UpdateStats_BizTalkMsgBoxDb  
  
-   Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb  
  
-   PurgeSubscriptionsJob_BizTalkMsgBoxDb  
  
-   Rules_Database_Cleanup_BizTalkRuleEngineDb  
  
-   TrackedMessages_Copy_BizTalkMsgBoxDb  
  
-   BTS 日志传送获取备份历史记录  
  
-   BTS 日志传送还原数据库  
  
-   BTS 日志传送还原到标记  
  
## <a name="back-up-a-job-using-a-script"></a>备份使用脚本的作业  
  
1.  打开**SQL Server Management Studio**。  
  
2.  展开 **“SQL Server 代理”**，然后展开 **“作业”**。  
  
3.  右键单击你想要创建的备份脚本，然后选择的作业**作为脚本作业**。  
  
4.  选择**创建到**或**拖放到**，然后选择**新查询编辑器窗口**，**文件**，或**剪贴板**若要选择脚本目标。 通常情况下，目标是为此文件**.sql**扩展。  
  
5.  为你要编写脚本的每个作业重复步骤 3 以后的过程。 请参考与 BizTalk Server 相关的作业列表，以确定你需要为哪些作业编写脚本。  
  
     至少，你应备份**备份 BizTalk Server (BizTalkMgmtDb)**作业后配置。  
  
## <a name="restore-a-job-from-a-script"></a>从脚本中还原作业  
  
1.  打开**SQL Server Management Studio**。  
  
2.  上**文件**菜单上，**打开**包含已编写脚本的作业的文件。  
  
3.  执行该脚本以创建作业。  
  
## <a name="next-steps"></a>后续步骤  
 [如何备份和还原 SQL Server 登录名](../core/how-to-back-up-and-restore-sql-server-logins.md)