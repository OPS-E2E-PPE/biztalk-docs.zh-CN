---
title: 如何创建链接的服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- servers, linking for backups
- backing up, linking servers
ms.assetid: 7d4aba3d-77c0-4cdf-8547-71e821ce34a1
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcb954062bb2cb2484a51570109b37341b1c12f9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980982"
---
# <a name="how-to-create-a-linked-server"></a><span data-ttu-id="81f4d-102">如何创建链接服务器</span><span class="sxs-lookup"><span data-stu-id="81f4d-102">How to Create a Linked Server</span></span>
<span data-ttu-id="81f4d-103">当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装在分布式拓扑中时，多个 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 上均存在属于 BizTalk 组的数据库。</span><span class="sxs-lookup"><span data-stu-id="81f4d-103">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed in a distributed topology, the databases that belong to a BizTalk Group exist on multiple [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="81f4d-104">在能够从 BizTalk 管理服务器备份整个 BizTalk 环境之前，必须配置到每个远程服务器的链接服务器连接。</span><span class="sxs-lookup"><span data-stu-id="81f4d-104">You must configure a linked server connection to each of the remote servers before you can back up the entire BizTalk environment from the BizTalk Management server.</span></span> <span data-ttu-id="81f4d-105">链接服务器是 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 分布式查询中使用的 OLE DB 数据源。</span><span class="sxs-lookup"><span data-stu-id="81f4d-105">A linked server is an OLE DB data source that is used in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] distributed queries.</span></span>  
  
 <span data-ttu-id="81f4d-106">在备份和还原过程中，备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业将自动创建链接服务器。</span><span class="sxs-lookup"><span data-stu-id="81f4d-106">As a part of the backup and restore process, the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job automatically creates linked servers.</span></span> <span data-ttu-id="81f4d-107">不过，如果需要，您可通过以下过程手动创建链接服务器。</span><span class="sxs-lookup"><span data-stu-id="81f4d-107">If necessary, however, you can manually create linked servers using this procedure.</span></span>  
  
 <span data-ttu-id="81f4d-108">此外可以使用创建链接的服务器*sp_addlinkedserver*存储过程。</span><span class="sxs-lookup"><span data-stu-id="81f4d-108">Linked servers can also be created using the *sp_addlinkedserver* stored procedure.</span></span> <span data-ttu-id="81f4d-109">执行此操作时，须注意以下安全事项。</span><span class="sxs-lookup"><span data-stu-id="81f4d-109">There are security considerations associated with this operation.</span></span> <span data-ttu-id="81f4d-110">在使用 sp_addlinkedserver 创建链接服务器时，所有本地登录都将默认映射到新的链接服务器。</span><span class="sxs-lookup"><span data-stu-id="81f4d-110">When a linked server is created using sp_addlinkedserver, all local logins will be mapped to the new linked server by default.</span></span> <span data-ttu-id="81f4d-111">若要控制对链接服务器的访问*sp_droplinkedsvrlogin*过程应该用于删除全局登录映射后, 跟*sp_addlinkedsvrlogin*将映射到的所需的登录帐户新建链接的服务器。</span><span class="sxs-lookup"><span data-stu-id="81f4d-111">To control access to the linked server, the *sp_droplinkedsvrlogin* procedure should be used to drop the global login mapping, followed by *sp_addlinkedsvrlogin* to map the desired login account(s) to the new linked server.</span></span> <span data-ttu-id="81f4d-112">在使用 sp_addlinkedsvrlogin 时，建议您设置@useself参数 = TRUE。</span><span class="sxs-lookup"><span data-stu-id="81f4d-112">When using sp_addlinkedsvrlogin, it is recommended that you set the @useself parameter = TRUE.</span></span> <span data-ttu-id="81f4d-113">这样就无需将用户名和密码嵌入到您的 SQL 脚本中。</span><span class="sxs-lookup"><span data-stu-id="81f4d-113">This avoids the need to embed a user name and password into your SQL script.</span></span>  

