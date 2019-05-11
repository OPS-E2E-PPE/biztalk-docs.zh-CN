---
title: 如何移动 BAM 分析数据库 2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, Analysis database [BAM]
- Analysis database [BAM], migrating
ms.assetid: b0320273-4840-4573-bb82-bba95021535e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9f0afd5c8bbd06786c07b84dd465f97cbb1559d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384515"
---
# <a name="how-to-move-the-bam-analysis-database"></a><span data-ttu-id="8c39c-102">如何移动 BAM 分析数据库</span><span class="sxs-lookup"><span data-stu-id="8c39c-102">How to Move the BAM Analysis Database</span></span>
<span data-ttu-id="8c39c-103">可以使用此过程将 BAM 分析数据库移到另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="8c39c-103">You can use this procedure to move the BAM Analysis database to another server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8c39c-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="8c39c-104">Prerequisites</span></span>  
 <span data-ttu-id="8c39c-105">您必须是 SQL Server sysadmin 固定服务器角色的成员才能执行此过程的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="8c39c-105">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-move-the-bam-analysis-database"></a><span data-ttu-id="8c39c-106">移动 BAM 分析数据库</span><span class="sxs-lookup"><span data-stu-id="8c39c-106">To move the BAM Analysis database</span></span>  
  
1. <span data-ttu-id="8c39c-107">获取用于还原 BAM 的.xml 文件的副本：</span><span class="sxs-lookup"><span data-stu-id="8c39c-107">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
   1. <span data-ttu-id="8c39c-108">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8c39c-108">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2. <span data-ttu-id="8c39c-109">在命令提示符处，导航到以下目录：</span><span class="sxs-lookup"><span data-stu-id="8c39c-109">At the command prompt, navigate to the following directory:</span></span>  
  
       [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="8c39c-110">跟踪</span><span class="sxs-lookup"><span data-stu-id="8c39c-110">Tracking</span></span>  
  
   3. <span data-ttu-id="8c39c-111">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="8c39c-111">At the command prompt, type:</span></span>  
  
      ```  
      Bm.exe get-config –filename:BAMConfiguration.xml  
      ```  
  
      > [!NOTE]
      >  <span data-ttu-id="8c39c-112">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="8c39c-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
2. <span data-ttu-id="8c39c-113">有关如何在旧服务器上备份数据库按照 SQL Server 联机丛书中的说明。</span><span class="sxs-lookup"><span data-stu-id="8c39c-113">Follow the instructions in SQL Server Books Online on how to back up the database on the old server.</span></span>  
  
3. <span data-ttu-id="8c39c-114">将 BAM 分析数据库复制到新的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="8c39c-114">Copy the BAM Analysis database to the new SQL Server.</span></span>  
  
4. <span data-ttu-id="8c39c-115">有关如何还原新服务器上的数据库，请按照 SQL Server 联机丛书中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="8c39c-115">Follow the instructions in SQL Server Books Online on how to restore the database on the new server.</span></span>  
  
5. <span data-ttu-id="8c39c-116">编辑 BAMConfiguration.xml 文件，并将 AnalysisDatabase DeploymentUnit 部分中的 ServerName 更改为新的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="8c39c-116">Edit the BAMConfiguration.xml file and change the ServerName in the AnalysisDatabase DeploymentUnit section to the new server name.</span></span>  
  
6. <span data-ttu-id="8c39c-117">保存并关闭 BAMConfiguration.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="8c39c-117">Save and close the BAMConfiguration.xml file.</span></span>  
  
7. <span data-ttu-id="8c39c-118">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8c39c-118">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="8c39c-119">在命令提示符处，导航到以下目录：</span><span class="sxs-lookup"><span data-stu-id="8c39c-119">At the command prompt, navigate to the following directory:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="8c39c-120">跟踪</span><span class="sxs-lookup"><span data-stu-id="8c39c-120">Tracking</span></span>  
  
9. <span data-ttu-id="8c39c-121">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="8c39c-121">At the command prompt, type:</span></span>  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="8c39c-122">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="8c39c-122">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c39c-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c39c-123">See Also</span></span>  
 [<span data-ttu-id="8c39c-124">移动 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="8c39c-124">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)