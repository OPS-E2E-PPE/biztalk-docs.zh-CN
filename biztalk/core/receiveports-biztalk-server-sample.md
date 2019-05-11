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
# <a name="receiveports-biztalk-server-sample"></a><span data-ttu-id="d460b-102">ReceivePorts （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="d460b-102">ReceivePorts (BizTalk Server Sample)</span></span>
<span data-ttu-id="d460b-103">ReceivePorts 示例演示如何创建新接收端口通过使用**ExplorerOM**管理类。</span><span class="sxs-lookup"><span data-stu-id="d460b-103">The ReceivePorts sample demonstrates how to create a new receive port by using the **ExplorerOM** administrative classes.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="d460b-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="d460b-104">Prerequisites</span></span>  

- <span data-ttu-id="d460b-105">您必须具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理权限才能使用此示例中的管理对象。</span><span class="sxs-lookup"><span data-stu-id="d460b-105">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  

- <span data-ttu-id="d460b-106">Windows PowerShell 脚本需要 Windows PowerShell 执行策略以允许脚本执行。</span><span class="sxs-lookup"><span data-stu-id="d460b-106">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="d460b-107">有关详细信息，请参阅 [检查执行策略](http://go.microsoft.com/fwlink/?LinkId=128930)。</span><span class="sxs-lookup"><span data-stu-id="d460b-107">For more information see [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="d460b-108">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="d460b-108">What This Sample Does</span></span>  
 <span data-ttu-id="d460b-109">此示例演示如何使用**BtsCatalogExplorer**并**ReceivePort**类**Microsoft.BizTalk.ExplorerOM**命名空间添加新接收端口[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d460b-109">This sample demonstrates using the **BtsCatalogExplorer** and **ReceivePort** classes from the **Microsoft.BizTalk.ExplorerOM** namespace to add a new receive port to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d460b-110">在 Microsoft 中编写示例[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d460b-110">The sample is written in Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span></span> <span data-ttu-id="d460b-111">本主题中还包含 Windows PowerShell 示例脚本。</span><span class="sxs-lookup"><span data-stu-id="d460b-111">A Windows PowerShell example script is also included in this topic.</span></span> <span data-ttu-id="d460b-112">此示例演示了以下操作：</span><span class="sxs-lookup"><span data-stu-id="d460b-112">The sample demonstrates the following operations:</span></span>  

-   <span data-ttu-id="d460b-113">通过使用连接到 BizTalk 管理数据库**BtsCatalogExplorer**类。</span><span class="sxs-lookup"><span data-stu-id="d460b-113">Connecting to the BizTalk Management database by using the **BtsCatalogExplorer** class.</span></span>  

-   <span data-ttu-id="d460b-114">通过添加新的接收端口**AddNewReceivePort**方法。</span><span class="sxs-lookup"><span data-stu-id="d460b-114">Adding a new receive port by using the **AddNewReceivePort** method.</span></span>  

-   <span data-ttu-id="d460b-115">枚举接收端口。</span><span class="sxs-lookup"><span data-stu-id="d460b-115">Enumerating receive ports.</span></span>  

-   <span data-ttu-id="d460b-116">删除接收端口。</span><span class="sxs-lookup"><span data-stu-id="d460b-116">Deleting receive ports.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="d460b-117">本示例的所在位置</span><span class="sxs-lookup"><span data-stu-id="d460b-117">Where To Find This Sample</span></span>  
 <span data-ttu-id="d460b-118">本示例位于以下 SDK 位置中：</span><span class="sxs-lookup"><span data-stu-id="d460b-118">The sample is located in the following SDK location:</span></span>  

 <span data-ttu-id="d460b-119">\<*Samples Path*\>\Admin\ExplorerOM\ReceivePorts</span><span class="sxs-lookup"><span data-stu-id="d460b-119">\<*Samples Path*\>\Admin\ExplorerOM\ReceivePorts</span></span>  

 <span data-ttu-id="d460b-120">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="d460b-120">The following table shows the files in this sample and describes their purpose.</span></span>  


|                 <span data-ttu-id="d460b-121">文件</span><span class="sxs-lookup"><span data-stu-id="d460b-121">File(s)</span></span>                  |                                                 <span data-ttu-id="d460b-122">Description</span><span class="sxs-lookup"><span data-stu-id="d460b-122">Description</span></span>                                                  |
|------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|             <span data-ttu-id="d460b-123">ReceivePorts.cs</span><span class="sxs-lookup"><span data-stu-id="d460b-123">ReceivePorts.cs</span></span>              | [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] <span data-ttu-id="d460b-124">此示例中演示的操作的源文件。</span><span class="sxs-lookup"><span data-stu-id="d460b-124">source file for operations demonstrated in this sample.</span></span> |
| <span data-ttu-id="d460b-125">ReceivePorts.sln 和 ReceivePorts.csproj</span><span class="sxs-lookup"><span data-stu-id="d460b-125">ReceivePorts.sln and ReceivePorts.csproj</span></span> |                                  <span data-ttu-id="d460b-126">本示例的解决方案和项目文件。</span><span class="sxs-lookup"><span data-stu-id="d460b-126">Solution and project file for the sample.</span></span>                                   |

## <a name="building-and-running-this-sample"></a><span data-ttu-id="d460b-127">生成并运行本示例</span><span class="sxs-lookup"><span data-stu-id="d460b-127">Building and Running This Sample</span></span>  

#### <a name="to-build-this-sample"></a><span data-ttu-id="d460b-128">生成示例</span><span class="sxs-lookup"><span data-stu-id="d460b-128">To build this sample</span></span>  

1. <span data-ttu-id="d460b-129">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开解决方案文件 ReceivePorts.sln。</span><span class="sxs-lookup"><span data-stu-id="d460b-129">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file ReceivePorts.sln.</span></span>  

2. <span data-ttu-id="d460b-130">在“生成”  菜单上，单击“生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="d460b-130">On the **Build** menu, click **Build Solution**.</span></span>  

#### <a name="to-run-this-sample"></a><span data-ttu-id="d460b-131">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="d460b-131">To run this sample</span></span>  

1.  <span data-ttu-id="d460b-132">打开命令窗口并导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="d460b-132">Open a command window and navigate to the following folder:</span></span>  

     <span data-ttu-id="d460b-133">\<*Samples Path*\>\Admin\ExplorerOM\ReceivePorts\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="d460b-133">\<*Samples Path*\>\Admin\ExplorerOM\ReceivePorts\bin\Debug</span></span>  

2.  <span data-ttu-id="d460b-134">运行文件 ReceivePorts.exe。</span><span class="sxs-lookup"><span data-stu-id="d460b-134">Run the file ReceivePorts.exe.</span></span> <span data-ttu-id="d460b-135">新的接收端口应创建并在端口枚举中所示。</span><span class="sxs-lookup"><span data-stu-id="d460b-135">The new receive port should be created and shown in the port enumeration.</span></span> <span data-ttu-id="d460b-136">枚举之后立即删除接收端口。</span><span class="sxs-lookup"><span data-stu-id="d460b-136">After the enumeration the receive port is immediately removed.</span></span>  

## <a name="windows-powershell-script-example"></a><span data-ttu-id="d460b-137">Windows Powershell 脚本示例</span><span class="sxs-lookup"><span data-stu-id="d460b-137">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="d460b-138">以下 Windows PowerShell 示例脚本可用于演示的相同功能**ExplorerOM**类：</span><span class="sxs-lookup"><span data-stu-id="d460b-138">The following Windows PowerShell example script can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  

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

 <span data-ttu-id="d460b-139">下面是运行 Windows PowerShell 脚本以创建新的示例接收端口：</span><span class="sxs-lookup"><span data-stu-id="d460b-139">Here is an example of running the Windows PowerShell script to create the new receive port:</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="d460b-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="d460b-140">See Also</span></span>  
 [<span data-ttu-id="d460b-141">Admin-ExplorerOM（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="d460b-141">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)