---
title: "如何将绑定导入到 BizTalk 组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- groups, importing
- importing, bindings
- groups, bindings
- bindings, groups
ms.assetid: 38da14fb-3522-4274-a633-2ff24e4bd574
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a64bac6c64a9aadc772bfe8445b23f87b469471d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-import-bindings-into-a-biztalk-group"></a><span data-ttu-id="5d9cc-102">如何将绑定导入到 BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="5d9cc-102">How to Import Bindings into a BizTalk Group</span></span>
<span data-ttu-id="5d9cc-103">本主题介绍如何使用 BizTalk Server 管理控制台或命令行通过 .xml 文件向 BizTalk 组导入绑定。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-103">This topic describes how to use the BizTalk Server Administration console or the command line to import bindings into a BizTalk group from an .xml file.</span></span> <span data-ttu-id="5d9cc-104">有关将绑定从 BizTalk 组导出到.xml 文件，你可以导入的说明，请参阅[如何导出绑定 BizTalk 组](../core/how-to-export-bindings-for-a-biztalk-group.md)。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-104">For instructions on exporting the bindings from a BizTalk group into an .xml file that you can import, see [How to Export Bindings for a BizTalk Group](../core/how-to-export-bindings-for-a-biztalk-group.md).</span></span>  
  
 <span data-ttu-id="5d9cc-105">你还可以导入绑定到 BizTalk 应用程序，如中所述[如何导入到 BizTalk 应用程序的绑定](../core/how-to-import-bindings-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-105">You can also import bindings into a BizTalk application, as described in [How to Import Bindings into a BizTalk Application](../core/how-to-import-bindings-into-a-biztalk-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5d9cc-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="5d9cc-106">Prerequisites</span></span>  
 <span data-ttu-id="5d9cc-107">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-107">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="5d9cc-108">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-import-bindings-into-a-biztalk-group"></a><span data-ttu-id="5d9cc-109">将绑定导入到 BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="5d9cc-109">To import bindings into a BizTalk group</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="5d9cc-110">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="5d9cc-110">Using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="5d9cc-111">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="5d9cc-112">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，然后右键单击**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-112">In the console tree, expand  **BizTalk Server Administration**, expand the BizTalk group, and then right-click **Applications**.</span></span>  
  
3.  <span data-ttu-id="5d9cc-113">指向**导入**，然后单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-113">Point to **Import**, and then click **Bindings**.</span></span>  
  
4.  <span data-ttu-id="5d9cc-114">单击绑定文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-114">Click the binding file and click **Open**.</span></span>  
  
     <span data-ttu-id="5d9cc-115">绑定文件中的项目将写入该组。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-115">The artifacts in the binding file are written to the group.</span></span> <span data-ttu-id="5d9cc-116">它们的相应文件夹中显示\<所有项目\>节点。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-116">They display in appropriate folders of the \<All Artifacts\> node.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="5d9cc-117">使用命令行</span><span class="sxs-lookup"><span data-stu-id="5d9cc-117">Using the command line</span></span>  
  
1.  <span data-ttu-id="5d9cc-118">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-118">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="5d9cc-119">键入以下命令，替换为适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="5d9cc-119">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
     <span data-ttu-id="5d9cc-120">**BTSTask ImportBindings /Source:** *值* **/GroupLevel** [**/Server:***值*] [**/数据库：***值*]</span><span class="sxs-lookup"><span data-stu-id="5d9cc-120">**BTSTask ImportBindings /Source:** *value* **/GroupLevel** [**/Server:***value*] [**/Database:***value*]</span></span>  
  
     <span data-ttu-id="5d9cc-121">例如，以下命令将绑定导入到 BizTalk 管理数据库中所定义的组，该 BizTalk 管理数据库运行在名为 MyServer 的 SQL Server 实例上。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-121">For example, the following command imports bindings into the group defined in the BizTalk Management database running on a SQL Server instance named MyServer.</span></span>  
  
     <span data-ttu-id="5d9cc-122">**BTSTask ImportBindings GroupLevel /Server:MyServer /Database:BiztalkMgmtDb /Source:C:\Bindings\Binding1.xml**</span><span class="sxs-lookup"><span data-stu-id="5d9cc-122">**BTSTask ImportBindings /GroupLevel /Server:MyServer /Database:BiztalkMgmtDb /Source:C:\Bindings\Binding1.xml**</span></span>  
  
    |<span data-ttu-id="5d9cc-123">参数</span><span class="sxs-lookup"><span data-stu-id="5d9cc-123">Parameter</span></span>|<span data-ttu-id="5d9cc-124">值</span><span class="sxs-lookup"><span data-stu-id="5d9cc-124">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="5d9cc-125">**/ 源**</span><span class="sxs-lookup"><span data-stu-id="5d9cc-125">**/Source**</span></span>|<span data-ttu-id="5d9cc-126">要导入的绑定文件的完整路径，包含文件名。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-126">Full path of the binding file to import, including the file name.</span></span> <span data-ttu-id="5d9cc-127">包含空格的路径必须放在引号 (") 中。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-127">Paths that include spaces must be enclosed in quotation marks (").</span></span>|  
    |<span data-ttu-id="5d9cc-128">**/ GroupLevel**</span><span class="sxs-lookup"><span data-stu-id="5d9cc-128">**/GroupLevel**</span></span>|<span data-ttu-id="5d9cc-129">将绑定文件导入到当前组的选项。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-129">Option to import the binding file into the current group.</span></span>|  
    |<span data-ttu-id="5d9cc-130">**/ 服务器**</span><span class="sxs-lookup"><span data-stu-id="5d9cc-130">**/Server**</span></span>|<span data-ttu-id="5d9cc-131">BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-131">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="5d9cc-132">只在实例名称与服务器名称不相同时才需要指定实例名称。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-132">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="5d9cc-133">只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-133">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="5d9cc-134">示例：</span><span class="sxs-lookup"><span data-stu-id="5d9cc-134">Examples:</span></span><br /><br /> <span data-ttu-id="5d9cc-135">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="5d9cc-135">Server=MyServer</span></span><br /><br /> <span data-ttu-id="5d9cc-136">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="5d9cc-136">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="5d9cc-137">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-137">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
    |<span data-ttu-id="5d9cc-138">**/ 数据库**</span><span class="sxs-lookup"><span data-stu-id="5d9cc-138">**/Database**</span></span>|<span data-ttu-id="5d9cc-139">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-139">Name of the BizTalk Management database.</span></span> <span data-ttu-id="5d9cc-140">如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="5d9cc-140">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5d9cc-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d9cc-141">See Also</span></span>  
 <span data-ttu-id="5d9cc-142">[导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="5d9cc-142">[Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md) </span></span>  
 [<span data-ttu-id="5d9cc-143">ImportBindings 命令</span><span class="sxs-lookup"><span data-stu-id="5d9cc-143">ImportBindings Command</span></span>](../core/importbindings-command.md)