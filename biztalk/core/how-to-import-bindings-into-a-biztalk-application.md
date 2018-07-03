---
title: 如何将绑定导入 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, applications
- applications, importing
- applications, bindings
- bindings, importing
ms.assetid: 89841b23-4e1b-46ff-8f00-cdad65d6216d
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 174a54b5f1ad98b4ba57c70a24ec2f621577271d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011942"
---
# <a name="how-to-import-bindings-into-a-biztalk-application"></a><span data-ttu-id="c081a-102">如何将绑定导入 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="c081a-102">How to Import Bindings into a BizTalk Application</span></span>
<span data-ttu-id="c081a-103">本主题介绍如何使用 BizTalk Server 管理控制台或命令行将绑定从 .xml 文件导入 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c081a-103">This topic describes how to use the BizTalk Server Administration console or the command line to import bindings into a BizTalk application from an .xml file.</span></span> <span data-ttu-id="c081a-104">您还可以导入绑定到 BizTalk 组，如中所述[如何将绑定导入到 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)。</span><span class="sxs-lookup"><span data-stu-id="c081a-104">You can also import bindings into a BizTalk group, as described in [How to Import Bindings into a BizTalk Group](../core/how-to-import-bindings-into-a-biztalk-group.md).</span></span>  
  
 <span data-ttu-id="c081a-105">您可导入已经从程序集、应用程序或组中导出的绑定。</span><span class="sxs-lookup"><span data-stu-id="c081a-105">You can import bindings that have been exported from an assembly, application, or group.</span></span> <span data-ttu-id="c081a-106">如果要导入组绑定，则只有同名的应用程序绑定应用到绑定所导入到的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c081a-106">If you import group bindings, only the bindings for an application having the same name are applied to the application into which you import the bindings.</span></span> <span data-ttu-id="c081a-107">您还可从具有不同名称的应用程序导入绑定。</span><span class="sxs-lookup"><span data-stu-id="c081a-107">You can also import bindings from an application that has a different name.</span></span> <span data-ttu-id="c081a-108">有关导出绑定的说明，请参阅[导出绑定](../core/exporting-bindings6.md)。</span><span class="sxs-lookup"><span data-stu-id="c081a-108">For instructions on exporting bindings, see [Exporting Bindings](../core/exporting-bindings6.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c081a-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="c081a-109">Prerequisites</span></span>  
 <span data-ttu-id="c081a-110">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="c081a-110">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="c081a-111">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="c081a-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-import-bindings-into-a-biztalk-application"></a><span data-ttu-id="c081a-112">将绑定导入到 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="c081a-112">To import bindings into a BizTalk application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="c081a-113">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="c081a-113">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="c081a-114">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="c081a-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="c081a-115">在控制台树中，依次展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”、“BizTalk 组”和“应用程序”。</span><span class="sxs-lookup"><span data-stu-id="c081a-115">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, and then expand Applications.</span></span>  
  
3. <span data-ttu-id="c081a-116">右键单击您要向其中导入绑定，指向应用的程序**导入**，然后单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="c081a-116">Right-click the application into which you want to import bindings, point to **Import**, and then click **Bindings**.</span></span>  
  
4. <span data-ttu-id="c081a-117">单击绑定文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="c081a-117">Click the binding file and click **Open**.</span></span>  
  
    <span data-ttu-id="c081a-118">绑定文件中的项目将写入该应用程序中。</span><span class="sxs-lookup"><span data-stu-id="c081a-118">The artifacts in the binding file are written to the application.</span></span> <span data-ttu-id="c081a-119">这些项目显示在该应用程序的相应文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c081a-119">They display in appropriate folders of the application.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="c081a-120">使用命令行</span><span class="sxs-lookup"><span data-stu-id="c081a-120">Using the command line</span></span>  
  
