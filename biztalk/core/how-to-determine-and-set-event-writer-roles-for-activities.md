---
title: 如何确定和设置活动的事件写入者角色 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73bfe8ff-167a-4bf0-ab87-3926290d52d8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc3ff2fcc8ed4397db8d1eb8d5906cebd5c26af1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385262"
---
# <a name="how-to-determine-and-set-event-writer-roles-for-activities"></a><span data-ttu-id="916d6-102">如何确定和设置活动的事件写入者角色</span><span class="sxs-lookup"><span data-stu-id="916d6-102">How to Determine and Set Event Writer Roles for Activities</span></span>
<span data-ttu-id="916d6-103">BAM 在写入活动事件时提供两种安全模式。</span><span class="sxs-lookup"><span data-stu-id="916d6-103">BAM provides two modes of security when writing events on activities.</span></span> <span data-ttu-id="916d6-104">您可以授予写入单独活动的事件的权限或您可以授予权限将事件写入上所有已部署的活动。</span><span class="sxs-lookup"><span data-stu-id="916d6-104">You can grant permissions to write events on individual activities or you can grant permissions to write events on all deployed activities.</span></span>  
  
 <span data-ttu-id="916d6-105">活动级别的安全性提供的部署 BAM 定义时创建的活动事件写入者角色。</span><span class="sxs-lookup"><span data-stu-id="916d6-105">Activity-level security is provided by activity event writer roles that are created when you deploy a BAM definition.</span></span> <span data-ttu-id="916d6-106">例如，如果部署为 CreditCard 的活动的定义，则 BAM 将创建名为 bam_CreditCard_EventWriter 的事件写入者角色。</span><span class="sxs-lookup"><span data-stu-id="916d6-106">For example, if you deploy a definition for an activity named CreditCard, BAM creates an event writer role named bam_CreditCard_EventWriter.</span></span> <span data-ttu-id="916d6-107">此角色具有写入活动事件的权限。</span><span class="sxs-lookup"><span data-stu-id="916d6-107">This role has permissions to write events for the activity.</span></span> <span data-ttu-id="916d6-108">若要授予用户写入活动事件的权限，请向角色添加用户。</span><span class="sxs-lookup"><span data-stu-id="916d6-108">To grant a user permissions to write events for the activity, you add the user to the role.</span></span>  
  
 <span data-ttu-id="916d6-109">或者，可以授予用户权限，以便将它们添加到超级角色 BAM_EVENT_WRITER，有权写入所有活动 eve2nts 都写入所有活动。</span><span class="sxs-lookup"><span data-stu-id="916d6-109">Alternatively, you can grant users rights to write eve2nts to all activities by adding them to the super role BAM_EVENT_WRITER, which has permissions to write to all activities.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="916d6-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="916d6-110">Prerequisites</span></span>  
 <span data-ttu-id="916d6-111">若要执行此过程，您必须：</span><span class="sxs-lookup"><span data-stu-id="916d6-111">To perform this procedure, you must have the following:</span></span>  
  
-   <span data-ttu-id="916d6-112">部署该活动的 bamprimaryimportdb 的连接。</span><span class="sxs-lookup"><span data-stu-id="916d6-112">A connection to BAMPrimaryImportDb on which the activity is deployed.</span></span>  
  
-   <span data-ttu-id="916d6-113">数据库的 DBO 权限。</span><span class="sxs-lookup"><span data-stu-id="916d6-113">DBO permissions on the database.</span></span>  
  
### <a name="to-add-a-user-to-an-event-writer-role"></a><span data-ttu-id="916d6-114">若要将用户添加到事件写入者角色</span><span class="sxs-lookup"><span data-stu-id="916d6-114">To add a user to an event writer role</span></span>  
  
1.  <span data-ttu-id="916d6-115">单击**启动**，依次指向**所有程序**，单击**Microsoft SQL Server 2008**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="916d6-115">Click **Start**, point to **All Programs**, click **Microsoft SQL Server 2008**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="916d6-116">在中**连接到 SQL Server**对话框中，选择 SQL Server 和相应的身份验证方法，然后单击**Connect**。</span><span class="sxs-lookup"><span data-stu-id="916d6-116">In the **Connect to SQL Server** dialog box, select the SQL Server and the appropriate authentication method, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="916d6-117">在中**对象资源管理器**窗格中展开**数据库**，然后选择 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="916d6-117">In the **Object Explorer** pane expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
4.  <span data-ttu-id="916d6-118">单击**新查询**工具栏上的图标。</span><span class="sxs-lookup"><span data-stu-id="916d6-118">Click the **New Query** icon on the toolbar.</span></span>  
  
