---
title: "如何移动 BAM 通知 Services Databases2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Notification Services Application database [BAM]
- Notification Services Instance database [BAM]
- migrating, Notification Services database [BAM]
ms.assetid: 4b7f3397-65c9-4c71-8374-8764f4c2e2e3
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 639a326878cd425a951581711c08a0a53127035b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-the-bam-notification-services-databases"></a><span data-ttu-id="713b0-102">如何移动 BAM 通知 Services 数据库</span><span class="sxs-lookup"><span data-stu-id="713b0-102">How to Move the BAM Notification Services Databases</span></span>
<span data-ttu-id="713b0-103">您可以使用此过程将 BAM Notification Services 数据库移到其他服务器。</span><span class="sxs-lookup"><span data-stu-id="713b0-103">You can use this procedure to move the BAM Notification Services databases to another server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="713b0-104">BAM Notification Services 应用程序 (BAMAlertsApplication) 数据库和 BAM Notification Services 实例 (BAMAlertsNSMain) 数据库必须一起移动。</span><span class="sxs-lookup"><span data-stu-id="713b0-104">You must move the BAM Notification Services Application (BAMAlertsApplication) database and BAM Notification Services Instance (BAMAlertsNSMain) database together.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="713b0-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="713b0-105">Prerequisites</span></span>  
 <span data-ttu-id="713b0-106">若要执行此过程，必须以 SQL Server sysadmin 固定服务器角色成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="713b0-106">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-move-the-bam-notification-services-databases"></a><span data-ttu-id="713b0-107">移动 BAM Notification Services 数据库</span><span class="sxs-lookup"><span data-stu-id="713b0-107">To move the BAM Notification Services databases</span></span>  
  
1.  <span data-ttu-id="713b0-108">获取用于还原 BAM 的 .xml 文件的副本：</span><span class="sxs-lookup"><span data-stu-id="713b0-108">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
    1.  <span data-ttu-id="713b0-109">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="713b0-109">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="713b0-110">在命令提示符下，导航到以下目录：</span><span class="sxs-lookup"><span data-stu-id="713b0-110">At the command prompt, navigate to the following directory:</span></span>  
  
         <span data-ttu-id="713b0-111">**%SystemDrive%\Program Files\Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\Tracking** </span><span class="sxs-lookup"><span data-stu-id="713b0-111">**%SystemDrive%\Program Files\Microsoft**  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\Tracking**</span></span>  
  
    3.  <span data-ttu-id="713b0-112">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="713b0-112">At the command prompt, type:</span></span>  
  
        ```  
        Bm.exe get-config –filename:BAMConfiguration.xml  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="713b0-113">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="713b0-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
2.  <span data-ttu-id="713b0-114">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="713b0-114">At the command prompt, type:</span></span>  
  
    ```  
    Net stop NS$BamAlerts  
    ```  
  
3.  <span data-ttu-id="713b0-115">有关如何将旧的服务器上备份数据库按照 SQL Server 联机丛书中的说明。</span><span class="sxs-lookup"><span data-stu-id="713b0-115">Follow the instructions in SQL Server Books Online on how to back up the database on the old server.</span></span>  
  
4.  <span data-ttu-id="713b0-116">将 BAM Notification Services 数据库复制到新的 SQL Server 中。</span><span class="sxs-lookup"><span data-stu-id="713b0-116">Copy the BAM Notification Services databases to the new SQL server.</span></span>  
  
5.  <span data-ttu-id="713b0-117">按照如何还原新服务器上的数据库上的 SQL Server 联机丛书中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="713b0-117">Follow the instructions in SQL Server Books Online on how to restore the database on the new server.</span></span>  
  
6.  <span data-ttu-id="713b0-118">编辑 BAMConfiguration.xml 文件，将 Alert DeploymentUnit 部分中的 ServerName 更改为新服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="713b0-118">Edit the BAMConfiguration.xml file and change the ServerName in the Alert DeploymentUnit section to the new server name.</span></span>  
  
7.  <span data-ttu-id="713b0-119">保存并关闭 BAMConfiguration.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="713b0-119">Save and close the BAMConfiguration.xml file.</span></span>  
  
8.  <span data-ttu-id="713b0-120">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="713b0-120">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="713b0-121">在命令提示符下，导航到以下目录：</span><span class="sxs-lookup"><span data-stu-id="713b0-121">At the command prompt, navigate to the following directory:</span></span>  
  
     <span data-ttu-id="713b0-122">**%SystemDrive%\Program Files\Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\Tracking** </span><span class="sxs-lookup"><span data-stu-id="713b0-122">**%SystemDrive%\Program Files\Microsoft**  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\Tracking**</span></span>  
  
10. <span data-ttu-id="713b0-123">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="713b0-123">At the command prompt, type:</span></span>  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="713b0-124">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="713b0-124">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
11. <span data-ttu-id="713b0-125">更新对 BAM Notification Services 数据库的引用。</span><span class="sxs-lookup"><span data-stu-id="713b0-125">Update references to the BAM Notification Services databases.</span></span> <span data-ttu-id="713b0-126">有关详细信息，请参阅[如何对 BAM 通知服务数据库的更新引用](../core/how-to-update-references-to-the-bam-notification-services-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="713b0-126">For more information, see [How to Update References to the BAM Notification Services Databases](../core/how-to-update-references-to-the-bam-notification-services-databases.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="713b0-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="713b0-127">See Also</span></span>  
 [<span data-ttu-id="713b0-128">将 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="713b0-128">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)