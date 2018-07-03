---
title: 如何将绑定导入 BizTalk 组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, importing
- importing, bindings
- groups, bindings
- bindings, groups
ms.assetid: 38da14fb-3522-4274-a633-2ff24e4bd574
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1bdc3f8c25e50567c9e12df5c61ba28cc225e5a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000374"
---
# <a name="how-to-import-bindings-into-a-biztalk-group"></a><span data-ttu-id="b4575-102">如何将绑定导入 BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="b4575-102">How to Import Bindings into a BizTalk Group</span></span>
<span data-ttu-id="b4575-103">本主题介绍如何使用 BizTalk Server 管理控制台或命令行通过 .xml 文件向 BizTalk 组导入绑定。</span><span class="sxs-lookup"><span data-stu-id="b4575-103">This topic describes how to use the BizTalk Server Administration console or the command line to import bindings into a BizTalk group from an .xml file.</span></span> <span data-ttu-id="b4575-104">有关 BizTalk 组中的绑定导出到.xml 文件，可以导入的说明，请参阅[如何为 BizTalk 组导出绑定](../core/how-to-export-bindings-for-a-biztalk-group.md)。</span><span class="sxs-lookup"><span data-stu-id="b4575-104">For instructions on exporting the bindings from a BizTalk group into an .xml file that you can import, see [How to Export Bindings for a BizTalk Group](../core/how-to-export-bindings-for-a-biztalk-group.md).</span></span>  
  
 <span data-ttu-id="b4575-105">您还可以导入绑定到 BizTalk 应用程序，如中所述[如何将绑定导入到 BizTalk 应用程序](../core/how-to-import-bindings-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="b4575-105">You can also import bindings into a BizTalk application, as described in [How to Import Bindings into a BizTalk Application](../core/how-to-import-bindings-into-a-biztalk-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b4575-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="b4575-106">Prerequisites</span></span>  
 <span data-ttu-id="b4575-107">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="b4575-107">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="b4575-108">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="b4575-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-import-bindings-into-a-biztalk-group"></a><span data-ttu-id="b4575-109">将绑定导入到 BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="b4575-109">To import bindings into a BizTalk group</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="b4575-110">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="b4575-110">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="b4575-111">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="b4575-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="b4575-112">在控制台树中，展开**BizTalk Server 管理**、 BizTalk 组，，然后右键单击**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="b4575-112">In the console tree, expand  **BizTalk Server Administration**, expand the BizTalk group, and then right-click **Applications**.</span></span>  
  
3. <span data-ttu-id="b4575-113">指向**导入**，然后单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="b4575-113">Point to **Import**, and then click **Bindings**.</span></span>  
  
4. <span data-ttu-id="b4575-114">单击绑定文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="b4575-114">Click the binding file and click **Open**.</span></span>  
  
    <span data-ttu-id="b4575-115">绑定文件中的项目将写入该组。</span><span class="sxs-lookup"><span data-stu-id="b4575-115">The artifacts in the binding file are written to the group.</span></span> <span data-ttu-id="b4575-116">它们的相应文件夹中显示\<的所有项目\>节点。</span><span class="sxs-lookup"><span data-stu-id="b4575-116">They display in appropriate folders of the \<All Artifacts\> node.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="b4575-117">使用命令行</span><span class="sxs-lookup"><span data-stu-id="b4575-117">Using the command line</span></span>  
  
1. <span data-ttu-id="b4575-118">按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b4575-118">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="b4575-119">键入以下命令，替换适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="b4575-119">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="b4575-120">**BTSTask ImportBindings /Source:** *值* **/GroupLevel** [**/Server:**<em>值</em>] [  **/数据库:**<em>值</em>]</span><span class="sxs-lookup"><span data-stu-id="b4575-120">**BTSTask ImportBindings /Source:** *value* **/GroupLevel** [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="b4575-121">例如，以下命令将绑定导入到 BizTalk 管理数据库中所定义的组，该 BizTalk 管理数据库运行在名为 MyServer 的 SQL Server 实例上。</span><span class="sxs-lookup"><span data-stu-id="b4575-121">For example, the following command imports bindings into the group defined in the BizTalk Management database running on a SQL Server instance named MyServer.</span></span>  
  
    <span data-ttu-id="b4575-122">**BTSTask ImportBindings GroupLevel /Server:MyServer /Database:BiztalkMgmtDb /Source:C:\Bindings\Binding1.xml**</span><span class="sxs-lookup"><span data-stu-id="b4575-122">**BTSTask ImportBindings /GroupLevel /Server:MyServer /Database:BiztalkMgmtDb /Source:C:\Bindings\Binding1.xml**</span></span>  
  
   |<span data-ttu-id="b4575-123">参数</span><span class="sxs-lookup"><span data-stu-id="b4575-123">Parameter</span></span>|<span data-ttu-id="b4575-124">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="b4575-124">Value</span></span>|  
   |---------------|-----------|  
   |<span data-ttu-id="b4575-125">**/ 源**</span><span class="sxs-lookup"><span data-stu-id="b4575-125">**/Source**</span></span>|<span data-ttu-id="b4575-126">要导入的绑定文件的完整路径，包含文件名。</span><span class="sxs-lookup"><span data-stu-id="b4575-126">Full path of the binding file to import, including the file name.</span></span> <span data-ttu-id="b4575-127">包含空格的路径必须放在引号 (") 中。</span><span class="sxs-lookup"><span data-stu-id="b4575-127">Paths that include spaces must be enclosed in quotation marks (").</span></span>|  
   |<span data-ttu-id="b4575-128">**/ GroupLevel**</span><span class="sxs-lookup"><span data-stu-id="b4575-128">**/GroupLevel**</span></span>|<span data-ttu-id="b4575-129">将绑定文件导入到当前组的选项。</span><span class="sxs-lookup"><span data-stu-id="b4575-129">Option to import the binding file into the current group.</span></span>|  
   |<span data-ttu-id="b4575-130">**/ 服务器**</span><span class="sxs-lookup"><span data-stu-id="b4575-130">**/Server**</span></span>|<span data-ttu-id="b4575-131">BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。</span><span class="sxs-lookup"><span data-stu-id="b4575-131">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="b4575-132">只在实例名称与服务器名称不相同时才需要指定实例名称。</span><span class="sxs-lookup"><span data-stu-id="b4575-132">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="b4575-133">只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。</span><span class="sxs-lookup"><span data-stu-id="b4575-133">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="b4575-134">示例：</span><span class="sxs-lookup"><span data-stu-id="b4575-134">Examples:</span></span><br /><br /> <span data-ttu-id="b4575-135">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="b4575-135">Server=MyServer</span></span><br /><br /> <span data-ttu-id="b4575-136">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="b4575-136">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="b4575-137">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="b4575-137">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="b4575-138">**/ 数据库**</span><span class="sxs-lookup"><span data-stu-id="b4575-138">**/Database**</span></span>|<span data-ttu-id="b4575-139">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="b4575-139">Name of the BizTalk Management database.</span></span> <span data-ttu-id="b4575-140">如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="b4575-140">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4575-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4575-141">See Also</span></span>  
 <span data-ttu-id="b4575-142">[导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="b4575-142">[Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md) </span></span>  
 [<span data-ttu-id="b4575-143">ImportBindings 命令</span><span class="sxs-lookup"><span data-stu-id="b4575-143">ImportBindings Command</span></span>](../core/importbindings-command.md)