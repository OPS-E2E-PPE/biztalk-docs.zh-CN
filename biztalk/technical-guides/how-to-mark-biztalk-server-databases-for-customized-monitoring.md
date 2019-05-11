---
title: 如何为自定义监视标记 BizTalk Server 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfbdc73d-a108-42ee-a5d8-401d5bfe5e7d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49e34847ae9ad93861a1e9cf18698f500cce5263
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396311"
---
# <a name="how-to-mark-biztalk-server-databases-for-customized-monitoring"></a>如何将 BizTalk Server 数据库标记为自定义监视
如果已安装 Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理包，您可以自定义的方式[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]监视数据库。 这可确保[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理包监视以下[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库：  
  
-   BAM 存档 (BAMArchive) 数据库  
  
-   BAM 主导入 (BAMPrimaryImport) 数据库  
  
-   BAM 星型架构 (BAMStarSchema) 数据库  
  
-   BizTalk 跟踪 (BizTalkDTADb) 数据库  
  
-   BizTalk 管理 (BizTalkMgmtDb) 数据库  
  
-   BizTalk MessageBox (BizTalkMsgBoxDb) 数据库  
  
-   规则引擎 (BizTalkRuleEngineDb) 数据库  
  
-   企业单一登录 (SSODB) 数据库  
  
> [!NOTE]
>  必须以 Operations Manager Advanced Operator 角色的成员身份登录或[!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)]管理组。  
  
### <a name="to-mark-biztalk-server-databases-for-customized-monitoring"></a>若要为自定义监视标记 BizTalk Server 数据库  
  
1. 单击**启动**，单击**所有程序**，单击**System Center Operations Manager 2007**，然后单击**操作控制台**。  
  
2. 在操作控制台中，单击**创作**按钮。  
  
3. 在中**创作**窗格中，展开**管理包对象**，然后单击**对象发现**。  
  
4. 若要找到适用于 SQL Server 发现，在操作控制台工具栏上单击**查找**，然后在**寻找**文本框中输入**SQL 2008**搜索 SQL Server 2008。  
  
5. 下**发现类型：SQL 2008 DB**类别中，选择**数据库引擎发现数据库**。  
  
6. 在操作控制台工具栏上，单击**重写**，然后指向**替代对象发现**。 您可以选择替代该发现，对于特定类型的对象或组中的所有对象。 选择要替代的对象类型组之后**重写属性**对话框随即打开。  
  
   > [!NOTE]  
   >  如果**重写**按钮仍不可用，请确保监视器窗格中选择了监视器而不是容器对象。  
  
7. 选择中的复选框**重写**列下一步**排除列表**参数，然后在**替代值**列中，键入你想要排除的数据库的名称从监视。 请确保[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]想要监视的数据库中未列出**替代值**列。  
  
   > [!TIP]  
   >  已修改的对象发现可用于创建新的管理包。 在底部窗格中，**选择目标管理包**下拉列表显示了默认值为**默认管理包**。 单击**新建**若要创建新的管理包使用的已修改的对象发现。  
  
## <a name="see-also"></a>请参阅  
 [监视 SQL Server](../technical-guides/monitoring-sql-servers.md)