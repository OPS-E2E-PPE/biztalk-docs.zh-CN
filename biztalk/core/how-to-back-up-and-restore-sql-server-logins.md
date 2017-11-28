---
title: "如何备份和还原 SQL Server 登录名 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 847c3a3d-0d97-415b-893e-4ba173085bae
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54fa6a51a27f82add8a96c613e36f5ed7ce88e87
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-back-up-and-restore-sql-server-logins"></a><span data-ttu-id="2e6b8-102">如何备份和还原 SQL Server 登录名</span><span class="sxs-lookup"><span data-stu-id="2e6b8-102">How to Back Up and Restore SQL Server Logins</span></span>
<span data-ttu-id="2e6b8-103">备份和还原与 BizTalk Server 关联的 SQL Server 登录名。</span><span class="sxs-lookup"><span data-stu-id="2e6b8-103">Back up and restore SQL Server logins associated with BizTalk Server.</span></span>  
  
## <a name="biztalk-server-sql-server-security-logins"></a><span data-ttu-id="2e6b8-104">BizTalk Server SQL Server 安全登录</span><span class="sxs-lookup"><span data-stu-id="2e6b8-104">BizTalk Server SQL Server Security Logins</span></span>  
 <span data-ttu-id="2e6b8-105">下面列出了与 BizTalk Server 关联的 SQL Server 安全登录。</span><span class="sxs-lookup"><span data-stu-id="2e6b8-105">The SQL Server security logins listed below are associated with BizTalk Server.</span></span> <span data-ttu-id="2e6b8-106">你可能有更多的登录与所创建的 BizTalk Server 应用程序相关联。</span><span class="sxs-lookup"><span data-stu-id="2e6b8-106">You may have additional logins associated with the BizTalk Server applications you have created.</span></span> <span data-ttu-id="2e6b8-107">将 BizTalk Server 数据库移动到新服务器或 SQL Server 的新实例时，需要备份和还原此登录。</span><span class="sxs-lookup"><span data-stu-id="2e6b8-107">You need to back up the logins and restore them when moving the BizTalk Server databases to a new server or new instance of SQL Server.</span></span>  
  
-   <span data-ttu-id="2e6b8-108">BizTalk Application Users</span><span class="sxs-lookup"><span data-stu-id="2e6b8-108">BizTalk Application Users</span></span>  
  
-   <span data-ttu-id="2e6b8-109">BizTalk Isolated Host Users</span><span class="sxs-lookup"><span data-stu-id="2e6b8-109">BizTalk Isolated Host Users</span></span>  
  
-   <span data-ttu-id="2e6b8-110">BizTalk Server Administrators</span><span class="sxs-lookup"><span data-stu-id="2e6b8-110">BizTalk Server Administrators</span></span>  
  
-   <span data-ttu-id="2e6b8-111">BizTalk Server Operators</span><span class="sxs-lookup"><span data-stu-id="2e6b8-111">BizTalk Server Operators</span></span>  
  
-   <span data-ttu-id="2e6b8-112">SSO Administrators</span><span class="sxs-lookup"><span data-stu-id="2e6b8-112">SSO Administrators</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="2e6b8-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="2e6b8-113">Prerequisites</span></span>  
<span data-ttu-id="2e6b8-114">您必须是属于**管理员**上 SQL Server 在备份和还原登录名的安全角色。</span><span class="sxs-lookup"><span data-stu-id="2e6b8-114">You must be a member of the **Administrators** security role on the SQL Server where you backup and restore the logins.</span></span>  
  
## <a name="back-up-a-login-using-a-script"></a><span data-ttu-id="2e6b8-115">备份使用脚本的登录名</span><span class="sxs-lookup"><span data-stu-id="2e6b8-115">Back up a login using a script</span></span>  
  
1.  <span data-ttu-id="2e6b8-116">打开**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="2e6b8-116">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="2e6b8-117">展开**安全**，，然后展开的列表**登录名**。</span><span class="sxs-lookup"><span data-stu-id="2e6b8-117">Expand **Security**, and expand the list of **Logins**.</span></span>  
  
3.  <span data-ttu-id="2e6b8-118">右键单击你想要创建的备份脚本，然后选择的登录名**脚本以用户身份登录**。</span><span class="sxs-lookup"><span data-stu-id="2e6b8-118">Right-click the login you want to create a backup script for, and then select **Script Login as**.</span></span>  
  
4.  <span data-ttu-id="2e6b8-119">选择**创建到**，然后选择其中一个**新查询编辑器窗口**，**文件**，或**剪贴板**若要为脚本选择一个目标。</span><span class="sxs-lookup"><span data-stu-id="2e6b8-119">Select **CREATE To**, and then select one of **New Query Editor Window**, **File**, or **Clipboard** to select a destination for the script.</span></span> <span data-ttu-id="2e6b8-120">通常情况下，目标是为此文件**.sql**扩展。</span><span class="sxs-lookup"><span data-stu-id="2e6b8-120">Typically, the destination is a file with a **.sql** extension.</span></span>  
  
5.  <span data-ttu-id="2e6b8-121">对于要生成脚本的每个登录，从步骤 3 重复此过程。</span><span class="sxs-lookup"><span data-stu-id="2e6b8-121">Repeat this procedure from Step 3 for each login you want to script.</span></span> <span data-ttu-id="2e6b8-122">请参考与 BizTalk Server 相关的登录名列表，以确定你需要为哪些登录名编写脚本。</span><span class="sxs-lookup"><span data-stu-id="2e6b8-122">Refer to the list of BizTalk Server related logins to determine which logins you need to script.</span></span>  
  
## <a name="restore-a-login-from-a-script"></a><span data-ttu-id="2e6b8-123">从脚本中还原一个登录名</span><span class="sxs-lookup"><span data-stu-id="2e6b8-123">Restore a login from a script</span></span>  
  
1.  <span data-ttu-id="2e6b8-124">打开**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="2e6b8-124">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="2e6b8-125">上**文件**菜单上，**打开**包含已编写脚本的登录名的文件。</span><span class="sxs-lookup"><span data-stu-id="2e6b8-125">On the **File** menu, **Open** the file containing the scripted login.</span></span>  
  
3.  <span data-ttu-id="2e6b8-126">执行该脚本以创建登录。</span><span class="sxs-lookup"><span data-stu-id="2e6b8-126">Execute the script to create the login.</span></span>