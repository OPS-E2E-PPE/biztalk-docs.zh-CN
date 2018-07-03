---
title: 如何移动 BAM 星型架构数据库 1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Star Schema database [BAM], migrating
- migrating, Star Schema database [BAM]
ms.assetid: b4a5f8fc-0dc4-4987-b96f-ecd49bd4dba3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3068c9d1c72c30c51f77d9fad7b8ddf5881ed09
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983406"
---
# <a name="how-to-move-the-bam-star-schema-database"></a><span data-ttu-id="afec3-102">如何移动 BAM 星型架构数据库</span><span class="sxs-lookup"><span data-stu-id="afec3-102">How to Move the BAM Star Schema Database</span></span>
<span data-ttu-id="afec3-103">您可以使用此过程将 BAM 星型架构数据库移到其他服务器。</span><span class="sxs-lookup"><span data-stu-id="afec3-103">You can use this procedure to move the BAM Star Schema database to another server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="afec3-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="afec3-104">Prerequisites</span></span>  
 <span data-ttu-id="afec3-105">若要执行此过程，必须以 SQL Server sysadmin 固定服务器角色成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="afec3-105">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-move-the-bam-star-schema-database"></a><span data-ttu-id="afec3-106">移动 BAM 星型架构数据库</span><span class="sxs-lookup"><span data-stu-id="afec3-106">To move the BAM Star Schema database</span></span>  
  
1. <span data-ttu-id="afec3-107">获取用于还原 BAM 的 .xml 文件的副本：</span><span class="sxs-lookup"><span data-stu-id="afec3-107">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
   1. <span data-ttu-id="afec3-108">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="afec3-108">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2. <span data-ttu-id="afec3-109">在命令提示符下，导航到以下目录：</span><span class="sxs-lookup"><span data-stu-id="afec3-109">At the command prompt, navigate to the following directory:</span></span>  
  
       [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="afec3-110">Tracking</span><span class="sxs-lookup"><span data-stu-id="afec3-110">Tracking</span></span>  
  
   3. <span data-ttu-id="afec3-111">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="afec3-111">At the command prompt, type:</span></span>  
  
      ```  
      Bm.exe get-config –filename:BAMConfiguration.xml  
      ```  
  
      > [!NOTE]
      >  <span data-ttu-id="afec3-112">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="afec3-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
2. <span data-ttu-id="afec3-113">有关如何在旧服务器上备份数据库按照 SQL Server 联机丛书中的说明。</span><span class="sxs-lookup"><span data-stu-id="afec3-113">Follow the instructions in SQL Server Books Online on how to back up the database on the old server.</span></span>  
  
3. <span data-ttu-id="afec3-114">将 BAM 星型架构数据库复制到新的 SQL Server 中。</span><span class="sxs-lookup"><span data-stu-id="afec3-114">Copy the BAM Star Schema database to the new SQL Server.</span></span>  
  
4. <span data-ttu-id="afec3-115">有关如何还原新服务器上的数据库，请按照 SQL Server 联机丛书中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="afec3-115">Follow the instructions in SQL Server Books Online on how to restore the database on the new server.</span></span>  
  
5. <span data-ttu-id="afec3-116">编辑 BAMConfiguration.xml 文件，将 StarSchemaDatabase DeploymentUnit 部分中的 ServerName 更改为新服务器名称。</span><span class="sxs-lookup"><span data-stu-id="afec3-116">Edit the BAMConfiguration.xml file and change the ServerName in the StarSchemaDatabase DeploymentUnit section to the new server name.</span></span>  
  
6. <span data-ttu-id="afec3-117">保存并关闭 BAMConfiguration.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="afec3-117">Save and close the BAMConfiguration.xml file.</span></span>  
  
7. <span data-ttu-id="afec3-118">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="afec3-118">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="afec3-119">在命令提示符下，导航到以下目录：</span><span class="sxs-lookup"><span data-stu-id="afec3-119">At the command prompt, navigate to the following directory:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="afec3-120">Tracking</span><span class="sxs-lookup"><span data-stu-id="afec3-120">Tracking</span></span>  
  
9. <span data-ttu-id="afec3-121">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="afec3-121">At the command prompt, type:</span></span>  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="afec3-122">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="afec3-122">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
10. <span data-ttu-id="afec3-123">按照以下步骤，更新 SQL Connection 2 以更改所有 BAM 分析 DTS 包（带有“BAM_AN_”前缀）中的服务器名称和数据库名称：</span><span class="sxs-lookup"><span data-stu-id="afec3-123">Update SQL Connection 2 to change the server and database name in all BAM analysis DTS packages, which are prefixed with "BAM_AN_", by following these steps:</span></span>  
  
    1.  <span data-ttu-id="afec3-124">使用 SQL Server Management Studio 打开 BAM 的宿主服务器。</span><span class="sxs-lookup"><span data-stu-id="afec3-124">Using SQL Server Management Studio, open the server hosting BAM.</span></span>  
  
    2.  <span data-ttu-id="afec3-125">打开**Data Transformation Services**文件夹。</span><span class="sxs-lookup"><span data-stu-id="afec3-125">Open the **Data Transformation Services** folder.</span></span>  
  
    3.  <span data-ttu-id="afec3-126">打开**本地包**文件夹。</span><span class="sxs-lookup"><span data-stu-id="afec3-126">Open the **Local Packages** folder.</span></span>  
  
    4.  <span data-ttu-id="afec3-127">打开 DTS 包，然后双击**Connection 2**来打开连接。</span><span class="sxs-lookup"><span data-stu-id="afec3-127">Open the DTS package, and then double-click **Connection 2** to open the connection.</span></span>  
  
    5.  <span data-ttu-id="afec3-128">在下拉框中选择新的服务器名称和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="afec3-128">Select the new server and database name in the drop-down box.</span></span>  
  
11. <span data-ttu-id="afec3-129">按照以下步骤更新 BAM 分析数据库中的数据源：</span><span class="sxs-lookup"><span data-stu-id="afec3-129">Update the data source in the BAM Analysis database as follows:</span></span>  
  
    1.  <span data-ttu-id="afec3-130">使用 SQL Server 分析管理器，打开 BAM 分析数据库的宿主服务器。</span><span class="sxs-lookup"><span data-stu-id="afec3-130">Using SQL Server Analysis Manager, open the server hosting the BAM Analysis database.</span></span>  
  
    2.  <span data-ttu-id="afec3-131">打开**数据源**文件夹。</span><span class="sxs-lookup"><span data-stu-id="afec3-131">Open the **Data Sources** folder.</span></span>  
  
    3.  <span data-ttu-id="afec3-132">右键单击多维数据集，数据源，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="afec3-132">Right-click the data source for the cube, and then click **Edit**.</span></span>  
  
    4.  <span data-ttu-id="afec3-133">上**连接**选项卡上，键入新的服务器名称和 BAM 星型架构数据库，数据库名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="afec3-133">On the **Connection** tab, type the new server name and database name for the BAM Star Schema database, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afec3-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="afec3-134">See Also</span></span>  
 [<span data-ttu-id="afec3-135">移动 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="afec3-135">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)