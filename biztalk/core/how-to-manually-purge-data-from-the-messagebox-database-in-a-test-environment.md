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
# <a name="how-to-manually-purge-data-from-the-messagebox-database-in-a-test-environment"></a><span data-ttu-id="d0d4e-102">如何从 MessageBox 数据库中的测试环境中手动清除数据</span><span class="sxs-lookup"><span data-stu-id="d0d4e-102">How to Manually Purge Data from the MessageBox Database in a Test Environment</span></span>
<span data-ttu-id="d0d4e-103">运行时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在开发或测试环境中，MessageBox 数据库中存储的数据通常不是业务关键"实时"数据，因此可能会被删除。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-103">When running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a development or test environment, data that is stored in the MessageBox database is not usually business critical "live" data and therefore may be deleted.</span></span> <span data-ttu-id="d0d4e-104">在这些情况下，可能需要的"快速和更新"方法清除的 MessageBox 数据库中的数据。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-104">In these scenarios, you may need a "quick and dirty" method for purging data from the MessageBox database.</span></span> <span data-ttu-id="d0d4e-105">请按照本主题，以从 MessageBox 数据库使用 bts_CleanupMsgbox 存储过程中手动清除数据中的过程。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-105">Follow the procedures in this topic to manually purge data from the MessageBox database using the bts_CleanupMsgbox stored procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0d4e-106">仅应在测试环境中执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-106">You should only perform these steps in a test environment.</span></span> <span data-ttu-id="d0d4e-107">不支持手动清除 BizTalk MessageBox 数据库在生产环境中。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-107">Manually purging the BizTalk MessageBox database in a production environment is not supported.</span></span>  
  
### <a name="to-stop-biztalk-services"></a><span data-ttu-id="d0d4e-108">若要停止 BizTalk 服务</span><span class="sxs-lookup"><span data-stu-id="d0d4e-108">To stop BizTalk services</span></span>  
  
1.  <span data-ttu-id="d0d4e-109">停止 BizTalk 服务服务控制台中的任何实例。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-109">Stop any instances of the BizTalk service from the Services console.</span></span>  
  
2.  <span data-ttu-id="d0d4e-110">如果在独立的主机 （例如，HTTP、 SOAP 或 WCF） 中正在运行的任何适配器，重新启动 IIS，通过在命令提示符下运行 IISRESET。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-110">If you are running any adapters in isolated hosts (for example HTTP, SOAP, or WCF), restart IIS by running the IISRESET from a command prompt.</span></span>  
  
3.  <span data-ttu-id="d0d4e-111">关闭正在运行的任何自定义独立适配器。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-111">Shut down any custom Isolated Adapters that are running.</span></span>  
  
### <a name="to-create-and-execute-the-btscleanupmsgbox-stored-procedure-using-sql-server-2008"></a><span data-ttu-id="d0d4e-112">若要创建和执行 bts_CleanupMsgbox 存储过程使用 SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="d0d4e-112">To create and execute the bts_CleanupMsgbox stored procedure using SQL Server 2008</span></span>  
  
1. <span data-ttu-id="d0d4e-113">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-113">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2. <span data-ttu-id="d0d4e-114">在中**连接到 SQL Server**对话框中，选择 SQL server 和相应的身份验证方法，然后单击**Connect**。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-114">In the **Connect to SQL Server** dialog box, select the SQL server and the appropriate authentication method, and then click **Connect**.</span></span>  
  
3. <span data-ttu-id="d0d4e-115">在中**可用数据库**下拉列表中，选择 BizTalk Messagebox 数据库 (**BizTalkMsgBoxDB**默认情况下)。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-115">In the **Available databases** drop-down list, select the BizTalk Messagebox database (**BizTalkMsgBoxDB** by default).</span></span>  
  
4. <span data-ttu-id="d0d4e-116">单击**新查询**工具栏上的图标。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-116">Click the **New Query** icon on the toolbar.</span></span>  
  
5. <span data-ttu-id="d0d4e-117">打开**msgbox_cleanup_logic.sql**文件从 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-117">Open the **msgbox_cleanup_logic.sql** file from SQL Server Management Studio.</span></span> <span data-ttu-id="d0d4e-118">Msgbox_cleanup_logic.sql 文件位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]的 BizTalk Server 计算机的 Schema\ 目录。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-118">The msgbox_cleanup_logic.sql file is located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\ directory of the BizTalk Server computer.</span></span>  
  
