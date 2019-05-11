---
title: DeleteParty （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, parties
- parties, examples
- deleting, parties
- examples, administering
- parties, deleting
- administering, examples
ms.assetid: 8161af7d-76ef-4df5-81c8-f0f5c81df9a8
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f188fb4b77babeb6e64260bc37004a6b15b7d28
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352190"
---
# <a name="deleteparty-biztalk-server-sample"></a><span data-ttu-id="bf179-102">DeleteParty （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="bf179-102">DeleteParty (BizTalk Server Sample)</span></span>
<span data-ttu-id="bf179-103">DeleteParty 示例演示如何删除指定参与方。</span><span class="sxs-lookup"><span data-stu-id="bf179-103">The DeleteParty sample demonstrates how to delete a specified party.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="bf179-104">如果不需要应在部署后删除的部署脚本。</span><span class="sxs-lookup"><span data-stu-id="bf179-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="bf179-105">管理脚本和其他必须保持的脚本应受 ACL 并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="bf179-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf179-106">删除参与方之前，必须首先创建一个。</span><span class="sxs-lookup"><span data-stu-id="bf179-106">Before you can delete a party, you must first create one.</span></span> <span data-ttu-id="bf179-107">执行操作的一种方法是运行[PartyResolution （BizTalk Server 示例）](../core/partyresolution-biztalk-server-sample.md)示例。</span><span class="sxs-lookup"><span data-stu-id="bf179-107">One way to do this is to run the [PartyResolution (BizTalk Server Sample)](../core/partyresolution-biztalk-server-sample.md) sample.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bf179-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="bf179-108">Prerequisites</span></span>  
  
- <span data-ttu-id="bf179-109">您必须具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理权限才能使用此示例中的管理对象。</span><span class="sxs-lookup"><span data-stu-id="bf179-109">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  
  