> [!TIP]
> <span data-ttu-id="81f4d-114">这些步骤可能随时间变化。</span><span class="sxs-lookup"><span data-stu-id="81f4d-114">These steps may change over time.</span></span> <span data-ttu-id="81f4d-115">我们建议引用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]文档，网址[创建链接服务器](https://docs.microsoft.com/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine)。</span><span class="sxs-lookup"><span data-stu-id="81f4d-115">We recommend referring to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] documentation at [Create Linked Servers](https://docs.microsoft.com/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="81f4d-116">必要條件</span><span class="sxs-lookup"><span data-stu-id="81f4d-116">Prerequisites</span></span>  
  
- <span data-ttu-id="81f4d-117">是的成员的帐户登录[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] **sysadmin**固定的服务器角色</span><span class="sxs-lookup"><span data-stu-id="81f4d-117">Sign in with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] **sysadmin** fixed server role</span></span>  
  
- <span data-ttu-id="81f4d-118">创建本地[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]登录名。</span><span class="sxs-lookup"><span data-stu-id="81f4d-118">Create a local [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] login.</span></span> <span data-ttu-id="81f4d-119">在以下步骤中，此帐户映射到登录名在[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，将链接到。</span><span class="sxs-lookup"><span data-stu-id="81f4d-119">In the following steps, this account is mapped to a login on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] you will link to.</span></span> 
  
## <a name="create-a-linked-server"></a><span data-ttu-id="81f4d-120">创建链接的服务器</span><span class="sxs-lookup"><span data-stu-id="81f4d-120">Create a linked server</span></span>
  
