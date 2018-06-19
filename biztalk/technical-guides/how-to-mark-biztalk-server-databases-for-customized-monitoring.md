---
title: 如何标记 BizTalk Server 数据库的自定义监视 |Microsoft 文档
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
ms.openlocfilehash: 08807b1a365b84765221e3a71cb131d8c037fcf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298237"
---
# <a name="how-to-mark-biztalk-server-databases-for-customized-monitoring"></a>如何将 BizTalk Server 数据库标记为自定义监视
如果你已安装 Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理包，你可以自定义的方式[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]监视数据库。 这样可确保[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理包监视以下[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库：  
  
-   BAM 存档 (BAMArchive) 数据库  
  
-   BAM 主导入 (BAMPrimaryImport) 数据库  
  
-   BAM 星型架构 (BAMStarSchema) 数据库  
  
-   BizTalk 跟踪 (BizTalkDTADb) 数据库  
  
-   BizTalk 管理 (BizTalkMgmtDb) 数据库  
  
-   BizTalk MessageBox (BizTalkMsgBoxDb) 数据库  
  
-   规则引擎 (BizTalkRuleEngineDb) 数据库  
  
-   企业单一登录 (SSODB) 数据库  
  
> [!NOTE]  
>  必须以 Operations Manager 高级操作员角色的成员身份登录或[!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)]管理组。  
  
### <a name="to-mark-biztalk-server-databases-for-customized-monitoring"></a>若要将 BizTalk Server 数据库标记为自定义监视  
  
1.  单击**启动**，单击**所有程序**，单击**System Center Operations Manager 2007**，然后单击**操作控制台**。  
  
2.  在操作控制台中，单击**创作**按钮。  
  
3.  在**创作**窗格中，展开**管理包对象**，然后单击**对象发现**。  
  
4.  若要找到发现 SQL server，操作控制台工具栏上单击**查找**，然后在**查找**文本框中输入**SQL 2008**搜索 SQL Server 2008。  
  
5.  下**发现的类型： SQL 2008 DB**类别中，选择**数据库引擎发现数据库**。  
  
6.  在操作控制台工具栏上，单击**重写**，然后指向**替代对象发现**。 你可以选择替代该发现，对特定类型的对象或组中的所有对象。 选择要重写，对象类型的组后**替代属性**对话框随即打开。  
  
    > [!NOTE]  
    >  如果**重写**按钮不可用，请确保已在监视器窗格中选择了监视器而不是容器对象。  
  
7.  选择中的复选框**重写**旁边的列**排除列表**参数，然后在**替代值**列中，键入你想要排除的数据库的名称从监视。 请确保[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]你想要监视的数据库中未列出**替代值**列。  
  
    > [!TIP]  
    >  已修改的对象发现可用于创建新的管理包。 在底部窗格中，**选择目标管理包**下拉列表显示的默认值为**默认管理包**。 单击**新建**以创建新管理包使用的已修改的对象发现。  
  
## <a name="see-also"></a>另请参阅  
 [监视 SQL Server](../technical-guides/monitoring-sql-servers.md)