1. <span data-ttu-id="c081a-121">按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c081a-121">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="c081a-122">键入以下命令，替换适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="c081a-122">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="c081a-123">**BTSTask ImportBindings /Source:** *值*[**/ApplicationName:**<em>值</em>] [**/Server:** <em>值</em>] [**/database:**<em>值</em>]</span><span class="sxs-lookup"><span data-stu-id="c081a-123">**BTSTask ImportBindings /Source:** *value* [**/ApplicationName:**<em>value</em>] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="c081a-124">例如，以下命令将绑定导入到默认 BizTalk 组下名为 MyApplication 的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="c081a-124">For example, the following command imports bindings into the application named MyApplication in the default BizTalk group.</span></span>  
  
    <span data-ttu-id="c081a-125">**BTSTask ImportBindings /ApplicationName:MyApplication** /**Source:C:\Bindings\Binding1.xml**</span><span class="sxs-lookup"><span data-stu-id="c081a-125">**BTSTask ImportBindings /ApplicationName:MyApplication** /**Source:C:\Bindings\Binding1.xml**</span></span>  
  
   |<span data-ttu-id="c081a-126">参数</span><span class="sxs-lookup"><span data-stu-id="c081a-126">Parameter</span></span>|<span data-ttu-id="c081a-127">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="c081a-127">Value</span></span>|  
   |---------------|-----------|  
   |<span data-ttu-id="c081a-128">**/ 源**</span><span class="sxs-lookup"><span data-stu-id="c081a-128">**/Source**</span></span>|<span data-ttu-id="c081a-129">要导入的绑定文件的完整路径，包含文件名。</span><span class="sxs-lookup"><span data-stu-id="c081a-129">Full path of the binding file to import, including the file name.</span></span> <span data-ttu-id="c081a-130">包含空格的路径必须放在引号 (") 中。</span><span class="sxs-lookup"><span data-stu-id="c081a-130">Paths that include spaces must be enclosed in quotation marks (").</span></span>|  
   |<span data-ttu-id="c081a-131">**/ 应用程序名称**</span><span class="sxs-lookup"><span data-stu-id="c081a-131">**/ApplicationName**</span></span>|<span data-ttu-id="c081a-132">绑定要导入到的 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="c081a-132">Name of the BizTalk application into which the bindings are to be imported.</span></span> <span data-ttu-id="c081a-133">该应用程序必须存在，否则导入操作将失败。</span><span class="sxs-lookup"><span data-stu-id="c081a-133">The application must exist or the import operation will fail.</span></span> <span data-ttu-id="c081a-134">如果未指定此参数，则使用默认 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c081a-134">If this parameter is not specified, the default BizTalk application is used.</span></span> <span data-ttu-id="c081a-135">包含空格的应用程序名必须放在引号 (") 中。</span><span class="sxs-lookup"><span data-stu-id="c081a-135">Application names that include spaces must be enclosed in quotation marks (").</span></span>|  
   |<span data-ttu-id="c081a-136">**/ 服务器**</span><span class="sxs-lookup"><span data-stu-id="c081a-136">**/Server**</span></span>|<span data-ttu-id="c081a-137">BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。</span><span class="sxs-lookup"><span data-stu-id="c081a-137">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="c081a-138">只在实例名称与服务器名称不相同时才需要指定实例名称。</span><span class="sxs-lookup"><span data-stu-id="c081a-138">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="c081a-139">只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。</span><span class="sxs-lookup"><span data-stu-id="c081a-139">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="c081a-140">示例：</span><span class="sxs-lookup"><span data-stu-id="c081a-140">Examples:</span></span><br /><br /> <span data-ttu-id="c081a-141">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="c081a-141">Server=MyServer</span></span><br /><br /> <span data-ttu-id="c081a-142">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="c081a-142">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="c081a-143">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="c081a-143">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="c081a-144">**/ 数据库**</span><span class="sxs-lookup"><span data-stu-id="c081a-144">**/Database**</span></span>|<span data-ttu-id="c081a-145">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="c081a-145">Name of the BizTalk Management database.</span></span> <span data-ttu-id="c081a-146">如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="c081a-146">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c081a-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="c081a-147">See Also</span></span>  
 <span data-ttu-id="c081a-148">[导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="c081a-148">[Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md) </span></span>  
 [<span data-ttu-id="c081a-149">ImportBindings 命令</span><span class="sxs-lookup"><span data-stu-id="c081a-149">ImportBindings Command</span></span>](../core/importbindings-command.md)