- <span data-ttu-id="bf179-110">Windows PowerShell 脚本需要 Windows PowerShell 执行策略以允许脚本执行。</span><span class="sxs-lookup"><span data-stu-id="bf179-110">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="bf179-111">有关详细信息，请参阅：[检查执行策略](http://go.microsoft.com/fwlink/?LinkId=128930)。</span><span class="sxs-lookup"><span data-stu-id="bf179-111">For more information see: [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="bf179-112">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="bf179-112">What This Sample Does</span></span>  
 <span data-ttu-id="bf179-113">此示例中，Microsoft 视觉对象中写入C#，使用 BizTalk 浏览器对象模型 (ExplorerOM) 中的对象，将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bf179-113">This sample, written in Microsoft Visual C#, using objects from the BizTalk Explorer object model (ExplorerOM), performs the following operations:</span></span>  
  
-   <span data-ttu-id="bf179-114">指定参与方的查询。</span><span class="sxs-lookup"><span data-stu-id="bf179-114">Query for a specified party.</span></span>  
  
-   <span data-ttu-id="bf179-115">删除该参与方。</span><span class="sxs-lookup"><span data-stu-id="bf179-115">Delete that party.</span></span>  
  
-   <span data-ttu-id="bf179-116">处理任何错误，以便向用户返回有意义的信息。</span><span class="sxs-lookup"><span data-stu-id="bf179-116">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="bf179-117">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="bf179-117">Where to Find This Sample</span></span>  
 <span data-ttu-id="bf179-118">此示例将位于以下 SDK 位置：</span><span class="sxs-lookup"><span data-stu-id="bf179-118">This sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="bf179-119">\<*Samples Path*\>\Admin\ExplorerOM\DeleteParty\\</span><span class="sxs-lookup"><span data-stu-id="bf179-119">\<*Samples Path*\>\Admin\ExplorerOM\DeleteParty\\</span></span>  
  
 <span data-ttu-id="bf179-120">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="bf179-120">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="bf179-121">文件</span><span class="sxs-lookup"><span data-stu-id="bf179-121">File(s)</span></span>|<span data-ttu-id="bf179-122">Description</span><span class="sxs-lookup"><span data-stu-id="bf179-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bf179-123">App.ico、 AssemblyInfo.cs、 DeleteParty.csproj、 DeleteParty.sln 和 DeleteParty.cs</span><span class="sxs-lookup"><span data-stu-id="bf179-123">App.ico, AssemblyInfo.cs, DeleteParty.csproj, DeleteParty.sln, DeleteParty.cs</span></span>|<span data-ttu-id="bf179-124">项目、 解决方案和源代码文件生成视觉对象C#命令行中删除指定参与方的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bf179-124">Project, solution, and source files for building a Visual C# command-line application that removes a specified party.</span></span>|  
  
### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="bf179-125">若要生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="bf179-125">To build and initialize this sample</span></span>  
  
1. <span data-ttu-id="bf179-126">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开 DeleteParty.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="bf179-126">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file DeleteParty.sln.</span></span>  
  
2. <span data-ttu-id="bf179-127">在“生成”  菜单上，单击“生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="bf179-127">On the **Build** menu, click **Build Solution**.</span></span>  
  
### <a name="to-run-this-sample"></a><span data-ttu-id="bf179-128">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="bf179-128">To run this sample</span></span>  
  
1. <span data-ttu-id="bf179-129">在命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="bf179-129">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="bf179-130">\<*Samples Path*\>\Admin\ExplorerOM\DeleteParty\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="bf179-130">\<*Samples Path*\>\Admin\ExplorerOM\DeleteParty\bin\Debug\\</span></span>  
  
2. <span data-ttu-id="bf179-131">运行 DeleteParty.exe，传递两个以下的命令行参数之一的文件：</span><span class="sxs-lookup"><span data-stu-id="bf179-131">Run the file DeleteParty.exe, passing one of the two following command-line arguments:</span></span>  
  
   - <span data-ttu-id="bf179-132">**\<** ***PartyName* \>.**</span><span class="sxs-lookup"><span data-stu-id="bf179-132">**\<** ***PartyName* \>.**</span></span> <span data-ttu-id="bf179-133">要删除的参与方的名称。</span><span class="sxs-lookup"><span data-stu-id="bf179-133">The name of a party to be deleted.</span></span> <span data-ttu-id="bf179-134">如果参与方名称包含空格，将名称括起来。</span><span class="sxs-lookup"><span data-stu-id="bf179-134">If the party name contains spaces, enclose the name in quotes.</span></span>  
  
   - <span data-ttu-id="bf179-135">**/?.**</span><span class="sxs-lookup"><span data-stu-id="bf179-135">**/?.**</span></span> <span data-ttu-id="bf179-136">显示帮助。</span><span class="sxs-lookup"><span data-stu-id="bf179-136">Displays help.</span></span>  
  
     <span data-ttu-id="bf179-137">例如：</span><span class="sxs-lookup"><span data-stu-id="bf179-137">For example:</span></span>  
  
   ```  
   DeleteParty "My Party #3"  
   ```  
  
    <span data-ttu-id="bf179-138">-或-</span><span class="sxs-lookup"><span data-stu-id="bf179-138">-OR-</span></span>  
  
   ```  
   DeleteParty /?  
   ```  
  
## <a name="windows-powershell-script-example"></a><span data-ttu-id="bf179-139">Windows Powershell 脚本示例</span><span class="sxs-lookup"><span data-stu-id="bf179-139">Windows Powershell Script example</span></span>  
 <span data-ttu-id="bf179-140">以下 Windows PowerShell 脚本片段可用于演示的相同功能**ExplorerOM**类：</span><span class="sxs-lookup"><span data-stu-id="bf179-140">The following Windows PowerShell script fragment can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  
  
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
  
 <span data-ttu-id="bf179-141">脚本示例需要一个单个参与方名称作为命令行参数进行传递。</span><span class="sxs-lookup"><span data-stu-id="bf179-141">The script example expects a single party name to be passed as a command line argument.</span></span>  <span data-ttu-id="bf179-142">它按名称查找该参与方，并尝试将其删除。</span><span class="sxs-lookup"><span data-stu-id="bf179-142">It looks for that party by name and attempts to delete it.</span></span>  <span data-ttu-id="bf179-143">如果没有命令行参数传递给它，该脚本会列出本地 Biztalk 服务器上的所有参与方。</span><span class="sxs-lookup"><span data-stu-id="bf179-143">The script will list all parties on the local Biztalk server if no commandline argument is passed to it.</span></span> <span data-ttu-id="bf179-144">下面是脚本的示例输出：</span><span class="sxs-lookup"><span data-stu-id="bf179-144">Here is example output from the script:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bf179-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf179-145">See Also</span></span>  
 [<span data-ttu-id="bf179-146">Admin-ExplorerOM（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="bf179-146">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)