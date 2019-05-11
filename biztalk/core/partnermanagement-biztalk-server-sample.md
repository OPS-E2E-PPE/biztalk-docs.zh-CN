---
title: PartnerManagement （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83e2a84f-ab25-4a7c-b8d7-0ba2dfa93095
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30e9004b1e464b9decc60b78f2aba670f08e5a9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395041"
---
# <a name="partnermanagement-biztalk-server-sample"></a>PartnerManagement （BizTalk Server 示例）
PartnerManagement 示例演示了如何管理中的参与方[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过使用环境**ExplorerOM**管理对象。  

## <a name="prerequisites"></a>先决条件  

- 您必须具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理权限才能使用此示例中的管理对象。  

- Windows PowerShell 脚本需要 Windows PowerShell 执行策略以允许脚本执行。 有关详细信息，请参阅 [检查执行策略](http://go.microsoft.com/fwlink/?LinkId=128930)。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例演示如何使用中的管理类**Microsoft.BizTalk.ExplorerOM**命名空间来管理参与方。 参与方表示贸易合作伙伴或后端应用程序可与之交互的业务流程。 有关参与方的详细信息一般情况下，请参阅的文档[参与方](../core/parties.md)或[角色链接和服务链接角色](../core/role-links-and-service-link-roles.md)。 在 Microsoft 中编写示例[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)]。 本主题中还包含 Windows PowerShell 示例脚本。 此示例演示了以下操作：  

- 使用自定义或标准别名创建新的参与方和添加现有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到参与方发送端口。  

- 登记新参与方与 BizTalk server 上的现有角色链接。  

- 取消登记新参与方。  

- 正在删除新参与方。  

## <a name="where-to-find-this-sample"></a>本示例的所在位置  
 本示例位于以下 SDK 位置中：  

 \<*Samples Path*\>\Admin\ExplorerOM\PartnerManagement  

 下表显示了本示例中的文件及其用途说明：  


|                      文件                       |                                                 Description                                                  |
|----------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|                PartnerManagement.cs                | [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 此示例中演示的操作的源文件。 |
| PartnerManagement.sln 和 PartnerManagement.csproj |                                  示例的解决方案文件和项目文件。                                  |

## <a name="building-and-running-this-sample"></a>生成并运行本示例  
 在生成本示例之前，您需要进行四次代码修改自定义 BizTalk server 的示例。 这是必需的因为该示例使用的发送端口与参与方和登记的任意角色名称相关联的任意名称。 因此您需要提供有效的名称的示例。 为了演示此示例，本主题将介绍第一次生成 PartyResolution 示例从以下目录：\<*示例路径*\>\Orchestrations\PartyResolution。 这种方法用于确保有效的角色名称和发送端口名称均存在于 BizTalk server 才能演示示例过程。  

#### <a name="to-build-this-sample"></a>生成示例  

1. 首先请确保已生成并初始化，以便可以通过该示例使用有效的角色名称和发送端口名称 PartyResolution 示例。 这在标题中的"生成和初始化此示例"部分中所述[PartyResolution （BizTalk Server 示例）](../core/partyresolution-biztalk-server-sample.md)。  

2. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开解决方案文件 PartnerManagement.sln。  

3. 在解决方案资源管理器中打开源文件 PartnerManagement.cs。  

4. 向下滚动到名为的函数**CreateParty**并插入两个发送端口名称来自 PartyResolution 示例，或使用来自 BizTalk server 环境的有效名称。 下面的代码示例演示如何使用来自 PartyResolution 示例的发送端口的更改。  

   ```  
   // Replacing arbitrary send port names with PartyResolution send port names ===  

   //            myParty.SendPorts.Add(catalog.SendPorts["NormalDelivery"]);  
   //            myParty.SendPorts.Add(catalog.SendPorts["ExpressDelivery"]);  
               myParty.SendPorts.Add(catalog.SendPorts["SP_FilesToShipmentAgency1"]);  
               myParty.SendPorts.Add(catalog.SendPorts["SP_FilesToShipmentAgency2"]);  

   ```  

5. 向下滚动到名为的函数**EnlistParty**并更改 foreach 循环，使其搜索 Supplier 程序集，名为"ShipmentRole"的角色来登记时使用。 下面的代码示例演示如何使用来自 PartyResolution 示例的 ShipmentRole 的更改。  

   ```  
               // Search for the “Shipmentrole” instead of “shipperRole”  
               Role svcRole = null;  
   //===       foreach (Role role in catalog.Assemblies[0].Roles)  
               foreach (Role role in catalog.Assemblies["Supplier"].Roles)  
               {  
   //===          if (role.Name == "ShipperRole")  
                  if (role.Name == "ShipmentRole")  
                  {  
                     svcRole = role;  
                     break;  
                  }  
               }  

   ```  

6. 向下滚动到名为的函数**UnenlistParty**并更改 foreach 循环，以搜索 Supplier 程序集，查找 ShipmentRole。 下面的代码示例演示了此更改。  

   ```  
               // Search for the “ShipmentRole” instead of “shipperRole”  
               Role svcRole = null;  
   //===       foreach (Role role in catalog.Assemblies[0].Roles)  
               foreach (Role role in catalog.Assemblies["Supplier"].Roles)  
               {  
   //===          if (role.Name == "ShipperRole")  
                  if (role.Name == "ShipmentRole")  
                  {  
                     svcRole = role;  
                     break;  
                  }  
               }  

   ```  

7. 之后创建并登记新参与方使用 ShipmentRole，示例用于立即注销-此参与方并将其删除。 将以下代码更改添加到要暂停执行，可以查看为新参与方创建的登记的主要过程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

   ```  
   static void Main(string[] args)  
   {  
      CreateParty();     
      EnlistParty();     

      Console.WriteLine("\nNew Party created and enlisted.\n\nPress <Enter> to unenlist and delete.\n");  
      Console.ReadLine();  

      UnenlistParty();   
      DeleteParty();  
   }  

   ```  

8. 在“生成”  菜单上，单击“生成解决方案” 。  

#### <a name="to-run-this-sample"></a>运行本示例的步骤  

1. 打开命令窗口并导航到以下文件夹：  

    \<*Samples Path*\>\Admin\ExplorerOM\PartnerManagement\bin\Debug  

2. 运行文件 PartnerManagement.exe。  

3. 当示例显示创建并登记新参与方的消息时，请打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台和视图命名为新参与方**FedEx**下**方**节点。  

4. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，导航到树视图**ShipmentRole**下**Applications\BizTalk Application 1\Role Links**。 双击**ShipmentRole** ，并注意**ShipmentAgency1**映射到**SupplierAdvice**操作和**ShipmentAgency2**映射到**SupplierOrder**中登记的操作。  

5. 在命令窗口中，按 ENTER 以允许示例注销的登记和删除新参与方。  

6. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，验证此参与方已从取消登记**ShipmentRole**并从已删除**方**节点。  

## <a name="windows-powershell-script-example"></a>Windows Powershell 脚本示例  
 以下 Windows PowerShell 脚本示例可用于演示的相同功能**ExplorerOM**类：  

```  
#===============================================================#  
#===                                                         ===#  
#=== Create a new party named "FedEx" as an example.         ===#  
#===                                                         ===#  
#=== Two Shipment agency send ports from the PartyResolution ===#  
#=== sample will be added to the party.                      ===#  
#===                                                         ===#  
#===============================================================#  
Function CreateParty  
{  
  #=== Create a party =====================#  
  $myParty = $Catalog.AddNewParty()  
  $myParty.Name = "FedEx"  

  #=== create a standard alias ==========================#  
  $standardAlias = $myParty.AddNewAlias()  
  $standardAlias.Name = "D-U-N-S (Dun & Bradstreet)"  
  $standardAlias.Value = "Value1"  

  #=== Create a custom alias ==================#  
  $customAlias = $myParty.AddNewAlias()  
  $customAlias.Name = "Telephone"  
  $customAlias.Qualifier = "100"  
  $customAlias.Value = "4255550234"  

  #=== Add party send ports =====================================================#  

  #===============================================================#  
  #=== Have to use IList directly on this sendports collection ===#  
  #=== to work around a PowerShell issue.                      ===#  
  #===============================================================#  
  $iList = [System.Collections.IList]  

  $sendport1 = $Catalog.SendPorts["SP_FilesToShipmentAgency1"]  
  [void] $iList.GetMethod("Add").Invoke($myParty.SendPorts,$sendport1)  

  $sendport2 = $Catalog.SendPorts["SP_FilesToShipmentAgency2"]  
  [void] $iList.GetMethod("Add").Invoke($myParty.SendPorts,$sendport2)  

  #=== Specify a signature certificate, make sure the certificate is available ===#  
  #=== in the AddressBook store of the Local Machine                           ===#  

  foreach ($certificate in $Catalog.Certificates)  
  {  
    if ($certificate.ShortName -eq "BR, Certisign Certificadora Digital Ltda., Certisign - Autoridade Certificadora - AC2")  
    {  
      $myParty.SignatureCert = $certificate  
    }  
  }  

  #=== Commit the changes ===#  
  $catalog.SaveChanges()  
}  

#===============================================================#  
#===                                                         ===#  
#=== Delete the party named "FedEx"                          ===#  
#===                                                         ===#  
#===============================================================#  
Function DeleteParty  
{  
  $Catalog.RemoveParty($Catalog.Parties["FedEx"])  

  #=== Commit the changes ===#  
  $catalog.SaveChanges()  
}  

#===============================================================#  
#===                                                         ===#  
#=== Enlist the "FedEx" party with the "ShipmentRole"        ===#  
#===                                                         ===#  
#===============================================================#  
Function EnlistParty  
{  
  $myParty = $Catalog.Parties["FedEx"]  

  #=== Get the "ShipmentRole" in the Supplier assembly.        ===#  
  $svcRole = $Catalog.Assemblies["Supplier"].Roles["ShipmentRole"]  

  #=== Enlist the party under the shipper role ===#  
  $enlistedParty = $svcRole.AddNewEnlistedParty($myParty)  

  #===============================================================#  
  #=== Have to use IList directly on this sendports collection ===#  
  #=== to work around a PowerShell issue.                      ===#  
  #===============================================================#  
  $iList = [System.Collections.IList]   

  #===============================================================#  
  #=== Example port to be used for the role's "SupplierAdvice" ===#  
  #=== operation.                                              ===#  
  #=== Using the first send port added to the new party which  ===#  
  #=== is "SP_FilesToShipmentAgency1" at index 0 in the        ===#  
  #=== sendports collection.                                   ===#  
  #===============================================================#  
  $enlistedParty.Mappings[0].SendPort = $iList.GetProperty("Item").GetValue($myParty.SendPorts,0)  

  #===============================================================#  
  #=== Example port to be used for the role's "SupplierOrder"  ===#  
  #=== operation.                                              ===#  
  #=== Using the second send port added to the new party which ===#  
  #=== is "SP_FilesToShipmentAgency2" at index 1 in the        ===#  
  #=== sendports collection.                                   ===#  
  #===============================================================#  
  $enlistedParty.Mappings[1].SendPort = $iList.GetProperty("Item").GetValue($myParty.SendPorts,1)  

  #=== Commit the changes ===#  
  $Catalog.SaveChanges()  
}  

#===============================================================#  
#===                                                         ===#  
#=== Unenlist the "FedEx" party from the ShipmentRole        ===#  
#===                                                         ===#  
#===============================================================#  
Function UnenlistParty  
{  
  #=== Get the "ShipmentRole" from the Supplier assembly. ===#  
  $svcRole = $Catalog.Assemblies["Supplier"].Roles["ShipmentRole"]  

  #=== Remove the "FedEx" party ===#  
  foreach ($enlistedparty in $svcRole.EnlistedParties)  
  {  
    if ($enlistedparty.Party.Name -eq "FedEx")  
    {  
      $svcRole.RemoveEnlistedParty($enlistedparty)  
      break  
    }  
  }  

  #=== Commit the changes ===#  
  $Catalog.SaveChanges()  
}  

#===================#  
#=== Main Script ===#  
#===================#  

#=== Make sure the ExplorerOM assembly is loaded ===#  

[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  

#=== Connect to the BizTalk Management database ===#  

$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  

#=== This sample expects the PartyResolution sample to be built and deployed  ===#  
#=== to the BizTalk Server.                                                   ===#  

write-host `r`nMake sure the "PartyResolution" sample application from the Orchestrations   
write-host sample directory is deployed and running.  
write-host By default it will be listed in the BizTalk Server Administration Console  
write-host with the application name: `"BizTalk.Application.1`"`r`n  

$SupplierAssembly = $Catalog.Assemblies["Supplier"]  

#==================================================================#  
#=== Register a trap handler to discard changes on exceptions   ===#  
#=== Execution will continue in the event we want to unenlist,  ===#  
#=== and delete the party.                                      ===#  
#==================================================================#  

$Script:NoExceptionOccurred = $true  
$ErrorActionPreference="silentlycontinue"  
trap   
{   
  $Script:NoExceptionOccurred = $false  
  "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes and continuing execution so we can attempt to clean up the party...`r`n"  
  $Catalog.DiscardChanges()  
}  

CreateParty  
EnlistParty  

if ($Script:NoExceptionOccurred)  
{  
  Write-Host "`r`nExample Party `"FedEx`" should be created and enlisted with the `"ShipmentRole`".`r`n"  
  Write-Host You can view the results in the BizTalk Server Administration console.`r`n  
  Write-Host "Press <Enter> to unenlist and delete...`r`n"  
  Read-Host  
}  

UnenlistParty  
DeleteParty  

```  

 下面是运行 PowerShell 示例脚本的示例输出。 如果脚本运行失败，请确保根据本主题顶部的要求说明启用 PowerShell 脚本。  

```  
PS C:\> .\PartnerManagement.ps1  

Make sure the PartyResolution sample application from the Orchestrations  
sample directory is deployed and running.  
By default it will be listed in the BizTalk Server Administration Console  
with the application name: "BizTalk.Application.1"  

Example Party "FedEx" should be created and enlisted with the "ShipmentRole".  

You can view the results in the BizTalk Server Administration console.  

Press <Enter> to unenlist and delete...  
```  

## <a name="see-also"></a>请参阅  
 [参与方](../core/parties.md)   
 [角色链接和服务链接角色](../core/role-links-and-service-link-roles.md)   
 [Admin（BizTalk Server 示例文件夹）](../core/admin-biztalk-server-samples-folder.md)