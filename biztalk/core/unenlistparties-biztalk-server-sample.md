---
title: UnenlistParties （BizTalk Server 示例） |Microsoft 文档
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
- parties, unenlisting
- examples, administering
- administering, examples
ms.assetid: a751a0fc-ca94-4610-a8aa-db3a24159334
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34cbb94dff7211a157fc492c1157fa379236641e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973467"
---
# <a name="unenlistparties-biztalk-server-sample"></a><span data-ttu-id="51a3f-102">UnenlistParties （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="51a3f-102">UnenlistParties (BizTalk Server Sample)</span></span>
<span data-ttu-id="51a3f-103">UnenlistParties 示例演示如何取消登记与部署的 BizTalk Server 程序集关联的所有参与方。</span><span class="sxs-lookup"><span data-stu-id="51a3f-103">The UnenlistParties sample demonstrates how to unenlist all of the parties associated with a deployed BizTalk Server assembly.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="51a3f-104">部署后，如果不再需要部署脚本，则应将其删除。</span><span class="sxs-lookup"><span data-stu-id="51a3f-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="51a3f-105">应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="51a3f-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="51a3f-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="51a3f-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="51a3f-107">您必须具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理权限才能使用此示例中的管理对象。</span><span class="sxs-lookup"><span data-stu-id="51a3f-107">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  
  
-   <span data-ttu-id="51a3f-108">Windows PowerShell 脚本需要 Windows PowerShell 执行策略以允许脚本执行。</span><span class="sxs-lookup"><span data-stu-id="51a3f-108">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="51a3f-109">有关详细信息请参阅：[检查执行策略](http://go.microsoft.com/fwlink/?LinkId=128930)。</span><span class="sxs-lookup"><span data-stu-id="51a3f-109">For more information see: [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="51a3f-110">本示例旨在如何以及为何</span><span class="sxs-lookup"><span data-stu-id="51a3f-110">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="51a3f-111">本示例以 Visual C# 编写，使用 BizTalk 浏览器对象模型中的对象执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="51a3f-111">This sample, written in Visual C# using objects from the BizTalk Explorer object model, performs the following operations:</span></span>  
  
-   <span data-ttu-id="51a3f-112">查询特定程序集。</span><span class="sxs-lookup"><span data-stu-id="51a3f-112">Query for a particular assembly.</span></span>  
  
-   <span data-ttu-id="51a3f-113">检索所有与该程序集关联的角色。</span><span class="sxs-lookup"><span data-stu-id="51a3f-113">Retrieve all of the roles associated with that assembly.</span></span>  
  
-   <span data-ttu-id="51a3f-114">取消登记所有与每个此类角色关联的参与方。</span><span class="sxs-lookup"><span data-stu-id="51a3f-114">Unenlist all of the parties associated with each such role.</span></span>  
  
-   <span data-ttu-id="51a3f-115">处理所有错误，以便向用户返回有意义的信息。</span><span class="sxs-lookup"><span data-stu-id="51a3f-115">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="51a3f-116">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="51a3f-116">Where to Find This Sample</span></span>  
 <span data-ttu-id="51a3f-117">本示例位于以下 SDK 位置中：</span><span class="sxs-lookup"><span data-stu-id="51a3f-117">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="51a3f-118">\<*示例路径*\>\Admin\ExplorerOM\UnenlistParties\\</span><span class="sxs-lookup"><span data-stu-id="51a3f-118">\<*Samples Path*\>\Admin\ExplorerOM\UnenlistParties\\</span></span>  
  
 <span data-ttu-id="51a3f-119">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="51a3f-119">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="51a3f-120">文件</span><span class="sxs-lookup"><span data-stu-id="51a3f-120">File(s)</span></span>|<span data-ttu-id="51a3f-121">Description</span><span class="sxs-lookup"><span data-stu-id="51a3f-121">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="51a3f-122">App.ico、AssemblyInfo.cs、UnenlistParties.csproj、UnenlistParties.sln、UnenlistParties.cs</span><span class="sxs-lookup"><span data-stu-id="51a3f-122">App.ico, AssemblyInfo.cs, UnenlistParties.csproj, UnenlistParties.sln, UnenlistParties.cs</span></span>|<span data-ttu-id="51a3f-123">用于生成取消登记特定程序集的所有参与方的 Visual C# 命令行应用程序的项目、解决方案和源文件。</span><span class="sxs-lookup"><span data-stu-id="51a3f-123">Project, solution, and source files for building a Visual C# command-line application that unenlists all of the parties for a particular assembly.</span></span>|  
  
### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="51a3f-124">构建和初始化此示例</span><span class="sxs-lookup"><span data-stu-id="51a3f-124">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="51a3f-125">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开解决方案文件 UnenlistParties.sln。</span><span class="sxs-lookup"><span data-stu-id="51a3f-125">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file UnenlistParties.sln.</span></span>  
  
2.  <span data-ttu-id="51a3f-126">在**生成**菜单上，选择**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="51a3f-126">In the **Build** menu, select **Build Solution**.</span></span>  
  
### <a name="to-run-this-sample"></a><span data-ttu-id="51a3f-127">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="51a3f-127">To run this sample</span></span>  
  
1.  <span data-ttu-id="51a3f-128">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="51a3f-128">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="51a3f-129">\<*示例路径*\>\Admin\ExplorerOM\UnenlistParties\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="51a3f-129">\<*Samples Path*\>\Admin\ExplorerOM\UnenlistParties\bin\Debug\\</span></span>  
  
2.  <span data-ttu-id="51a3f-130">运行 UnenlistParties.exe 文件，并传递下面两个命令行参数之一：</span><span class="sxs-lookup"><span data-stu-id="51a3f-130">Run the file UnenlistParties.exe, passing one of the two following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="51a3f-131">**\<** ***AssemblyName* \>** 。</span><span class="sxs-lookup"><span data-stu-id="51a3f-131">**\<** ***AssemblyName* \>**.</span></span> <span data-ttu-id="51a3f-132">将取消登记的所有参与方所在的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="51a3f-132">The name of an assembly from which all associated parties are to be unenlisted.</span></span> <span data-ttu-id="51a3f-133">如果程序集名称包含空格，则将该名称置于引号中。</span><span class="sxs-lookup"><span data-stu-id="51a3f-133">If the assembly name contains spaces, enclose the name in quotes.</span></span>  
  
    -   <span data-ttu-id="51a3f-134">**/?.**</span><span class="sxs-lookup"><span data-stu-id="51a3f-134">**/?.**</span></span> <span data-ttu-id="51a3f-135">显示帮助。</span><span class="sxs-lookup"><span data-stu-id="51a3f-135">Displays help.</span></span>  
  
     <span data-ttu-id="51a3f-136">例如：</span><span class="sxs-lookup"><span data-stu-id="51a3f-136">For example:</span></span>  
  
    ```  
    UnenlistParties "My BizTalk Assembly.dll"  
    ```  
  
     <span data-ttu-id="51a3f-137">-或者-</span><span class="sxs-lookup"><span data-stu-id="51a3f-137">-OR-</span></span>  
  
    ```  
    UnenlistParties /?  
    ```  
  
## <a name="windows-powershell-script-example"></a><span data-ttu-id="51a3f-138">Windows Powershell 脚本示例</span><span class="sxs-lookup"><span data-stu-id="51a3f-138">Windows Powershell Script Example</span></span>  
 <span data-ttu-id="51a3f-139">以下 Windows Powershell 脚本片段可以用于演示的相同功能**ExplorerOM**类：</span><span class="sxs-lookup"><span data-stu-id="51a3f-139">The following Windows Powershell script fragment can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  
  
```  
#===================#  
#=== Main Script ===#  
#===================#  
  
#=== Make sure the ExplorerOM assembly is loaded ===#  
  
[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  
  
#=== Connect to the BizTalk Management database ===#  
  
$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  
  
#=====================================================#  
#=== If no assembly name is specified, just list   ===#  
#=== the assemblies, roles and partyies enlisted.  ===#  
#=====================================================#  
  
if ($args[0] -eq $null)  
{  
  Write-Host `r`n===========================================================  
  Write-Host No assembly name provided for party unenlist operation.  
  Write-Host Listing Parties for each assembly on local BizTalk Server:  
  Write-Host ===========================================================`r`n  
  
  foreach ($assembly in $Catalog.Assemblies)  
  {  
    write-host $Assembly.Name`r`n  
  
    foreach ($role in $Assembly.Roles)  
    {  
      write-host `t($role.name)  
  
      foreach($party in $role.EnlistedParties)  
      {  
        Write-Host `t`t($party.Party.Name)  
      }  
      write-host  
    }  
  }  
  
  write-host  
}  
  