6. <span data-ttu-id="d0d4e-119">单击**执行查询**图标在工具栏上，若要运行该脚本创建 bts_CleanupMsgbox 存储过程。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-119">Click the **Execute Query** icon on the toolbar to run the script to create the bts_CleanupMsgbox stored procedure.</span></span> <span data-ttu-id="d0d4e-120">Bts_CleanupMsgbox 存储过程然后可以在存储过程的列表中作为 dbo.bts_CleanupMsgbox 查看。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-120">The bts_CleanupMsgbox stored procedure can then be viewed in the list of stored procedures as dbo.bts_CleanupMsgbox.</span></span>  
  
7. <span data-ttu-id="d0d4e-121">单击**新查询**工具栏上的图标。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-121">Click the **New Query** icon on the toolbar.</span></span>  
  
8. <span data-ttu-id="d0d4e-122">将以下命令粘贴到新查询窗口：</span><span class="sxs-lookup"><span data-stu-id="d0d4e-122">Paste the following command into the new query window:</span></span>  
  
   ```  
   exec bts_CleanupMsgbox  
   ```  
  
9. <span data-ttu-id="d0d4e-123">单击**执行查询**图标在工具栏上，以便运行 bts_CleanupMsgbox 存储过程。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-123">Click the **Execute Query** icon on the toolbar to run the bts_CleanupMsgbox stored procedure.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="d0d4e-124">不要在正在运行的生产服务器上运行 bts_CleanupMsgbox 存储过程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-124">Do not run the bts_CleanupMsgbox stored procedure on a production server that is running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d0d4e-125">只应在测试环境中运行 bts_CleanupMsgbox 存储过程。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-125">You should only run the bts_CleanupMsgbox stored procedure in a test environment.</span></span> <span data-ttu-id="d0d4e-126">不支持运行 bts_CleanupMsgbox 存储的过程在生产环境中。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-126">Running the bts_CleanupMsgbox stored procedure in a production environment is not supported.</span></span>  
  
10. <span data-ttu-id="d0d4e-127">根据需要重新启动 BizTalk 服务。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-127">Restart BizTalk services as needed.</span></span>  
  
## <a name="considerations-when-running-the-btscleanupmsgbox-stored-procedure"></a><span data-ttu-id="d0d4e-128">运行 bts_CleanupMsgbox 存储过程时的注意事项</span><span class="sxs-lookup"><span data-stu-id="d0d4e-128">Considerations when running the bts_CleanupMsgbox stored procedure</span></span>  
 <span data-ttu-id="d0d4e-129">运行 bts_CleanupMsgbox 存储过程时，应考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="d0d4e-129">The following considerations apply when running the bts_CleanupMsgbox stored procedure:</span></span>  
  
1.  <span data-ttu-id="d0d4e-130">如果您安装了修补到你的测试系统的更新 BizTalk 数据库架构，热修复补丁程序可能会覆盖 bts_CleanupMsgbox 存储过程，此存储过程的空版本。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-130">If you install a hot fix onto your test system that updates the BizTalk database schemas, the hot fix may overwrite the bts_CleanupMsgbox stored procedure with an empty version of this stored procedure.</span></span> <span data-ttu-id="d0d4e-131">在这种情况下，需要按照本主题，以重新创建 bts_CleanupMsgbox 存储过程中所述的过程。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-131">In this case, you will need to follow the procedures outlined in this topic to recreate the bts_CleanupMsgbox stored procedure.</span></span>  
  
2.  <span data-ttu-id="d0d4e-132">如果创建新的 MessageBox 数据库，bts_CleanupMsgbox 存储过程将为空，并且将需要按照本主题，以重新创建 bts_CleanupMsgbox 存储过程中所述的过程。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-132">If you create a new MessageBox database, the bts_CleanupMsgbox stored procedure will be empty and you will need to follow the procedures outlined in this topic to recreate the bts_CleanupMsgbox stored procedure.</span></span>  
  
3.  <span data-ttu-id="d0d4e-133">使用 bts_CleanupMsgbox 存储过程是**不支持**生产系统上。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-133">Use of the bts_CleanupMsgbox stored procedure is **not supported** on a production system.</span></span> <span data-ttu-id="d0d4e-134">此存储的过程将删除所有 MessageBox 数据库中的数据。</span><span class="sxs-lookup"><span data-stu-id="d0d4e-134">This stored procedure will delete all of the data in your MessageBox database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0d4e-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0d4e-135">See Also</span></span>  
 [<span data-ttu-id="d0d4e-136">如何从 BizTalk 跟踪数据库中清除数据</span><span class="sxs-lookup"><span data-stu-id="d0d4e-136">How to Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)