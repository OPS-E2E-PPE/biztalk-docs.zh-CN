---
title: 如何配置用于存档和清除数据从跟踪数据库 BizTalk BTS_BACKUP_USERS 角色 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- purging, BTS_BACKUP_USERS role
- Tracking database, purging
- BTS_BACKUP_USERS role
- DTA Purge and Archive job
- archiving [Tracking database], BTS_BACKUP_USERS role
- archiving [Tracking database], DTA Purge and Archive job
- Tracking database, BTS_BACKUP_USERS role
- Tracking database, archiving
- purging, DTA Purge and Archive job
ms.assetid: c27aad2a-5788-4236-b5eb-ca730bf79851
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 923fb083f3755259ab2176541213d1637ce872c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232445"
---
# <a name="how-to-configure-the-btsbackupusers-role-for-archiving-and-purging-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="e1e57-102">如何配置 BTS_BACKUP_USERS 角色以存档和清除 BizTalk 跟踪数据库中的数据</span><span class="sxs-lookup"><span data-stu-id="e1e57-102">How to Configure the BTS_BACKUP_USERS Role for Archiving and Purging Data from the BizTalk Tracking Database</span></span>
<span data-ttu-id="e1e57-103">DTA 清除和存档 (BizTAlkDTADb) 作业通常使用已登录的 SQL Server 代理服务帐户用户的凭据运行。</span><span class="sxs-lookup"><span data-stu-id="e1e57-103">The DTA Purge and Archive (BizTAlkDTADb) job normally runs using the credentials of the logged-on SQL Server Agent service account user.</span></span> <span data-ttu-id="e1e57-104">但是，为了增强安全性，可以将 DTA 清除和存档 (BizTalkDTADb) 作业配置为使用 BTS_BACKUP_USERS 角色的成员帐户的凭据运行。</span><span class="sxs-lookup"><span data-stu-id="e1e57-104">For added security, however, you can configure the DTA Purge and Archive (BizTalkDTADb) job to run using the credentials of an account which is a member of the BTS_BACKUP_USERS role.</span></span> <span data-ttu-id="e1e57-105">通过以具有基本权限的帐户身份运行 SQL Server 代理作业，这样可以防止特权提升。</span><span class="sxs-lookup"><span data-stu-id="e1e57-105">This helps to prevent elevation of privileges by running SQL Server Agent jobs under accounts with essential permissions.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e1e57-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="e1e57-106">Prerequisites</span></span>  
 <span data-ttu-id="e1e57-107">若要执行此过程，必须以 SQL Server sysadmin 固定服务器角色成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="e1e57-107">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-configure-the-btsbackupusers-role-for-archiving-and-purging-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="e1e57-108">配置 BTS_BACKUP_USERS 角色以存档和清除 BizTalk 跟踪数据库中的数据</span><span class="sxs-lookup"><span data-stu-id="e1e57-108">To configure the BTS_BACKUP_USERS role for archiving and purging data from the BizTalk Tracking database</span></span>  
  
1.  <span data-ttu-id="e1e57-109">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="e1e57-109">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="e1e57-110">在**连接到服务器**对话框中，指定 BizTalk 跟踪 (BizTalkDTADb) 数据库所在的 SQL server 和适当的身份验证类型的名称，然后单击**连接**到连接到相应的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="e1e57-110">In the **Connect to Server** dialog box, specify the name of the SQL server where the BizTalk Tracking (BizTalkDTADb) database resides and the appropriate authentication type, and then click **Connect** to connect to the appropriate SQL Server.</span></span>  
  
3.  <span data-ttu-id="e1e57-111">在**Microsoft SQL Server Management Studio**，双击**BizTalkDTADb**，双击**安全**，双击**角色**，和然后双击**数据库角色**。</span><span class="sxs-lookup"><span data-stu-id="e1e57-111">In **Microsoft SQL Server Management Studio**, double-click **BizTalkDTADb**, double-click **Security**, double-click **Roles**, and then double-click **Database Roles**.</span></span>  
  
4.  <span data-ttu-id="e1e57-112">在**对象资源管理器详细信息**窗格中，双击**BTS_BACKUP_USERS**。</span><span class="sxs-lookup"><span data-stu-id="e1e57-112">In the **Object Explorer Details** pane, double-click **BTS_BACKUP_USERS**.</span></span>  
  
5.  <span data-ttu-id="e1e57-113">在**数据库角色属性-BTS_BACKUP_USERS**对话框中，在**此角色的成员**，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="e1e57-113">In the **Database Role Properties – BTS_BACKUP_USERS** dialog box, under **Members of this role**, click **Add**.</span></span>  
  
6.  <span data-ttu-id="e1e57-114">在**选择数据库用户或角色**对话框中，输入具有 SQL Server 代理服务凭据的用户帐户，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e1e57-114">In the **Select Database User or Role** dialog box, enter a user account with SQL Server Agent Service credentials, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e57-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1e57-115">See Also</span></span>  
 [<span data-ttu-id="e1e57-116">存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="e1e57-116">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)