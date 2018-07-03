---
title: ReceiveLocations （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87d75941-3973-4166-91b0-f1192b25a804
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df19296fcf6c93d582034464402597248335e826
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019165"
---
# <a name="receivelocations-biztalk-server-sample"></a>ReceiveLocations（BizTalk Server 示例）
ReceiveLocations 示例演示了如何创建接收位置中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过使用环境**ExplorerOM**管理对象。 有关详细信息在一般情况下接收位置，请参阅[接收位置](../core/receive-locations.md)。  

## <a name="prerequisites"></a>必要條件  

- 您必须具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理权限才能使用此示例中的管理对象。  

- Windows PowerShell 脚本需要 Windows PowerShell 执行策略以允许脚本执行。 有关详细信息，请参阅 [检查执行策略](http://go.microsoft.com/fwlink/?LinkId=128930)。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例演示如何使用**ExplorerOM**管理类来创建和配置接收端口和接收位置。 本主题中还包含 Windows PowerShell 示例脚本。 本示例将执行以下操作：  

-   创建名为“我的接收端口”的新接收端口。  

-   创建与新端口相关的新接收位置，并将该位置配置为使用 HTTP 传输协议。  

-   本示例还包含用于删除和枚举接收端口和位置的示例过程。  

## <a name="where-to-find-this-sample"></a>本示例的所在位置  
 此示例将位于以下 SDK 位置：  

 \<*示例路径*\> \Admin\ExplorerOM\ReceiveLocations  

 下表显示了本示例中的文件及其用途说明：  


|                     文件                      |                                                   Description                                                    |
|--------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|               ReceiveLocations.cs                | 本示例中演示的操作的 [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 源文件。 |
| ReceiveLocations.sln 和 ReceiveLocations.csproj |                                   本示例的解决方案文件和项目文件。                                    |

## <a name="building-and-running-this-sample"></a>生成并运行本示例  

#### <a name="to-build-this-sample"></a>生成示例  

1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开解决方案文件 ReceiveLocations.sln。  

2. 在“生成”  菜单上，单击“生成解决方案” 。  

#### <a name="to-run-this-sample"></a>运行本示例的步骤  

1. 使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员权限打开命令提示符。  

2. 将更改为\<*示例*\>\Admin\ExplorerOM\ReceiveLocations\bin\debug 目录。  

3. 运行 ReceiveLocations.exe。  

4. 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中查看新的接收端口和接收位置。  

## <a name="windows-powershell-script-example"></a>Windows Powershell 脚本示例  
 以下 PowerShell 示例脚本演示与 [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 版本相同的操作。 确保已按照本主题的要求部分中所述正确配置了脚本执行策略。  

```  
#==================================================================#  
#===                                                            ===#  
#=== Create a new receive port named "My Receive Port" as an    ===#  
#=== example.                                                   ===#  
#===                                                            ===#  
#=== A new receive location will also be created and associated ===#  
#=== with the receive port.                                     ===#  
#===                                                            ===#  
#==================================================================#  
Function CreateAndConfigureReceiveLocation()  
{  
   $myreceivePort = $catalog.AddNewReceivePort($false)  

   #=== Note that if you don’t set the name property for the receieve port, ===#  
   #=== it will create a new receive location and add it to the receive     ===#     
   #=== port.                                                               ===#  

   $myreceivePort.Name = "My Receive Port"  

   #=== Create a new receive location and add it to the receive port ===#  
   $myreceiveLocation = $myreceivePort.AddNewReceiveLocation()  

   foreach ($handler in $catalog.ReceiveHandlers)  
   {  
      if ($handler.TransportType.Name -eq "HTTP")  
      {  
         $myreceiveLocation.ReceiveHandler = $handler  
         break  
      }  
   }  

   #=== Associate a transport protocol and URI with the receive location. ===#   
   $myreceiveLocation.TransportType = $catalog.ProtocolTypes["HTTP"]  
   $myreceiveLocation.Address = "/home"  

   #=== Assign the first receive pipeline found to process the message. ===#  
   foreach ($pipeline in $catalog.Pipelines)  
   {  
      if ($pipeline.Type -eq [Microsoft.Biztalk.ExplorerOM.PipelineType] "Receive")  
      {  
         $myreceiveLocation.ReceivePipeline = $pipeline  
         break  
      }  

      #=== Enable the receive location. ===#  
      $myreceiveLocation.Enable = $true  

      #=== Optional Properties ===#  
      $myreceiveLocation.FragmentMessages = [Microsoft.BizTalk.ExplorerOM.Fragmentation] "Yes"  
      $myreceiveLocation.ServiceWindowEnabled = $false    
   }  

    #=== Try to commit the changes made so far. If the commit fails, ===#  
    #=== roll back all changes.                                      ===#  
    $catalog.SaveChanges()  
}  

#===============================================================#  
#===                                                         ===#  
#=== Delete the receive port named "My Receive Port"         ===#  
#===                                                         ===#  
#===============================================================#  
Function DeleteReceivePort  
{  
  $receivePort = $catalog.ReceivePorts["My Receive Port"]  

  if ($receivePort -ne $null)  
  {  

    #=== Enumerate the receive locations. ===#  
    foreach ($location in $receivePort.ReceiveLocations)  
    {  
        if (($location.Name -eq "Receive Location1") -and ($location.IsPrimary -eq $false))  
        {  
          $receivePort.RemoveReceiveLocation($location)  
        }  
    }  

    $catalog.RemoveReceivePort($receivePort)    

    #=== Try to commit the changes made so far. If the commit fails, ===#  
    #=== roll back all changes in the trap handler.                  ===#  
    $catalog.SaveChanges()  
  }  
}  

#================================================================#  
#===                                                          ===#  
#=== Enumerate the receive ports and their receive locations. ===#  
#===                                                          ===#  
#================================================================#  
Function EnumerateReceiveLocations  
{  
   #=== Enumerate the receive locations in each of the receive ports. ===#  
   foreach ($receivePort in $catalog.ReceivePorts)  
   {  
      Write-host "`r`n$($receivePort.Name)"  

      #=== Enumerate the receive locations. ===#  
      foreach ($location in $receivePort.ReceiveLocations)  
      {  
         Write-Host "`t$($location.Name)"  
      }  
   }  

   Write-host ""  
}  

