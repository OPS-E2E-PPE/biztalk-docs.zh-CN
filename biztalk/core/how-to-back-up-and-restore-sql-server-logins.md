---
title: 如何备份和还原 SQL Server 登录名 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 847c3a3d-0d97-415b-893e-4ba173085bae
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87634ca9e9f8bbd3cc7508ce0bcfe54e5154ca0f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387111"
---
# <a name="how-to-back-up-and-restore-sql-server-logins"></a><span data-ttu-id="53aa6-102">如何备份和还原 SQL Server 登录名</span><span class="sxs-lookup"><span data-stu-id="53aa6-102">How to Back Up and Restore SQL Server Logins</span></span>
<span data-ttu-id="53aa6-103">备份和还原与 BizTalk Server 相关联的 SQL Server 登录名。</span><span class="sxs-lookup"><span data-stu-id="53aa6-103">Back up and restore SQL Server logins associated with BizTalk Server.</span></span>  
  
## <a name="biztalk-server-sql-server-security-logins"></a><span data-ttu-id="53aa6-104">BizTalk Server SQL Server 安全登录</span><span class="sxs-lookup"><span data-stu-id="53aa6-104">BizTalk Server SQL Server Security Logins</span></span>  
 <span data-ttu-id="53aa6-105">下面列出的 SQL Server 安全登录名是与 BizTalk Server 相关联。</span><span class="sxs-lookup"><span data-stu-id="53aa6-105">The SQL Server security logins listed below are associated with BizTalk Server.</span></span> <span data-ttu-id="53aa6-106">您可能必须与已创建的 BizTalk Server 应用程序相关联的其他登录名。</span><span class="sxs-lookup"><span data-stu-id="53aa6-106">You may have additional logins associated with the BizTalk Server applications you have created.</span></span> <span data-ttu-id="53aa6-107">需要备份的登录名并将其还原时将 BizTalk Server 数据库移动到新的服务器或 SQL Server 的新实例。</span><span class="sxs-lookup"><span data-stu-id="53aa6-107">You need to back up the logins and restore them when moving the BizTalk Server databases to a new server or new instance of SQL Server.</span></span>  
  
-   <span data-ttu-id="53aa6-108">BizTalk Application Users</span><span class="sxs-lookup"><span data-stu-id="53aa6-108">BizTalk Application Users</span></span>  
  
-   <span data-ttu-id="53aa6-109">BizTalk Isolated Host Users</span><span class="sxs-lookup"><span data-stu-id="53aa6-109">BizTalk Isolated Host Users</span></span>  
  
-   <span data-ttu-id="53aa6-110">BizTalk Server Administrators</span><span class="sxs-lookup"><span data-stu-id="53aa6-110">BizTalk Server Administrators</span></span>  
  
-   <span data-ttu-id="53aa6-111">BizTalk Server Operators</span><span class="sxs-lookup"><span data-stu-id="53aa6-111">BizTalk Server Operators</span></span>  
  
-   <span data-ttu-id="53aa6-112">SSO Administrators</span><span class="sxs-lookup"><span data-stu-id="53aa6-112">SSO Administrators</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="53aa6-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="53aa6-113">Prerequisites</span></span>  
<span data-ttu-id="53aa6-114">您必须是属于**管理员**上 SQL Server 备份和还原登录的安全角色。</span><span class="sxs-lookup"><span data-stu-id="53aa6-114">You must be a member of the **Administrators** security role on the SQL Server where you backup and restore the logins.</span></span>  
  
## <a name="back-up-a-login-using-a-script"></a><span data-ttu-id="53aa6-115">备份使用脚本的登录名</span><span class="sxs-lookup"><span data-stu-id="53aa6-115">Back up a login using a script</span></span>  
  
1.  <span data-ttu-id="53aa6-116">打开 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="53aa6-116">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="53aa6-117">展开**安全**，然后展开的列表**登录名**。</span><span class="sxs-lookup"><span data-stu-id="53aa6-117">Expand **Security**, and expand the list of **Logins**.</span></span>  
  
3.  <span data-ttu-id="53aa6-118">右键单击你想要创建备份脚本，然后选择登录的名**编写登录脚本为**。</span><span class="sxs-lookup"><span data-stu-id="53aa6-118">Right-click the login you want to create a backup script for, and then select **Script Login as**.</span></span>  
  
4.  <span data-ttu-id="53aa6-119">选择**创建到**，然后选择其中一个**新查询编辑器窗口**，**文件**，或**剪贴板**以选择脚本目标。</span><span class="sxs-lookup"><span data-stu-id="53aa6-119">Select **CREATE To**, and then select one of **New Query Editor Window**, **File**, or **Clipboard** to select a destination for the script.</span></span> <span data-ttu-id="53aa6-120">通常情况下，目标是文件，并且 **.sql**扩展。</span><span class="sxs-lookup"><span data-stu-id="53aa6-120">Typically, the destination is a file with a **.sql** extension.</span></span>  
  
5.  <span data-ttu-id="53aa6-121">每个登录名要编写脚本重复步骤 3 中的此过程。</span><span class="sxs-lookup"><span data-stu-id="53aa6-121">Repeat this procedure from Step 3 for each login you want to script.</span></span> <span data-ttu-id="53aa6-122">到的列表，请参阅 BizTalk Server 相关的登录名，以确定需要脚本的登录名。</span><span class="sxs-lookup"><span data-stu-id="53aa6-122">Refer to the list of BizTalk Server related logins to determine which logins you need to script.</span></span>  
  
## <a name="restore-a-login-from-a-script"></a><span data-ttu-id="53aa6-123">从脚本还原登录名</span><span class="sxs-lookup"><span data-stu-id="53aa6-123">Restore a login from a script</span></span>  
  
1.  <span data-ttu-id="53aa6-124">打开 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="53aa6-124">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="53aa6-125">上**文件**菜单中，**打开**包含脚本登录名的文件。</span><span class="sxs-lookup"><span data-stu-id="53aa6-125">On the **File** menu, **Open** the file containing the scripted login.</span></span>  
  
3.  <span data-ttu-id="53aa6-126">执行脚本以创建登录名。</span><span class="sxs-lookup"><span data-stu-id="53aa6-126">Execute the script to create the login.</span></span>