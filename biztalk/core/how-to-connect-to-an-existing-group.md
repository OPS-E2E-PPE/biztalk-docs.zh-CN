---
title: 如何连接到现有组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.procedure.connecttogroup
helpviewer_keywords:
- groups, existing
- groups, connecting
- managing [groups], connecting
ms.assetid: 1eedbcd5-f3f1-4da5-b91c-67377131f889
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e29b57f39ab1cb86e34a9e744063ff248d12ad1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994350"
---
# <a name="how-to-connect-to-an-existing-group"></a><span data-ttu-id="f4621-102">如何连接到现有组</span><span class="sxs-lookup"><span data-stu-id="f4621-102">How to Connect to an Existing Group</span></span>
<span data-ttu-id="f4621-103">只要企业中的一个或多个 BizTalk Server 组位于同一域或可信域中的计算机上，你就可以在企业中任何计算机上使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台远程管理这些组。</span><span class="sxs-lookup"><span data-stu-id="f4621-103">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console on any computer in your enterprise to remotely manage one or more BizTalk Server groups within your enterprise, as long as these groups are located on computers within the same domain or within trusted domains.</span></span>  
  
 <span data-ttu-id="f4621-104">BizTalk Server 管理控制台中的 BizTalk Server 管理节点是所有的 BizTalk 组的最高级别的节点，将现有的 BizTalk Server 组添加到 BizTalk Server 管理控制台时，使用的级别。</span><span class="sxs-lookup"><span data-stu-id="f4621-104">The BizTalk Server Administration node in the BizTalk Server Administration console is the highest-level node for all BizTalk groups, and is the level that you use when adding an existing BizTalk Server group to the BizTalk Server Administration console.</span></span> <span data-ttu-id="f4621-105">在添加组时，必须指定要连接到的现有服务器和 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="f4621-105">When you add a group, you must specify an existing server and BizTalk Management database to which you want to connect.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f4621-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="f4621-106">Prerequisites</span></span>  
 <span data-ttu-id="f4621-107">若要执行此步骤，则必须以 BizTalk Server Operators 组成员或 BizTalk Server Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="f4621-107">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group or as a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-connect-to-an-existing-group"></a><span data-ttu-id="f4621-108">连接到现有组</span><span class="sxs-lookup"><span data-stu-id="f4621-108">To connect to an existing group</span></span>  
  
1. <span data-ttu-id="f4621-109">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="f4621-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="f4621-110">在控制台树中，右键单击**BizTalk Server 管理**，然后单击**连接到现有组**。</span><span class="sxs-lookup"><span data-stu-id="f4621-110">In the console tree, right-click **BizTalk Server Administration**, and then click **Connect to Existing Group**.</span></span>  
  
3. <span data-ttu-id="f4621-111">在中**连接到现有 BizTalk Server 配置数据库**对话框中**SQL Server 名称**下拉列表框中，选择承载 BizTalk 的 Microsoft SQL Server 实例的名称管理数据库 （也称为配置数据库）。</span><span class="sxs-lookup"><span data-stu-id="f4621-111">In the **Connect to Existing BizTalk Server Configuration Database** dialog box, in the **SQL Server name** drop-down list box, select the name of the Microsoft SQL Server instance that hosts the BizTalk Management database (also referred to as the Configuration database).</span></span> <span data-ttu-id="f4621-112">在选择 SQL Server 的实例后，BizTalk Server 将自动尝试检测该计算机上的 BizTalk Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="f4621-112">When you select the instance of SQL Server, BizTalk Server automatically attempts to detect BizTalk Server databases on that computer.</span></span>  
  
4. <span data-ttu-id="f4621-113">在中**数据库名称**下拉列表框中，选择 BizTalk Server 管理数据库 (**BizTalkMgmtDb**) 到想要连接，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f4621-113">In the **Database name** drop-down list box, select the BizTalk Server Management database (**BizTalkMgmtDb**) to which you want to connect, and then click **OK**.</span></span>  
  
    <span data-ttu-id="f4621-114">在 BizTalk Server 管理控制台将 BizTalk Server 组添加到控制台树中。</span><span class="sxs-lookup"><span data-stu-id="f4621-114">The BizTalk Server Administration console adds the BizTalk Server group to the console tree.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f4621-115">如果 BizTalk Server 管理数据库存储在 SQL Server 群集上，且该群集正在进行故障转移，则在尝试连接到管理数据库时，可能会出现类似下面的错误：</span><span class="sxs-lookup"><span data-stu-id="f4621-115">If the BizTalk Server Management database is housed on a SQL Server cluster and the cluster is in the process of failing over then you may receive an error similar to the following when you attempt to connect to the Management database:</span></span>  
   >   
   >  <span data-ttu-id="f4621-116">无法加载组 [\<servername\>:\<管理数据库\>] 数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="f4621-116">Failed to load Group [\<servername\>:\<management database\>] data providers.</span></span>  
   >   
   >  <span data-ttu-id="f4621-117">And</span><span class="sxs-lookup"><span data-stu-id="f4621-117">And</span></span>  
   >   
   >  <span data-ttu-id="f4621-118">其他信息：</span><span class="sxs-lookup"><span data-stu-id="f4621-118">ADDITIONAL INFORMATION:</span></span>  
   >   
   >  <span data-ttu-id="f4621-119">找不到 WMI 类的实例。</span><span class="sxs-lookup"><span data-stu-id="f4621-119">Instance of the WMI class is not found.</span></span> <span data-ttu-id="f4621-120">(WinMgmt)</span><span class="sxs-lookup"><span data-stu-id="f4621-120">(WinMgmt)</span></span>  
   >   
   >  <span data-ttu-id="f4621-121">出现这种错误的原因是，BizTalk 数据库在进行故障转移时不可用。</span><span class="sxs-lookup"><span data-stu-id="f4621-121">This error can occur because the BizTalk databases are not available while they are being failed over.</span></span> <span data-ttu-id="f4621-122">解决此问题，请在 SQL Server 的群集实例之前等待处于联机状态之前尝试使用在 BizTalk Server 管理控制台连接到它。</span><span class="sxs-lookup"><span data-stu-id="f4621-122">To workaround this issue, wait until after the clustered instance of SQL Server is online before attempting to connect to it with the BizTalk Server Administration console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4621-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4621-123">See Also</span></span>  
 <span data-ttu-id="f4621-124">[管理组](../core/managing-groups.md) </span><span class="sxs-lookup"><span data-stu-id="f4621-124">[Managing Groups](../core/managing-groups.md) </span></span>  
 [<span data-ttu-id="f4621-125">BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="f4621-125">BizTalk Groups</span></span>](../core/biztalk-groups.md)