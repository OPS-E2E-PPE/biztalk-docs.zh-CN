---
title: 如何备份和还原 SQL 代理作业 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f82fc5a5-5ea5-476c-bed1-c5d41a50e673
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea39b09736904a6ba9ef7d19dc20e833b1d1f351
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342489"
---
# <a name="how-to-back-up-and-restore-sql-agent-jobs"></a>如何备份和还原 SQL 代理作业
本主题介绍如何备份和还原 SQL Server 代理作业。 在配置它们之后，应备份 SQL 作业。  
  
## <a name="biztalk-server-jobs"></a>BizTalk Server 作业  
 以下 SQL Server 代理作业与 BizTalk Server 相关联。 每个服务器上安装的作业是安装和配置的功能而异。 BizTalk Server 安装过程中创建大多数这些作业。 配置日志传送时创建多个。  
  
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
  
## <a name="back-up-a-job-using-a-script"></a>备份作业使用的脚本  
  
1.  打开 SQL Server Management Studio。  
  
2.  展开 **“SQL Server 代理”**，然后展开 **“作业”**。  
  
3.  右键单击你想要创建备份脚本，然后选择的作业**编写作业脚本为**。  
  
4.  选择**创建到**或**拖放到**，然后选择**新查询编辑器窗口**，**文件**，或**剪贴板**若要选择脚本目标。 通常情况下，目标是文件，并且 **.sql**扩展。  
  
5.  重复此过程步骤 3 中的为每个要编写脚本的作业。 到的列表，请参阅 BizTalk Server 相关的作业，以确定哪些作业需要脚本。  
  
     至少，您应该备份**备份 BizTalk Server (BizTalkMgmtDb)** 作业配置后。  
  
## <a name="restore-a-job-from-a-script"></a>从脚本还原作业  
  
1.  打开 SQL Server Management Studio。  
  
2.  上**文件**菜单中，**打开**包含已编写脚本的作业的文件。  
  
3.  执行脚本以创建作业。  
  
## <a name="next-steps"></a>后续步骤  
 [如何备份和还原 SQL Server 登录名](../core/how-to-back-up-and-restore-sql-server-logins.md)