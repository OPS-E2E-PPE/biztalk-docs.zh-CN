---
title: "如何移动 BAM 存档 Database2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Archive database [BAM], migrating
- migrating, Archive database [BAM]
ms.assetid: 88b96dc2-8c9c-43f5-afb9-a937e05de36b
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4398e155168a903d39f3fbd1c9fd8f1421862cc1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-the-bam-archive-database"></a><span data-ttu-id="1c026-102">如何移动 BAM 存档数据库</span><span class="sxs-lookup"><span data-stu-id="1c026-102">How to Move the BAM Archive Database</span></span>
<span data-ttu-id="1c026-103">您可以使用此过程将 BAM 存档数据库移到其他服务器。</span><span class="sxs-lookup"><span data-stu-id="1c026-103">You can use this procedure to move the BAM Archive database to another server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1c026-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="1c026-104">Prerequisites</span></span>  
 <span data-ttu-id="1c026-105">若要执行此过程，必须以 SQL Server sysadmin 固定服务器角色成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="1c026-105">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-move-the-bam-archive-database"></a><span data-ttu-id="1c026-106">移动 BAM 存档数据库</span><span class="sxs-lookup"><span data-stu-id="1c026-106">To move the BAM Archive database</span></span>  
  
1.  <span data-ttu-id="1c026-107">获取用于还原 BAM 的 .xml 文件的副本：</span><span class="sxs-lookup"><span data-stu-id="1c026-107">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
    1.  <span data-ttu-id="1c026-108">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1c026-108">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="1c026-109">在命令提示符下，导航到以下目录：</span><span class="sxs-lookup"><span data-stu-id="1c026-109">At the command prompt, navigate to the following directory:</span></span>  
  
         [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="1c026-110">Tracking</span><span class="sxs-lookup"><span data-stu-id="1c026-110">Tracking</span></span>  
  
    3.  <span data-ttu-id="1c026-111">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="1c026-111">At the command prompt, type:</span></span>  
  
        ```  
        Bm.exe get-config –filename:BAMConfiguration.xml  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="1c026-112">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="1c026-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
2.  <span data-ttu-id="1c026-113">按照 SQL Server 联机丛书中的说明，以将旧的服务器上备份数据库。</span><span class="sxs-lookup"><span data-stu-id="1c026-113">Follow the instructions in SQL Server Books Online to back up the database on the old server.</span></span>  
  
3.  <span data-ttu-id="1c026-114">将 BAM 存档数据库复制到新的 SQL Server 中。</span><span class="sxs-lookup"><span data-stu-id="1c026-114">Copy the BAM Archive database to the new SQL server.</span></span>  
  
4.  <span data-ttu-id="1c026-115">按照 SQL Server 联机丛书中的说明还原新服务器上的数据库。</span><span class="sxs-lookup"><span data-stu-id="1c026-115">Follow the instructions in SQL Server Books Online to restore the database on the new server.</span></span>  
  
5.  <span data-ttu-id="1c026-116">编辑 BAMConfiguration.xml 文件，将 ArchivingDatabase DeploymentUnit 部分中的 ServerName 更改为新服务器名称。</span><span class="sxs-lookup"><span data-stu-id="1c026-116">Edit the BAMConfiguration.xml file and change the ServerName in the ArchivingDatabase DeploymentUnit section to the new server name.</span></span>  
  
6.  <span data-ttu-id="1c026-117">保存并关闭 BAMConfiguration.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="1c026-117">Save and close the BAMConfiguration.xml file.</span></span>  
  
7.  <span data-ttu-id="1c026-118">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1c026-118">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="1c026-119">在命令提示符下，导航到以下目录：</span><span class="sxs-lookup"><span data-stu-id="1c026-119">At the command prompt, navigate to the following directory:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="1c026-120">Tracking</span><span class="sxs-lookup"><span data-stu-id="1c026-120">Tracking</span></span>  
  
9. <span data-ttu-id="1c026-121">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="1c026-121">At the command prompt, type:</span></span>  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="1c026-122">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="1c026-122">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c026-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c026-123">See Also</span></span>  
 [<span data-ttu-id="1c026-124">将 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="1c026-124">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)