#===================#  
#=== Main Script ===#  
#===================#  

#=== Make sure the ExplorerOM assembly is loaded ===#  

[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  

#=== Connect to the BizTalk Management database ===#  

$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  

#==================================================================#  
#=== Register a trap handler to discard changes on exceptions   ===#  
#=== Execution will continue in the event we want to delete the ===#  
#=== receive port.                                              ===#  
#==================================================================#  

$Script:NoExceptionOccurred = $true  
$ErrorActionPreference="silentlycontinue"  
trap   
{   
  $Script:NoExceptionOccurred = $false  
  "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes and continuing execution so we can attempt to clean up the receive port...`r`n"  
  $Catalog.DiscardChanges()  
}  

#=== Create the new receive port with its new receive location ===#  
CreateAndConfigureReceiveLocation  
Write-Host "`r`n`"My Receive Port`" created."  

#=== Enumerate each receive port along with its receive locations ===#  
Write-Host "`r`nEnumerating all receive ports...`r`n"  
EnumerateReceiveLocations  

#=== Prompt before removing the new example receive port and location ===#  
Write-Host "`r`nPress <ENTER> to delete `"My Receive Port`"..."  
Read-Host  
DeleteReceivePort  

#=== Enumerate again to show the receive port and location was removed ===#  
Write-Host "`r`nEnumerating all receive ports to show `"My Receive Port`" was removed...`r`n"  
EnumerateReceiveLocations  

```  

 以下是 PowerShell 脚本执行的示例输出，显示了将要创建和删除的接收端口和位置：  

```  
PS C:\> .\ReceiveLocations.ps1  

"My Receive Port" created.  

Enumerating all receive ports...  

BatchControlMessageRecvPort  
        BatchControlMessageRecvLoc  

ResendReceivePort  
        ResendReceiveLocation  

HelloWorldReceivePort  
        HelloWorldReceiveLocation  

CBRReceivePort  
        CBRReceiveLocation  

RP_ReceivePOFromInternal  
        RL_ReceivePOFromInternal  

RP_ShipmentAgency1_OrderFiles  
        RL_ShipmentAgency1_OrderFiles  

RP_ShipmentAgency2_OrderFiles  
        RL_ShipmentAgency2_OrderFiles  

RP_ReceivePOFromBuyer  
        RL_ReceivePOFromBuyer  

RP_Receive_ShipmentAgency_Ack  
        RL_Receive_ShipmentAgency_Ack  

My Receive Port  
        Receive Location1  

Press <ENTER> to delete "My Receive Port"...  

Enumerating all receive ports to show "My Receive Port" was removed...  

BatchControlMessageRecvPort  
        BatchControlMessageRecvLoc  

ResendReceivePort  
        ResendReceiveLocation  

HelloWorldReceivePort  
        HelloWorldReceiveLocation  

CBRReceivePort  
        CBRReceiveLocation  

RP_ReceivePOFromInternal  
        RL_ReceivePOFromInternal  

RP_ShipmentAgency1_OrderFiles  
        RL_ShipmentAgency1_OrderFiles  

RP_ShipmentAgency2_OrderFiles  
        RL_ShipmentAgency2_OrderFiles  

RP_ReceivePOFromBuyer  
        RL_ReceivePOFromBuyer  

RP_Receive_ShipmentAgency_Ack  
        RL_Receive_ShipmentAgency_Ack  

```  

## <a name="see-also"></a>请参阅  
 [接收位置](../core/receive-locations.md)   
 [Admin-ExplorerOM（BizTalk Server 示例文件夹）](../core/admin-explorerom-biztalk-server-samples-folder.md)