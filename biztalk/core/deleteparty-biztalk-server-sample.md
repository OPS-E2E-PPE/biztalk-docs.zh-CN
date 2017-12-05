---
title: "DeleteParty （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, parties
- parties, examples
- deleting, parties
- examples, administering
- parties, deleting
- administering, examples
ms.assetid: 8161af7d-76ef-4df5-81c8-f0f5c81df9a8
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68016285a53a2655c56810028925a91c1f8d66b0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="deleteparty-biztalk-server-sample"></a><span data-ttu-id="64266-102">DeleteParty （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="64266-102">DeleteParty (BizTalk Server Sample)</span></span>
<span data-ttu-id="64266-103">DeleteParty 示例演示如何删除指定参与方。</span><span class="sxs-lookup"><span data-stu-id="64266-103">The DeleteParty sample demonstrates how to delete a specified party.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="64266-104">部署后，如果不再需要部署脚本，则应将其删除。</span><span class="sxs-lookup"><span data-stu-id="64266-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="64266-105">应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="64266-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64266-106">在删除参与方之前，必须先创建一个参与方。</span><span class="sxs-lookup"><span data-stu-id="64266-106">Before you can delete a party, you must first create one.</span></span> <span data-ttu-id="64266-107">一种办法是运行[PartyResolution （BizTalk Server 示例）](../core/partyresolution-biztalk-server-sample.md)示例。</span><span class="sxs-lookup"><span data-stu-id="64266-107">One way to do this is to run the [PartyResolution (BizTalk Server Sample)](../core/partyresolution-biztalk-server-sample.md) sample.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="64266-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="64266-108">Prerequisites</span></span>  
  
-   <span data-ttu-id="64266-109">您必须具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理权限才能使用此示例中的管理对象。</span><span class="sxs-lookup"><span data-stu-id="64266-109">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  
  
