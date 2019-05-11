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
ms.openlocfilehash: 30cd7c587f09911b1ce3e16c21aae265a0a94ea8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385006"
---
# <a name="how-to-import-bindings-into-a-biztalk-application"></a><span data-ttu-id="94609-102">如何将绑定导入 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="94609-102">How to Import Bindings into a BizTalk Application</span></span>
<span data-ttu-id="94609-103">本主题介绍如何使用 BizTalk Server 管理控制台或命令行来绑定导入到 BizTalk 应用程序从.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="94609-103">This topic describes how to use the BizTalk Server Administration console or the command line to import bindings into a BizTalk application from an .xml file.</span></span> <span data-ttu-id="94609-104">您还可以导入绑定到 BizTalk 组，如中所述[如何将绑定导入到 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)。</span><span class="sxs-lookup"><span data-stu-id="94609-104">You can also import bindings into a BizTalk group, as described in [How to Import Bindings into a BizTalk Group](../core/how-to-import-bindings-into-a-biztalk-group.md).</span></span>  
  
 <span data-ttu-id="94609-105">您可以导入已从程序集、 应用程序或组中导出的绑定。</span><span class="sxs-lookup"><span data-stu-id="94609-105">You can import bindings that have been exported from an assembly, application, or group.</span></span> <span data-ttu-id="94609-106">如果导入组绑定，仅具有相同名称的应用程序的绑定应用到应用程序在其中导入绑定。</span><span class="sxs-lookup"><span data-stu-id="94609-106">If you import group bindings, only the bindings for an application having the same name are applied to the application into which you import the bindings.</span></span> <span data-ttu-id="94609-107">您还可以从具有不同名称的应用程序导入绑定。</span><span class="sxs-lookup"><span data-stu-id="94609-107">You can also import bindings from an application that has a different name.</span></span> <span data-ttu-id="94609-108">有关导出绑定的说明，请参阅[导出绑定](../core/exporting-bindings6.md)。</span><span class="sxs-lookup"><span data-stu-id="94609-108">For instructions on exporting bindings, see [Exporting Bindings](../core/exporting-bindings6.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="94609-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="94609-109">Prerequisites</span></span>  
 <span data-ttu-id="94609-110">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="94609-110">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="94609-111">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="94609-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-import-bindings-into-a-biztalk-application"></a><span data-ttu-id="94609-112">绑定导入到 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="94609-112">To import bindings into a BizTalk application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="94609-113">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="94609-113">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="94609-114">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="94609-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="94609-115">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，然后展开应用程序。</span><span class="sxs-lookup"><span data-stu-id="94609-115">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, and then expand Applications.</span></span>  
  
3. <span data-ttu-id="94609-116">右键单击您要向其中导入绑定，指向应用的程序**导入**，然后单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="94609-116">Right-click the application into which you want to import bindings, point to **Import**, and then click **Bindings**.</span></span>  
  
4. <span data-ttu-id="94609-117">单击绑定文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="94609-117">Click the binding file and click **Open**.</span></span>  
  
    <span data-ttu-id="94609-118">绑定文件中的项目将写入到应用程序。</span><span class="sxs-lookup"><span data-stu-id="94609-118">The artifacts in the binding file are written to the application.</span></span> <span data-ttu-id="94609-119">它们显示在应用程序的相应文件夹中。</span><span class="sxs-lookup"><span data-stu-id="94609-119">They display in appropriate folders of the application.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="94609-120">使用命令行</span><span class="sxs-lookup"><span data-stu-id="94609-120">Using the command line</span></span>  
  
1. <span data-ttu-id="94609-121">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="94609-121">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="94609-122">键入以下命令，替换适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="94609-122">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="94609-123">**BTSTask ImportBindings /Source:** *value* [**/ApplicationName:**<em>value</em>] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span><span class="sxs-lookup"><span data-stu-id="94609-123">**BTSTask ImportBindings /Source:** *value* [**/ApplicationName:**<em>value</em>] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="94609-124">例如，以下命令将绑定到默认 BizTalk 组中名为 MyApplication 的应用程序导入。</span><span class="sxs-lookup"><span data-stu-id="94609-124">For example, the following command imports bindings into the application named MyApplication in the default BizTalk group.</span></span>  
  
    <span data-ttu-id="94609-125">**BTSTask ImportBindings /ApplicationName:MyApplication** /**Source:C:\Bindings\Binding1.xml**</span><span class="sxs-lookup"><span data-stu-id="94609-125">**BTSTask ImportBindings /ApplicationName:MyApplication** /**Source:C:\Bindings\Binding1.xml**</span></span>  
  
   |<span data-ttu-id="94609-126">参数</span><span class="sxs-lookup"><span data-stu-id="94609-126">Parameter</span></span>|<span data-ttu-id="94609-127">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="94609-127">Value</span></span>|  
   |---------------|-----------|  
   |<span data-ttu-id="94609-128">**/Source**</span><span class="sxs-lookup"><span data-stu-id="94609-128">**/Source**</span></span>|<span data-ttu-id="94609-129">要导入，其中包括文件名的绑定文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="94609-129">Full path of the binding file to import, including the file name.</span></span> <span data-ttu-id="94609-130">包含空格的路径必须括在引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="94609-130">Paths that include spaces must be enclosed in quotation marks (").</span></span>|  
   |<span data-ttu-id="94609-131">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="94609-131">**/ApplicationName**</span></span>|<span data-ttu-id="94609-132">在其中绑定是要导入 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="94609-132">Name of the BizTalk application into which the bindings are to be imported.</span></span> <span data-ttu-id="94609-133">该应用程序必须存在，或导入操作将失败。</span><span class="sxs-lookup"><span data-stu-id="94609-133">The application must exist or the import operation will fail.</span></span> <span data-ttu-id="94609-134">如果未指定此参数，则使用默认 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="94609-134">If this parameter is not specified, the default BizTalk application is used.</span></span> <span data-ttu-id="94609-135">包含空格的应用程序名必须括在引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="94609-135">Application names that include spaces must be enclosed in quotation marks (").</span></span>|  
   |<span data-ttu-id="94609-136">**/Server**</span><span class="sxs-lookup"><span data-stu-id="94609-136">**/Server**</span></span>|<span data-ttu-id="94609-137">承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="94609-137">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="94609-138">实例名称仅是所需的实例名称不同于服务器名称时。</span><span class="sxs-lookup"><span data-stu-id="94609-138">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="94609-139">端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。</span><span class="sxs-lookup"><span data-stu-id="94609-139">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="94609-140">示例：</span><span class="sxs-lookup"><span data-stu-id="94609-140">Examples:</span></span><br /><br /> <span data-ttu-id="94609-141">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="94609-141">Server=MyServer</span></span><br /><br /> <span data-ttu-id="94609-142">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="94609-142">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="94609-143">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="94609-143">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="94609-144">**/Database**</span><span class="sxs-lookup"><span data-stu-id="94609-144">**/Database**</span></span>|<span data-ttu-id="94609-145">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="94609-145">Name of the BizTalk Management database.</span></span> <span data-ttu-id="94609-146">如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="94609-146">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="94609-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="94609-147">See Also</span></span>  
 <span data-ttu-id="94609-148">[导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="94609-148">[Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md) </span></span>  
 [<span data-ttu-id="94609-149">ImportBindings 命令</span><span class="sxs-lookup"><span data-stu-id="94609-149">ImportBindings Command</span></span>](../core/importbindings-command.md)