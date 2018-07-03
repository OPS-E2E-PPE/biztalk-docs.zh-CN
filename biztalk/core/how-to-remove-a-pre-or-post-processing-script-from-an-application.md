---
title: 如何从应用程序删除预处理或后处理脚本 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [scripts], deleting
- deleting, scripts
- managing [applications], scripts
- scripts, deleting
- applications, scripts
ms.assetid: 7911f098-97f2-4a5d-87fe-20b55231113e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c9742b6c523f193a8670c1171f38949ef5dd1cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010006"
---
# <a name="how-to-remove-a-pre--or-post-processing-script-from-an-application"></a><span data-ttu-id="dad3b-102">如何从应用程序中删除预处理脚本和后处理脚本</span><span class="sxs-lookup"><span data-stu-id="dad3b-102">How to Remove a Pre- or Post-processing Script from an Application</span></span>
<span data-ttu-id="dad3b-103">本主题描述如何使用 BizTalk Server 管理控制台或命令行从应用程序删除预处理脚本或后处理脚本。</span><span class="sxs-lookup"><span data-stu-id="dad3b-103">This topic describes how to use the BizTalk Server Administration console or the command line to remove a pre- or post-processing script from an application.</span></span> <span data-ttu-id="dad3b-104">这将从 BizTalk 管理数据库删除脚本，以便它将不会导出到应用程序的 .msi 文件中。</span><span class="sxs-lookup"><span data-stu-id="dad3b-104">This removes the script from the BizTalk Management database, so that it will not be exported in the application .msi file.</span></span> <span data-ttu-id="dad3b-105">如果本地文件系统中存在脚本，该方法并不会从那里删除该脚本。</span><span class="sxs-lookup"><span data-stu-id="dad3b-105">This does not remove the script from the local file system, if it exists there.</span></span>  
  
 <span data-ttu-id="dad3b-106">如果包含该脚本的应用程序已安装在本地文件系统上，并且该脚本设计为在卸载期间运行，则必须从文件系统中删除该脚本，以便避免该脚本在卸载应用程序时运行。</span><span class="sxs-lookup"><span data-stu-id="dad3b-106">If the application containing the script has been installed on the local file system, and the script is designed to run during uninstallation, you must remove the script from the file system to prevent it from running when the application is uninstalled.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dad3b-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="dad3b-107">Prerequisites</span></span>  
 <span data-ttu-id="dad3b-108">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="dad3b-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="dad3b-109">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="dad3b-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-remove-a-script-from-an-application"></a><span data-ttu-id="dad3b-110">从应用程序中删除脚本</span><span class="sxs-lookup"><span data-stu-id="dad3b-110">To remove a script from an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="dad3b-111">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="dad3b-111">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="dad3b-112">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="dad3b-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="dad3b-113">在控制台树中，展开 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开包含要删除的脚本的 BizTalk 组，接着展开包含该脚本的应用程序。</span><span class="sxs-lookup"><span data-stu-id="dad3b-113">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the script to remove, and then expand the application containing the script.</span></span>  
  
3. <span data-ttu-id="dad3b-114">单击**资源**文件夹中，右键单击脚本，然后依次**删除**。</span><span class="sxs-lookup"><span data-stu-id="dad3b-114">Click the **Resources** folder, right-click the script, and then click **Remove**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="dad3b-115">使用命令行</span><span class="sxs-lookup"><span data-stu-id="dad3b-115">Using the command line</span></span>  
  
