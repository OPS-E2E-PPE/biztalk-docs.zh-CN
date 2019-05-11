---
title: 如何创建应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, creating
- creating, applications
ms.assetid: 6a8682a7-3bef-4978-996f-5a9c5154ce62
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e7734be0d965e57df627b1f5fda4bb18955cd34
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385524"
---
# <a name="how-to-create-an-application"></a><span data-ttu-id="b10b8-102">如何创建应用程序</span><span class="sxs-lookup"><span data-stu-id="b10b8-102">How to Create an Application</span></span>
<span data-ttu-id="b10b8-103">有三种方法来创建新的 BizTalk 应用程序：</span><span class="sxs-lookup"><span data-stu-id="b10b8-103">There are three ways to create a new BizTalk application:</span></span>  
  
- <span data-ttu-id="b10b8-104">使用 BizTalk Server 管理控制台的新的应用程序命令或 BTSTask 命令行工具的 AddApp 命令创建的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b10b8-104">Create the BizTalk application by using the New Application command of the BizTalk Server Administration console or the AddApp command of the BTSTask command-line tool.</span></span> <span data-ttu-id="b10b8-105">您可以执行此操作在本主题后面找到过程。</span><span class="sxs-lookup"><span data-stu-id="b10b8-105">You can find the procedures for doing this later in this topic.</span></span>  
  
