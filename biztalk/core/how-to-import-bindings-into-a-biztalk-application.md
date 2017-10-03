---
title: "如何将绑定导入 BizTalk 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- bindings, applications
- applications, importing
- applications, bindings
- bindings, importing
ms.assetid: 89841b23-4e1b-46ff-8f00-cdad65d6216d
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b07e2c7cb5e63ee3e03ac69ad591d7939b22d5d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-import-bindings-into-a-biztalk-application"></a><span data-ttu-id="04543-102">如何将绑定导入 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="04543-102">How to Import Bindings into a BizTalk Application</span></span>
<span data-ttu-id="04543-103">本主题介绍如何使用 BizTalk Server 管理控制台或命令行将绑定从 .xml 文件导入 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="04543-103">This topic describes how to use the BizTalk Server Administration console or the command line to import bindings into a BizTalk application from an .xml file.</span></span> <span data-ttu-id="04543-104">你还可以导入绑定到 BizTalk 组中所述[如何导入绑定到 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)。</span><span class="sxs-lookup"><span data-stu-id="04543-104">You can also import bindings into a BizTalk group, as described in [How to Import Bindings into a BizTalk Group](../core/how-to-import-bindings-into-a-biztalk-group.md).</span></span>  
  
 <span data-ttu-id="04543-105">您可导入已经从程序集、应用程序或组中导出的绑定。</span><span class="sxs-lookup"><span data-stu-id="04543-105">You can import bindings that have been exported from an assembly, application, or group.</span></span> <span data-ttu-id="04543-106">如果要导入组绑定，则只有同名的应用程序绑定应用到绑定所导入到的应用程序。</span><span class="sxs-lookup"><span data-stu-id="04543-106">If you import group bindings, only the bindings for an application having the same name are applied to the application into which you import the bindings.</span></span> <span data-ttu-id="04543-107">您还可从具有不同名称的应用程序导入绑定。</span><span class="sxs-lookup"><span data-stu-id="04543-107">You can also import bindings from an application that has a different name.</span></span> <span data-ttu-id="04543-108">有关导出绑定的说明，请参阅[导出绑定](../core/exporting-bindings6.md)。</span><span class="sxs-lookup"><span data-stu-id="04543-108">For instructions on exporting bindings, see [Exporting Bindings](../core/exporting-bindings6.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="04543-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="04543-109">Prerequisites</span></span>  
 <span data-ttu-id="04543-110">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="04543-110">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="04543-111">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="04543-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-import-bindings-into-a-biztalk-application"></a><span data-ttu-id="04543-112">将绑定导入到 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="04543-112">To import bindings into a BizTalk application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="04543-113">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="04543-113">Using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="04543-114">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="04543-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="04543-115">在控制台树中，依次展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”、“BizTalk 组”和“应用程序”。</span><span class="sxs-lookup"><span data-stu-id="04543-115">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, and then expand Applications.</span></span>  
  
3.  <span data-ttu-id="04543-116">右键单击你想要导入的绑定，指向在其中的应用**导入**，然后单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="04543-116">Right-click the application into which you want to import bindings, point to **Import**, and then click **Bindings**.</span></span>  
  
4.  <span data-ttu-id="04543-117">单击绑定文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="04543-117">Click the binding file and click **Open**.</span></span>  
  
     <span data-ttu-id="04543-118">绑定文件中的项目将写入该应用程序中。</span><span class="sxs-lookup"><span data-stu-id="04543-118">The artifacts in the binding file are written to the application.</span></span> <span data-ttu-id="04543-119">这些项目显示在该应用程序的相应文件夹中。</span><span class="sxs-lookup"><span data-stu-id="04543-119">They display in appropriate folders of the application.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="04543-120">使用命令行</span><span class="sxs-lookup"><span data-stu-id="04543-120">Using the command line</span></span>  
  
1.  <span data-ttu-id="04543-121">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="04543-121">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="04543-122">键入以下命令，替换为适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="04543-122">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
     <span data-ttu-id="04543-123">**BTSTask ImportBindings /Source:** *值*[**/ApplicationName:***值*] [**/Server:** *值*] [**/数据库：***值*]</span><span class="sxs-lookup"><span data-stu-id="04543-123">**BTSTask ImportBindings /Source:** *value* [**/ApplicationName:***value*] [**/Server:***value*] [**/Database:***value*]</span></span>  
  
     <span data-ttu-id="04543-124">例如，以下命令将绑定导入到默认 BizTalk 组下名为 MyApplication 的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="04543-124">For example, the following command imports bindings into the application named MyApplication in the default BizTalk group.</span></span>  
  
     <span data-ttu-id="04543-125">**BTSTask ImportBindings /ApplicationName:MyApplication** /**Source:C:\Bindings\Binding1.xml**</span><span class="sxs-lookup"><span data-stu-id="04543-125">**BTSTask ImportBindings /ApplicationName:MyApplication** /**Source:C:\Bindings\Binding1.xml**</span></span>  
  
    |<span data-ttu-id="04543-126">参数</span><span class="sxs-lookup"><span data-stu-id="04543-126">Parameter</span></span>|<span data-ttu-id="04543-127">值</span><span class="sxs-lookup"><span data-stu-id="04543-127">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="04543-128">**/ 源**</span><span class="sxs-lookup"><span data-stu-id="04543-128">**/Source**</span></span>|<span data-ttu-id="04543-129">要导入的绑定文件的完整路径，包含文件名。</span><span class="sxs-lookup"><span data-stu-id="04543-129">Full path of the binding file to import, including the file name.</span></span> <span data-ttu-id="04543-130">包含空格的路径必须放在引号 (") 中。</span><span class="sxs-lookup"><span data-stu-id="04543-130">Paths that include spaces must be enclosed in quotation marks (").</span></span>|  
    |<span data-ttu-id="04543-131">**/ 应用程序名称**</span><span class="sxs-lookup"><span data-stu-id="04543-131">**/ApplicationName**</span></span>|<span data-ttu-id="04543-132">绑定要导入到的 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="04543-132">Name of the BizTalk application into which the bindings are to be imported.</span></span> <span data-ttu-id="04543-133">该应用程序必须存在，否则导入操作将失败。</span><span class="sxs-lookup"><span data-stu-id="04543-133">The application must exist or the import operation will fail.</span></span> <span data-ttu-id="04543-134">如果未指定此参数，则使用默认 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="04543-134">If this parameter is not specified, the default BizTalk application is used.</span></span> <span data-ttu-id="04543-135">包含空格的应用程序名必须放在引号 (") 中。</span><span class="sxs-lookup"><span data-stu-id="04543-135">Application names that include spaces must be enclosed in quotation marks (").</span></span>|  
    |<span data-ttu-id="04543-136">**/ 服务器**</span><span class="sxs-lookup"><span data-stu-id="04543-136">**/Server**</span></span>|<span data-ttu-id="04543-137">BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。</span><span class="sxs-lookup"><span data-stu-id="04543-137">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="04543-138">只在实例名称与服务器名称不相同时才需要指定实例名称。</span><span class="sxs-lookup"><span data-stu-id="04543-138">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="04543-139">只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。</span><span class="sxs-lookup"><span data-stu-id="04543-139">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="04543-140">示例：</span><span class="sxs-lookup"><span data-stu-id="04543-140">Examples:</span></span><br /><br /> <span data-ttu-id="04543-141">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="04543-141">Server=MyServer</span></span><br /><br /> <span data-ttu-id="04543-142">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="04543-142">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="04543-143">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="04543-143">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
    |<span data-ttu-id="04543-144">**/ 数据库**</span><span class="sxs-lookup"><span data-stu-id="04543-144">**/Database**</span></span>|<span data-ttu-id="04543-145">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="04543-145">Name of the BizTalk Management database.</span></span> <span data-ttu-id="04543-146">如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="04543-146">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="04543-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04543-147">See Also</span></span>  
 <span data-ttu-id="04543-148">[导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="04543-148">[Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md) </span></span>  
 [<span data-ttu-id="04543-149">ImportBindings 命令</span><span class="sxs-lookup"><span data-stu-id="04543-149">ImportBindings Command</span></span>](../core/importbindings-command.md)