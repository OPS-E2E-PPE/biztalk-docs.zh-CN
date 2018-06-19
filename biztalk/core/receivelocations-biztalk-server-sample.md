---
title: 接收位置 （BizTalk Server 示例） |Microsoft 文档
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
ms.openlocfilehash: b5b1a6d6b651ea07430f67667a17029dfe162d4d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972619"
---
# <a name="receivelocations-biztalk-server-sample"></a><span data-ttu-id="aaa6f-102">ReceiveLocations（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="aaa6f-102">ReceiveLocations (BizTalk Server Sample)</span></span>
<span data-ttu-id="aaa6f-103">示例演示如何创建接收位置接收中的位置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境使用**ExplorerOM**管理对象。</span><span class="sxs-lookup"><span data-stu-id="aaa6f-103">The ReceiveLocations sample demonstrates how to create receive locations in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment by using the **ExplorerOM** administration objects.</span></span> <span data-ttu-id="aaa6f-104">有关详细信息通常接收位置，请参阅[接收位置](../core/receive-locations.md)。</span><span class="sxs-lookup"><span data-stu-id="aaa6f-104">For more information about receive locations in general, see [Receive Locations](../core/receive-locations.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aaa6f-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="aaa6f-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="aaa6f-106">您必须具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理权限才能使用此示例中的管理对象。</span><span class="sxs-lookup"><span data-stu-id="aaa6f-106">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  
  
-   <span data-ttu-id="aaa6f-107">Windows PowerShell 脚本需要 Windows PowerShell 执行策略以允许脚本执行。</span><span class="sxs-lookup"><span data-stu-id="aaa6f-107">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="aaa6f-108">有关详细信息，请参阅 [检查执行策略](http://go.microsoft.com/fwlink/?LinkId=128930)。</span><span class="sxs-lookup"><span data-stu-id="aaa6f-108">For more information see [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="aaa6f-109">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="aaa6f-109">What This Sample Does</span></span>  
 <span data-ttu-id="aaa6f-110">此示例演示如何使用**ExplorerOM**管理的类来创建和配置接收端口和接收位置。</span><span class="sxs-lookup"><span data-stu-id="aaa6f-110">This sample demonstrates using the **ExplorerOM** administrative classes to create and configure receive ports and receive locations.</span></span> <span data-ttu-id="aaa6f-111">本主题中还包含 Windows PowerShell 示例脚本。</span><span class="sxs-lookup"><span data-stu-id="aaa6f-111">A Windows PowerShell example script is also included in this topic.</span></span> <span data-ttu-id="aaa6f-112">本示例将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="aaa6f-112">The sample performs the following operations:</span></span>  
  
-   <span data-ttu-id="aaa6f-113">创建名为“我的接收端口”的新接收端口。</span><span class="sxs-lookup"><span data-stu-id="aaa6f-113">Create a new receive port named “My Receive Port”.</span></span>  
  
-   <span data-ttu-id="aaa6f-114">创建与新端口相关的新接收位置，并将该位置配置为使用 HTTP 传输协议。</span><span class="sxs-lookup"><span data-stu-id="aaa6f-114">Create a new receive location associated with the new port and configured to use the HTTP transport protocol.</span></span>  
  
-   <span data-ttu-id="aaa6f-115">本示例还包含用于删除和枚举接收端口和位置的示例过程。</span><span class="sxs-lookup"><span data-stu-id="aaa6f-115">This sample also contains example procedures to delete and enumerate receive ports and locations.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="aaa6f-116">本示例的所在位置</span><span class="sxs-lookup"><span data-stu-id="aaa6f-116">Where To Find This Sample</span></span>  
 <span data-ttu-id="aaa6f-117">此示例位于以下 SDK 的位置：</span><span class="sxs-lookup"><span data-stu-id="aaa6f-117">This sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="aaa6f-118">\<*示例路径*\> \Admin\ExplorerOM\ReceiveLocations</span><span class="sxs-lookup"><span data-stu-id="aaa6f-118">\<*Samples Path*\> \Admin\ExplorerOM\ReceiveLocations</span></span>  
  
 <span data-ttu-id="aaa6f-119">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="aaa6f-119">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="aaa6f-120">文件</span><span class="sxs-lookup"><span data-stu-id="aaa6f-120">File(s)</span></span>|<span data-ttu-id="aaa6f-121">Description</span><span class="sxs-lookup"><span data-stu-id="aaa6f-121">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aaa6f-122">ReceiveLocations.cs</span><span class="sxs-lookup"><span data-stu-id="aaa6f-122">ReceiveLocations.cs</span></span>|<span data-ttu-id="aaa6f-123">本示例中演示的操作的 [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 源文件。</span><span class="sxs-lookup"><span data-stu-id="aaa6f-123">[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] source file for the operations demonstrated in this sample.</span></span>|  
|<span data-ttu-id="aaa6f-124">ReceiveLocations.sln 和 ReceiveLocations.csproj</span><span class="sxs-lookup"><span data-stu-id="aaa6f-124">ReceiveLocations.sln and ReceiveLocations.csproj</span></span>|<span data-ttu-id="aaa6f-125">本示例的解决方案文件和项目文件。</span><span class="sxs-lookup"><span data-stu-id="aaa6f-125">Solution and project files for this sample.</span></span>|  
  
## <a name="building-and-running-this-sample"></a><span data-ttu-id="aaa6f-126">生成并运行本示例</span><span class="sxs-lookup"><span data-stu-id="aaa6f-126">Building and Running This Sample</span></span>  
  
#### <a name="to-build-this-sample"></a><span data-ttu-id="aaa6f-127">生成示例</span><span class="sxs-lookup"><span data-stu-id="aaa6f-127">To build this sample</span></span>  
  
1.  <span data-ttu-id="aaa6f-128">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开解决方案文件 ReceiveLocations.sln。</span><span class="sxs-lookup"><span data-stu-id="aaa6f-128">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file ReceiveLocations.sln.</span></span>  
  
2.  <span data-ttu-id="aaa6f-129">在“生成”  菜单上，单击“生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="aaa6f-129">On the **Build** menu, click **Build Solution**.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="aaa6f-130">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="aaa6f-130">To run this sample</span></span>  
  
1.  <span data-ttu-id="aaa6f-131">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员权限打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="aaa6f-131">Open a command prompt with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges.</span></span>  
  
2.  <span data-ttu-id="aaa6f-132">将更改为\<*示例*\>\Admin\ExplorerOM\ReceiveLocations\bin\debug 目录。</span><span class="sxs-lookup"><span data-stu-id="aaa6f-132">Change to the \<*Samples*\>\Admin\ExplorerOM\ReceiveLocations\bin\debug directory.</span></span>  
  
3.  <span data-ttu-id="aaa6f-133">运行 ReceiveLocations.exe。</span><span class="sxs-lookup"><span data-stu-id="aaa6f-133">Run ReceiveLocations.exe.</span></span>  
  
4.  <span data-ttu-id="aaa6f-134">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中查看新的接收端口和接收位置。</span><span class="sxs-lookup"><span data-stu-id="aaa6f-134">View the new receive port and receive location with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="windows-powershell-script-example"></a><span data-ttu-id="aaa6f-135">Windows Powershell 脚本示例</span><span class="sxs-lookup"><span data-stu-id="aaa6f-135">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="aaa6f-136">以下 PowerShell 示例脚本演示与 [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 版本相同的操作。</span><span class="sxs-lookup"><span data-stu-id="aaa6f-136">The following PowerShell example script demonstrates the same operations as the [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] version.</span></span> <span data-ttu-id="aaa6f-137">确保已按照本主题的要求部分中所述正确配置了脚本执行策略。</span><span class="sxs-lookup"><span data-stu-id="aaa6f-137">Make sure the script execution policy has been properly configured as mentioned in the requirements section of this topic.</span></span>  
  
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
  
 <span data-ttu-id="aaa6f-138">以下是 PowerShell 脚本执行的示例输出，显示了将要创建和删除的接收端口和位置：</span><span class="sxs-lookup"><span data-stu-id="aaa6f-138">Here is example output from the PowerShell script execution showing the receive port and location being created and deleted:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aaa6f-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aaa6f-139">See Also</span></span>  
 <span data-ttu-id="aaa6f-140">[接收位置](../core/receive-locations.md) </span><span class="sxs-lookup"><span data-stu-id="aaa6f-140">[Receive Locations](../core/receive-locations.md) </span></span>  
 [<span data-ttu-id="aaa6f-141">Admin-ExplorerOM（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="aaa6f-141">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)