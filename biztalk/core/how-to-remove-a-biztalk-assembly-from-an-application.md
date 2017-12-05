---
title: "如何从应用程序删除 BizTalk 程序集 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [applications], assemblies
- assemblies, deleting
- deleting, assemblies
- applications, assemblies
- managing [assemblies], deleting
ms.assetid: 0691c3b6-476d-4e01-b50b-47d7c0b299bf
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89e46b8610114149e8618811361090d8644f82aa
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-remove-a-biztalk-assembly-from-an-application"></a><span data-ttu-id="ca300-102">如何从应用程序中删除 BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="ca300-102">How to Remove a BizTalk Assembly from an Application</span></span>
<span data-ttu-id="ca300-103">本主题介绍如何使用 BizTalk Server 管理控制台或命令行从 BizTalk 应用程序删除 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="ca300-103">This topic describes how use the BizTalk Server Administration console or the command line to remove a BizTalk assembly from a BizTalk application.</span></span> <span data-ttu-id="ca300-104">执行此操作时，程序集和其中包含的项目（如业务流程、架构和管道）都将从应用程序和 BizTalk 管理数据库中删除。</span><span class="sxs-lookup"><span data-stu-id="ca300-104">When you do this, the assembly and the artifacts that it includes, such as orchestrations, schemas, and pipelines, are removed from the application and the BizTalk Management database.</span></span>  
  
 <span data-ttu-id="ca300-105">在删除 BizTalk 程序集之前，请切记以下几点重要事项：</span><span class="sxs-lookup"><span data-stu-id="ca300-105">Before removing a BizTalk assembly, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="ca300-106">删除 BizTalk 程序集时，程序集文件不会自动从全局程序集缓存 (GAC) 或本地文件系统中删除（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="ca300-106">When you remove a BizTalk assembly, the assembly file is not automatically removed from the global assembly cache (GAC) or the local file system, if it exists there.</span></span> <span data-ttu-id="ca300-107">您必须手动删除它。</span><span class="sxs-lookup"><span data-stu-id="ca300-107">You must manually remove it.</span></span> <span data-ttu-id="ca300-108">有关说明，请参阅[如何从 GAC 中卸载程序集](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4)和[如何的 BizTalk 应用程序删除其他文件和设置](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="ca300-108">For instructions, see [How to Uninstall an Assembly from the GAC](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4) and [How to Remove Other Files and Settings for a BizTalk Application](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="ca300-109">如果删除包含管道的 BizTalk 程序集，则同一应用程序中使用该管道的所有发送端口都将重置为使用默认的 PassThruTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="ca300-109">If you remove a BizTalk assembly that includes a pipeline, any send ports in the same application that use the pipeline will be reset to use the default, PassThruTransmit pipeline.</span></span>  
  
-   <span data-ttu-id="ca300-110">不能删除其他项目所依赖的 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="ca300-110">You cannot remove a BizTalk assembly on which other artifacts depend.</span></span> <span data-ttu-id="ca300-111">必须首先删除依存项目。</span><span class="sxs-lookup"><span data-stu-id="ca300-111">You must first remove the dependent artifacts.</span></span> <span data-ttu-id="ca300-112">然后才能删除 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="ca300-112">Then you can remove the BizTalk assembly.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ca300-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="ca300-113">Prerequisites</span></span>  
 <span data-ttu-id="ca300-114">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ca300-114">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="ca300-115">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="ca300-115">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-remove-a-biztalk-assembly-from-an-application"></a><span data-ttu-id="ca300-116">从应用程序中删除 BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="ca300-116">To remove a BizTalk assembly from an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="ca300-117">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="ca300-117">Using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="ca300-118">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="ca300-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ca300-119">在控制台树中，展开 BizTalk Server 管理，展开包含要删除的 BizTalk 程序集的 BizTalk 组，然后展开包含 BizTalk 程序集的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ca300-119">In the console tree, expand BizTalk Server Administration, expand the BizTalk group containing the BizTalk assembly to remove, and then expand the application containing the BizTalk assembly.</span></span>  
  
3.  <span data-ttu-id="ca300-120">单击**资源**文件夹中，右键单击 BizTalk 程序集，并依次**删除**。</span><span class="sxs-lookup"><span data-stu-id="ca300-120">Click the **Resources** folder, right-click the BizTalk assembly, and then click **Remove**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="ca300-121">使用命令行</span><span class="sxs-lookup"><span data-stu-id="ca300-121">Using the command line</span></span>  
  
1.  <span data-ttu-id="ca300-122">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ca300-122">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="ca300-123">键入以下命令，替换为适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="ca300-123">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
     <span data-ttu-id="ca300-124">**BTSTask RemoveResource** [**/ApplicationName:***值*] **/Luid:***值*[**/Server:***值*] [**/数据库：***值*]</span><span class="sxs-lookup"><span data-stu-id="ca300-124">**BTSTask RemoveResource** [**/ApplicationName:***value*] **/Luid:***value* [**/Server:***value*] [**/Database:***value*]</span></span>  
  
     <span data-ttu-id="ca300-125">例如：</span><span class="sxs-lookup"><span data-stu-id="ca300-125">Example:</span></span>  
  
     <span data-ttu-id="ca300-126">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations，版本 = 1.0.0.0，Culture = neutral，PublicKeyToken = 0123456789ABCDEF"**</span><span class="sxs-lookup"><span data-stu-id="ca300-126">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**</span></span>  
  
    |<span data-ttu-id="ca300-127">参数</span><span class="sxs-lookup"><span data-stu-id="ca300-127">Parameter</span></span>|<span data-ttu-id="ca300-128">Description</span><span class="sxs-lookup"><span data-stu-id="ca300-128">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="ca300-129">**/ 应用程序名称**</span><span class="sxs-lookup"><span data-stu-id="ca300-129">**/ApplicationName**</span></span>|<span data-ttu-id="ca300-130">包含要删除的 BizTalk 程序集的 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="ca300-130">Name of the BizTalk application containing the BizTalk assembly to delete.</span></span> <span data-ttu-id="ca300-131">如果未指定此参数，则使用默认的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ca300-131">If this parameter is not specified, the default application is used.</span></span> <span data-ttu-id="ca300-132">如果名称包含空格，必须将它括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="ca300-132">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
    |<span data-ttu-id="ca300-133">**/ Luid**</span><span class="sxs-lookup"><span data-stu-id="ca300-133">**/Luid**</span></span>|<span data-ttu-id="ca300-134">BizTalk 程序集的本地唯一标识符 (LUID)。</span><span class="sxs-lookup"><span data-stu-id="ca300-134">Locally unique identifier (LUID) of the BizTalk assembly.</span></span> <span data-ttu-id="ca300-135">你可以通过使用获取而定**ListApp**命令时中, 所述[ListApp 命令](../core/listapp-command.md)。</span><span class="sxs-lookup"><span data-stu-id="ca300-135">You can obtain the LUID by using the **ListApp** command, as described in [ListApp Command](../core/listapp-command.md).</span></span>|  
    |<span data-ttu-id="ca300-136">**/ 服务器**</span><span class="sxs-lookup"><span data-stu-id="ca300-136">**/Server**</span></span>|<span data-ttu-id="ca300-137">BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。</span><span class="sxs-lookup"><span data-stu-id="ca300-137">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="ca300-138">只在实例名称与服务器名称不相同时才需要指定实例名称。</span><span class="sxs-lookup"><span data-stu-id="ca300-138">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="ca300-139">只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。</span><span class="sxs-lookup"><span data-stu-id="ca300-139">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="ca300-140">示例：</span><span class="sxs-lookup"><span data-stu-id="ca300-140">Examples:</span></span><br /><br /> <span data-ttu-id="ca300-141">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="ca300-141">Server=MyServer</span></span><br /><br /> <span data-ttu-id="ca300-142">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="ca300-142">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="ca300-143">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="ca300-143">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
    |<span data-ttu-id="ca300-144">**/ 数据库**</span><span class="sxs-lookup"><span data-stu-id="ca300-144">**/Database**</span></span>|<span data-ttu-id="ca300-145">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="ca300-145">Name of the BizTalk Management database.</span></span> <span data-ttu-id="ca300-146">如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="ca300-146">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca300-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca300-147">See Also</span></span>  
 <span data-ttu-id="ca300-148">[管理 BizTalk 程序集](../core/managing-biztalk-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="ca300-148">[Managing BizTalk Assemblies](../core/managing-biztalk-assemblies.md) </span></span>  
 [<span data-ttu-id="ca300-149">RemoveResource 命令</span><span class="sxs-lookup"><span data-stu-id="ca300-149">RemoveResource Command</span></span>](../core/removeresource-command.md)