1. <span data-ttu-id="dad3b-116">按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="dad3b-116">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="dad3b-117">键入以下命令，替换适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="dad3b-117">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="dad3b-118">**BTSTask RemoveResource** [**/ApplicationName:**<em>值</em>] **/Luid:**<em>值</em>[**/Server:** <em>值</em>] [**/database:**<em>值</em>]</span><span class="sxs-lookup"><span data-stu-id="dad3b-118">**BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="dad3b-119">例如：</span><span class="sxs-lookup"><span data-stu-id="dad3b-119">Example:</span></span>  
  
    <span data-ttu-id="dad3b-120">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApplication:MyScript.vbs"**</span><span class="sxs-lookup"><span data-stu-id="dad3b-120">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApplication:MyScript.vbs"**</span></span>  
  
   |<span data-ttu-id="dad3b-121">参数</span><span class="sxs-lookup"><span data-stu-id="dad3b-121">Parameter</span></span>|<span data-ttu-id="dad3b-122">Description</span><span class="sxs-lookup"><span data-stu-id="dad3b-122">Description</span></span>|  
   |---------------|-----------------|  
   |<span data-ttu-id="dad3b-123">**/ 应用程序名称**</span><span class="sxs-lookup"><span data-stu-id="dad3b-123">**/ApplicationName**</span></span>|<span data-ttu-id="dad3b-124">包含要删除的 BizTalk 脚本的 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="dad3b-124">Name of the BizTalk application containing the BizTalk script to delete.</span></span> <span data-ttu-id="dad3b-125">如果名称中包含空格，则必须将其括在双引号 (") 中。</span><span class="sxs-lookup"><span data-stu-id="dad3b-125">If the name includes spaces, it must be enclosed in double quotation marks (").</span></span> <span data-ttu-id="dad3b-126">如果未指定此参数，则使用默认的应用程序。</span><span class="sxs-lookup"><span data-stu-id="dad3b-126">If this parameter is not specified, the default application is used.</span></span>|  
   |<span data-ttu-id="dad3b-127">**/ Luid**</span><span class="sxs-lookup"><span data-stu-id="dad3b-127">**/Luid**</span></span>|<span data-ttu-id="dad3b-128">脚本的本地唯一标识符 (LUID)。</span><span class="sxs-lookup"><span data-stu-id="dad3b-128">Locally unique identifier (LUID) of the script.</span></span> <span data-ttu-id="dad3b-129">可通过获得 LUID [ListApp 命令](../core/listapp-command.md)。</span><span class="sxs-lookup"><span data-stu-id="dad3b-129">You can obtain the LUID by using the [ListApp Command](../core/listapp-command.md).</span></span>|  
   |<span data-ttu-id="dad3b-130">**/ 服务器**</span><span class="sxs-lookup"><span data-stu-id="dad3b-130">**/Server**</span></span>|<span data-ttu-id="dad3b-131">BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。</span><span class="sxs-lookup"><span data-stu-id="dad3b-131">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="dad3b-132">只在实例名称与服务器名称不相同时才需要指定实例名称。</span><span class="sxs-lookup"><span data-stu-id="dad3b-132">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="dad3b-133">只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。</span><span class="sxs-lookup"><span data-stu-id="dad3b-133">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="dad3b-134">示例：</span><span class="sxs-lookup"><span data-stu-id="dad3b-134">Examples:</span></span><br /><br /> <span data-ttu-id="dad3b-135">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="dad3b-135">Server=MyServer</span></span><br /><br /> <span data-ttu-id="dad3b-136">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="dad3b-136">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="dad3b-137">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="dad3b-137">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="dad3b-138">**/ 数据库**</span><span class="sxs-lookup"><span data-stu-id="dad3b-138">**/Database**</span></span>|<span data-ttu-id="dad3b-139">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="dad3b-139">Name of the BizTalk Management database.</span></span> <span data-ttu-id="dad3b-140">如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="dad3b-140">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dad3b-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="dad3b-141">See Also</span></span>  
 <span data-ttu-id="dad3b-142">[管理预处理和后处理脚本](../core/managing-pre-and-post-processing-scripts.md) </span><span class="sxs-lookup"><span data-stu-id="dad3b-142">[Managing Pre- and Post-processing Scripts](../core/managing-pre-and-post-processing-scripts.md) </span></span>  
 [<span data-ttu-id="dad3b-143">RemoveResource 命令</span><span class="sxs-lookup"><span data-stu-id="dad3b-143">RemoveResource Command</span></span>](../core/removeresource-command.md)