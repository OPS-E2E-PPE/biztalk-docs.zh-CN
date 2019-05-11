---
title: OrchestrationBinding （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea14c0db-ea83-4bf9-b417-f877b3cb1bf9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 372c3b7e7ce839729af416385b1404c09a7ca5dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322364"
---
# <a name="orchestrationbinding-biztalk-server-sample"></a>OrchestrationBinding （BizTalk Server 示例）
业务流程绑定示例演示使用 [Microsoft.BizTalk.ExplorerOM](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.aspx) 管理对象来配置和管理业务流程。  

## <a name="prerequisites"></a>先决条件  

- 此示例要求，通过运行位于中的 setup.bat 来部署 HelloWorld 示例\<*示例路径*\>\Orchestrations\HelloWorld 目录。  

- 您必须具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理权限才能使用此示例中的管理对象。  

- Windows PowerShell 脚本示例需要 Windows PowerShell 执行策略才能允许脚本执行。 有关详细信息，请参阅 [检查执行策略](http://go.microsoft.com/fwlink/?LinkId=128930)。  

## <a name="what-this-sample-does"></a>本示例的用途  
 本示例演示使用 **Microsoft.BizTalk.ExplorerOM** 命名空间中的管理对象来管理业务流程。 本示例演示如何使用 **ExplorerOM** 对象完成以下操作：  

-   使用[Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.btscatalogexplorer.aspx) 类连接到 BizTalk 管理数据库。  

-   通过更改 **Microsoft.BizTalk.ExplorerOM.BtsOrchestration** 类的 [Status](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) 属性来停止和启动业务流程。  

-   通过更改 **Microsoft.BizTalk.ExplorerOM.BtsOrchestration** 类的 [Status](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) 属性来登记和取消登记业务流程。  

-   通过使用 **Microsoft.BizTalk.ExplorerOM.BtsOrchestration** 类上的 [Ports](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) 集合来绑定和取消绑定业务流程。  

## <a name="where-to-find-this-sample"></a>本示例的所在位置  
 本示例位于以下 SDK 位置中：  

 \<*Samples Path*\>\Admin\ExplorerOM\OrchestrationBinding  

 下表显示了本示例中的文件及其用途说明：  


|                                     文件                                     |                                                 Description                                                  |
|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|                             OrchestrationBinding.cs                             | [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 此示例中演示的操作的源文件。 |
| OrchestrationBinding.sln、OrchestrationBinding.csproj、OrchestrationBinding.suo |                                  示例的解决方案文件和项目文件。                                  |

## <a name="building-and-running-this-sample"></a>生成并运行本示例  

#### <a name="to-build-this-sample"></a>生成示例  

1. 确保您已经完成生成和初始化 HelloWorld 示例的步骤。 中提供了这些步骤[HelloWorld （BizTalk Server 示例）](../core/helloworld-biztalk-server-sample.md)。  

2. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]中，打开解决方案文件 OrchestrationBinding.sln。  

3. 在“生成”  菜单上，单击“生成解决方案” 。  

#### <a name="to-run-this-sample"></a>运行本示例的步骤  

1.  打开命令窗口并导航到以下文件夹：  

     \<*Samples Path*\>\Admin\ExplorerOM\OrchestrationBinding\bin\Debug  

2.  运行文件 OrchestrationBinding.exe 并按照示例提供的说明进行操作。  

## <a name="windows-powershell-script-example"></a>Windows Powershell 脚本示例  
 以下 Windows PowerShell 脚本可用于演示 **ExplorerOM** 类的相同功能。  

```  

Function RefreshPrompt($oldstatus,$newstatus)  
{  
  Write-Host Orchestration Status should now be `"$oldstatus`"  
  Write-Host Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify   

  if ($newstatus)  
  {  
    Write-Host Pressing `<Enter`> now will $newstatus the orchestration using ExplorerOM`.`.`.  
    Read-Host  
    Write-Host "=== Please wait, attempting to $newstatus the orchestration... ===`r`n"  
  }  
  else  
  {  
    write-host `r`n  
  }  
}  

#===================#  
#=== Main Script ===#  
#===================#  

#=== Make sure the ExplorerOM assembly is loaded ===#  

[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  

#=== Connect to the BizTalk Management database ===#  

$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  

#=== This sample expects the HelloWorld sample orchestration to be using the ===#  
#=== default name "Biztalk Application 1"                                    ===#  

$HelloWorldApp = $Catalog.Applications["Biztalk Application 1"]  
$orch = $HelloWorldApp.orchestrations["Microsoft.Samples.BizTalk.HelloWorld.HelloSchedule"]  

#==================================================================#  
#=== Register a trap handler to discard changes on exceptions   ===#  
#=== Execution will continue in the event we need to re-enlist, ===#  
#=== re-bind, or restart the orchestration.                     ===#  
#==================================================================#  

$ErrorActionPreference="silentlycontinue"  
trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes and continuing execution...`r`n";$Catalog.DiscardChanges();}  

write-host `r`nMake sure the "HelloWorld" sample application is deployed and running.  
write-host By default it will be listed in the BizTalk Server Administration Console  
write-host with the application name: `"BizTalk.Application.1`"`r`n  

#==========================================================#  
#=== Change orchestration state from Started to stopped ===#  
#==========================================================#  

RefreshPrompt Started stop  
$orch.Status = [Microsoft.BizTalk.ExplorerOM.OrchestrationStatus] "Enlisted"  
$Catalog.SaveChanges()  

#=============================================================#  
#=== Change orchestration state from stopped to unenlisted ===#  
#=============================================================#  

RefreshPrompt Stopped unenlist  
$orch.Status = [Microsoft.BizTalk.ExplorerOM.OrchestrationStatus] "Unenlisted"  
$Catalog.SaveChanges()  

#=============================================================#  
#=== Change orchestration state from unenlisted to unbound ===#  
#=============================================================#  

RefreshPrompt Unenlisted unbind  
$orch.Ports["SendInvoicePort"].SendPort = $null  
$orch.Ports["ReceivePOPort"].ReceivePort = $null;  
$orch.Host = $null  
$Catalog.SaveChanges()  

#==================================================================#  
#=== Change orchestration state from unbound back to unenlisted ===#  
#==================================================================#  

RefreshPrompt Unenlisted`(Unbound`) re-bind  
$orch.Ports["SendInvoicePort"].SendPort = $Catalog.SendPorts["HelloWorldSendPort"]  
$orch.Ports["ReceivePOPort"].ReceivePort = $Catalog.ReceivePorts["HelloWorldReceivePort"]  
$orch.Host = $Catalog.Hosts["BizTalkServerApplication"]  
$Catalog.SaveChanges()  

#==================================================================#  
#=== Change orchestration state from unenlisted back to stopped ===#  
#==================================================================#  

RefreshPrompt Unenlisted enlist  
$orch.Status = [Microsoft.BizTalk.ExplorerOM.OrchestrationStatus] "Enlisted"  
$Catalog.SaveChanges()  

#===============================================================#  
#=== Change orchestration state from stopped back to started ===#  
#===============================================================#  

RefreshPrompt Stopped restart  
$orch.Status = [Microsoft.BizTalk.ExplorerOM.OrchestrationStatus] "Started"  
$Catalog.SaveChanges()  

RefreshPrompt Started  

```  

 下面是运行 Windows PowerShell 脚本的示例输出。  

```  
PS C:\> .\OrchestrationBind.ps1  

Make sure the HelloWorld sample application is deployed and running.  
By default it will be listed in the BizTalk Server Administration Console  
with the application name: "BizTalk.Application.1"  

Orchestration Status should now be "Started"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will stop the orchestration using ExplorerOM...  

=== Please wait, attempting to stop the orchestration... ===  

Orchestration Status should now be "Stopped"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will unenlist the orchestration using ExplorerOM...  

=== Please wait, attempting to unenlist the orchestration... ===  

Orchestration Status should now be "Unenlisted"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will unbind the orchestration using ExplorerOM...  

=== Please wait, attempting to unbind the orchestration... ===  

Orchestration Status should now be "Unenlisted(Unbound)"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will re-bind the orchestration using ExplorerOM...  

=== Please wait, attempting to re-bind the orchestration... ===  

Orchestration Status should now be "Unenlisted"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will enlist the orchestration using ExplorerOM...  

=== Please wait, attempting to enlist the orchestration... ===  

Orchestration Status should now be "Stopped"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will restart the orchestration using ExplorerOM...  

=== Please wait, attempting to restart the orchestration... ===  

Orchestration Status should now be "Started"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  

```  

## <a name="see-also"></a>请参阅  
 [Admin-explorerom （BizTalk Server 示例文件夹）](../core/admin-explorerom-biztalk-server-samples-folder.md)   
 [HelloWorld（BizTalk Server 示例）](../core/helloworld-biztalk-server-sample.md)