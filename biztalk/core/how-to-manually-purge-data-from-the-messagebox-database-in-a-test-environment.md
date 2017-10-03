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
# <a name="how-to-manually-purge-data-from-the-messagebox-database-in-a-test-environment"></a><span data-ttu-id="9c551-102">如何在测试环境中从 MessageBox 数据库中手动清除数据</span><span class="sxs-lookup"><span data-stu-id="9c551-102">How to Manually Purge Data from the MessageBox Database in a Test Environment</span></span>
<span data-ttu-id="9c551-103">在开发或测试环境中运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时，MessageBox 数据库中存储的数据通常不是业务关键的“实时”数据，因此可能会被删除。</span><span class="sxs-lookup"><span data-stu-id="9c551-103">When running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a development or test environment, data that is stored in the MessageBox database is not usually business critical "live" data and therefore may be deleted.</span></span> <span data-ttu-id="9c551-104">在这些情况下，可能需要一个“快速和更新”的方法将数据从 MessageBox 数据库清除。</span><span class="sxs-lookup"><span data-stu-id="9c551-104">In these scenarios, you may need a "quick and dirty" method for purging data from the MessageBox database.</span></span> <span data-ttu-id="9c551-105">按照本主题中的过程，使用 bts_CleanupMsgbox 存储过程将数据从 MessageBox 数据库手动清除。</span><span class="sxs-lookup"><span data-stu-id="9c551-105">Follow the procedures in this topic to manually purge data from the MessageBox database using the bts_CleanupMsgbox stored procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c551-106">应该只在测试环境中执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="9c551-106">You should only perform these steps in a test environment.</span></span> <span data-ttu-id="9c551-107">不支持在生产环境中手动清除 BizTalk MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="9c551-107">Manually purging the BizTalk MessageBox database in a production environment is not supported.</span></span>  
  
### <a name="to-stop-biztalk-services"></a><span data-ttu-id="9c551-108">停止 BizTalk 服务</span><span class="sxs-lookup"><span data-stu-id="9c551-108">To stop BizTalk services</span></span>  
  
1.  <span data-ttu-id="9c551-109">从 Services 控制台停止 BizTalk 服务的任何实例。</span><span class="sxs-lookup"><span data-stu-id="9c551-109">Stop any instances of the BizTalk service from the Services console.</span></span>  
  
2.  <span data-ttu-id="9c551-110">如果正在运行独立主机（例如 HTTP、SOAP 或 WCF）中的任何适配器，请通过从命令提示符下运行 IISRESET 来重新启动 IIS。</span><span class="sxs-lookup"><span data-stu-id="9c551-110">If you are running any adapters in isolated hosts (for example HTTP, SOAP, or WCF), restart IIS by running the IISRESET from a command prompt.</span></span>  
  
3.  <span data-ttu-id="9c551-111">关闭任何正在运行的自定义独立适配器。</span><span class="sxs-lookup"><span data-stu-id="9c551-111">Shut down any custom Isolated Adapters that are running.</span></span>  
  
### <a name="to-create-and-execute-the-btscleanupmsgbox-stored-procedure-using-sql-server-2008"></a><span data-ttu-id="9c551-112">使用 SQL Server 2008 创建和执行 bts_CleanupMsgbox 存储过程</span><span class="sxs-lookup"><span data-stu-id="9c551-112">To create and execute the bts_CleanupMsgbox stored procedure using SQL Server 2008</span></span>  
  
1.  <span data-ttu-id="9c551-113">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="9c551-113">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="9c551-114">在**连接到 SQL Server**对话框中，选择 SQL server 和适当的身份验证方法，，然后单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="9c551-114">In the **Connect to SQL Server** dialog box, select the SQL server and the appropriate authentication method, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="9c551-115">在**可用数据库**下拉列表中，选择 BizTalk Messagebox 数据库 (**BizTalkMsgBoxDB**默认情况下)。</span><span class="sxs-lookup"><span data-stu-id="9c551-115">In the **Available databases** drop-down list, select the BizTalk Messagebox database (**BizTalkMsgBoxDB** by default).</span></span>  
  
4.  <span data-ttu-id="9c551-116">单击**新查询**工具栏上的图标。</span><span class="sxs-lookup"><span data-stu-id="9c551-116">Click the **New Query** icon on the toolbar.</span></span>  
  
5.  <span data-ttu-id="9c551-117">打开**msgbox_cleanup_logic.sql**文件从 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="9c551-117">Open the **msgbox_cleanup_logic.sql** file from SQL Server Management Studio.</span></span> <span data-ttu-id="9c551-118">msgbox_cleanup_logic.sql 文件位于 BizTalk Server 计算机的 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\ 目录。</span><span class="sxs-lookup"><span data-stu-id="9c551-118">The msgbox_cleanup_logic.sql file is located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\ directory of the BizTalk Server computer.</span></span>  
  
