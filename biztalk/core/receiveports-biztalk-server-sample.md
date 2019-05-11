---
title: ReceivePorts （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c403005d-5e0e-4015-b138-6318e03192af
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a338b0349329ab0f74dfb1ab3683b10502ed66d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398097"
---
# <a name="receiveports-biztalk-server-sample"></a>ReceivePorts （BizTalk Server 示例）
ReceivePorts 示例演示如何创建新接收端口通过使用**ExplorerOM**管理类。  

## <a name="prerequisites"></a>先决条件  

- 您必须具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理权限才能使用此示例中的管理对象。  

- Windows PowerShell 脚本需要 Windows PowerShell 执行策略以允许脚本执行。 有关详细信息，请参阅 [检查执行策略](http://go.microsoft.com/fwlink/?LinkId=128930)。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例演示如何使用**BtsCatalogExplorer**并**ReceivePort**类**Microsoft.BizTalk.ExplorerOM**命名空间添加新接收端口[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. 在 Microsoft 中编写示例[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)]。 本主题中还包含 Windows PowerShell 示例脚本。 此示例演示了以下操作：  

-   通过使用连接到 BizTalk 管理数据库**BtsCatalogExplorer**类。  

-   通过添加新的接收端口**AddNewReceivePort**方法。  

-   枚举接收端口。  

-   删除接收端口。  

## <a name="where-to-find-this-sample"></a>本示例的所在位置  
 本示例位于以下 SDK 位置中：  

 \<*Samples Path*\>\Admin\ExplorerOM\ReceivePorts  

 下表显示了本示例中的文件及其用途说明：  


|                 文件                  |                                                 Description                                                  |
|------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|             ReceivePorts.cs              | [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 此示例中演示的操作的源文件。 |
| ReceivePorts.sln 和 ReceivePorts.csproj |                                  本示例的解决方案和项目文件。                                   |

## <a name="building-and-running-this-sample"></a>生成并运行本示例  

#### <a name="to-build-this-sample"></a>生成示例  

1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开解决方案文件 ReceivePorts.sln。  

2. 在“生成”  菜单上，单击“生成解决方案” 。  

#### <a name="to-run-this-sample"></a>运行本示例的步骤  

1.  打开命令窗口并导航到以下文件夹：  

     \<*Samples Path*\>\Admin\ExplorerOM\ReceivePorts\bin\Debug  

2.  运行文件 ReceivePorts.exe。 新的接收端口应创建并在端口枚举中所示。 枚举之后立即删除接收端口。  

## <a name="windows-powershell-script-example"></a>Windows Powershell 脚本示例  
 以下 Windows PowerShell 示例脚本可用于演示的相同功能**ExplorerOM**类：  

```  
#==================================================================#  
#===                                                            ===#  
#=== Create a new receive port named "My Receive Port".         ===#  
#===                                                            ===#  
#==================================================================#  
Function CreateReceivePort()  
{   
  #=== Passing false here creates a one-way receive port opposed to a two-way ===#  
  $myreceivePort = $catalog.AddNewReceivePort($false)  

  $myreceivePort.Name = "My Receive Port"  
  $myreceivePort.Tracking = [Microsoft.BizTalk.ExplorerOM.TrackingTypes] "AfterReceivePipeline"  

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
    $catalog.RemoveReceivePort($receivePort)    

    #=== Try to commit the changes made so far. If the commit fails, ===#  
    #=== roll back all changes in the trap handler.                  ===#  
    $catalog.SaveChanges()  
  }  
}  

#================================================================#  
#===                                                          ===#  
#=== Enumerate the receive ports.                             ===#  
#===                                                          ===#  
#================================================================#  
Function EnumerateReceivePorts  
{  
   #=== Enumerate the receive ports. ===#  
   foreach ($receivePort in $catalog.ReceivePorts)  
   {  
      Write-host "`r`n$($receivePort.Name)"  
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
  "Exception encountered:`r`n"; $_; "`r`nDiscarding changes and continuing execution so we can attempt to clean up the receive port...`r`n"  
  $Catalog.DiscardChanges()  
}  

#=== Create the new receive port ===#  
Write-Host "`r`nAttempting to create `"My Receive Port`"..."  
CreateReceivePort  

#=== Enumerate each receive port ===#  
Write-Host "`r`nEnumerating all receive ports...`r`n"  
EnumerateReceivePorts  

#=== Prompt before removing the new example receive port ===#  
Write-Host "`r`nPress <ENTER> to delete `"My Receive Port`"..."  
Read-Host  
DeleteReceivePort  

#=== Enumerate again to show the receive port was removed ===#  
Write-Host "`r`nEnumerating all receive ports to show `"My Receive Port`" was removed...`r`n"  
EnumerateReceivePorts  

```  

 下面是运行 Windows PowerShell 脚本以创建新的示例接收端口：  

```  
PS C:\> .\receiveports.ps1  

Attempting to create "My Receive Port"...  

Enumerating all receive ports...  

BatchControlMessageRecvPort  

ResendReceivePort  

HelloWorldReceivePort  

CBRReceivePort  

RP_ReceivePOFromInternal  

RP_ShipmentAgency1_OrderFiles  

RP_ShipmentAgency2_OrderFiles  

RP_ReceivePOFromBuyer  

RP_Receive_ShipmentAgency_Ack  

My Receive Port  

Press <ENTER> to delete "My Receive Port"...  

Enumerating all receive ports to show "My Receive Port" was removed...  

BatchControlMessageRecvPort  

ResendReceivePort  

HelloWorldReceivePort  

CBRReceivePort  

RP_ReceivePOFromInternal  

RP_ShipmentAgency1_OrderFiles  

RP_ShipmentAgency2_OrderFiles  

RP_ReceivePOFromBuyer  

RP_Receive_ShipmentAgency_Ack  
```  

## <a name="see-also"></a>请参阅  
 [Admin-ExplorerOM（BizTalk Server 示例文件夹）](../core/admin-explorerom-biztalk-server-samples-folder.md)