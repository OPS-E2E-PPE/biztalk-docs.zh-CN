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
ms.openlocfilehash: ea069140b9dd89fafa13fe57be9eefa17eceb790
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023707"
---
# <a name="how-to-mark-biztalk-server-databases-for-customized-monitoring"></a><span data-ttu-id="b4d72-102">如何将 BizTalk Server 数据库标记为自定义监视</span><span class="sxs-lookup"><span data-stu-id="b4d72-102">How to Mark BizTalk Server Databases for Customized Monitoring</span></span>
<span data-ttu-id="b4d72-103">如果已安装 Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理包，您可以自定义的方式[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]监视数据库。</span><span class="sxs-lookup"><span data-stu-id="b4d72-103">If you have installed the Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack, you can customize the way [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are monitored.</span></span> <span data-ttu-id="b4d72-104">这可确保[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理包监视以下[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库：</span><span class="sxs-lookup"><span data-stu-id="b4d72-104">This ensures that the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack monitors the following [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases:</span></span>  
  
-   <span data-ttu-id="b4d72-105">BAM 存档 (BAMArchive) 数据库</span><span class="sxs-lookup"><span data-stu-id="b4d72-105">BAM Archive (BAMArchive) database</span></span>  
  
-   <span data-ttu-id="b4d72-106">BAM 主导入 (BAMPrimaryImport) 数据库</span><span class="sxs-lookup"><span data-stu-id="b4d72-106">BAM Primary Import (BAMPrimaryImport) database</span></span>  
  
-   <span data-ttu-id="b4d72-107">BAM 星型架构 (BAMStarSchema) 数据库</span><span class="sxs-lookup"><span data-stu-id="b4d72-107">BAM Star Schema (BAMStarSchema) database</span></span>  
  
-   <span data-ttu-id="b4d72-108">BizTalk 跟踪 (BizTalkDTADb) 数据库</span><span class="sxs-lookup"><span data-stu-id="b4d72-108">BizTalk Tracking (BizTalkDTADb) database</span></span>  
  
-   <span data-ttu-id="b4d72-109">BizTalk 管理 (BizTalkMgmtDb) 数据库</span><span class="sxs-lookup"><span data-stu-id="b4d72-109">BizTalk Management (BizTalkMgmtDb) database</span></span>  
  
-   <span data-ttu-id="b4d72-110">BizTalk MessageBox (BizTalkMsgBoxDb) 数据库</span><span class="sxs-lookup"><span data-stu-id="b4d72-110">BizTalk MessageBox (BizTalkMsgBoxDb) database</span></span>  
  
-   <span data-ttu-id="b4d72-111">规则引擎 (BizTalkRuleEngineDb) 数据库</span><span class="sxs-lookup"><span data-stu-id="b4d72-111">Rule Engine (BizTalkRuleEngineDb) database</span></span>  
  
-   <span data-ttu-id="b4d72-112">企业单一登录 (SSODB) 数据库</span><span class="sxs-lookup"><span data-stu-id="b4d72-112">Enterprise Single Sign-On (SSODB) database</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4d72-113">必须以 Operations Manager Advanced Operator 角色的成员身份登录或[!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)]管理组。</span><span class="sxs-lookup"><span data-stu-id="b4d72-113">You must be logged on as a member of the Operations Manager Advanced Operator role or [!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)] Management Group.</span></span>  
  
### <a name="to-mark-biztalk-server-databases-for-customized-monitoring"></a><span data-ttu-id="b4d72-114">若要为自定义监视标记 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="b4d72-114">To mark BizTalk Server databases for customized monitoring</span></span>  
  
1. <span data-ttu-id="b4d72-115">单击**启动**，单击**所有程序**，单击**System Center Operations Manager 2007**，然后单击**操作控制台**。</span><span class="sxs-lookup"><span data-stu-id="b4d72-115">Click **Start**, click **All Programs**, click **System Center Operations Manager 2007**, and then click **Operations Console**.</span></span>  
  
2. <span data-ttu-id="b4d72-116">在操作控制台中，单击**创作**按钮。</span><span class="sxs-lookup"><span data-stu-id="b4d72-116">In the Operations console, click the **Authoring** button.</span></span>  
  
3. <span data-ttu-id="b4d72-117">在中**创作**窗格中，展开**管理包对象**，然后单击**对象发现**。</span><span class="sxs-lookup"><span data-stu-id="b4d72-117">In the **Authoring** pane, expand **Management Pack Objects**, and then click **Object Discoveries**.</span></span>  
  
4. <span data-ttu-id="b4d72-118">若要找到适用于 SQL Server 发现，在操作控制台工具栏上单击**查找**，然后在**寻找**文本框中输入**SQL 2008**搜索 SQL Server 2008。</span><span class="sxs-lookup"><span data-stu-id="b4d72-118">To locate a discovery for SQL Server, on the Operations console toolbar click **Find**, and in the **Look for** text box enter **SQL 2008** to search for SQL Server 2008.</span></span>  
  
5. <span data-ttu-id="b4d72-119">下**发现的类型： SQL 2008 DB**类别中，选择**为数据库引擎发现数据库**。</span><span class="sxs-lookup"><span data-stu-id="b4d72-119">Under the **Discovered Type: SQL 2008 DB** category, select **Discover Databases for a Database Engine**.</span></span>  
  
6. <span data-ttu-id="b4d72-120">在操作控制台工具栏上，单击**重写**，然后指向**替代对象发现**。</span><span class="sxs-lookup"><span data-stu-id="b4d72-120">On the Operations console toolbar, click **Overrides** and then point to **Override the Object Discovery**.</span></span> <span data-ttu-id="b4d72-121">您可以选择替代该发现，对于特定类型的对象或组中的所有对象。</span><span class="sxs-lookup"><span data-stu-id="b4d72-121">You can choose to override the discovery for objects of a specific type or for all objects within a group.</span></span> <span data-ttu-id="b4d72-122">选择要替代的对象类型组之后**重写属性**对话框随即打开。</span><span class="sxs-lookup"><span data-stu-id="b4d72-122">After you choose which group of object type to override, the **Override Properties** dialog box opens.</span></span>  
  
   > [!NOTE]  
   >  <span data-ttu-id="b4d72-123">如果**重写**按钮仍不可用，请确保监视器窗格中选择了监视器而不是容器对象。</span><span class="sxs-lookup"><span data-stu-id="b4d72-123">If the **Overrides** button is not available, make sure you have selected a monitor and not a container object in the Monitors pane.</span></span>  
  
7. <span data-ttu-id="b4d72-124">选择中的复选框**重写**列下一步**排除列表**参数，然后在**替代值**列中，键入你想要排除的数据库的名称从监视。</span><span class="sxs-lookup"><span data-stu-id="b4d72-124">Select the check box in the **Override** column next to the **Exclude List** parameter, and in the **Override Value** column, type the name of the database that you want to exclude from monitoring.</span></span> <span data-ttu-id="b4d72-125">请确保[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]想要监视的数据库中未列出**替代值**列。</span><span class="sxs-lookup"><span data-stu-id="b4d72-125">Make sure the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases that you want to monitor are not listed in the **Override Value** column.</span></span>  
  
   > [!TIP]  
   >  <span data-ttu-id="b4d72-126">已修改的对象发现可用于创建新的管理包。</span><span class="sxs-lookup"><span data-stu-id="b4d72-126">You can use the modified object discoveries to create a new management pack.</span></span> <span data-ttu-id="b4d72-127">在底部窗格中，**选择目标管理包**下拉列表显示了默认值为**默认管理包**。</span><span class="sxs-lookup"><span data-stu-id="b4d72-127">At the bottom of the pane, the **Select destination management pack** drop-down shows a default value of **Default Management Pack**.</span></span> <span data-ttu-id="b4d72-128">单击**新建**若要创建新的管理包使用的已修改的对象发现。</span><span class="sxs-lookup"><span data-stu-id="b4d72-128">Click **New** to create a new management pack using the modified object discoveries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4d72-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4d72-129">See Also</span></span>  
 [<span data-ttu-id="b4d72-130">监视 SQL Server</span><span class="sxs-lookup"><span data-stu-id="b4d72-130">Monitoring SQL Servers</span></span>](../technical-guides/monitoring-sql-servers.md)