1. <span data-ttu-id="81f4d-121">打开**SQL Server Management Studio**，输入你的本地名称[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，然后选择**Connect**。</span><span class="sxs-lookup"><span data-stu-id="81f4d-121">Open **SQL Server Management Studio**, enter the name of your local [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], and then select **Connect**.</span></span>  
  
2. <span data-ttu-id="81f4d-122">展开**Server 对象**，右键单击**链接服务器**，然后选择**新建链接服务器**。</span><span class="sxs-lookup"><span data-stu-id="81f4d-122">Expand **Server Objects**, right-click **Linked Servers**, and then select **New Linked Server**.</span></span>  

   <span data-ttu-id="81f4d-123">若要查看**Server 对象**，连接到本地内部[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="81f4d-123">To see **Server Objects**, connect to a local on-premises [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="81f4d-124">然后， **Server 对象**应显示。</span><span class="sxs-lookup"><span data-stu-id="81f4d-124">Then, **Server Objects** should be displayed.</span></span>
  
3. <span data-ttu-id="81f4d-125">在中**链接服务器**文字框中，输入的完整网络名称[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]你想要链接到。</span><span class="sxs-lookup"><span data-stu-id="81f4d-125">In the **Linked server** text box, enter the full network name of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] you want to link to.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="81f4d-126">此过程通常针对的是要链接到的作为远程服务器的服务器。</span><span class="sxs-lookup"><span data-stu-id="81f4d-126">This procedure often refers to the server you are linking to as the remote server.</span></span> <span data-ttu-id="81f4d-127">这只是为了方便，用以指示链接（“远程”）服务器与本地服务器的关系。</span><span class="sxs-lookup"><span data-stu-id="81f4d-127">This is for convenience only, to indicate the relationship of the linked (“remote”) server to the local server.</span></span>  
  
4. <span data-ttu-id="81f4d-128">下**服务器类型**，选择**SQL Server**。</span><span class="sxs-lookup"><span data-stu-id="81f4d-128">Under **Server type**, select **SQL Server**.</span></span>  
  
5. <span data-ttu-id="81f4d-129">在左窗格中，选择“安全性” 。</span><span class="sxs-lookup"><span data-stu-id="81f4d-129">In the left pane, select **Security**.</span></span> 

   <span data-ttu-id="81f4d-130">在此步骤中，你创建的本地帐户映射到远程服务器登录名。</span><span class="sxs-lookup"><span data-stu-id="81f4d-130">In this step, you map the local account you created to the remote server login.</span></span> <span data-ttu-id="81f4d-131">选项包括：</span><span class="sxs-lookup"><span data-stu-id="81f4d-131">Your options:</span></span> 
    
   | | | 
   |---|---|
   | <span data-ttu-id="81f4d-132">**可使用登录名的当前安全上下文**</span><span class="sxs-lookup"><span data-stu-id="81f4d-132">**Be made using the login’s current security context**</span></span> | <span data-ttu-id="81f4d-133">在域环境中，用户通常使用其域登录名连接。</span><span class="sxs-lookup"><span data-stu-id="81f4d-133">In domain environments, users typically connect with their domain logins.</span></span> <span data-ttu-id="81f4d-134">由于登录的域帐户的安全上下文映射到你创建的本地帐户，此选项可能是最佳。</span><span class="sxs-lookup"><span data-stu-id="81f4d-134">This option may be best since the security context of the signed-in domain account is mapped to the local account you created.</span></span>|
   | <span data-ttu-id="81f4d-135">**使用此安全上下文建立连接**</span><span class="sxs-lookup"><span data-stu-id="81f4d-135">**Be made using this security context**</span></span> | <span data-ttu-id="81f4d-136">当用户连接到本地 SQL Server 使用 SQL Server 登录名时，则此选项可能是最佳。</span><span class="sxs-lookup"><span data-stu-id="81f4d-136">When users connect to the local SQL Server using a SQL Server login, then this option may be best.</span></span> <span data-ttu-id="81f4d-137">然后输入登录名和密码的帐户链接的服务器上。</span><span class="sxs-lookup"><span data-stu-id="81f4d-137">Then enter the login and password for the account on the linked server.</span></span> |


6. <span data-ttu-id="81f4d-138">选择**添加**，并输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="81f4d-138">Select **Add**, and enter the following:</span></span> 

   1. <span data-ttu-id="81f4d-139">下**本地登录名**，选择你创建的本地帐户。</span><span class="sxs-lookup"><span data-stu-id="81f4d-139">Under **Local Login**, select the local account you created.</span></span> 
   2. <span data-ttu-id="81f4d-140">检查**Impersonate**如果远程服务器上还存在本地登录名。</span><span class="sxs-lookup"><span data-stu-id="81f4d-140">Check **Impersonate** if the local login also exists on the remote server.</span></span> 
   3. <span data-ttu-id="81f4d-141">或者，如果将本地登录名映射到远程[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]登录名，输入**远程用户**名称并**远程密码**的远程服务器登录名。</span><span class="sxs-lookup"><span data-stu-id="81f4d-141">Alternatively, if the local login will be mapped to a remote [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] login you, enter the **Remote User** name and **Remote Password** for the remote server login.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="81f4d-142">若要使用模拟，则您的 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 配置和登录帐户必须满足委派要求。</span><span class="sxs-lookup"><span data-stu-id="81f4d-142">To use impersonation, your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] configuration and login accounts must meet the requirements for delegation.</span></span> <span data-ttu-id="81f4d-143">请参阅[委派配置链接服务器](https://msdn.microsoft.com/library/ms189580.aspx)的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="81f4d-143">See [Configuring Linked Servers for Delegation](https://msdn.microsoft.com/library/ms189580.aspx) for more details.</span></span>  

7. <span data-ttu-id="81f4d-144">在左窗格中，选择**服务器选项**。</span><span class="sxs-lookup"><span data-stu-id="81f4d-144">In the left pane, choose **Server Options**.</span></span> <span data-ttu-id="81f4d-145">设置**RPC**并**RPC Out**参数**True**，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="81f4d-145">Set the **RPC** and **RPC Out** parameters to **True**, and then select **OK**.</span></span> 
 
> [!TIP]
> <span data-ttu-id="81f4d-146">有关详细信息和建议创建链接的服务器时使用 includig`sp_addlinkedserver`存储 procedcure，请参阅[创建链接服务器](https://docs.microsoft.com/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine)。</span><span class="sxs-lookup"><span data-stu-id="81f4d-146">For more details and recommendations when creating linked servers, includig using the `sp_addlinkedserver` stored procedcure, see [Create Linked Servers](https://docs.microsoft.com/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine).</span></span>

  
## <a name="see-also"></a><span data-ttu-id="81f4d-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="81f4d-147">See Also</span></span>  
 [<span data-ttu-id="81f4d-148">有关备份和还原的高级信息</span><span class="sxs-lookup"><span data-stu-id="81f4d-148">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)