-   <span data-ttu-id="64266-110">Windows PowerShell 脚本需要 Windows PowerShell 执行策略以允许脚本执行。</span><span class="sxs-lookup"><span data-stu-id="64266-110">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="64266-111">有关详细信息请参阅：[检查执行策略](http://go.microsoft.com/fwlink/?LinkId=128930)。</span><span class="sxs-lookup"><span data-stu-id="64266-111">For more information see: [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="64266-112">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="64266-112">What This Sample Does</span></span>  
 <span data-ttu-id="64266-113">本示例以 Microsoft Visual C# 编写，该示例使用 BizTalk 浏览器对象模型 (ExplorerOM) 中的对象执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="64266-113">This sample, written in Microsoft Visual C#, using objects from the BizTalk Explorer object model (ExplorerOM), performs the following operations:</span></span>  
  
-   <span data-ttu-id="64266-114">查询指定参与方。</span><span class="sxs-lookup"><span data-stu-id="64266-114">Query for a specified party.</span></span>  
  
-   <span data-ttu-id="64266-115">删除此参与方。</span><span class="sxs-lookup"><span data-stu-id="64266-115">Delete that party.</span></span>  
  
-   <span data-ttu-id="64266-116">处理所有错误，以便向用户返回有意义的信息。</span><span class="sxs-lookup"><span data-stu-id="64266-116">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="64266-117">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="64266-117">Where to Find This Sample</span></span>  
 <span data-ttu-id="64266-118">此示例位于以下 SDK 的位置：</span><span class="sxs-lookup"><span data-stu-id="64266-118">This sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="64266-119">\<*示例路径*\>\Admin\ExplorerOM\DeleteParty\\</span><span class="sxs-lookup"><span data-stu-id="64266-119">\<*Samples Path*\>\Admin\ExplorerOM\DeleteParty\\</span></span>  
  
 <span data-ttu-id="64266-120">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="64266-120">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="64266-121">文件</span><span class="sxs-lookup"><span data-stu-id="64266-121">File(s)</span></span>|<span data-ttu-id="64266-122">Description</span><span class="sxs-lookup"><span data-stu-id="64266-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="64266-123">App.ico、AssemblyInfo.cs、DeleteParty.csproj、DeleteParty.sln 和 DeleteParty.cs</span><span class="sxs-lookup"><span data-stu-id="64266-123">App.ico, AssemblyInfo.cs, DeleteParty.csproj, DeleteParty.sln, DeleteParty.cs</span></span>|<span data-ttu-id="64266-124">用于生成删除指定参与方的 Visual C# 命令行应用程序的项目、解决方案和源文件。</span><span class="sxs-lookup"><span data-stu-id="64266-124">Project, solution, and source files for building a Visual C# command-line application that removes a specified party.</span></span>|  
  
### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="64266-125">构建和初始化此示例</span><span class="sxs-lookup"><span data-stu-id="64266-125">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="64266-126">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开解决方案文件 DeleteParty.sln。</span><span class="sxs-lookup"><span data-stu-id="64266-126">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file DeleteParty.sln.</span></span>  
  
2.  <span data-ttu-id="64266-127">在“生成”  菜单上，单击“生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="64266-127">On the **Build** menu, click **Build Solution**.</span></span>  
  
### <a name="to-run-this-sample"></a><span data-ttu-id="64266-128">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="64266-128">To run this sample</span></span>  
  
1.  <span data-ttu-id="64266-129">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="64266-129">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="64266-130">\<*示例路径*\>\Admin\ExplorerOM\DeleteParty\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="64266-130">\<*Samples Path*\>\Admin\ExplorerOM\DeleteParty\bin\Debug\\</span></span>  
  
2.  <span data-ttu-id="64266-131">运行 DeleteParty.exe 文件，并传递下面两个命令行参数之一：</span><span class="sxs-lookup"><span data-stu-id="64266-131">Run the file DeleteParty.exe, passing one of the two following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="64266-132">**\<** ***PartyName* \>。**</span><span class="sxs-lookup"><span data-stu-id="64266-132">**\<** ***PartyName* \>.**</span></span> <span data-ttu-id="64266-133">要删除的参与方的名称。</span><span class="sxs-lookup"><span data-stu-id="64266-133">The name of a party to be deleted.</span></span> <span data-ttu-id="64266-134">如果参与方名称包含空格，则将该名称置于引号中。</span><span class="sxs-lookup"><span data-stu-id="64266-134">If the party name contains spaces, enclose the name in quotes.</span></span>  
  
    -   <span data-ttu-id="64266-135">**/?.**</span><span class="sxs-lookup"><span data-stu-id="64266-135">**/?.**</span></span> <span data-ttu-id="64266-136">显示帮助。</span><span class="sxs-lookup"><span data-stu-id="64266-136">Displays help.</span></span>  
  
     <span data-ttu-id="64266-137">例如：</span><span class="sxs-lookup"><span data-stu-id="64266-137">For example:</span></span>  
  
    ```  
    DeleteParty "My Party #3"  
    ```  
  
     <span data-ttu-id="64266-138">-或者-</span><span class="sxs-lookup"><span data-stu-id="64266-138">-OR-</span></span>  
  
    ```  
    DeleteParty /?  
    ```  
  
## <a name="windows-powershell-script-example"></a><span data-ttu-id="64266-139">Windows Powershell 脚本示例</span><span class="sxs-lookup"><span data-stu-id="64266-139">Windows Powershell Script example</span></span>  
 <span data-ttu-id="64266-140">以下 Windows PowerShell 脚本片段可以用于演示的相同功能**ExplorerOM**类：</span><span class="sxs-lookup"><span data-stu-id="64266-140">The following Windows PowerShell script fragment can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  
  
```  
  
#===================#  
#=== Main Script ===#  
#===================#  
  
#=== Make sure the ExplorerOM assembly is loaded ===#  
  
[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  
  
#=== Connect to the BizTalk Management database ===#  
  
$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  
  
#=======================================#  
#=== If no party name is specified   ===#  
#=== just list the parties.          ===#  
#=======================================#  
  
if ($args[0] -eq $null)  
{  
  Write-Host `r`nNo party name provided for delete operation.`r`n`r`nListing Parties on local Biztalk Server:  
  
  $Catalog.Parties | Format-List Name  
}  
  
#==========================================#  
#=== Delete the specified party by name ===#  
#==========================================#  
  
else  
{  
  $party = $Catalog.Parties[$args[0]]  
  Write-Host `r`nRemoving Party named `"($args[0])`"`r`n  
  $catalog.RemoveParty($party)  
  $catalog.SaveChanges()  
}  
```  
  
 <span data-ttu-id="64266-141">该脚本示例希望将单个参与方名称作为命令行参数来传递。</span><span class="sxs-lookup"><span data-stu-id="64266-141">The script example expects a single party name to be passed as a command line argument.</span></span>  <span data-ttu-id="64266-142">它通过名称来查找该参与方，并尝试将其删除。</span><span class="sxs-lookup"><span data-stu-id="64266-142">It looks for that party by name and attempts to delete it.</span></span>  <span data-ttu-id="64266-143">如果没有传递命令行参数给脚本，则该脚本会列出本地 Biztalk Server 上的所有参与方。</span><span class="sxs-lookup"><span data-stu-id="64266-143">The script will list all parties on the local Biztalk server if no commandline argument is passed to it.</span></span> <span data-ttu-id="64266-144">下面是该脚本的示例输出：</span><span class="sxs-lookup"><span data-stu-id="64266-144">Here is example output from the script:</span></span>  
  
```  
PS C:\> .\DeletePart.ps1  
  
No party name provided for delete operation.  
  
Listing Parties on local Biztalk Server:  
  
Name : Party1  
  
Name : Party3  
  
Name : Party2  
  
PS C:\> .\DeletePart.ps1 Party3  
  
Removing Party named " Party3 "  
  
PS C:\> .\DeletePart.ps1  
  
No party name provided for delete operation.  
  
Listing Parties on local Biztalk Server:  
  
Name : Party1  
  
Name : Party2  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="64266-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64266-145">See Also</span></span>  
 [<span data-ttu-id="64266-146">Admin-ExplorerOM（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="64266-146">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)