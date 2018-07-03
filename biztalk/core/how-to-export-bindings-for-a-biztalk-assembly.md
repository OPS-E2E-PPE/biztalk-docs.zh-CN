---
title: 如何导出 BizTalk 程序集的绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies, bindings
- assemblies, exporting
- exporting, assemblies
ms.assetid: 7e37348d-5fa5-43cc-b3c0-2d8cb6a8f394
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30075db1d02f14fe528817edc356c5294894071e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015134"
---
# <a name="how-to-export-bindings-for-a-biztalk-assembly"></a><span data-ttu-id="d5691-102">如何导出 BizTalk 程序集的绑定</span><span class="sxs-lookup"><span data-stu-id="d5691-102">How to Export Bindings for a BizTalk Assembly</span></span>
<span data-ttu-id="d5691-103">本主题介绍如何使用 BizTalk Server 管理控制台或命令行将 BizTalk 程序集的绑定导出至 .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="d5691-103">This topic describes how to use the BizTalk Server Administration console or the command line to export the bindings for a BizTalk assembly to an .xml file.</span></span> <span data-ttu-id="d5691-104">然后可以将这些绑定导入到 BizTalk 应用程序中，与现有绑定同名的导入绑定将覆盖现有绑定。</span><span class="sxs-lookup"><span data-stu-id="d5691-104">You can then import these bindings into a BizTalk application, which overwrites existing bindings with the imported bindings of the same name.</span></span> <span data-ttu-id="d5691-105">在更新程序集之前可能需要导出程序集的绑定，以便在更新之后再导入绑定，以重新应用它们。</span><span class="sxs-lookup"><span data-stu-id="d5691-105">You might want to export the bindings for an assembly before you update it, so that you can import the bindings after you update it to reapply them.</span></span> <span data-ttu-id="d5691-106">有关更新应用程序和程序集的详细信息，请参阅[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="d5691-106">For more information about updating applications and assemblies, see [Updating BizTalk Applications](../core/updating-biztalk-applications.md).</span></span> <span data-ttu-id="d5691-107">有关使用绑定文件的详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="d5691-107">For more information about using binding files, see [Binding Files and Application Deployment](../core/binding-files-and-application-deployment.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d5691-108">必要條件</span><span class="sxs-lookup"><span data-stu-id="d5691-108">Prerequisites</span></span>  
 <span data-ttu-id="d5691-109">要执行本主题中介绍的过程，必须以 BizTalk Server Administrators 组或 BizTalk Server Operators 组成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d5691-109">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators or BizTalk Server Operators group.</span></span> <span data-ttu-id="d5691-110">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="d5691-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-export-bindings-for-a-biztalk-assembly"></a><span data-ttu-id="d5691-111">导出 BizTalk 程序集的绑定</span><span class="sxs-lookup"><span data-stu-id="d5691-111">To export bindings for a BizTalk assembly</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="d5691-112">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="d5691-112">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="d5691-113">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="d5691-113">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="d5691-114">在控制台树中，依次展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”、“BizTalk 组”和“应用程序”。</span><span class="sxs-lookup"><span data-stu-id="d5691-114">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, and then expand Applications.</span></span>  
  
3. <span data-ttu-id="d5691-115">右键单击包含该程序集的应用程序，指向**导出**，然后单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="d5691-115">Right-click the application containing the assembly, point to **Export**, and then click **Bindings**.</span></span>  
  
4. <span data-ttu-id="d5691-116">在导出绑定页上，在**导出到文件**，键入要导出绑定到的.xml 文件的绝对路径。</span><span class="sxs-lookup"><span data-stu-id="d5691-116">On the Export Bindings page, in **Export to file**, type the absolute path of the .xml file to which to export the bindings.</span></span>  
  
    <span data-ttu-id="d5691-117">示例： **C:\Bindings\MyAssemblyBindings_Staging1.xml**</span><span class="sxs-lookup"><span data-stu-id="d5691-117">Example: **C:\Bindings\MyAssemblyBindings_Staging1.xml**</span></span>  
  
5. <span data-ttu-id="d5691-118">在导出绑定页上，单击**导出的所选程序集绑定**，然后在**程序集**，单击该程序集。</span><span class="sxs-lookup"><span data-stu-id="d5691-118">On the Export Bindings page, click **Export bindings for the selected assembly**, and then in **Assembly**, click the assembly.</span></span>  
  
6. <span data-ttu-id="d5691-119">如果你想要导出所有组中的参与方信息，请选择**导出全局参与方信息**。</span><span class="sxs-lookup"><span data-stu-id="d5691-119">If you want to export all of the party information in the group, select **Export Global Party Information**.</span></span>  
  
    <span data-ttu-id="d5691-120">绑定被导出到指定位置上的 .xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="d5691-120">The bindings are exported to an .xml file in the location that you specified.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="d5691-121">使用命令行</span><span class="sxs-lookup"><span data-stu-id="d5691-121">Using the command line</span></span>  
  
1. <span data-ttu-id="d5691-122">按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d5691-122">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="d5691-123">键入以下命令，替换适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="d5691-123">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="d5691-124">**BTSTask ExportBindings /Destination:** *值* **/AssemblyName:** *值*[**/GlobalParties**] [**/Server:**<em>值</em>] [**/database:**<em>值</em>]</span><span class="sxs-lookup"><span data-stu-id="d5691-124">**BTSTask ExportBindings /Destination:** *value* **/AssemblyName:** *value* [**/GlobalParties**] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="d5691-125">例如：</span><span class="sxs-lookup"><span data-stu-id="d5691-125">Example:</span></span>  
  
    <span data-ttu-id="d5691-126">**BTSTask ExportBindings /Destination:"C:\Binding Files\MyBindings.xml"/AssemblyName:"ErrorHandling.ErrorHandler，版本 = 1.0.0.0，区域性 = 中性，PublicKeyToken = 11e921d58826420e"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span><span class="sxs-lookup"><span data-stu-id="d5691-126">**BTSTask ExportBindings /Destination:"C:\Binding Files\MyBindings.xml" /AssemblyName:"ErrorHandling.ErrorHandler, Version=1.0.0.0, Culture=neutral, PublicKeyToken=11e921d58826420e" /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span></span>  
  
   |<span data-ttu-id="d5691-127">参数</span><span class="sxs-lookup"><span data-stu-id="d5691-127">Parameter</span></span>|<span data-ttu-id="d5691-128">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="d5691-128">Value</span></span>|  
   |---------------|-----------|  
   |<span data-ttu-id="d5691-129">**/ 目标**</span><span class="sxs-lookup"><span data-stu-id="d5691-129">**/Destination**</span></span>|<span data-ttu-id="d5691-130">要创建的绑定文件的完整路径，包含文件名。</span><span class="sxs-lookup"><span data-stu-id="d5691-130">Full path of the binding file to create, including the file name.</span></span> <span data-ttu-id="d5691-131">如果已存在具有相同路径的绑定文件，则该文件将被覆盖。</span><span class="sxs-lookup"><span data-stu-id="d5691-131">If a binding file having the same path already exists, it is overwritten.</span></span> <span data-ttu-id="d5691-132">如果路径中有空格，则必须将其括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="d5691-132">If there are spaces in the path, you must enclose it in double quotation marks (").</span></span>|  
   |<span data-ttu-id="d5691-133">**/ 程序集名称**</span><span class="sxs-lookup"><span data-stu-id="d5691-133">**/AssemblyName**</span></span>|<span data-ttu-id="d5691-134">从中导出绑定程序集的本地唯一标识符 (LUID)。</span><span class="sxs-lookup"><span data-stu-id="d5691-134">Locally unique identifier (LUID) of the assembly from which to export bindings.</span></span> <span data-ttu-id="d5691-135">你可以通过使用获取应用程序中的项目的 Luid 的列表[ListApp 命令](../core/listapp-command.md)。</span><span class="sxs-lookup"><span data-stu-id="d5691-135">You can obtain a list of LUIDs for the artifacts in an application by using the [ListApp Command](../core/listapp-command.md).</span></span>|  
   |<span data-ttu-id="d5691-136">**/ GlobalParties**</span><span class="sxs-lookup"><span data-stu-id="d5691-136">**/GlobalParties**</span></span>|<span data-ttu-id="d5691-137">如果指定，则导出组的全局参与方信息。</span><span class="sxs-lookup"><span data-stu-id="d5691-137">When specified, exports global pary information for the group.</span></span>|  
   |<span data-ttu-id="d5691-138">**/ 服务器**</span><span class="sxs-lookup"><span data-stu-id="d5691-138">**/Server**</span></span>|<span data-ttu-id="d5691-139">BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。</span><span class="sxs-lookup"><span data-stu-id="d5691-139">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="d5691-140">只在实例名称与服务器名称不相同时才需要指定实例名称。</span><span class="sxs-lookup"><span data-stu-id="d5691-140">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="d5691-141">只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。</span><span class="sxs-lookup"><span data-stu-id="d5691-141">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="d5691-142">示例：</span><span class="sxs-lookup"><span data-stu-id="d5691-142">Examples:</span></span><br /><br /> <span data-ttu-id="d5691-143">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="d5691-143">Server=MyServer</span></span><br /><br /> <span data-ttu-id="d5691-144">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="d5691-144">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="d5691-145">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="d5691-145">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="d5691-146">**/ 数据库**</span><span class="sxs-lookup"><span data-stu-id="d5691-146">**/Database**</span></span>|<span data-ttu-id="d5691-147">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="d5691-147">Name of the BizTalk Management database.</span></span> <span data-ttu-id="d5691-148">如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="d5691-148">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5691-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5691-149">See Also</span></span>  
 <span data-ttu-id="d5691-150">[导出绑定](../core/exporting-bindings6.md) </span><span class="sxs-lookup"><span data-stu-id="d5691-150">[Exporting Bindings](../core/exporting-bindings6.md) </span></span>  
 <span data-ttu-id="d5691-151">[ExportBindings 命令](../core/exportbindings-command.md) </span><span class="sxs-lookup"><span data-stu-id="d5691-151">[ExportBindings Command](../core/exportbindings-command.md) </span></span>  
 [<span data-ttu-id="d5691-152">导入 BizTalk 应用程序、绑定和策略</span><span class="sxs-lookup"><span data-stu-id="d5691-152">Importing BizTalk Applications, Bindings, and Policies</span></span>](../core/importing-biztalk-applications-bindings-and-policies.md)