- <span data-ttu-id="b10b8-106">导入从另一个应用程序导出的.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="b10b8-106">Import an .msi file that was exported from another application.</span></span> <span data-ttu-id="b10b8-107">如果当前的 BizTalk 组中不存在该应用程序，包括其项目的应用程序是自动创建当前 BizTalk 组中。</span><span class="sxs-lookup"><span data-stu-id="b10b8-107">If the application does not already exist in the current BizTalk group, the application, including its artifacts, is automatically created in the current BizTalk group.</span></span> <span data-ttu-id="b10b8-108">有关详细信息，请参阅[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="b10b8-108">For more information, see [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
- <span data-ttu-id="b10b8-109">部署 BizTalk 程序集从 Visual Studio 到 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b10b8-109">Deploy BizTalk assemblies from Visual Studio into a BizTalk application.</span></span> <span data-ttu-id="b10b8-110">如果当前的 BizTalk 组中不存在指定 Visual Studio 中的应用程序，它是自动创建。</span><span class="sxs-lookup"><span data-stu-id="b10b8-110">If the application specified in Visual Studio does not already exist in the current BizTalk group, it is automatically created.</span></span> <span data-ttu-id="b10b8-111">有关详细信息，请参阅[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="b10b8-111">For more information, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
  <span data-ttu-id="b10b8-112">然后再创建新的应用程序，你可能想要决定如何配置以下选项：</span><span class="sxs-lookup"><span data-stu-id="b10b8-112">Before creating a new application, you might want to decide how to configure the following options:</span></span>  
  
- <span data-ttu-id="b10b8-113">**如何命名新的应用程序。**</span><span class="sxs-lookup"><span data-stu-id="b10b8-113">**What to name the new application.**</span></span> <span data-ttu-id="b10b8-114">在 BizTalk 组中的每个应用程序必须具有唯一名称。</span><span class="sxs-lookup"><span data-stu-id="b10b8-114">Each application in the BizTalk group must have a unique name.</span></span>  
  
- <span data-ttu-id="b10b8-115">**您是否需要添加对其他应用程序的任何引用。**</span><span class="sxs-lookup"><span data-stu-id="b10b8-115">**Whether you need to add any references to other applications.**</span></span> <span data-ttu-id="b10b8-116">来自此应用程序到包含你想要在此应用程序中重复使用的项目的任何应用程序，必须添加的引用。</span><span class="sxs-lookup"><span data-stu-id="b10b8-116">You must add a reference from this application to any applications containing artifacts that you want to reuse in this application.</span></span> <span data-ttu-id="b10b8-117">这将创建应用程序，这会影响您部署这些方法之间的依赖项。</span><span class="sxs-lookup"><span data-stu-id="b10b8-117">This creates a dependency between the applications, which affects the way that you must deploy them.</span></span> <span data-ttu-id="b10b8-118">有关背景信息，请参阅[依赖项和应用程序部署](../core/dependencies-and-application-deployment.md)并[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。</span><span class="sxs-lookup"><span data-stu-id="b10b8-118">For background information, see [Dependencies and Application Deployment](../core/dependencies-and-application-deployment.md) and [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
- <span data-ttu-id="b10b8-119">**您是否需要创建多个应用程序。**</span><span class="sxs-lookup"><span data-stu-id="b10b8-119">**Whether you need to create more than one application.**</span></span> <span data-ttu-id="b10b8-120">您可能需要将某些项目部署到单独的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b10b8-120">You may need to deploy some artifacts into separate applications.</span></span> <span data-ttu-id="b10b8-121">例如，共享的项目应部署到其自身的、 单独的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b10b8-121">For example, shared artifacts should be deployed into their own, separate application.</span></span> <span data-ttu-id="b10b8-122">有关详细信息，请参阅[部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="b10b8-122">For more information, see [Best Practices for Deploying a BizTalk Application](../core/best-practices-for-deploying-a-biztalk-application.md).</span></span>  
  
  <span data-ttu-id="b10b8-123">创建应用程序后，可以向其添加项目和进行其他修改，如本部分中的其他主题中所述 ([创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md))。</span><span class="sxs-lookup"><span data-stu-id="b10b8-123">Once you have created an application, you can add artifacts to it and make other modifications, as described in the other topics in this section ([Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md)).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b10b8-124">先决条件</span><span class="sxs-lookup"><span data-stu-id="b10b8-124">Prerequisites</span></span>  
 <span data-ttu-id="b10b8-125">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="b10b8-125">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="b10b8-126">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="b10b8-126">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-create-a-biztalk-application"></a><span data-ttu-id="b10b8-127">若要创建 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="b10b8-127">To create a BizTalk application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="b10b8-128">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="b10b8-128">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="b10b8-129">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="b10b8-129">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="b10b8-130">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击您要在其中创建新的应用程序，指向该 BizTalk 组**新建**，然后单击**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="b10b8-130">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click the BizTalk group in which you want to create the new application, point to **New**, and then click **Application**.</span></span>  
  
3. <span data-ttu-id="b10b8-131">在中**名称**，键入应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="b10b8-131">In **Name**, type the name of the application.</span></span> <span data-ttu-id="b10b8-132">名称必须是 BizTalk 组中唯一的。</span><span class="sxs-lookup"><span data-stu-id="b10b8-132">The name must be unique in the BizTalk group.</span></span>  
  
4. <span data-ttu-id="b10b8-133">如果你想要将此 BizTalk 组的默认应用程序，请选择**将此默认应用程序**复选框。</span><span class="sxs-lookup"><span data-stu-id="b10b8-133">If you want to make this the default application for the BizTalk group, select the **Make this the default application** check box.</span></span>  
  
5. <span data-ttu-id="b10b8-134">在中**说明**，键入应用程序的说明。</span><span class="sxs-lookup"><span data-stu-id="b10b8-134">In **Description**, type a description for the application.</span></span>  
  
6. <span data-ttu-id="b10b8-135">如果此应用程序将重用来自另一个应用程序的项目，请单击**引用**和执行的其余步骤。</span><span class="sxs-lookup"><span data-stu-id="b10b8-135">If this application will reuse artifacts from another application, click **References** and follow the remaining steps.</span></span> <span data-ttu-id="b10b8-136">否则，请单击**确定**和不再执行任何步骤。</span><span class="sxs-lookup"><span data-stu-id="b10b8-136">Otherwise, click **OK** and take no further steps.</span></span>  
  
7. <span data-ttu-id="b10b8-137">单击**外**，选择包含你想要在此应用程序中重复使用，然后单击的项目的应用程序**确定**。</span><span class="sxs-lookup"><span data-stu-id="b10b8-137">Click **Add**, select the application that contains the artifacts you want to reuse in this application, and then click **OK**.</span></span> <span data-ttu-id="b10b8-138">你想要添加的引用任何其他应用程序重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="b10b8-138">Repeat this step for any additional applications for which you want to add references.</span></span>  
  
8. <span data-ttu-id="b10b8-139">如果你想要从列表中删除应用程序，选择应用程序并单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="b10b8-139">If you want to remove an application from the list, select the application and click **Remove**.</span></span>  
  
9. <span data-ttu-id="b10b8-140">完成后，单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b10b8-140">When finished, click **OK**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="b10b8-141">使用命令行</span><span class="sxs-lookup"><span data-stu-id="b10b8-141">Using the command line</span></span>  
  
1. <span data-ttu-id="b10b8-142">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b10b8-142">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="b10b8-143">键入以下命令，替换适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="b10b8-143">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="b10b8-144">**BTSTask AddApp /ApplicationName:** *value* [**/Default**] [**/Description:**<em>value</em>] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span><span class="sxs-lookup"><span data-stu-id="b10b8-144">**BTSTask AddApp /ApplicationName:** *value* [**/Default**] [**/Description:**<em>value</em>] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="b10b8-145">例如：</span><span class="sxs-lookup"><span data-stu-id="b10b8-145">Example:</span></span>  
  
    <span data-ttu-id="b10b8-146">**BTSTask AddApp /ApplicationName:MyApplication /Description:"My favorite application" /Server:MySQLServer /Database:BizTalkMgmtDb**</span><span class="sxs-lookup"><span data-stu-id="b10b8-146">**BTSTask AddApp /ApplicationName:MyApplication /Description:"My favorite application" /Server:MySQLServer /Database:BizTalkMgmtDb**</span></span>  
  
   |<span data-ttu-id="b10b8-147">参数</span><span class="sxs-lookup"><span data-stu-id="b10b8-147">Parameter</span></span>|<span data-ttu-id="b10b8-148">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="b10b8-148">Value</span></span>|  
   |---------------|-----------|  
   |<span data-ttu-id="b10b8-149">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="b10b8-149">**/ApplicationName**</span></span>|<span data-ttu-id="b10b8-150">要创建的应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="b10b8-150">Name of the application to be created.</span></span> <span data-ttu-id="b10b8-151">包含空格的名称必须括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="b10b8-151">Names containing spaces must be enclosed in double quotation marks (").</span></span>|  
   |<span data-ttu-id="b10b8-152">**/ 默认**</span><span class="sxs-lookup"><span data-stu-id="b10b8-152">**/Default**</span></span>|<span data-ttu-id="b10b8-153">如果指定，使新的应用程序的 BizTalk 组的默认应用程序。</span><span class="sxs-lookup"><span data-stu-id="b10b8-153">When specified, makes the new application the default application for the BizTalk group.</span></span>|  
   |<span data-ttu-id="b10b8-154">**/ 说明**</span><span class="sxs-lookup"><span data-stu-id="b10b8-154">**/Description**</span></span>|<span data-ttu-id="b10b8-155">应用程序的说明。</span><span class="sxs-lookup"><span data-stu-id="b10b8-155">Description of the application.</span></span> <span data-ttu-id="b10b8-156">包含空格的说明必须括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="b10b8-156">Descriptions containing spaces must be enclosed in double quotation marks (").</span></span>|  
   |<span data-ttu-id="b10b8-157">**/Server**</span><span class="sxs-lookup"><span data-stu-id="b10b8-157">**/Server**</span></span>|<span data-ttu-id="b10b8-158">承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="b10b8-158">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="b10b8-159">实例名称仅是所需的实例名称不同于服务器名称时。</span><span class="sxs-lookup"><span data-stu-id="b10b8-159">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="b10b8-160">端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。</span><span class="sxs-lookup"><span data-stu-id="b10b8-160">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="b10b8-161">示例：</span><span class="sxs-lookup"><span data-stu-id="b10b8-161">Examples:</span></span><br /><br /> <span data-ttu-id="b10b8-162">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="b10b8-162">Server=MyServer</span></span><br /><br /> <span data-ttu-id="b10b8-163">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="b10b8-163">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="b10b8-164">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="b10b8-164">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="b10b8-165">**/Database**</span><span class="sxs-lookup"><span data-stu-id="b10b8-165">**/Database**</span></span>|<span data-ttu-id="b10b8-166">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="b10b8-166">Name of the BizTalk Management database.</span></span> <span data-ttu-id="b10b8-167">如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="b10b8-167">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b10b8-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="b10b8-168">See Also</span></span>  
 <span data-ttu-id="b10b8-169">[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="b10b8-169">[Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="b10b8-170">AddApp 命令</span><span class="sxs-lookup"><span data-stu-id="b10b8-170">AddApp Command</span></span>](../core/addapp-command.md)