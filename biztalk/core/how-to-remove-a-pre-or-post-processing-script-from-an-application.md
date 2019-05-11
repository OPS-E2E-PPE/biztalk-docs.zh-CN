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
ms.openlocfilehash: 4af32e7aa3edae39fb43c1bf884c97ec376c7acf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384382"
---
# <a name="how-to-remove-a-pre--or-post-processing-script-from-an-application"></a><span data-ttu-id="131a4-102">如何从应用程序删除预处理或后处理脚本</span><span class="sxs-lookup"><span data-stu-id="131a4-102">How to Remove a Pre- or Post-processing Script from an Application</span></span>
<span data-ttu-id="131a4-103">本主题介绍如何使用 BizTalk Server 管理控制台或命令行从应用程序删除预处理或后处理脚本。</span><span class="sxs-lookup"><span data-stu-id="131a4-103">This topic describes how to use the BizTalk Server Administration console or the command line to remove a pre- or post-processing script from an application.</span></span> <span data-ttu-id="131a4-104">这样，以便在应用程序.msi 文件中将不导出从 BizTalk 管理数据库中删除的脚本。</span><span class="sxs-lookup"><span data-stu-id="131a4-104">This removes the script from the BizTalk Management database, so that it will not be exported in the application .msi file.</span></span> <span data-ttu-id="131a4-105">如果存在，这不会不删除从本地文件系统中，脚本。</span><span class="sxs-lookup"><span data-stu-id="131a4-105">This does not remove the script from the local file system, if it exists there.</span></span>  
  
 <span data-ttu-id="131a4-106">如果已在本地文件系统上，安装包含该脚本的应用程序和脚本设计为在卸载期间运行，则必须从文件系统，以防止其运行时卸载应用程序中删除该脚本。</span><span class="sxs-lookup"><span data-stu-id="131a4-106">If the application containing the script has been installed on the local file system, and the script is designed to run during uninstallation, you must remove the script from the file system to prevent it from running when the application is uninstalled.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="131a4-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="131a4-107">Prerequisites</span></span>  
 <span data-ttu-id="131a4-108">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="131a4-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="131a4-109">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="131a4-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-remove-a-script-from-an-application"></a><span data-ttu-id="131a4-110">若要从应用程序中删除脚本</span><span class="sxs-lookup"><span data-stu-id="131a4-110">To remove a script from an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="131a4-111">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="131a4-111">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="131a4-112">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="131a4-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="131a4-113">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开包含该脚本的 BizTalk 组删除，，然后展开包含该脚本的应用程序。</span><span class="sxs-lookup"><span data-stu-id="131a4-113">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the script to remove, and then expand the application containing the script.</span></span>  
  
3. <span data-ttu-id="131a4-114">单击**资源**文件夹中，右键单击脚本，然后依次**删除**。</span><span class="sxs-lookup"><span data-stu-id="131a4-114">Click the **Resources** folder, right-click the script, and then click **Remove**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="131a4-115">使用命令行</span><span class="sxs-lookup"><span data-stu-id="131a4-115">Using the command line</span></span>  
  
1. <span data-ttu-id="131a4-116">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="131a4-116">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="131a4-117">键入以下命令，替换适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="131a4-117">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="131a4-118">**BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span><span class="sxs-lookup"><span data-stu-id="131a4-118">**BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="131a4-119">例如：</span><span class="sxs-lookup"><span data-stu-id="131a4-119">Example:</span></span>  
  
    <span data-ttu-id="131a4-120">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApplication:MyScript.vbs"**</span><span class="sxs-lookup"><span data-stu-id="131a4-120">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApplication:MyScript.vbs"**</span></span>  
  
   |<span data-ttu-id="131a4-121">参数</span><span class="sxs-lookup"><span data-stu-id="131a4-121">Parameter</span></span>|<span data-ttu-id="131a4-122">Description</span><span class="sxs-lookup"><span data-stu-id="131a4-122">Description</span></span>|  
   |---------------|-----------------|  
   |<span data-ttu-id="131a4-123">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="131a4-123">**/ApplicationName**</span></span>|<span data-ttu-id="131a4-124">包含 BizTalk 脚本的 BizTalk 应用程序若要删除的名称。</span><span class="sxs-lookup"><span data-stu-id="131a4-124">Name of the BizTalk application containing the BizTalk script to delete.</span></span> <span data-ttu-id="131a4-125">如果名称包含空格，则必须放在双引号 （"） 中。</span><span class="sxs-lookup"><span data-stu-id="131a4-125">If the name includes spaces, it must be enclosed in double quotation marks (").</span></span> <span data-ttu-id="131a4-126">如果未指定此参数，则使用默认应用程序。</span><span class="sxs-lookup"><span data-stu-id="131a4-126">If this parameter is not specified, the default application is used.</span></span>|  
   |<span data-ttu-id="131a4-127">**/Luid**</span><span class="sxs-lookup"><span data-stu-id="131a4-127">**/Luid**</span></span>|<span data-ttu-id="131a4-128">该脚本的本地唯一标识符 (LUID)。</span><span class="sxs-lookup"><span data-stu-id="131a4-128">Locally unique identifier (LUID) of the script.</span></span> <span data-ttu-id="131a4-129">可通过获得 LUID [ListApp 命令](../core/listapp-command.md)。</span><span class="sxs-lookup"><span data-stu-id="131a4-129">You can obtain the LUID by using the [ListApp Command](../core/listapp-command.md).</span></span>|  
   |<span data-ttu-id="131a4-130">**/Server**</span><span class="sxs-lookup"><span data-stu-id="131a4-130">**/Server**</span></span>|<span data-ttu-id="131a4-131">承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="131a4-131">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="131a4-132">实例名称仅是所需的实例名称不同于服务器名称时。</span><span class="sxs-lookup"><span data-stu-id="131a4-132">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="131a4-133">端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。</span><span class="sxs-lookup"><span data-stu-id="131a4-133">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="131a4-134">示例：</span><span class="sxs-lookup"><span data-stu-id="131a4-134">Examples:</span></span><br /><br /> <span data-ttu-id="131a4-135">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="131a4-135">Server=MyServer</span></span><br /><br /> <span data-ttu-id="131a4-136">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="131a4-136">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="131a4-137">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="131a4-137">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="131a4-138">**/Database**</span><span class="sxs-lookup"><span data-stu-id="131a4-138">**/Database**</span></span>|<span data-ttu-id="131a4-139">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="131a4-139">Name of the BizTalk Management database.</span></span> <span data-ttu-id="131a4-140">如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="131a4-140">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="131a4-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="131a4-141">See Also</span></span>  
 <span data-ttu-id="131a4-142">[管理预处理和后处理脚本](../core/managing-pre-and-post-processing-scripts.md) </span><span class="sxs-lookup"><span data-stu-id="131a4-142">[Managing Pre- and Post-processing Scripts](../core/managing-pre-and-post-processing-scripts.md) </span></span>  
 [<span data-ttu-id="131a4-143">RemoveResource 命令</span><span class="sxs-lookup"><span data-stu-id="131a4-143">RemoveResource Command</span></span>](../core/removeresource-command.md)