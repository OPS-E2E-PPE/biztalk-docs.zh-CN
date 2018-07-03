---
title: 如何添加新的 MessageBox 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adding, MessageBox database
- MessageBox database, adding
- managing [MessageBox database], adding
ms.assetid: 98d850dc-fe3e-43dd-8b5d-9b8c23c006ae
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db394722afcdf9e5972a925963b5200b4eba157e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974518"
---
# <a name="how-to-add-a-new-messagebox-database"></a><span data-ttu-id="930bb-102">如何添加新的 MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="930bb-102">How to Add a New MessageBox Database</span></span>
<span data-ttu-id="930bb-103">可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台向 BizTalk Server 部署添加新的 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="930bb-103">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console to add a new MessageBox database to your BizTalk Server deployment.</span></span> <span data-ttu-id="930bb-104">MessageBox 数据库是跨服务器执行协作处理的负载平衡工作项的基础。</span><span class="sxs-lookup"><span data-stu-id="930bb-104">MessageBox databases are the basis for load-balancing work items across servers that do cooperative processing.</span></span> <span data-ttu-id="930bb-105">若要增加系统可处理的消息数，则可能需要添加其他 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="930bb-105">To increase the number of messages that your system can process, you may need to add additional MessageBox databases.</span></span>  
  
 <span data-ttu-id="930bb-106">您无法在创建新的 MessageBox 数据库时已登记业务流程、发送端口或发送端口组。</span><span class="sxs-lookup"><span data-stu-id="930bb-106">You cannot create a new MessageBox database and have enlisted orchestrations, send ports, or send port groups at the same time.</span></span> <span data-ttu-id="930bb-107">已登记的业务流程、发送端口或发送端口组需要访问 BizTalk Server 必须复制到新的 MessageBox 数据库中的数据。</span><span class="sxs-lookup"><span data-stu-id="930bb-107">Enlisted orchestrations, send ports, or send port groups access data that BizTalk Server must copy to the new MessageBox database.</span></span> <span data-ttu-id="930bb-108">在访问此数据的过程中，BizTalk Server 无法将其复制到新的 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="930bb-108">While this data is being accessed, BizTalk Server cannot copy it into the new MessageBox database.</span></span>  
  
 <span data-ttu-id="930bb-109">可以指定本地和远程数据库作为 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="930bb-109">You can designate both local and remote databases as MessageBox databases.</span></span> <span data-ttu-id="930bb-110">有关 BizTalk Server 数据库的信息，请参阅[BizTalk Server 中的数据库](../core/databases-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="930bb-110">For information about BizTalk Server databases, see [Databases in BizTalk Server](../core/databases-in-biztalk-server.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="930bb-111">必须在要添加新的 MessageBox 数据库的 SQL 服务器上运行 SQL Server 代理。</span><span class="sxs-lookup"><span data-stu-id="930bb-111">SQL Server Agent must be running on all of the SQL servers to which you want to add a new MessageBox database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="930bb-112">必要條件</span><span class="sxs-lookup"><span data-stu-id="930bb-112">Prerequisites</span></span>  
 <span data-ttu-id="930bb-113">管理 MessageBox 数据库的管理员必须具有所需的用户权限。</span><span class="sxs-lookup"><span data-stu-id="930bb-113">Administrators who manage MessageBox databases must have the required user rights.</span></span> <span data-ttu-id="930bb-114">必须具有以下用户权限才能管理 MessageBox 数据库并禁用新消息发布：</span><span class="sxs-lookup"><span data-stu-id="930bb-114">You must have the following user rights to manage MessageBox databases and disable new message publication:</span></span>  
  
-   <span data-ttu-id="930bb-115">必须以 BizTalk Server Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="930bb-115">You must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
-   <span data-ttu-id="930bb-116">必须是该数据库所在的计算机的 SQL Server 管理员。</span><span class="sxs-lookup"><span data-stu-id="930bb-116">You must be a SQL Server Administrator on the computer where the database exists.</span></span>  
  
### <a name="to-add-a-new-messagebox-database"></a><span data-ttu-id="930bb-117">添加新的 MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="930bb-117">To add a new MessageBox database</span></span>  
  
1. <span data-ttu-id="930bb-118">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="930bb-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="930bb-119">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、 BizTalk 组，然后依次**平台设置**。</span><span class="sxs-lookup"><span data-stu-id="930bb-119">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, and then click **Platform Settings**.</span></span>  
  
3. <span data-ttu-id="930bb-120">右键单击**消息框**，单击**新建**，然后单击**消息框**。</span><span class="sxs-lookup"><span data-stu-id="930bb-120">Right-click **Message Boxes**, click **New**, and then click **Message Box**.</span></span>  
  
4. <span data-ttu-id="930bb-121">在中**消息框属性**对话框中，执行以下操作，然后依次**确定**:</span><span class="sxs-lookup"><span data-stu-id="930bb-121">In the **Message Box Properties** dialog box, do the following, and then click **OK**:</span></span>  
  
   |<span data-ttu-id="930bb-122">使用此选项</span><span class="sxs-lookup"><span data-stu-id="930bb-122">Use this</span></span>|<span data-ttu-id="930bb-123">执行的操作</span><span class="sxs-lookup"><span data-stu-id="930bb-123">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="930bb-124">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="930bb-124">**SQL Server**</span></span>|<span data-ttu-id="930bb-125">显示承载 MessageBox 数据库的 SQL 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="930bb-125">Displays the name of the SQL server that hosts the MessageBox database.</span></span>|  
   |<span data-ttu-id="930bb-126">**“数据库”**</span><span class="sxs-lookup"><span data-stu-id="930bb-126">**Database**</span></span>|<span data-ttu-id="930bb-127">显示 MessageBox 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="930bb-127">Displays the name of the MessageBox database.</span></span>|  
   |<span data-ttu-id="930bb-128">**主订阅 messagebox**</span><span class="sxs-lookup"><span data-stu-id="930bb-128">**Master subscription message box**</span></span>|<span data-ttu-id="930bb-129">指示选定的 MessageBox 数据库是否为主数据库。</span><span class="sxs-lookup"><span data-stu-id="930bb-129">Indicates whether the selected MessageBox database is the master.</span></span> <span data-ttu-id="930bb-130">如果当前的 MessageBox 数据库为主数据库，则此复选框将处于选中状态并且不可用。</span><span class="sxs-lookup"><span data-stu-id="930bb-130">If the current MessageBox database is the master, this check box is selected and unavailable.</span></span> <span data-ttu-id="930bb-131">默认情况下，运行配置向导时创建的第一个 MessageBox 数据库为主数据库。</span><span class="sxs-lookup"><span data-stu-id="930bb-131">The first MessageBox database created when you run the Configuration Wizard is the master by default.</span></span>|  
   |<span data-ttu-id="930bb-132">**禁止发布新消息**</span><span class="sxs-lookup"><span data-stu-id="930bb-132">**Disable new message publication**</span></span>|<span data-ttu-id="930bb-133">选中此复选框可指定不希望此 MessageBox 数据库接收激活消息。</span><span class="sxs-lookup"><span data-stu-id="930bb-133">Select this check box to specify that you do not want this MessageBox database to receive activation messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="930bb-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="930bb-134">See Also</span></span>  
 <span data-ttu-id="930bb-135">[管理 MessageBox 数据库](../core/managing-messagebox-databases.md) </span><span class="sxs-lookup"><span data-stu-id="930bb-135">[Managing MessageBox Databases](../core/managing-messagebox-databases.md) </span></span>  
 <span data-ttu-id="930bb-136">[如何禁用发布新消息](../core/how-to-disable-new-message-publication.md) </span><span class="sxs-lookup"><span data-stu-id="930bb-136">[How to Disable New Message Publication](../core/how-to-disable-new-message-publication.md) </span></span>  
 <span data-ttu-id="930bb-137">[如何删除 MessageBox 数据库](../core/how-to-delete-a-messagebox-database.md) </span><span class="sxs-lookup"><span data-stu-id="930bb-137">[How to Delete a MessageBox Database](../core/how-to-delete-a-messagebox-database.md) </span></span>  
 <span data-ttu-id="930bb-138">[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="930bb-138">[Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md) </span></span>  
 [<span data-ttu-id="930bb-139">MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="930bb-139">The MessageBox Database</span></span>](../core/the-messagebox-database.md)