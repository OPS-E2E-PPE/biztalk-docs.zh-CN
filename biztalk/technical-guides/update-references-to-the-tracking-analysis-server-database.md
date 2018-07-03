---
title: 更新对跟踪分析服务器数据库的引用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a403325-1394-4668-946f-01b610cb686e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 417569d99b7326b435422b5fa0dff28019006116
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014702"
---
# <a name="update-references-to-the-tracking-analysis-server-database"></a><span data-ttu-id="807d7-102">更新对跟踪分析服务器数据库的引用</span><span class="sxs-lookup"><span data-stu-id="807d7-102">Update References to the Tracking Analysis Server Database</span></span>
<span data-ttu-id="807d7-103">跟踪分析服务器数据库是可选的包含联机分析处理 (OLAP) 多维数据集。</span><span class="sxs-lookup"><span data-stu-id="807d7-103">The Tracking Analysis Server database is an optional and contains the online analytical processing (OLAP) cubes.</span></span> <span data-ttu-id="807d7-104">这些 OLAP 多维数据集是 BizTalk 跟踪数据库中包含的数据的聚合。</span><span class="sxs-lookup"><span data-stu-id="807d7-104">These OLAP cubes are aggregations of data contained in the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="807d7-105">若要还原跟踪分析服务器数据库，请使用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]分析管理器来处理 MessageMetrics 和 ServiceMetrics 多维数据集。</span><span class="sxs-lookup"><span data-stu-id="807d7-105">To restore the Tracking Analysis Server database, use [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Manager to process the MessageMetrics and ServiceMetrics cubes.</span></span> <span data-ttu-id="807d7-106">有关说明，请参阅[管理备份和还原 (Analysis Services)](http://go.microsoft.com/fwlink/?LinkId=130939) (<http://go.microsoft.com/fwlink/?LinkId=130939>) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]联机丛书。</span><span class="sxs-lookup"><span data-stu-id="807d7-106">For instructions, see [Managing Backing Up and Restoring (Analysis Services)](http://go.microsoft.com/fwlink/?LinkId=130939) (<http://go.microsoft.com/fwlink/?LinkId=130939>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="807d7-107">若要跟踪分析服务器数据库还原到其他计算机，还必须通过使用以下过程中更新对 BizTalk 管理数据库中的数据库名称的引用。</span><span class="sxs-lookup"><span data-stu-id="807d7-107">To restore the Tracking Analysis Server database to an alternate computer, you must also update references to the database name in the BizTalk Management database by using the following procedure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="807d7-108">必要條件</span><span class="sxs-lookup"><span data-stu-id="807d7-108">Prerequisites</span></span>  
 <span data-ttu-id="807d7-109">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="807d7-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to perform this procedure.</span></span>  
  
### <a name="to-update-references-to-the-tracking-analysis-server-database-name"></a><span data-ttu-id="807d7-110">若要更新对跟踪分析服务器数据库名称的引用</span><span class="sxs-lookup"><span data-stu-id="807d7-110">To update references to the Tracking Analysis Server database name</span></span>  
  
1.  <span data-ttu-id="807d7-111">在目标系统上，单击**启动**，单击**程序**，单击**Microsoft SQL Server 2008**，然后单击**SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="807d7-111">On the destination system, click **Start**, click **Programs**, click **Microsoft SQL Server 2008**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="807d7-112">在中**连接到服务器**对话框中，选择**服务器类型**作为**数据库引擎**，提供服务器名称，提供凭据以连接到服务器，然后单击**Connect**。</span><span class="sxs-lookup"><span data-stu-id="807d7-112">In the **Connect to Server** dialog box, select the **Server type** as **Database Engine**, provide a server name, provide the credentials to connect ot the server, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="807d7-113">通过单击它，双击打开相应的服务器**数据库**，双击**BizTalkMgmtDb**，然后单击**表**。</span><span class="sxs-lookup"><span data-stu-id="807d7-113">Open the appropriate server by clicking it, double-clicking **Databases**, double-clicking **BizTalkMgmtDb**, and then clicking **Tables**.</span></span>  
  
4.  <span data-ttu-id="807d7-114">在细节窗格中，右键单击**adm_Group**，然后指向**打开表**。</span><span class="sxs-lookup"><span data-stu-id="807d7-114">In the details pane, right-click **adm_Group**, and then point to **Open Table**.</span></span>  
  
5.  <span data-ttu-id="807d7-115">修改对应于原始数据库的列，以引用新数据库的相应值。</span><span class="sxs-lookup"><span data-stu-id="807d7-115">Modify the columns corresponding to the original database to reference the appropriate values for the new database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="807d7-116">*\<DBType\>*  DBServerName 和*\<DBType\>* DBName 指示的位置的数据库，其中*\<DBType\>* 数据库，如 TrackingAnalysis 的类型相对应。</span><span class="sxs-lookup"><span data-stu-id="807d7-116">*\<DBType\>* DBServerName and *\<DBType\>* DBName indicate the location of the database, where *\<DBType\>* corresponds to the type of the database, for example, TrackingAnalysis.</span></span>  
  
6.  <span data-ttu-id="807d7-117">关闭该表以保存新值。</span><span class="sxs-lookup"><span data-stu-id="807d7-117">Close the table to save the new values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="807d7-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="807d7-118">See Also</span></span>  
 [<span data-ttu-id="807d7-119">更新数据库引用</span><span class="sxs-lookup"><span data-stu-id="807d7-119">Updating Database References</span></span>](../technical-guides/updating-database-references.md)