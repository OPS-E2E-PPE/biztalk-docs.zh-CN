---
title: 连接到 SQL Server 与 SQL 适配器使用 Windows 身份验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45c54b2a-e056-496f-9f10-f19b6a3ca1a6
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6a96137243612042c8283ec5e5d15ced9d1d83b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369904"
---
# <a name="connect-to-sql-server-using-windows-authentication-with-the-sql-adapter"></a><span data-ttu-id="9a8f3-102">连接到 SQL Server 与 SQL 适配器使用 Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="9a8f3-102">Connect to SQL Server using Windows Authentication with the SQL adapter</span></span>
<span data-ttu-id="9a8f3-103">[!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)]使适配器客户端能够使用 Windows 身份验证建立与 SQL Server 的连接。</span><span class="sxs-lookup"><span data-stu-id="9a8f3-103">The [!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)] enables adapter clients to use Windows Authentication to establish a connection with SQL Server.</span></span> <span data-ttu-id="9a8f3-104">若要使用 Windows 身份验证，适配器客户端必须输入的空用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="9a8f3-104">To use Windows Authentication, adapter clients must enter an empty user name and password.</span></span> 

<span data-ttu-id="9a8f3-105">若要连接到 SQL Server 使用 Visual Studio 中的 Windows 身份验证，请参阅[连接到 SQL Server 在 Visual Studio 中使用适配器服务外接程序使用](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="9a8f3-105">To connect to SQL Server using Windows Authentication within Visual Studio, see [Connect to SQL Server in Visual Studio using the Consume Adapter Service Add-in](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md).</span></span>  
  
 <span data-ttu-id="9a8f3-106">若要启用适配器客户端使用 Windows 身份验证来连接到 SQL Server，请运行 SQL Server 的计算机上的用户启用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="9a8f3-106">To enable adapter clients to use Windows Authentication to connect to SQL Server, enable Windows Authentication for the user on the computer running SQL Server.</span></span>  

> [!TIP]
> <span data-ttu-id="9a8f3-107">如果在 SQL Server 上未安装 SQL Server Management Studio，你可以[下载 SQL Server Management Studio (SSMS)](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms)，并将其安装。</span><span class="sxs-lookup"><span data-stu-id="9a8f3-107">If SQL Server Management Studio is not installed on your SQL Server, you can [Download SQL Server Management Studio (SSMS)](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms), and install it.</span></span> 
 
## <a name="add-the-user-in-sql-server"></a><span data-ttu-id="9a8f3-108">在 SQL Server 中添加用户</span><span class="sxs-lookup"><span data-stu-id="9a8f3-108">Add the user in SQL Server</span></span>  
  
1.  <span data-ttu-id="9a8f3-109">打开 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="9a8f3-109">Open SQL Server Management Studio.</span></span> <span data-ttu-id="9a8f3-110">在中**连接到服务器**，选择**数据库引擎**，输入 SQL**服务器名称**，并输入管理员凭据以连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="9a8f3-110">In **Connect to Server**, select **Database Engine**, enter your SQL **Server name**, and enter administrator credentials to connect to the server.</span></span>  

    <span data-ttu-id="9a8f3-111">选择“连接”。</span><span class="sxs-lookup"><span data-stu-id="9a8f3-111">Select **Connect**.</span></span>
  
2.  <span data-ttu-id="9a8f3-112">在中**对象资源管理器**，展开 SQL 服务器，展开**安全**，右键单击**登录名**，然后选择**新登录名**。</span><span class="sxs-lookup"><span data-stu-id="9a8f3-112">In **Object Explorer**, expand the SQL Server, expand **Security**, right-click **Logins**, and then select **New Login**.</span></span>  
  
3.  <span data-ttu-id="9a8f3-113">有关**登录名**，输入中的 Windows 用户名`domain\username`格式。</span><span class="sxs-lookup"><span data-stu-id="9a8f3-113">For the **Login name**, enter the Windows user name in the `domain\username` format.</span></span>  

    > [!NOTE]
    >* <span data-ttu-id="9a8f3-114">使用此适配器时 BizTalk 使用，您输入的登录名是主机实例帐户的标识。</span><span class="sxs-lookup"><span data-stu-id="9a8f3-114">When using this adapter with BizTalk, then the login name you enter, is the identity of the host instance account.</span></span>  
    >
    >* <span data-ttu-id="9a8f3-115">使用此适配器时的.NET 代码中，您输入的登录名是该进程的标识。</span><span class="sxs-lookup"><span data-stu-id="9a8f3-115">When using this adapter in .NET code, then the login name you enter, is the identity for that process.</span></span>
  
4.  <span data-ttu-id="9a8f3-116">选择**用户映射**（左的窗格）。</span><span class="sxs-lookup"><span data-stu-id="9a8f3-116">Select **User Mapping** (left pane).</span></span> <span data-ttu-id="9a8f3-117">选择要将与用户相关联的数据库。</span><span class="sxs-lookup"><span data-stu-id="9a8f3-117">Select a database to associate with the user.</span></span> <span data-ttu-id="9a8f3-118">典型的 BizTalk 用户应与以下数据库相关联：</span><span class="sxs-lookup"><span data-stu-id="9a8f3-118">A typical BizTalk user should be associated with the following databases:</span></span> 

* <span data-ttu-id="9a8f3-119">BizTalkDTADb</span><span class="sxs-lookup"><span data-stu-id="9a8f3-119">BizTalkDTADb</span></span>
* <span data-ttu-id="9a8f3-120">BizTalkMgmtDb</span><span class="sxs-lookup"><span data-stu-id="9a8f3-120">BizTalkMgmtDb</span></span>
* <span data-ttu-id="9a8f3-121">BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="9a8f3-121">BizTalkMsgBoxDb</span></span>
* <span data-ttu-id="9a8f3-122">BTAHL7</span><span class="sxs-lookup"><span data-stu-id="9a8f3-122">BTAHL7</span></span>
* <span data-ttu-id="9a8f3-123">SSODB</span><span class="sxs-lookup"><span data-stu-id="9a8f3-123">SSODB</span></span>

5. <span data-ttu-id="9a8f3-124">在中**数据库角色成员身份**框中，选择**db_owner**的所有 BizTalk 数据库。</span><span class="sxs-lookup"><span data-stu-id="9a8f3-124">In the **Database role membership for** box, select **db_owner** for all the BizTalk databases.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="9a8f3-125">[服务器和 SQL Server 中的数据库角色](https://msdn.microsoft.com/library/bb669065.aspx)角色上提供有用信息。</span><span class="sxs-lookup"><span data-stu-id="9a8f3-125">[Server and Database Roles in SQL Server](https://msdn.microsoft.com/library/bb669065.aspx) provides good info on the roles.</span></span> 
  
6. <span data-ttu-id="9a8f3-126">选择**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="9a8f3-126">Select **OK** to save your changes.</span></span>
  
   <span data-ttu-id="9a8f3-127">添加用户后，用户可以连接并进行身份验证与 SQL Server 使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、 日志记录使用空白用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="9a8f3-127">After you have added the user, the user can connect and authenticate to SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], logging in with a blank username and password.</span></span>  



## <a name="see-also"></a><span data-ttu-id="9a8f3-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a8f3-128">See Also</span></span>  
 [<span data-ttu-id="9a8f3-129">创建与 SQL Server 的连接</span><span class="sxs-lookup"><span data-stu-id="9a8f3-129">Create a connection to SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/create-a-connection-to-sql-server.md)