---
title: 如何导出 BizTalk 应用程序的绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, exportings
- applications, exporting
- applications, bindings
ms.assetid: 700d2781-480b-42ed-a313-1a67a7406369
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6750ff2f6684942c20eb4fdaa286dcbc181bb5b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385052"
---
# <a name="how-to-export-bindings-for-a-biztalk-application"></a><span data-ttu-id="3647e-102">如何导出 BizTalk 应用程序的绑定</span><span class="sxs-lookup"><span data-stu-id="3647e-102">How to Export Bindings for a BizTalk Application</span></span>
<span data-ttu-id="3647e-103">本主题介绍如何使用 BizTalk Server 管理控制台或命令行导出到.xml 文件的 BizTalk 应用程序的绑定。</span><span class="sxs-lookup"><span data-stu-id="3647e-103">This topic describes how to use the BizTalk Server Administration console or the command line export the bindings for a BizTalk application to an .xml file.</span></span> <span data-ttu-id="3647e-104">您然后可以导入另一个应用程序，使用相同名称的导入绑定将覆盖在应用程序中的当前绑定的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="3647e-104">You can then import the binding file into another application, which overwrites the current bindings in the application with the imported bindings of the same name.</span></span> <span data-ttu-id="3647e-105">有关详细信息，请参阅[导入绑定到 BizTalk 应用程序如何](../core/how-to-import-bindings-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="3647e-105">For more information, see [How to Import Bindings into a BizTalk Application](../core/how-to-import-bindings-into-a-biztalk-application.md).</span></span> <span data-ttu-id="3647e-106">有关使用绑定文件的详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="3647e-106">For more information about using binding files, see [Binding Files and Application Deployment](../core/binding-files-and-application-deployment.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3647e-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="3647e-107">Prerequisites</span></span>  
 <span data-ttu-id="3647e-108">若要执行本主题中的过程，必须是 BizTalk Server Administrators 或 BizTalk Server Operators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="3647e-108">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators or BizTalk Server Operators group.</span></span> <span data-ttu-id="3647e-109">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="3647e-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-export-bindings-for-a-biztalk-application"></a><span data-ttu-id="3647e-110">导出 BizTalk 应用程序的绑定</span><span class="sxs-lookup"><span data-stu-id="3647e-110">To export bindings for a BizTalk application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="3647e-111">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="3647e-111">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="3647e-112">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="3647e-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="3647e-113">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="3647e-113">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="3647e-114">右键单击你想要导出，其的绑定指向应用程序**导出**，然后单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="3647e-114">Right-click the application whose bindings you want to export, point to **Export**, and then click **Bindings**.</span></span>  
  
4. <span data-ttu-id="3647e-115">在导出绑定页上，在**导出到文件**，键入要导出绑定到的.xml 文件的绝对路径。</span><span class="sxs-lookup"><span data-stu-id="3647e-115">On the Export Bindings page, in **Export to file**, type the absolute path of the .xml file to which to export the bindings.</span></span>  
  
    <span data-ttu-id="3647e-116">例如：**C:\Bindings\Application1Bindings_Staging1.xml**</span><span class="sxs-lookup"><span data-stu-id="3647e-116">Example: **C:\Bindings\Application1Bindings_Staging1.xml**</span></span>  
  
5. <span data-ttu-id="3647e-117">絋粄**导出当前应用程序中的所有绑定**已选中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3647e-117">Ensure that **Export all bindings from the current application** is selected, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="3647e-118">若要导出组的所有参与方信息，请选择**导出全局参与方信息**复选框。</span><span class="sxs-lookup"><span data-stu-id="3647e-118">To export all party information for the group, select the **Export Global Party information** check box.</span></span>  
  
    <span data-ttu-id="3647e-119">绑定被导出到.xml 文件中指定的位置。</span><span class="sxs-lookup"><span data-stu-id="3647e-119">The bindings are exported into an .xml file in the location that you specified.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="3647e-120">使用命令行</span><span class="sxs-lookup"><span data-stu-id="3647e-120">Using the command line</span></span>  
  
1. <span data-ttu-id="3647e-121">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3647e-121">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="3647e-122">键入以下命令，替换适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="3647e-122">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="3647e-123">**BTSTask ExportBindings /Destination:** *值*[**/ApplicationName:**<em>值</em>] [**/GlobalParties**] [**/Server:**<em>值</em>] [**/database:**<em>值</em>]</span><span class="sxs-lookup"><span data-stu-id="3647e-123">**BTSTask ExportBindings /Destination:** *value* [**/ApplicationName:**<em>value</em>] [**/GlobalParties**] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="3647e-124">例如：</span><span class="sxs-lookup"><span data-stu-id="3647e-124">Example:</span></span>  
  
    <span data-ttu-id="3647e-125">**BTSTask ExportBindings /Destination:"C:\Binding Files\MyBindings.xml" /ApplicationName:MyApplication /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span><span class="sxs-lookup"><span data-stu-id="3647e-125">**BTSTask ExportBindings /Destination:"C:\Binding Files\MyBindings.xml" /ApplicationName:MyApplication /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span></span>  
  
   |<span data-ttu-id="3647e-126">参数</span><span class="sxs-lookup"><span data-stu-id="3647e-126">Parameter</span></span>|<span data-ttu-id="3647e-127">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="3647e-127">Value</span></span>|  
   |---------------|-----------|  
   |<span data-ttu-id="3647e-128">**/ 目标**</span><span class="sxs-lookup"><span data-stu-id="3647e-128">**/Destination**</span></span>|<span data-ttu-id="3647e-129">若要创建，其中包括文件名的绑定文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="3647e-129">Full path of the binding file to create, including the file name.</span></span> <span data-ttu-id="3647e-130">如果绑定文件具有相同的路径已存在，则将覆盖。</span><span class="sxs-lookup"><span data-stu-id="3647e-130">If a binding file having the same path already exists, it is overwritten.</span></span> <span data-ttu-id="3647e-131">如果路径中有空格，则必须将其括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="3647e-131">If there are spaces in the path, you must enclose it in double quotation marks (").</span></span>|  
   |<span data-ttu-id="3647e-132">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="3647e-132">**/ApplicationName**</span></span>|<span data-ttu-id="3647e-133">从中导出绑定的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="3647e-133">Name of the application from which to export bindings.</span></span> <span data-ttu-id="3647e-134">该应用程序必须存在。</span><span class="sxs-lookup"><span data-stu-id="3647e-134">The application must exist.</span></span> <span data-ttu-id="3647e-135">若要验证的应用程序名称，可以使用**ListApps**命令，如中所述[ListApps 命令](../core/listapps-command.md)。</span><span class="sxs-lookup"><span data-stu-id="3647e-135">To verify the application name, you can use the **ListApps** command, as described in [ListApps Command](../core/listapps-command.md).</span></span> <span data-ttu-id="3647e-136">如果未指定此参数，则使用默认 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="3647e-136">If this parameter is not specified, the default BizTalk application is used.</span></span> <span data-ttu-id="3647e-137">如果名称中有空格，则必须将其括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="3647e-137">If there are spaces in the name, you must enclose it in double quotation marks (").</span></span>|  
   |<span data-ttu-id="3647e-138">**/GlobalParties**</span><span class="sxs-lookup"><span data-stu-id="3647e-138">**/GlobalParties**</span></span>|<span data-ttu-id="3647e-139">如果指定，将导出组的全局参与方信息。</span><span class="sxs-lookup"><span data-stu-id="3647e-139">When specified, exports global party information for the group.</span></span>|  
   |<span data-ttu-id="3647e-140">**/Server**</span><span class="sxs-lookup"><span data-stu-id="3647e-140">**/Server**</span></span>|<span data-ttu-id="3647e-141">承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="3647e-141">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="3647e-142">实例名称仅是所需的实例名称不同于服务器名称时。</span><span class="sxs-lookup"><span data-stu-id="3647e-142">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="3647e-143">端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。</span><span class="sxs-lookup"><span data-stu-id="3647e-143">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="3647e-144">示例：</span><span class="sxs-lookup"><span data-stu-id="3647e-144">Examples:</span></span><br /><br /> <span data-ttu-id="3647e-145">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="3647e-145">Server=MyServer</span></span><br /><br /> <span data-ttu-id="3647e-146">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="3647e-146">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="3647e-147">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="3647e-147">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="3647e-148">**/Database**</span><span class="sxs-lookup"><span data-stu-id="3647e-148">**/Database**</span></span>|<span data-ttu-id="3647e-149">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="3647e-149">Name of the BizTalk Management database.</span></span> <span data-ttu-id="3647e-150">如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="3647e-150">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3647e-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="3647e-151">See Also</span></span>  
 <span data-ttu-id="3647e-152">[导出绑定](../core/exporting-bindings6.md) </span><span class="sxs-lookup"><span data-stu-id="3647e-152">[Exporting Bindings](../core/exporting-bindings6.md) </span></span>  
 <span data-ttu-id="3647e-153">[ExportBindings 命令](../core/exportbindings-command.md) </span><span class="sxs-lookup"><span data-stu-id="3647e-153">[ExportBindings Command](../core/exportbindings-command.md) </span></span>  
 [<span data-ttu-id="3647e-154">导入 BizTalk 应用程序、绑定和策略</span><span class="sxs-lookup"><span data-stu-id="3647e-154">Importing BizTalk Applications, Bindings, and Policies</span></span>](../core/importing-biztalk-applications-bindings-and-policies.md)