5.  <span data-ttu-id="916d6-119">复制以下命令并将其粘贴到查询窗口。</span><span class="sxs-lookup"><span data-stu-id="916d6-119">Copy the following commands and paste them into the Query Window.</span></span> <span data-ttu-id="916d6-120">域名、 用户名和活动名称占位符替换为适当的值。</span><span class="sxs-lookup"><span data-stu-id="916d6-120">Replace the domain name, user name, and activity name placeholders with the appropriate values.</span></span>  
  
    ```  
    EXEC sp_grantlogin '<domain name>\<user name>’  
    EXEC sp_grantdbaccess '<domain name>\<user name>', 'ActivityLogin'  
    EXEC sp_addrolemember 'bam_<activity name>_EventWriter', 'SpecialLogin'  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="916d6-121">角色名称是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="916d6-121">Role names are case-sensitive.</span></span> <span data-ttu-id="916d6-122">活动名称也是区分大小写，也就是说，它们必须匹配部署活动时使用这种情况。</span><span class="sxs-lookup"><span data-stu-id="916d6-122">Activity names are also case-sensitive, that is, they must match the case used when deploying the activity.</span></span>  
  
6.  <span data-ttu-id="916d6-123">单击**Execute**按 f5 键以运行命令的工具栏上的图标。</span><span class="sxs-lookup"><span data-stu-id="916d6-123">Click the **Execute** icon on the toolbar or press F5 to run the commands.</span></span>  
  
### <a name="to-add-a-user-to-an-event-writer-super-role"></a><span data-ttu-id="916d6-124">若要将用户添加到事件写入者超级角色</span><span class="sxs-lookup"><span data-stu-id="916d6-124">To add a user to an event writer super role</span></span>  
  
1.  <span data-ttu-id="916d6-125">单击**启动**，依次指向**所有程序**，单击**Microsoft SQL Server 2008**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="916d6-125">Click **Start**, point to **All Programs**, click **Microsoft SQL Server 2008**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="916d6-126">在中**连接到 SQL Server**对话框中，选择 SQL Server 和相应的身份验证方法，然后单击**Connect**。</span><span class="sxs-lookup"><span data-stu-id="916d6-126">In the **Connect to SQL Server** dialog box, select the SQL Server and the appropriate authentication method, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="916d6-127">在中**对象资源管理器**窗格中展开**数据库**，然后选择 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="916d6-127">In the **Object Explorer** pane expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
4.  <span data-ttu-id="916d6-128">单击**新查询**工具栏上的图标。</span><span class="sxs-lookup"><span data-stu-id="916d6-128">Click the **New Query** icon on the toolbar.</span></span>  
  
5.  <span data-ttu-id="916d6-129">复制以下命令并将其粘贴到查询窗口。</span><span class="sxs-lookup"><span data-stu-id="916d6-129">Copy the following commands and paste them into the Query Window.</span></span> <span data-ttu-id="916d6-130">使用适当的值替换域名和用户名。</span><span class="sxs-lookup"><span data-stu-id="916d6-130">Replace the domain name and user name with the appropriate values.</span></span>  
  
    ```  
    EXEC sp_grantlogin '<domain name>\<user name>’  
    EXEC sp_grantdbaccess '<domain name>\<user name>', 'ActivityLogin'  
    EXEC sp_addrolemember 'BAM_EVENT_WRITER', 'SpecialLogin'  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="916d6-131">角色名称是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="916d6-131">Role names are case sensitive.</span></span> <span data-ttu-id="916d6-132">您必须指定为指定的事件写入者角色。</span><span class="sxs-lookup"><span data-stu-id="916d6-132">You must specify the event writer role as specified.</span></span>  
  
6.  <span data-ttu-id="916d6-133">单击**Execute**按 f5 键以运行命令的工具栏上的图标。</span><span class="sxs-lookup"><span data-stu-id="916d6-133">Click the **Execute** icon on the toolbar or press F5 to run the commands.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="916d6-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="916d6-134">See Also</span></span>  
 [<span data-ttu-id="916d6-135">管理 BAM 安全性</span><span class="sxs-lookup"><span data-stu-id="916d6-135">Managing BAM Security</span></span>](../core/managing-bam-security.md)