6.  <span data-ttu-id="9c551-119">单击**执行查询**来运行脚本，创建 bts_CleanupMsgbox 工具栏上的图标的存储过程。</span><span class="sxs-lookup"><span data-stu-id="9c551-119">Click the **Execute Query** icon on the toolbar to run the script to create the bts_CleanupMsgbox stored procedure.</span></span> <span data-ttu-id="9c551-120">Bts_CleanupMsgbox 存储过程然后可以在存储过程的列表中为 dbo.bts_CleanupMsgbox 查看。</span><span class="sxs-lookup"><span data-stu-id="9c551-120">The bts_CleanupMsgbox stored procedure can then be viewed in the list of stored procedures as dbo.bts_CleanupMsgbox.</span></span>  
  
7.  <span data-ttu-id="9c551-121">单击**新查询**工具栏上的图标。</span><span class="sxs-lookup"><span data-stu-id="9c551-121">Click the **New Query** icon on the toolbar.</span></span>  
  
8.  <span data-ttu-id="9c551-122">将以下命令粘贴到新的查询窗口中：</span><span class="sxs-lookup"><span data-stu-id="9c551-122">Paste the following command into the new query window:</span></span>  
  
    ```  
    exec bts_CleanupMsgbox  
    ```  
  
9. <span data-ttu-id="9c551-123">单击**执行查询**运行 bts_CleanupMsgbox 工具栏上的图标的存储过程。</span><span class="sxs-lookup"><span data-stu-id="9c551-123">Click the **Execute Query** icon on the toolbar to run the bts_CleanupMsgbox stored procedure.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="9c551-124">不要在运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的生产服务器上运行 bts_CleanupMsgbox 存储过程。</span><span class="sxs-lookup"><span data-stu-id="9c551-124">Do not run the bts_CleanupMsgbox stored procedure on a production server that is running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="9c551-125">您仅应在测试环境中运行 bts_CleanupMsgbox 存储过程。</span><span class="sxs-lookup"><span data-stu-id="9c551-125">You should only run the bts_CleanupMsgbox stored procedure in a test environment.</span></span> <span data-ttu-id="9c551-126">不支持运行 bts_CleanupMsgbox 在生产环境中的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="9c551-126">Running the bts_CleanupMsgbox stored procedure in a production environment is not supported.</span></span>  
  
10. <span data-ttu-id="9c551-127">根据需要重新启动 BizTalk 服务。</span><span class="sxs-lookup"><span data-stu-id="9c551-127">Restart BizTalk services as needed.</span></span>  
  
## <a name="considerations-when-running-the-btscleanupmsgbox-stored-procedure"></a><span data-ttu-id="9c551-128">运行 bts_CleanupMsgbox 存储过程时的注意事项</span><span class="sxs-lookup"><span data-stu-id="9c551-128">Considerations when running the bts_CleanupMsgbox stored procedure</span></span>  
 <span data-ttu-id="9c551-129">运行 bts_CleanupMsgbox 存储过程时，应考虑以下注意事项：</span><span class="sxs-lookup"><span data-stu-id="9c551-129">The following considerations apply when running the bts_CleanupMsgbox stored procedure:</span></span>  
  
1.  <span data-ttu-id="9c551-130">如果热修复补丁程序安装到你的测试系统更新 BizTalk 数据库架构时，热修复补丁程序可能用此存储过程的空版本覆盖 bts_CleanupMsgbox 存储过程。</span><span class="sxs-lookup"><span data-stu-id="9c551-130">If you install a hot fix onto your test system that updates the BizTalk database schemas, the hot fix may overwrite the bts_CleanupMsgbox stored procedure with an empty version of this stored procedure.</span></span> <span data-ttu-id="9c551-131">在这种情况下，你将需要按照本主题以重新创建 bts_CleanupMsgbox 存储过程中概述的过程。</span><span class="sxs-lookup"><span data-stu-id="9c551-131">In this case, you will need to follow the procedures outlined in this topic to recreate the bts_CleanupMsgbox stored procedure.</span></span>  
  
2.  <span data-ttu-id="9c551-132">如果你创建新的 MessageBox 数据库，bts_CleanupMsgbox 存储过程将为空，并且将需要按照本主题以重新创建 bts_CleanupMsgbox 存储过程中概述的过程。</span><span class="sxs-lookup"><span data-stu-id="9c551-132">If you create a new MessageBox database, the bts_CleanupMsgbox stored procedure will be empty and you will need to follow the procedures outlined in this topic to recreate the bts_CleanupMsgbox stored procedure.</span></span>  
  
3.  <span data-ttu-id="9c551-133">Bts_CleanupMsgbox 存储过程的使用是**不支持**生产系统上。</span><span class="sxs-lookup"><span data-stu-id="9c551-133">Use of the bts_CleanupMsgbox stored procedure is **not supported** on a production system.</span></span> <span data-ttu-id="9c551-134">此存储过程会删除 MessageBox 数据库中的所有数据。</span><span class="sxs-lookup"><span data-stu-id="9c551-134">This stored procedure will delete all of the data in your MessageBox database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c551-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c551-135">See Also</span></span>  
 [<span data-ttu-id="9c551-136">如何从 BizTalk 跟踪数据库清除数据</span><span class="sxs-lookup"><span data-stu-id="9c551-136">How to Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)