#=====================================================#  
#=== If assembly name is specified, remove parties ===#  
#=== enlisted in all roles for the assembly.       ===#  
#=====================================================#  
  
else  
{  
  $Assembly = $Catalog.Assemblies[$args[0]]  
  
  if ($assembly -eq $null)  
  {  
    write-host Assembly named $args[0] not found.`r`n  
  }   
  
  else  
  {  
    write-host `r`nUnenlisting parties from all roles in ($Assembly.Name)`r`n  
  
    foreach ($role in $Assembly.Roles)  
    {  
  
      $count = $role.EnlistedParties.count  
  
      for($c=0; $c -lt $count; $c++)  
      {  
        #==========================================================#  
        #=== Array index stays at zero because the collection   ===#  
        #=== changes after each item is removed.                ===#  
        #==========================================================#  
  
        $party = $role.EnlistedParties[0]  
  
        Write-Host Unenlisting ($party.Party.Name) from ($role.Name)...  
        $role.RemoveEnlistedParty($party)  
        Write-Host done.`r`n  
      }  
    }  
  
    write-Host Comitting changes...  
    $catalog.SaveChanges()  
    Write-Host done.`r`n  
  }  
}  
  
```  
  
 <span data-ttu-id="51a3f-140">以下脚本输出是通过从属于 PartyResolution 示例的供应商程序集中注销参与方生成的。</span><span class="sxs-lookup"><span data-stu-id="51a3f-140">The following script output was generated from unenlisting parties from the Supplier assembly which is part of the PartyResolution sample.</span></span> <span data-ttu-id="51a3f-141">PartyResolution 示例位于\<*示例路径*\>\Admin\Orchestrations\PartyResolution 目录。</span><span class="sxs-lookup"><span data-stu-id="51a3f-141">The PartyResolution sample is located in the \<*Samples Path*\>\Admin\Orchestrations\PartyResolution directory.</span></span>  
  
```  
PS C:\> .\UnenlistParties.ps1 Supplier  
  
Unenlisting parties from all roles in Supplier  
  
Unenlisting ShipmentAgency1 from ShipmentRole ...  
done.  
  
Unenlisting ShipmentAgency2 from ShipmentRole ...  
done.  
  
Unenlisting BuyerAgency from Buyer ...  
done.  
  
Comitting changes...  
done.  
```  
  
## <a name="see-also"></a><span data-ttu-id="51a3f-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51a3f-142">See Also</span></span>  
 [<span data-ttu-id="51a3f-143">Admin-ExplorerOM（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="51a3f-143">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)