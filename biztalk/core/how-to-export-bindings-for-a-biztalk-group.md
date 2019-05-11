---
title: 如何导出 BizTalk 组的绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, exporting
- groups, bindings
- groups, exporting
ms.assetid: 51955266-f87f-41c9-992c-93036b40f663
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a4a28c046f34aa0d753b07b62ed41dc1933d980
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385085"
---
# <a name="how-to-export-bindings-for-a-biztalk-group"></a><span data-ttu-id="b769c-102">如何导出 BizTalk 组的绑定</span><span class="sxs-lookup"><span data-stu-id="b769c-102">How to Export Bindings for a BizTalk Group</span></span>
<span data-ttu-id="b769c-103">本主题介绍如何使用 BizTalk Server 管理控制台或命令行来将 BizTalk 组的绑定导出到.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="b769c-103">This topic describes how to use the BizTalk Server Administration console or the command line to export the bindings for a BizTalk group to an .xml file.</span></span> <span data-ttu-id="b769c-104">你可以然后这些绑定导入到 BizTalk 组或应用程序，如中所述[如何将绑定导入到 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)并[如何导入到 BizTalk 应用程序的绑定](../core/how-to-import-bindings-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="b769c-104">You can then import these bindings into a BizTalk group or application, as described in [How to Import Bindings into a BizTalk Group](../core/how-to-import-bindings-into-a-biztalk-group.md) and [How to Import Bindings into a BizTalk Application](../core/how-to-import-bindings-into-a-biztalk-application.md).</span></span> <span data-ttu-id="b769c-105">有关使用绑定文件的详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="b769c-105">For more information about using binding files, see [Binding Files and Application Deployment](../core/binding-files-and-application-deployment.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b769c-106">是否或不指定此选项始终导出组的绑定导出全局参与方信息。</span><span class="sxs-lookup"><span data-stu-id="b769c-106">Exporting bindings for a group always exports global party information, whether this option is specified or not.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b769c-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="b769c-107">Prerequisites</span></span>  
 <span data-ttu-id="b769c-108">若要执行本主题中的过程，必须是 BizTalk Server Administrators 或 BizTalk Operators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="b769c-108">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="b769c-109">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="b769c-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-export-bindings-for-a-biztalk-group"></a><span data-ttu-id="b769c-110">若要导出的 BizTalk 组绑定</span><span class="sxs-lookup"><span data-stu-id="b769c-110">To export bindings for a BizTalk group</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="b769c-111">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="b769c-111">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="b769c-112">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="b769c-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="b769c-113">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，右键单击**应用程序**，依次指向**导出**，然后单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="b769c-113">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, right-click **Applications**, point to **Export**, and then click **Bindings**.</span></span>  
  
3. <span data-ttu-id="b769c-114">在导出绑定页上，在**导出到文件**，键入要导出绑定到的.xml 文件的绝对路径。</span><span class="sxs-lookup"><span data-stu-id="b769c-114">On the Export Bindings page, in **Export to file**, type the absolute path of the .xml file to which to export the bindings.</span></span>  
  
    <span data-ttu-id="b769c-115">例如：C:\Bindings\Group1Bindings_Staging1.xml</span><span class="sxs-lookup"><span data-stu-id="b769c-115">Example: C:\Bindings\Group1Bindings_Staging1.xml</span></span>  
  
4. <span data-ttu-id="b769c-116">絋粄**导出当前组中的所有绑定**已选中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b769c-116">Ensure that **Export all bindings from the current group** is selected, and then click **OK**.</span></span>  
  
    <span data-ttu-id="b769c-117">绑定被导出到.xml 文件中指定的位置。</span><span class="sxs-lookup"><span data-stu-id="b769c-117">The bindings are exported to an .xml file in the location that you specified.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="b769c-118">使用命令行</span><span class="sxs-lookup"><span data-stu-id="b769c-118">Using the command line</span></span>  
  
1. <span data-ttu-id="b769c-119">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b769c-119">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="b769c-120">键入以下命令，替换适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="b769c-120">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="b769c-121">**BTSTask ExportBindings /Destination:** *值* **/GroupLevel** [**/GlobalParties**] [**/Server:** <em>值</em>] [**/database:**<em>值</em>]</span><span class="sxs-lookup"><span data-stu-id="b769c-121">**BTSTask ExportBindings /Destination:** *value* **/GroupLevel** [**/GlobalParties**] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="b769c-122">例如：</span><span class="sxs-lookup"><span data-stu-id="b769c-122">Example:</span></span>  
  
    <span data-ttu-id="b769c-123">**BTSTask ExportBindings /Destination:"C:\Binding Files\MyBindings.xml" /GroupLevel /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span><span class="sxs-lookup"><span data-stu-id="b769c-123">**BTSTask ExportBindings /Destination:"C:\Binding Files\MyBindings.xml" /GroupLevel /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span></span>  
  
   |<span data-ttu-id="b769c-124">参数</span><span class="sxs-lookup"><span data-stu-id="b769c-124">Parameter</span></span>|<span data-ttu-id="b769c-125">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="b769c-125">Value</span></span>|  
   |---------------|-----------|  
   |<span data-ttu-id="b769c-126">**/ 目标**</span><span class="sxs-lookup"><span data-stu-id="b769c-126">**/Destination**</span></span>|<span data-ttu-id="b769c-127">若要创建，其中包括文件名的绑定文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="b769c-127">Full path of the binding file to create, including the file name.</span></span> <span data-ttu-id="b769c-128">如果绑定文件具有相同的路径已存在，则将覆盖。</span><span class="sxs-lookup"><span data-stu-id="b769c-128">If a binding file having the same path already exists, it is overwritten.</span></span> <span data-ttu-id="b769c-129">如果路径中有空格，则必须将其括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="b769c-129">If there are spaces in the path, you must enclose it in double quotation marks (").</span></span>|  
   |<span data-ttu-id="b769c-130">**/GroupLevel**</span><span class="sxs-lookup"><span data-stu-id="b769c-130">**/GroupLevel**</span></span>|<span data-ttu-id="b769c-131">如果指定，将导出当前 BizTalk 组中的所有绑定。</span><span class="sxs-lookup"><span data-stu-id="b769c-131">When specified, all bindings in the current BizTalk group are exported.</span></span>|  
   |<span data-ttu-id="b769c-132">**/GlobalParties**</span><span class="sxs-lookup"><span data-stu-id="b769c-132">**/GlobalParties**</span></span>|<span data-ttu-id="b769c-133">如果指定，将导出组的全局参与方信息。</span><span class="sxs-lookup"><span data-stu-id="b769c-133">When specified, exports global party information for the group.</span></span>|  
   |<span data-ttu-id="b769c-134">**/Server**</span><span class="sxs-lookup"><span data-stu-id="b769c-134">**/Server**</span></span>|<span data-ttu-id="b769c-135">承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="b769c-135">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="b769c-136">实例名称仅是所需的实例名称不同于服务器名称时。</span><span class="sxs-lookup"><span data-stu-id="b769c-136">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="b769c-137">端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。</span><span class="sxs-lookup"><span data-stu-id="b769c-137">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="b769c-138">示例：</span><span class="sxs-lookup"><span data-stu-id="b769c-138">Examples:</span></span><br /><br /> <span data-ttu-id="b769c-139">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="b769c-139">Server=MyServer</span></span><br /><br /> <span data-ttu-id="b769c-140">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="b769c-140">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="b769c-141">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="b769c-141">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="b769c-142">**/Database**</span><span class="sxs-lookup"><span data-stu-id="b769c-142">**/Database**</span></span>|<span data-ttu-id="b769c-143">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="b769c-143">Name of the BizTalk Management database.</span></span> <span data-ttu-id="b769c-144">如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="b769c-144">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b769c-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="b769c-145">See Also</span></span>  
 <span data-ttu-id="b769c-146">[导出绑定](../core/exporting-bindings6.md) </span><span class="sxs-lookup"><span data-stu-id="b769c-146">[Exporting Bindings](../core/exporting-bindings6.md) </span></span>  
 <span data-ttu-id="b769c-147">[ExportBindings 命令](../core/exportbindings-command.md) </span><span class="sxs-lookup"><span data-stu-id="b769c-147">[ExportBindings Command](../core/exportbindings-command.md) </span></span>  
 [<span data-ttu-id="b769c-148">导入 BizTalk 应用程序、绑定和策略</span><span class="sxs-lookup"><span data-stu-id="b769c-148">Importing BizTalk Applications, Bindings, and Policies</span></span>](../core/importing-biztalk-applications-bindings-and-policies.md)