---
title: UnenlistParties （BizTalk Server 示例） |Microsoft Docs
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
ms.openlocfilehash: c7525e97ba93ebd35d2439044b8c1be55a70be3d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973022"
---
# <a name="unenlistparties-biztalk-server-sample"></a>UnenlistParties （BizTalk Server 示例）
UnenlistParties 示例演示如何取消登记与部署的 BizTalk Server 程序集关联的所有参与方。  
  
> [!WARNING]
>  部署后，如果不再需要部署脚本，则应将其删除。 应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。  
  
## <a name="prerequisites"></a>必要條件  
  
- 您必须具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理权限才能使用此示例中的管理对象。  
  
- Windows PowerShell 脚本需要 Windows PowerShell 执行策略以允许脚本执行。 有关详细信息请参阅：[检查执行策略](http://go.microsoft.com/fwlink/?LinkId=128930)。  
  
## <a name="how-this-sample-is-designed-and-why"></a>此示例设计方式和原因  
 本示例以 Visual C# 编写，使用 BizTalk 浏览器对象模型中的对象执行下列操作：  
  
-   查询特定程序集。  
  
-   检索所有与该程序集关联的角色。  
  
-   取消登记所有与每个此类角色关联的参与方。  
  
-   处理所有错误，以便向用户返回有意义的信息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 本示例位于以下 SDK 位置中：  
  
 \<*示例路径*\>\Admin\ExplorerOM\UnenlistParties\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|App.ico、AssemblyInfo.cs、UnenlistParties.csproj、UnenlistParties.sln、UnenlistParties.cs|用于生成取消登记特定程序集的所有参与方的 Visual C# 命令行应用程序的项目、解决方案和源文件。|  
  
### <a name="to-build-and-initialize-this-sample"></a>构建和初始化此示例  
  
1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开 UnenlistParties.sln 解决方案文件。  
  
2. 在中**构建**菜单中，选择**生成解决方案**。  
  
### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1. 在命令窗口中，导航到下面的文件夹：  
  
    \<*示例路径*\>\Admin\ExplorerOM\UnenlistParties\bin\Debug\  
  
2. 运行 UnenlistParties.exe 文件，并传递下面两个命令行参数之一：  
  
   - **\<** ***程序集名称* \>** 。 将取消登记的所有参与方所在的程序集的名称。 如果程序集名称包含空格，则将该名称置于引号中。  
  
   - **/?.** 显示帮助。  
  
     例如：  
  
   ```  
   UnenlistParties "My BizTalk Assembly.dll"  
   ```  
  
    -或-  
  
   ```  
   UnenlistParties /?  
   ```  
  
## <a name="windows-powershell-script-example"></a>Windows Powershell 脚本示例  
 以下 Windows Powershell 脚本片段可用于演示的相同功能**ExplorerOM**类：  
  
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
  
 以下脚本输出是通过从属于 PartyResolution 示例的供应商程序集中注销参与方生成的。 PartyResolution 示例位于\<*示例路径*\>\Admin\Orchestrations\PartyResolution 目录。  
  
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
  
## <a name="see-also"></a>请参阅  
 [Admin-ExplorerOM（BizTalk Server 示例文件夹）](../core/admin-explorerom-biztalk-server-samples-folder.md)