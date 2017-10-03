---
title: "如何创建应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications, creating
- creating, applications
ms.assetid: 6a8682a7-3bef-4978-996f-5a9c5154ce62
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6078e292673a1d9dbe3634ea9c0c4e79ab9c2cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-an-application"></a><span data-ttu-id="13794-102">如何创建应用程序</span><span class="sxs-lookup"><span data-stu-id="13794-102">How to Create an Application</span></span>
<span data-ttu-id="13794-103">有三种方法可以创建新的 BizTalk 应用程序：</span><span class="sxs-lookup"><span data-stu-id="13794-103">There are three ways to create a new BizTalk application:</span></span>  
  
-   <span data-ttu-id="13794-104">使用 BizTalk Server 管理控制台的 New Application 命令或 BTSTask 命令行工具的 AddApp 命令来创建 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="13794-104">Create the BizTalk application by using the New Application command of the BizTalk Server Administration console or the AddApp command of the BTSTask command-line tool.</span></span> <span data-ttu-id="13794-105">您可以在本主题后面部分找到具体步骤。</span><span class="sxs-lookup"><span data-stu-id="13794-105">You can find the procedures for doing this later in this topic.</span></span>  
  
-   <span data-ttu-id="13794-106">导入从另一个应用程序导出的 .msi 文件。</span><span class="sxs-lookup"><span data-stu-id="13794-106">Import an .msi file that was exported from another application.</span></span> <span data-ttu-id="13794-107">如果该应用程序在当前 BizTalk 组中不存在，则在当前 BizTalk 组中自动创建该应用程序，包括其项目。</span><span class="sxs-lookup"><span data-stu-id="13794-107">If the application does not already exist in the current BizTalk group, the application, including its artifacts, is automatically created in the current BizTalk group.</span></span> <span data-ttu-id="13794-108">有关详细信息，请参阅[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="13794-108">For more information, see [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="13794-109">将 BizTalk 程序集从 Visual Studio 部署到 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="13794-109">Deploy BizTalk assemblies from Visual Studio into a BizTalk application.</span></span> <span data-ttu-id="13794-110">如果 Visual Studio 中指定的应用程序在当前 BizTalk 组中不存在，则自动创建该应用程序。</span><span class="sxs-lookup"><span data-stu-id="13794-110">If the application specified in Visual Studio does not already exist in the current BizTalk group, it is automatically created.</span></span> <span data-ttu-id="13794-111">有关详细信息，请参阅[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="13794-111">For more information, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
 <span data-ttu-id="13794-112">在创建新的应用程序之前，可能需要确定如何配置以下选项：</span><span class="sxs-lookup"><span data-stu-id="13794-112">Before creating a new application, you might want to decide how to configure the following options:</span></span>  
  
-   <span data-ttu-id="13794-113">**要将新的应用程序的内容。**</span><span class="sxs-lookup"><span data-stu-id="13794-113">**What to name the new application.**</span></span> <span data-ttu-id="13794-114">BizTalk 组中的每个应用程序必须具有唯一名称。</span><span class="sxs-lookup"><span data-stu-id="13794-114">Each application in the BizTalk group must have a unique name.</span></span>  
  
-   <span data-ttu-id="13794-115">**是否需要添加对其他应用程序的任何引用。**</span><span class="sxs-lookup"><span data-stu-id="13794-115">**Whether you need to add any references to other applications.**</span></span> <span data-ttu-id="13794-116">必须从此应用程序添加对任何包含您要在此应用程序中重用的项目的应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="13794-116">You must add a reference from this application to any applications containing artifacts that you want to reuse in this application.</span></span> <span data-ttu-id="13794-117">这样会在应用程序之间建立依赖关系，这会影响您部署这些应用程序的方式。</span><span class="sxs-lookup"><span data-stu-id="13794-117">This creates a dependency between the applications, which affects the way that you must deploy them.</span></span> <span data-ttu-id="13794-118">有关背景信息，请参阅[依赖关系和应用程序部署](../core/dependencies-and-application-deployment.md)和[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。</span><span class="sxs-lookup"><span data-stu-id="13794-118">For background information, see [Dependencies and Application Deployment](../core/dependencies-and-application-deployment.md) and [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
-   <span data-ttu-id="13794-119">**是否需要创建多个应用程序。**</span><span class="sxs-lookup"><span data-stu-id="13794-119">**Whether you need to create more than one application.**</span></span> <span data-ttu-id="13794-120">您可能需要将某些项目部署到单独的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="13794-120">You may need to deploy some artifacts into separate applications.</span></span> <span data-ttu-id="13794-121">例如，共享项目应部署到自己的单独的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="13794-121">For example, shared artifacts should be deployed into their own, separate application.</span></span> <span data-ttu-id="13794-122">有关详细信息，请参阅[部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="13794-122">For more information, see [Best Practices for Deploying a BizTalk Application](../core/best-practices-for-deploying-a-biztalk-application.md).</span></span>  
  
 <span data-ttu-id="13794-123">一旦你已创建应用程序，可以向其添加项目和此部分中的其他主题中所述进行其他修改，([创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md))。</span><span class="sxs-lookup"><span data-stu-id="13794-123">Once you have created an application, you can add artifacts to it and make other modifications, as described in the other topics in this section ([Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md)).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="13794-124">先决条件</span><span class="sxs-lookup"><span data-stu-id="13794-124">Prerequisites</span></span>  
 <span data-ttu-id="13794-125">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="13794-125">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="13794-126">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="13794-126">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-create-a-biztalk-application"></a><span data-ttu-id="13794-127">创建 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="13794-127">To create a BizTalk application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="13794-128">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="13794-128">Using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="13794-129">单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="13794-129">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="13794-130">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击你要在其中创建新的应用程序，指向的 BizTalk 组**新建**，然后单击**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="13794-130">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click the BizTalk group in which you want to create the new application, point to **New**, and then click **Application**.</span></span>  
  
3.  <span data-ttu-id="13794-131">在**名称**，键入应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="13794-131">In **Name**, type the name of the application.</span></span> <span data-ttu-id="13794-132">该名称在 BizTalk 组中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="13794-132">The name must be unique in the BizTalk group.</span></span>  
  
4.  <span data-ttu-id="13794-133">如果你想要使此 BizTalk 组的默认应用程序，选择**使这成为默认应用**复选框。</span><span class="sxs-lookup"><span data-stu-id="13794-133">If you want to make this the default application for the BizTalk group, select the **Make this the default application** check box.</span></span>  
  
5.  <span data-ttu-id="13794-134">在**说明**，键入应用程序的说明。</span><span class="sxs-lookup"><span data-stu-id="13794-134">In **Description**, type a description for the application.</span></span>  
  
6.  <span data-ttu-id="13794-135">如果此应用程序将重复使用从另一个应用程序的项目，请单击**引用**和执行的其余步骤。</span><span class="sxs-lookup"><span data-stu-id="13794-135">If this application will reuse artifacts from another application, click **References** and follow the remaining steps.</span></span> <span data-ttu-id="13794-136">否则，请单击**确定**并采取任何进一步的步骤。</span><span class="sxs-lookup"><span data-stu-id="13794-136">Otherwise, click **OK** and take no further steps.</span></span>  
  
7.  <span data-ttu-id="13794-137">单击**添加**，选择包含你想要在此应用程序中重复使用，然后单击的项目的应用程序**确定**。</span><span class="sxs-lookup"><span data-stu-id="13794-137">Click **Add**, select the application that contains the artifacts you want to reuse in this application, and then click **OK**.</span></span> <span data-ttu-id="13794-138">对任何其他要添加引用的应用程序重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="13794-138">Repeat this step for any additional applications for which you want to add references.</span></span>  
  
8.  <span data-ttu-id="13794-139">如果你想要从列表中删除应用程序，选择应用程序，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="13794-139">If you want to remove an application from the list, select the application and click **Remove**.</span></span>  
  
9. <span data-ttu-id="13794-140">完成后，单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="13794-140">When finished, click **OK**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="13794-141">使用命令行</span><span class="sxs-lookup"><span data-stu-id="13794-141">Using the command line</span></span>  
  
1.  <span data-ttu-id="13794-142">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="13794-142">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="13794-143">键入以下命令，替换为适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="13794-143">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
     <span data-ttu-id="13794-144">**BTSTask AddApp /ApplicationName:** *值*[**/默认**] [**/Description:***值*] [**/服务器：***值*] [**/数据库：***值*]</span><span class="sxs-lookup"><span data-stu-id="13794-144">**BTSTask AddApp /ApplicationName:** *value* [**/Default**] [**/Description:***value*] [**/Server:***value*] [**/Database:***value*]</span></span>  
  
     <span data-ttu-id="13794-145">例如：</span><span class="sxs-lookup"><span data-stu-id="13794-145">Example:</span></span>  
  
     <span data-ttu-id="13794-146">**BTSTask AddApp /ApplicationName:MyApplication /Description:"我最喜欢的应用程序"/Server:MySQLServer /Database:BizTalkMgmtDb**</span><span class="sxs-lookup"><span data-stu-id="13794-146">**BTSTask AddApp /ApplicationName:MyApplication /Description:"My favorite application" /Server:MySQLServer /Database:BizTalkMgmtDb**</span></span>  
  
    |<span data-ttu-id="13794-147">参数</span><span class="sxs-lookup"><span data-stu-id="13794-147">Parameter</span></span>|<span data-ttu-id="13794-148">值</span><span class="sxs-lookup"><span data-stu-id="13794-148">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="13794-149">**/ 应用程序名称**</span><span class="sxs-lookup"><span data-stu-id="13794-149">**/ApplicationName**</span></span>|<span data-ttu-id="13794-150">要创建的应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="13794-150">Name of the application to be created.</span></span> <span data-ttu-id="13794-151">包含空格的名称必须括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="13794-151">Names containing spaces must be enclosed in double quotation marks (").</span></span>|  
    |<span data-ttu-id="13794-152">**/ 默认**</span><span class="sxs-lookup"><span data-stu-id="13794-152">**/Default**</span></span>|<span data-ttu-id="13794-153">如果指定，使新的应用程序的默认应用程序的 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="13794-153">When specified, makes the new application the default application for the BizTalk group.</span></span>|  
    |<span data-ttu-id="13794-154">**/ 说明**</span><span class="sxs-lookup"><span data-stu-id="13794-154">**/Description**</span></span>|<span data-ttu-id="13794-155">应用程序的说明。</span><span class="sxs-lookup"><span data-stu-id="13794-155">Description of the application.</span></span> <span data-ttu-id="13794-156">包含空格的说明必须括在双引号 (") 中。</span><span class="sxs-lookup"><span data-stu-id="13794-156">Descriptions containing spaces must be enclosed in double quotation marks (").</span></span>|  
    |<span data-ttu-id="13794-157">**/ 服务器**</span><span class="sxs-lookup"><span data-stu-id="13794-157">**/Server**</span></span>|<span data-ttu-id="13794-158">BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。</span><span class="sxs-lookup"><span data-stu-id="13794-158">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="13794-159">只在实例名称与服务器名称不相同时才需要指定实例名称。</span><span class="sxs-lookup"><span data-stu-id="13794-159">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="13794-160">只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。</span><span class="sxs-lookup"><span data-stu-id="13794-160">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="13794-161">示例：</span><span class="sxs-lookup"><span data-stu-id="13794-161">Examples:</span></span><br /><br /> <span data-ttu-id="13794-162">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="13794-162">Server=MyServer</span></span><br /><br /> <span data-ttu-id="13794-163">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="13794-163">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="13794-164">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="13794-164">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
    |<span data-ttu-id="13794-165">**/ 数据库**</span><span class="sxs-lookup"><span data-stu-id="13794-165">**/Database**</span></span>|<span data-ttu-id="13794-166">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="13794-166">Name of the BizTalk Management database.</span></span> <span data-ttu-id="13794-167">如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="13794-167">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13794-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13794-168">See Also</span></span>  
 <span data-ttu-id="13794-169">[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="13794-169">[Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="13794-170">AddApp 命令</span><span class="sxs-lookup"><span data-stu-id="13794-170">AddApp Command</span></span>](../core/addapp-command.md)